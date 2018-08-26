---
layout: practica
title:  "Práctica de Ejercicios Seguridad"
date:   2017-09-03 20:22:49 -0300
categories: practicas seguridad
type: post
---

Referencias:

* <b>Clave Primaria​</b>, 
* <u>Clave Foránea</u>, 
* <b><u>Clave Primaria y Foránea al mismo tiempo</u></b>

#### Ejercicio 1

Dada la siguiente base de datos:

<pre>
Almacén       (<b>Nro</b>, Responsable)
Artículo      (<b>CodArt</b>, descripción, Precio)
Material      (<b>CodMat</b>, Descripción)
Proveedor     (<b>CodProv</b>, Nombre, Domicilio, Ciudad)
Tiene         (<b><u>Nro</u></b>, <b><u>CodArt</u></b>)
CompuestoPor  (<b><u>CodArt</u></b>, <b><u>CodMat</u></b>)
ProvistoPor   (<b><u>CodMat</u></b>, <b><u>CodProv</u></b>)
</pre>

Definida en un motor ``MySQL1``. Genere las siguientes pautas de seguridad.

1. Cree 4 usuarios, con nombres y sus respectivas claves: 	
  * Administrador del Sistema (``as``)
  * Comprador (``co``)
  * Vendedor (```ve``)
  * Administrador (``ad``)

1. Asigne todos los permisos posibles al ``Administrador del sistema``
1. Asigne permisos de lectura/escritura sobre ``Proveedor``/``Material``/``ProvistoPor`` al usuario ``Comprador``
1. Asigne permisos de lectura/escritura sobre ``Almacén``/``Artículo``/``Tiene`` al usuario ``Vendedor``
1. Asigne permisos de lectura, actualización y escritura sobre ``CompuestoPor`` al usuario ``Administrador``
1. Renombre al usuario ``Administrador`` como usuario ``Operador`` con clave ``op``
1. Revoque el permiso de modificación de estructuras a los usuarios ``Comprador``/``Vendedor`` y ``Operador``

Diseñe y cree los objetos necesarios para definir estos permisos.

#### Ejercicio 2

Dada la siguiente base de datos:

<pre>
Vive      (<b><u>nomPersona</u></b>, calle, ciudad)
Trabaja   (<b><u>nomPersona</u></b>, <b><u>nomEmpresa</u></b>, salario, fec_ingreso)
SituadaEn (<b><u>nomEmpresa</u></b>, ciudad)
Supervisa (<b><u>nomPersona</u></b>, <b><u>nomSupervisor</u></b>)
</pre>

Definida en un motor ``PostgreSQL2``.  Genere las siguientes pautas de seguridad.

1. Cree 3 roles, con nombres y sus respectivas claves: 	
  * ``Juan`` / tipo: ``Super usuario``
  * ``Ana``
  * ``Pedro``

1. Asigne permisos a ``Ana`` para solo escribir en todas las tablas
1. Asigne permisos de modificación a ``Ana`` para los campos que no sean claves
1. Asigne permisos a ``Pedro`` para ver solamente los nombres de las personas que viven en la misma ciudad donde viven sus jefes.
1. Asigne permisos a ``Pedro`` para ver las empresas donde todos los empleados tienen salarios superiores al promedio de salarios. 

Diseñe y cree los objetos necesarios para definir estos permisos.

#### Ejercicio 3

Dada la siguiente base de datos:

<pre>
Vuelo    (<b>NroVuelo</b>, Desde, Hasta)
Avion    (<b>NroVuelo</b>, TipoAvion, NroAvion)
Persona  (<b>Documento</b>, Nombre, Origen, Destino)
Pasajero (<b><u>NroVuelo</u></b>, <b><u>Documento</u></b>)
</pre>

Definida en un motor ``MS SQL Server 3``.  Genere las siguientes pautas de seguridad.

1. Cree 3 usuarios, con nombres y sus respectivas claves: 	
  * ``Administrador`` / tipo: ``Super usuario`` 
  * ``Call Center``
  * ``Ventanilla``

1. Asigne permisos al ``Administrador`` para solo modificar estructuras de las tablas, no sus datos.
1. Asigne permisos de inserción para los usuarios del ``Call Center`` en ``Pasajero``, mientras que para ``Persona`` de inserción y modificación. 
1. Asigne permisos al usuario ``Ventanilla`` de solo consulta en todas las tablas.

Diseñe y cree los objetos necesarios para definir estos permisos.

#### Ejercicio 4

Dada la siguiente base de datos:

<pre>
Persona    (<b>TipoDoc</b>, <b>NroDoc</b>, Nombre, Dirección, FechaNac, Sexo)
Progenitor (<b><u>TipoDoc</u></b>, <b><u>NroDoc</u></b>, <b><u>tipoDocHijo</u></b>, <b><u>nroDocHijo</u></b>)
</pre>

Definida en un motor ``Oracle4``.  Genere las siguientes pautas de seguridad.

1. Cree 3 usuarios, con nombres y sus respectivas claves: 	
  * ``Administrador`` / tipo: ``Super usuario`` 
  * ``DataEntry``
  * ``Consultor``

1. Asigne permisos al ``Administrador`` para solo modificar estructuras de las tablas, no sus datos.
1. Asigne permisos de inserción para los usuarios del ``Call Center`` en ``Persona``, mientras que para ``Progenitor`` de inserción y modificación. 
1. Asigne permisos al usuario ``Consultor`` para solo ver las personas que sean abuelos. 

### Referencias

1. ``MySQL`` http://dev.mysql.com/doc/refman/5.0/es/account-management-sql.html
1. ``PostgreSQL`` http://www.postgresql.org/docs/current/static/index.html
1. ``MS SQL Server`` http://technet.microsoft.com/en-us/library/ff848791.aspx
1. ``Oracle`` http://docs.oracle.com/cd/B19306_01/server.102/b14200/statements_8003.htm

>Nota: Las referencias señaladas son a modo de ejemplo. Utilizadas y asociadas a una versión particular de los motores de base de datos mencionados. No por esto definitivos ni únicas. No es responsabilidad del autor del presente documento la mantención ni la propiedad de dichos sitios. 
