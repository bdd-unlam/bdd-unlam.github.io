---
layout: post
title:  "Distintos tipos de Juntas (JOINs) y sus  resultados"
date:   2016-10-22 11:53:49 -0300
categories: apuntes sql juntas
---

## Conjuntos Iniciales 
 
### Tabla 1 (t1) 
 
|num  | name ­­­­|­­­­­­
|-----|------| 
|1	| a |
|2	| b |
|3	| c |
 

### Tabla 2 (t2) 

num  | value 
--- | ---
 1 | xxx 
 3 | yyy 
 5 | zzz 
 
 
### Producto Cartesiano 

{% highlight sql %}
SELECT * FROM t1 CROSS JOIN t2;
{% endhighlight %}

 
 num | name | num | value 
 --- | --- | --- | ---
   1 | a    |   1 | xxx 
   1 | a    |   3 | yyy 
1	| a    |   5 | zzz 
2	| b    |   1 | xxx 
   2 | b    |   3 | yyy 
2	| b    |   5 | zzz 
3	| c    |   1 | xxx 
   3 | c    |   3 | yyy 
   3 | c    |   5 | zzz 

(9 rows) 
 
 
Junta por campos relacionados  
 
{% highlight sql %}
SELECT * FROM t1 INNER JOIN	t2 ON t1.num = t2.num;
{% endhighlight %}
o  
{% highlight sql %}
SELECT * FROM t1 JOIN t2 ON t1.num = t2.num;
{% endhighlight %}
 
 num | name | num | value 
--- | --- | --- | ---
   1 | a    |   1 | xxx    
   3 | c    |   3 | yyy

(2 rows) 

### Junta por campos relacionados II ( USING) 
 
{% highlight sql %}
SELECT * FROM t1 INNER JOIN t2 USING (num); 
{% endhighlight %}
o  
{% highlight sql %}
SELECT * FROM t1 JOIN t2 USING (num); 
{% endhighlight %}

 num | name | value 
--- | --- | --- 
   1 | a    | xxx 
   3 | c    | yyy 

(2 rows) 

### Junta por campos relacionados III ( NATURAL) 
 
{% highlight sql %}
SELECT * FROM t1 NATURAL INNER JOIN t2; 
{% endhighlight %}
o  
{% highlight sql %}
SELECT * FROM t1 NATURAL JOIN t2; 
{% endhighlight %}
 
 num | name | value 
--- | --- | --- 
   1 | a    | xxx 
   3 | c    | yyy 

(2 rows) 

### Junta manteniendo todos los registros de la tabla izquierda 
 
{% highlight sql %}
SELECT * FROM t1 LEFT JOIN t2 ON t1.num = t2.num;
{% endhighlight %}
 
 num | name | num | value | 
--- | --- | --- | ---
1	| a    |   1 | xxx 
2	| b    |     |         | <­ Tiene valores para t1 y no para t2 
3	| c    |   3 | yyy 

(3 rows) 
 
### Junta manteniendo todos los registros de la tabla izquierda y usando el USING 
 
 
{% highlight sql %}
SELECT * FROM t1 LEFT JOIN t2 USING	(num);
{% endhighlight %}
 
 num | name | value |
--- | --- | --- | ---
1	| a    | xxx 
2	| b    |        | <­ Tiene valores para t1 y no para t2 
3	| c    | yyy 

### Junta manteniendo todos los registros de la tabla derecha 
 
{% highlight sql %}
SELECT * FROM t1 RIGHT JOIN	t2 ON t1.num = t2.num;
{% endhighlight %}
 
 num | name | num | value |
--- | --- | --- | --- | ---
   1 | a    |   1 | xxx 
   3 | c    |   3 | yyy    |<­ Tiene valores para t2 y no para t1
      |      |   5 | zzz   |<­ Tiene valores para t2 y no para t1 
 
### Junta completa. Todos los registros de la izquierda presentes. También los de la derecha 
 
{% highlight sql %}
SELECT * FROM t1 FULL JOIN t2 ON t1.num = t2.num;
{% endhighlight %}
 
 num | name | num | value |
--- | --- | --- | --- | ---
   1 | a    |   1 | xxx    |<­ Hay correspondencia entre ambas tablas    
   2 | b    |     |        |<­ Tiene valores para t1 y no para t2 
   3 | c    |   3 | yyy    |<­ Hay correspondencia entre ambas tablas 
     |      |   5 | zzz    |<­ Tiene valores para t2 y no para t1 (4 rows) 
 
### Diferencias en poner una condición en el WHERE o en el JOIN 
 
{% highlight sql %}
SELECT * FROM t1 LEFT JOIN t2 ON t1.num = t2.num  
AND t2.value = 'xxx'; 
{% endhighlight %}
 
 
 num | name | num | value |
--- | --- | --- | --- | ---
1	| a    |   1 | xxx 
2	| b    |     |        |<­ Como es un LEFT JOIN, solo aplicará el =’xxx’ 
3	| c    |     |        |  en las tuplas que ese campo tenga datos. (3 rows) 

Ahora, si la condición está en el where 
 
{% highlight sql %}
SELECT * FROM t1 LEFT JOIN t2 ON t1.num = t2.num  
WHERE t2.value = 'xxx'; 
{% endhighlight %}
 
 num | name | num | value |
--- | --- | --- | --- | ---
1 | a    |   1 | xxx    |<­ Aplica el where luego de hacer la junta entonces elimina las tuplas sin valores 

(1 row) 
 
