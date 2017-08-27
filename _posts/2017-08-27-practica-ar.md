---
layout: practica
title:  "Práctica de Ejercicios Álgebra Relacional"
date:   2017-08-27 14:26:49 -0300
categories: practica ar
---
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

## Álgebra Relacional

Referencias:

* <b>Clave Primaria​</b>, 
* <u>Clave Foránea</u>, 
* <b><u>Clave Primaria y Foránea al mismo tiempo</u></b>

#### Ejercicio De Repaso

* Demuestre porque no están ordenadas las tuplas de una relación
* Demuestre mediante teoría de conjuntos la diferencia entre clave y súper clave.
* Justifique que Junta Natural es equivalente a un producto cartesiano con una selección.
* Reemplace el operador DIVISIÓN con una secuencia válida de operaciones ``ρ``, ``X`` y ``-``
* Demostrar cuando ``R ⋈ S`` es equivalente a  ``R x S``


#### 1. Dados los esquemas de relaciones 

```
R(A,B)
S(B,C)
```

y sean ``r(R)`` y ``s(S)`` las siguientes instancias de las respectivas relaciones:

<table>
<tr><th>R </th><th>S</th></tr>
<tr><td>

| A | B |
|---|---|
| a | b |
| c | b |
| d | e |

</td><td>

| B | C |
|---|---|
| c | b |
| e | a |
| b | d |

</td></tr>
</table>

Se pide obtener:

1. \\(\mathsf{R \cup S}\\)
1. \\(\mathsf{R - S}\\)
1. \\(\mathsf{R \times S}\\)
1. \\(\mathsf{R ⋈ S}\\)
1. \\(\mathsf{\pi_A(R)}\\)
1. \\(\mathsf{\sigma_{A="c"}(R x S)}\\)


#### 2. Dado el siguiente esquema relacional

<pre>
Alumno (<b>Dni</b>, nombre, apellido, dirección)
Carrera (<b>codCarrera</b>, nombre)
Cursa (<b><u>dni</u></b>, <b><u>codCarrera</u></b>)
</pre>

Resolver: 

1. Obtener el nombre y la dirección de todos los alumnos que cursan 'Derecho'.
1. Obtener los alumnos de nombre 'Nicolás'.
1. Obtener los alumnos que **no cursan** 'Ingeniería'.

