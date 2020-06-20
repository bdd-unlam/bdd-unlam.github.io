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
  ``Proj[a,b](A)`` o ``Proy[a,b](A)``
* Selección (*):
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

(*) Las siguientes símbolos lógicos pueden utilizarse para construir las condiciones en la selección:

* Igualdad: ``=``
* Desigualdades: ``>``, ``<``, ``>=``, ``<=``, ``<>``
* Operadoes: ``AND``, ``OR``, ``NOT``

**Ejemplos de expresiones válidas:**

```
Proj[DNI](Sel[nombre = 'Luis' AND ciudad = 'Lujan'](Persona |X| Ciudad)
```

```
Sel[Number>2 AND Number<5 OR Number >= 19 ](Number)
```

```
P <- Product
C <- Color
PCA <- ProductColorAvailability
Proj[ProductId](PCA) - Proj[ProductId]((Proj[ProductId,ColorId](P x C)-PCA))
```

## Enunciados