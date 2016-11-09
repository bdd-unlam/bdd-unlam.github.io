---
layout: post
title:  "Pasaje del operador división de AR a ansi SQL"
date:   2016-10-22 11:53:49 -0300
categories: apuntes sql ar cociente
author: alf
---

<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

## División del Álgebra Relacional en SQL    

Tomemos el problema:  

$$
\mathsf{A( x, y )} \div \mathsf{B( y )}
$$

Ejemplos: 

- Hallar proveedores que suministran todas las piezas indicadas  
- Hallar profesores que hayan dictado todas las materias indicadas 
- Hallar alumnos que hayan aprobado todas las materias indicadas 

Estrategias 

- Conversión directa del álgebra relacional. 
- Usando una tautología de cuantificación. 
- Por inclusión de conjuntos.
- Por comparación de cardinalidades. 

Siguiendo el álgebra relacional:   


$$
\mathsf{A \div B = \Pi_{X} (A) – \Pi_{X} ( \Pi_{X} (A) \times B – A )}
$$

1. La diferencia es un `EXCEPT`.  
1. Una lista de table references en un `FROM` sin `WHERE` es un producto cartesiano.  
1. La anidación de `SELECT’s` exige renombramientos, más riguroso:  
    1. Una <query expression> que pasa a un <table reference> requiere paréntesis  y nombre, o dicho de otra manera, es una subconsulta con un alias.           

### 1. Conversión directa del álgebra relacional 

**AR**

$$
\mathsf{\Pi_{X} (A) – \Pi_{X} ( \Pi_{X} (A) \times B – A )}
$$

**SQL**

{% highlight sql %}
SELECT DISTINCT x FROM A
EXCEPT
SELECT x FROM 
    (   SELECT x, y FROM 
            ( SELECT x FROM A ) as C,
            ( SELECT y FROM B ) as D
        EXCEPT
        SELECT x, y FROM A
    ) as E
{% endhighlight %}
 

### 2. Usando una tautología de cuantificación 
 
Queremos hallar los **x** tal que: 
 
$$
\mathsf{(\forall y \in B) [ (x,y) \in A ]} 
$$
 
Pero no hay cuantificación universal en SQL, entonces vamos por doble negación 
 
$$
\mathsf{ \neg (\exists y \in B ) [ (x,y) \notin A ] } 
$$
 
Quedando entonces: 

$$
\mathsf{ \{ x | \neg (\exists y \in B ) [ (x,y) \notin A ] \} } 
$$

**SQL**

{% highlight sql %}
SELECT DISTINCT x FROM A as H 
WHERE NOT EXISTS 
    (   SELECT y FROM B 
        WHERE NOT EXISTS 
            (   SELECT * FROM A as G 
                WHERE G.y = B.y 
                AND G.x = H.x  
            ) 
    ) 
{% endhighlight %}
 
### 3. Por inclusión de conjuntos 
 
Si **x** se asocia en **A** a un conjunto de **y’s** que contenga a las **y’s** posibles **x** está con todas las **y’s**. 
Pero no existe el relacional \\( U \supseteq V \\) , entonces lo fabricamos como \\( V – U = \emptyset \\) y NOT EXISTS V – U.

Entonces,  

$$
\mathsf{ \{ y \in B | (x,y) \in A \} \supseteq B } 
$$
 
Por lo cual, la definición completa sería: 

$$
\mathsf{ Β ­\{ y \in B | (x,y) \in A \} = \emptyset } 
$$
 
**SQL**


{% highlight sql %}
SELECT DISTINCT x FROM A as G 
WHERE NOT EXISTS  
    ( 
        (   SELECT y FROM B ) 
        EXCEPT 
        (   SELECT B.y 
            FROM B, A 
            WHERE A.y = B.y And A.x = G.x 
        ) 
    ) 
{% endhighlight %}
 
> NOTA: Más fácil de entender por no tener doble negación 
 
 
### 4. Por comparación de cardinalidades 

La idea es contar ambos conjuntos esperando que tengan la misma cardinalidad.

$$
\mathsf{ \# \{ y \in B | (x , y) \in A \} = \# B } 
$$

**SQL**

{% highlight sql %}
SELECT DISTINCT x 
FROM A, B 
WHERE A.y = B.y 
GROUP BY A.x 
HAVING COUNT(DISTINCT A.y) = 
    (   SELECT COUNT(DISTINCT y) FROM B ) 
{% endhighlight %}
