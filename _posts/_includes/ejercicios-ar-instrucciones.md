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