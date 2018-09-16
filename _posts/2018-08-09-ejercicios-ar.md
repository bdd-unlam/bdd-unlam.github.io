---
layout: ejercicios-ar
title:  "Ejercicios Álgebra Relacional"
date:   2018-08-26 20:26:49 -0300
categories: practicas ar
author: javi
type: draft
exercise: exercises.json
---

## Ejercicios de Álgebra Relacional

Resuelva los siguientes ejercicios utilizando el intérprete de AR embebido en cada ejercicio. Cada ejercicio contiene el resultado esperado; trate de conseguir el mismo resultado utilizando la cantidad de expresiones de AR que crea necesario.

> Notas: 
> La aplicación no valida que el resultado coincida con el esperado
> La aplicación no guarda las expresiones utilizadas. Asegurese de guardar las expresiones utilizadas antes de salir de la página si desea conservarlas

#### Instrucciones

Utilice los siguientes operadores soportados por el interprete. Las distintas sentencias pueden separarse utilizando un punto y coma (``;``), o un salto de línea.

* Asignación: 
  ``A <- B``
* Asignación con renombre:
  ``A(a,b) <- B``
* Renombrar:
  ``Ren[a,b](A)``
* Proyección:
  ``Proj[a,b](A)``
* Selección:
  ``Sel[Condicion](A)``
* Producto Cartesiano:
  ``A x B``
* Junta Natural
  ``A |x| B``
* Unión. Cualquiera de estas opciones:
  ``A U B``,
  ``A ∪ B``
* Intersección. Cualquiera de estas opciones:
  ``A INT B``, 
  ``A ∩ B``
* Resta:
  ``A - B``
