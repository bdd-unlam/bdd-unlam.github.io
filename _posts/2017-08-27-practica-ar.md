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

* **R:**

    | A | B |
    |---|---|
    | a | b |
    | c | b |
    | d | e |

* **S:**

    | B | C |
    |---|---|
    | c | b |
    | e | a |
    | b | d |

Se pide obtener:

1. \\(\mathsf{R \cup S}\\)
1. \\(\mathsf{R - S}\\)
1. \\(\mathsf{R \times S}\\)
1. \\(\mathsf{R ⋈ S}\\)
1. \\(\mathsf{\pi_A(R)}\\)
1. \\(\mathsf{\sigma_{A="c"}(R \times S)}\\)


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

#### 3. 

Dadas dos relaciones ``A`` y ``B`` con claves primarias <code>K<sub>A</sub></code> y <code>K<sub>B</sub></code>. Asumiendo que ``A`` y ``B`` tienen esquemas compatibles según se necesite, indicar la clave primaria para cada una de las relaciones resultantes siguientes:

1. \\(\mathsf{\sigma_{p}(A)}\\), siendo p un predicado cualquiera.
1. \\(\mathsf{\pi_{L}(A)}\\), siendo L una lista de atributos de A cualesquiera.
1. \\(\mathsf{A \times B}\\)
1. \\(\mathsf{A \cup B}\\)
1. \\(\mathsf{A \cap B}\\)
1. \\(\mathsf{A - B}\\)
1. \\(\mathsf{A ⋈ B}\\)

#### 4. Dado el siguiente esquema relacional:

<pre>
Almacén       (<b>Nro</b>, Responsable)
Artículo      (<b>CodArt</b>, descripción, Precio)
Material      (<b>CodMat</b>, Descripción)
Proveedor     (<b>CodProv</b>, Nombre, Domicilio, Ciudad)
Tiene         (<b><u>Nro</u></b>, <b><u>CodArt</u></b>)
CompuestoPor  (<b><u>CodArt</u></b>, <b><u>CodMat</u></b>)
ProvistoPor   (<b><u>CodMat</u></b>, <b><u>CodProv</u></b>)
</pre>

Realizar las siguientes consultas en Álgebra Relacional:

1. Listar los nombres de los proveedores de la ciudad de ``La Plata``.
1. Listar los números de artículos cuyo precio sea inferior a ``$10``.
1. Listar los responsables de los almacenes.
1. Listar los códigos de los materiales que provea el proveedor ``10`` y no los provea el proveedor ``15``.
1. Listar los números de almacenes que almacenan el artículo ``A``.
1. Listar los proveedores de ``Pergamino`` que se llamen ``Pérez``.
1. Listar los almacenes que contienen los artículos ``A`` y los artículos ``B`` (ambos).
1. Listar los artículos que cuesten más de ``$100`` o que estén compuestos por el material ``M1``.
1. Listar los materiales, código y descripción, provistos por proveedores de la ciudad de ``Rosario``.
1. Listar el código, descripción y precio de los artículos que se almacenan en ``A1``.
1. Listar la descripción de los materiales que componen el artículo ``B``.
1. Listar los nombres de los proveedores que proveen los materiales al almacén que ``Martín Gómez`` tiene a su cargo.
1. Listar códigos y descripciones de los artículos compuestos por al menos un material provisto por el proveedor ``López``.
1. Hallar los códigos y nombres de los proveedores que proveen al menos un material que se usa en algún artículo cuyo precio es mayor a ``$100``.
1. Hallar el o los códigos de los artículos de mayor precio.
1. Listar los números de almacenes que tienen todos los artículos que incluyen el material con código ``123``.

#### 5. Dado el siguiente esquema relacional:

<pre>
Vive      (<b><u>nombrePersona</u></b>, calle, ciudad)
Trabaja   (<b><u>nombrePersona</u></b>, <b><u>nombreEmpresa</u></b>, salario, fe_ingreso)
Situada_En(<b><u>nombreEmpresa</u></b>, ciudad)
Supervisa (<b><u>nombrePersona</u></b>, <b><u>nombreSupervisor</u></b>)
</pre>

Construir las siguientes consultas en álgebra relacional:

1. Encontrar el nombre de todas las personas que trabajan en la empresa ``Banelco``.
1. Localizar el nombre y la ciudad de todas las personas que trabajan para la empresa ``Telecom``.
1. Buscar el nombre, calle y ciudad de todas las personas que trabajan para la empresa ``Paulinas`` y ganan más de ``$1500``.
1. Encontrar las personas que viven en la misma ciudad en la que se halla la empresa en donde trabajan.
1. Hallar todas las personas que viven en la misma ciudad y en la misma calle que su supervisor.
1. Buscar todas las personas que no trabajan en la empresa ``Jumbo``.
1. Encontrar todas las personas que ganan más que cualquier empleado de la empresa ``Clarín``.
1. Localizar las ciudades en las que todos los trabajadores que vienen en ellas ganan más de ``$1000``.
1. Listar los primeros empleados que la compañía ``Sony`` contrató.

#### 6. Dado el siguiente esquema de relación:

<pre>
Película (<b>CodPel</b>, Título, Duración, Año, <u>CodRubro</u>)
Rubro    (<b>CodRubro</b>, NombRubro)
Ejemplar (<b>CodEj</b>, <b>CodPel</b>, Estado, Ubicación) 
          Estado: Libre, Ocupado
Cliente  (<b>CodCli</b>, NyA, Direccion, Tel, Email)
Préstamo (<b>CodPrest</b>, <u>CodEj</u>, <u>CodPel</u>, <u>CodCli</u>, FechaPrest, FechaDev)
</pre>

>Nota: ``FechaDev`` Se carga cuando el cliente efectúa la devolución del ejemplar.

Realizar las siguientes consultas en Álgebra Relacional:

1. Listar los clientes que no hayan reportado préstamos del rubro ``Policial``.
1. Listar las películas de mayor duración que alguna vez fueron prestadas.
1. Listar los clientes que tienen más de un préstamo sobre la misma película.
1. Listar los clientes que han realizado préstamos del título ``Rey León`` y ``Terminador 3`` (Ambos).
1. Listar los clientes que hayan alquilado todas las películas del vídeo.

#### 7. Dada la siguiente base de datos:

<pre>
Proveedor(<b>NroProv</b>, NomProv, Categoria, CiudadProv)
Artículo (<b>NroArt</b>, Descripción, CiudadArt, Precio)
Cliente  (<b>NroCli</b>, NomCli, CiudadCli)
Pedido   (<b>NroPed</b>, <u>NroArt</u>, <u>NroCli</u>, <u>NroProv</u>, Cantidad, PrecioTotal)
</pre>

Realizar las siguientes consultas en Álgebra Relacional:

1. Hallar el código (``nroProv``) de los proveedores que proveen el artículo ``a146``.
1. Hallar los clientes (``nomCli``) que solicitan artículos provistos por ``p015``.
1. Hallar los clientes que solicitan algún ítem provisto por proveedores con categoría mayor que ``4``.
1. Hallar los ítems pedidos por clientes de ``Rosario``.
1. Hallar los pedidos en los que un cliente de ``Rosario`` solicita artículos producidos en la ciudad de ``Mendoza``.
1. Hallar los pedidos en los que el cliente ``c23`` solicita artículos citados por el cliente ``c30``.
1. Hallar los pares de ciudades en la forma ``(ciudad1, ciudad2)``, tales que un proveedor en ``ciudad1`` provea artículos pedidos por clientes de ``ciudad2``.
1. Hallar los nombres de los proveedores cuya categoría sea mayor que la de todos los proveedores que proveen el artículo ``cuaderno``.
1. Hallar los clientes que han pedido dos o más artículos distintos.

#### 8. Dados los siguientes esquemas de relación:

<pre>
Vuelo    (<b>NroVuelo</b>, Desde, Hasta)
Avion    (<b>NroVuelo</b>, Tipo_avion, NroAvion)
Persona  (<b>Documento</b>, Nombre, Origen, Destino)
Pasajero (<b><u>NroVuelo</u></b>, <b><u>Documento</u></b>)
</pre>

>Nota: Los vuelos no pueden tener más de dos escalas y no hay cambio de tipo de avión para un mismo vuelo.

Realizar las siguientes consultas:

1. Hallar los números de vuelo desde el origen ``A`` hasta el destino ``F``.
1. Hallar los tipos de avión que no son utilizados en ningún vuelo que pase por ``B``.
1. Hallar los pasajeros y números de vuelo para aquellos pasajeros que viajan desde ``A`` a ``D`` pasando por ``B``.
1. Hallar los tipos de avión que pasan por ``C``.

#### 9. Dada la siguiente base de datos relacional:

<pre>
Frecuenta (<b><u>nombrePersona</u></b>, <b><u>nombreBar</u></b>)
Sirve     (<b><u>nombreBar</u></b>, <b><u>nombreCerveza</u></b>)
Gusta     (<b><u>nombrePersona</u></b>, <b><u>nombreCerveza</u></b>)
</pre>

Usar el álgebra relacional para hallar las personas que:

1. Frecuentan solamente bares que sirven alguna cerveza que les guste.
1. No frecuentan ningún bar que sirva alguna cerveza que les guste.
1. Frecuentan solamente los bares que sirven todas las cervezas que les gustan.
1. Frecuentan solamente los bares que no sirven ninguna de las cervezas que no les gusta.

#### 10. Dada la siguiente base de datos relacional:

<pre>
Persona    (<b>TipoDoc</b>, <b>NroDoc</b>, Nombre, Dirección, FechaNac, Sexo)
Progenitor (<b><u>TipoDoc</u></b>, <b><u>NroDoc</u></b>, <b><u>tipoDocHijo</u></b>, <b><u>nroDocHijo</u></b>)
</pre>

Realizar las siguientes consultas:

1. Hallar para una persona dada, por ejemplo José Pérez, los tipos y números de documentos, nombres, dirección y fecha de nacimiento de todos sus hijos.
1. Hallar para cada persona los tipos y números de documento, nombre, domicilio  y fecha de nacimiento de:
  * Todos sus hermanos, incluyendo medios hermanos.
  * Su madre
  * Su abuelo materno
  * Todos sus nietos

#### 11. Dada la siguiente base de datos relacional:

<pre>
Alumno         (<b>legajo</b>, nombre, apellido, sexo, fechaNac, feIngreso)
Carrera        (<b>id</b>, descripción)
Materia        (<b>codMat</b>, nombre, descripción)
MateriaCarrera (<b>codMat</b>, <u>codCarrera</u>)
Comisión       (<b>nroComisión</b>, <b><u>codMateria</u></b>, día, turno, aula, docente)
Cursa          (<b><u>comisión</u></b>, <b><u>materia</u></b>, <b><u>legajo</u></b>)
Rendida        (<b><u>codMmat</u></b>, <b><u>legajo</u></b>, <b>fecha</b>, nota, doc)
Docente        (<b>id</b>, nombre, apellido)
</pre>

1. Muestre los nombres de los alumnos que están cursando comisiones en 3 turnos distintos.
1. Muestre los datos de los alumnos y profesores que coinciden en más de 1 comisión. 
1. Identifique al alumno con mayor antigüedad en la facultad.
1. De los alumnos que hayan hecho materias de 2 o mas carreras indique aquellos que aún están en la facultad.
1. Identifique las carreras donde nunca haya habido desaprobados.
1. Indique los legajos de los alumnos que hayan promocionado ``Sistemas de computación 2``.
1. Muestre todos los datos de los alumnos que hayan rendido mal en mas de 1 ocasión ``Programación 3``.
1. Identifique los alumnos que hayan aprobado todas las materias de una carrera.

#### 12. Dada la siguiente base de datos relacional:

<pre>
ALUMNO      (<b>dni</b>, apellido, nombre, <u>codEscuela</u>)
HERMANO_DE  (<b>dni</b>, dniHermano)
ESCUELA     (<b>cod</b>, nombre, dirección)
ALIMENTO    (<b>id</b>, descripción, marca)
ALMUERZA_EN (<b><u>dniAlumno</u></b>, <b><u>idAlimento</u></b>, <u>codEscuela</u>)
</pre>

1. Listar a los alumnos con al menos 3 hermanos que asisten a distintas escuelas y Almuerzan en la misma institución.
1. Mostrar todos los alimentos que son servidos a todos los alumnos de la escuela ``J. L. Borges``.
1. Listar a los alumnos que asisten a escuelas donde no sirven alimentos y almuerzan en otro establecimiento.
1. Mostrar todas las escuelas que sirven alimentos a todos sus alumnos que no tienen más de dos hermanos

#### 13. Teniendo: 

<pre>
R (<b>DNI</b>, nombre)
A (<b>patente</b>, marca, modelo)
D (<b><u>patente</u></b>, <b><u>DNI</u></b>) 
</pre>

1. Mostrar la persona con más autos.
1. Mostrar a las personas sin autos.
1. Mostrar a las personas con un solo auto.
1. Seleccionar las personas que no tenga autos marca ``Ford`` y que tengan todos los modelos de ``Opel``. (al mismo tiempo)
1. Seleccionar las personas que tienen entre 2 y 5 autos. Donde al menos dos son del mismo modelo y no tienen 3 de la misma marca.
1. Mostrar a la persona con todos los modelos de la marca ``Ford``, alguno de ``Smart`` y ninguno de ``Chrysler``.
1. Mostrar los autos que tienen más de un propietario, donde los propietarios no tengan más de un auto.
