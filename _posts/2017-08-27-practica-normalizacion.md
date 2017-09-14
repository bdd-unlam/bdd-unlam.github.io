---
layout: practica
title:  "Práctica de Ejercicios Dependencias Funcionales"
date:   2017-08-27 12:53:49 -0300
categories: practicas normalizacion
---

## Normalización - Formas Normales - Algoritmos

Referencias:

* <b>Clave Primaria​</b>, 
* <u>Clave Foránea</u>, 
* <b><u>Clave Primaria y Foránea al mismo tiempo</u></b>

#### Ejercicio 1

Dada la siguiente relación

```
MiMusica (NombreAlbum, NombreArtista, Genero, NroTema,  NombreTema, Duracion, Discografica, Año)
```

Se pide: Identificar las Dependencias Funcionales, indicando todas las suposiciones tomadas, por ej:

* Suponemos que no hay dos versiones del mismo tema en un mismo Álbum.
* Cada Artista pertenece a un único Género.

#### Ejercicio 2

Dada la siguiente relación 

```
Registro (NombreCurso, Profesor, Hora, Aula, Estudiante, Nota) 
```

Y las siguientes restricciones (dadas por las reglas del negocio):

* Cada curso es impartido por varios profesores.
* A una hora y en un aula se imparte un solo curso.
* A una hora determinada, un profesor está es una única aula.
* Cada estudiante obtiene una nota en cada curso tomado (y solo puede tomar una vez cada curso).
* A una hora determinada, un estudiante puede estar en una sola aula.

Se pide: Identificar las Dependencias Funcionales.

#### Ejercicio 3

Dados la Relación ``R`` y el Conjunto ``F`` siguiente, demuestre que la dependencia funcional ``X → V`` pertenece a ``F+``, utilizando los axiomas de Armstrong.

```
R (X, Y, Z, W, V)
F = { X → Y, XY → Z, Z → X, YZ → W, W → XY, W → V }
```

#### Ejercicio 4

Sea la relación ``R`` y el conjunto de DF ``F`` dados, demostrar que las dependencias ``A → G, BC → E, AB → E y ADG → C`` pertenecen a ``F+``, utilizando únicamente los axiomas de Armstrong

```
R (A,B,C,D,E,G)
F = { AD → E, C → G, GE → C, A → C, BC → A, B → D }
```

#### Ejercicio 5

Dado ``R (A, B, C, D)`` con ``F = { AB → C, C → D, D → A }``

Identifique **TODAS** las superclaves de ``R`` que no son claves candidatas.

#### Ejercicio 6

Demostrar cada una de los tres Axiomas de Armstrong (**_Reflexividad_**, **_Aumento_** y **_Transitividad_**) en base a la definición de Dependencia Funcional.

#### Ejercicio 7

Demostrar cada una de las tres reglas derivadas (**_Unión_**, **_Descomposición_** y **_Pseudotransitividad_**) en base a los axiomas de Armstrong.

#### Ejercicio 8

Dado el siguiente esquema de relación: 

```
R (ABCDEF)
```

Se pide:

Verifique formalmente si los siguientes conjuntos de dependencias funcionales son equivalentes:

```
F1 = { A → B, AB → C, C → EF, BC → D, D → AB, E → F, D → E, 
       FC → E, E → C }

F2 = { A → E, C → E, CE → F, E → FC, AF → B, AE → C, AFC → DE, 
       D → C, FD → A, BE → D }
```

#### Ejercicio 9

Dado ``R (BDIOQS)`` con ``F = { S → D, I → B, IS → Q, B → O }``

Se pide:

1. Encontrar TODAS las claves candidatas.
1. Si se descompone a ``R`` en ``R1(ISQD)`` y ``R2(IBO)``, diga si hubo pérdida de información. ¿En que forma normal se encuentra cada relación?
1. Encontrar una descomposición de ``R`` en FNBC sin pérdida de información. ¿Se conservaron las dependencias funcionales?

#### Ejercicio 10

Dado ``R (ABCDEF)`` con ``F = { A → BC, B → C, C → A, AD → E, AE → F, CD → E}``

Se  pide:

1. Encontrar TODAS las claves candidatas.
1. Encontrar un F mínimo.
1. Decir en que forma normal se encuentra ``R``. ¿Porque?
1. Descomponer a ``R`` en FNBC usando el algoritmo visto en clase.

#### Ejercicio 11

Dado ``R (ABCDE)`` con ``F = { A → BC, CD → E, B → D, E → A}``

Se pide:

1. Hallar TODAS las claves candidatas.
1. Decir si la descomposición de ``R`` en ``R1 (ABC)`` y ``R2 (CDE)`` es sin pérdida de información. Justificar.
1. Encontrar una descomposición en FNBC.


#### Ejercicio 12

Dado ``R (ABCDEF)`` con ``F = { B → D, CF → A, DE → C, C → EF, F → D }``

Se pide:

1. Hallar TODAS las claves candidatas.
1. Decir en que forma normal se encuentra ``R``.
1. Hallar una descomposición en FNBC.


#### Ejercicio 13

Dado ``R (ABCDE)`` con ``F = { A → BC, BC → A, BCD → E, E → C }``

Se pide:

1. Hallar TODAS las claves candidatas.
1. Decir en que forma normal se encuentra ``R``.
1. Hallar una descomposición en FNBC.


#### Ejercicio 14

Dado ``R (ABCD)`` con ``F = { AB → D, C → D, AB → C, C → B }``

Se pide:

1. Encontrar TODAS las claves candidatas.
1. Encontrar una descomposición en 3FN. ¿Se conservan las dependencias?
1. Encontrar una descomposición en FNBC. ¿Se conservan las dependencias?


####  Ejercicio15

Dado ``R (AOIVND)`` con ``F = { V → D, I → A, IV → N, A → O }``

Indique si hay pérdida de información si descompone a ``R`` en:

1. ``R1(VD), R2(IA), R3(IVD), R4(AO)``
1. ``R1(IVN), R2(IA), R3(VD), R4(IVO)``

#### Ejercicio 16

Dado ``R (ABCDE)`` con ``F = { AB → D, DE → B, A → C, BC → E }``

Utilice el Teorema de Heath para verificar si la siguiente descomposición es sin pérdida de información.

```
R1 (ABED), 
R2 (ABC)
```


#### Ejercicio 17

Demuestre que cualquier relación de 2 elementos se encuentra en FNBC:

Por ejemplo: ``R (A, B)``

#### Ejercicio 18

Dado el siguiente esquema de relación: 

```
R (A, B, C, D, E, F)            
F = { AB → C, C → D, ABC → E, F → A, AB → FD, A → F }
```

1. Obtenga un cubrimiento minimal.
1. Normalizar a 3 FN
1. Justificar si hubo pérdida de información y/o pérdida de dependencias funcionales.

#### Ejercicio 19

Dado el siguiente esquema de relación:

```
Encuesta (nroEncuesta, descEncuesta, cantMin, codTipoPoblacion, descTipoPobl, cantEncuestadaXpobl, fecha, DNIEncuestado, codMotivo)
```

Y las siguientes restricciones:

* Una encuesta posee un número unívoco que se va incrementado automáticamente.
* A cada encuesta se le asigna una descripción, una fecha de la encuesta y la cantidad mínima de personas a encuestar
* Las encuestas se podrán realizar a diferentes tipos de poblaciones y se llevará un registro de cuántas personas se ha encuestado por cada tipo de población. Los tipos de población se codificarán y poseen una descripción alfanumérica.
* La encuesta se realizará a un conjunto de personas que cumplan con las condiciones que especifique la misma. Si una persona fue utilizada para una encuesta ya no podrá volver a pertenecer a otra.
* Si un encuestado no ha podido localizarse para ser encuestado, se dejará asentado el motivo.

Se pide:

1. Indicar las dependencias funcionales del esquema ``Encuesta``.
1. Justificar en qué forma normal se encuentra la relación.
1. Normalizar a FNBC en el caso que fuese necesario. Indicar si hubo pérdida de dependencias.

#### Ejercicio 20

Dado el siguiente esquema de relación:

```
Reservas(ciudad, teatro, título)
```

con  

{% raw %}
```
F= {{teatro} → {ciudad}, {título, ciudad} → {teatro}}
```
{% endraw %}

Se pide:

1. Demostrar que Reservas no está en forma normal de Boyce-Codd.
1. Descomponer Reservas para obtener un conjunto de esquemas de relación en FNBC.
1. ¿La transformación ha preservado las dependencias funcionales?
1. Descomponer Reservas para obtener un conjunto de esquemas de relación en 3FN.


#### Ejercicio 21

Pasar a forma normal de Boyce-Codd y a tercera forma normal:

```
R (A,B,C,D,E) con F = {AB → C, DE → C, B → D}
R (A,B,C,D,E) con F = {A → B, C → D}
```

#### Ejercicio 22

Indique en qué Forma Normal se encuentran cada uno de los siguientes esquemas:

```
R1 (ABCDEF)  F1={ AB → C, C → D, AB → E, F → A, A → F }
R2 (ABCDE)   F2={ E → D, C → E, B → E, AD → B }
R3 (ABCDE)   F3={ AB → D, DE → B, AB → C, BC → E }
R4 (PQM)     F4={ PQ → M, P → Q }
R5 (XZWY)    F5={ }
R6 (STU)     F6={ T → T, SU → U }
```