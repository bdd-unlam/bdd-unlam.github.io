Resuelva los siguientes ejercicios utilizando el intérprete de AR embebido en cada ejercicio. Cada ejercicio contiene el resultado esperado; trate de conseguir el mismo resultado utilizando la cantidad de expresiones de AR que crea necesario.

> **Notas:**
>
>  * La aplicación no valida que el resultado coincida con el esperado
>  * La aplicación no guarda las expresiones utilizadas. Asegurese de guardar las expresiones utilizadas antes de salir de la página si desea conservarlas
>  * La coincidencia en el resultado no implica que el ejercicio este correcto. Los docentes pueden utilizar un set de datos diferente para validar el  ejercicio.


> **Problemas/Limitaciones conocidos de la herramienta:**
>
>  * No se puede usar guión bajo (_) para los nombres
>  * No fue validada y puede no funcionar correctamente en Internet Explorer
>  * La herramienta utiliza un pequeño motor SQLite para resolver las consultas (se traslada del AR a SQL). En ocasiones las consultas resultantes tienen un nivel de anidamiento demasiado grande para que lo pueda manejar el motor y devuelve un error de Stack Overflow. En esos caso trate de simplificar la consulta.

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
* Junta Natural:
  ``A |x| B``
* Junta Theta (*):
  ``A |x(Condicion)| B``
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