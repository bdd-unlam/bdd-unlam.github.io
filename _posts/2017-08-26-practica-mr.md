---
layout: practica
title:  "Práctica de Ejercicios MR"
date:   2017-08-26 15:22:49 -0300
categories: practica mr
---

## Modelo Relacional

Referencias:

* <b>Clave Primaria​</b>, 
* <u>Clave Foránea</u>, 
* <b><u>Clave Primaria y Foránea al mismo tiempo</u></b>

#### Ejercicio 1

Desarrollar el Modelo Relacional correspondiente a cada uno de los ejercicios de la práctica de DER.

Identificar claves primarias y claves foráneas de cada Relación resultante.

#### Ejercicio 2

Dado el siguiente Modelo Relacional, confeccionar el DER que le dio origen.

<pre>
A (<b>a1</b>​, a2, a3)
B (<b>b1</b>, <b>b2</b>​, b3)
C (<b>c1</b>​, c2, <b><u>​a1​​</u></b>)
D (<b>d1</b>​, d2, d3, <b><u>​a1</u>​</b>, <b><u>​c1​​</u></b>)
E (<b><u>​a1​</u></b>, <b><u>​b1​</u></b>, <b><u>​b2​​</u></b>, e1)
F (<b>f1</b>​, f2, <u>b1</u>, <u>b2</u>)
G (<b>a1</b>, <b>b1</b>, <b>b2</b>​, <u>f1</u>, g1)
</pre>

Tener en cuenta las siguientes pautas:

* Indicar la cardinalidad de las relaciones.
* No colocar nombres a las relaciones de N:1, 1:N y 1:1.
* No indicar la opcionalidad de las relaciones.

#### Ejercicio 3

​Dado el siguiente esquema de base de datos relacional

<pre>
PAIS           (<b>IdPais</b>​, Nombre)
PARTICIPANTE   (<u><b>IdTipoDoc​</b></u>, <b>NúmeroDocumento​</b>, Nombre, Apellido, Dirección, Teléfono, <u>IdPais</u>, <u>IdHotel</u>, <u>NumeroSucursal</u>, TipoParticipante)
TIPO_DOCUMENTO (<b>IdTipoDoc​</b>, Descripción)
JUGADOR        (<u><b>IdTipoDoc​</b></u>, <u><b>​NúmeroDocumento​</b></u>, Nivel)
DISPUTA        (<u><b>IdTipoDoc​</b></u>, <u><b>​NúmeroDocumento​</b></u>, <u><b>​IdPartido​</b></u>, Color)
ARBITRO        (<u><b>IdTipoDoc​</b></u>, <u><b>​NúmeroDocumento​</b></u>, Fecha_inicio_profesional)
HOTEL          (<b>IdHotel​</b>, Razón Social, Cant_Sucursales)
SALA           (<b>NúmSala​</b>, <u><b>NúmeroSucursal</b></u>, <u><b>IdHotel​</b></u>, Nombre, CantAsientos)
PARTIDO        (<b>IdPartido​</b>, Duración, Fecha, <u>IdTipoDocArbitro</u>, <u>númeroDocumentoArbitro</u>, <u>NumeroSala</u>, <u>NúmeroSucursal</u>, <u>IdHotel</u>)
JUGADA         (<b>NumeroJugada​</b>, <u><b>IdPartido​</b></u>, <u>IdTipoDoc</u>, <u>NúmeroDocumento</u>,
Movimiento, Comentario)
EMPLEADO       (<b>Legajo​</b>, Nombre, Apellido, FechaNacim, <u>LegSupervisor</u>)
ASIGNACIÓN     (<u><b>Legajo​</b></u>, <u><b>​NumeroSucursal​</b></u>, <u><b>​IdHotel​</b></u>, <u>IdPuesto</u>)
SUCURSAL       (<b>numeroSucursal</b>, <b><u>​IdHotel​</u></b>, dirección, teléfono)
PUESTO         (<b>IdPuesto​</b>, Descripción)
</pre>

A - Obtener al menos un diagrama ER del cual se haya podido derivar.

B – En el diagrama incluir los siguientes cambios solicitados:

>Nota: Se debe dibujar un único DER que contemple los cambios

1. Se solicita que el diseño no permita el almacenamiento de más de 2 jugadores
en una Partida, manteniendo el registro del color con el que el jugador participó
de la misma.

1. Se solicita llevar un registro de la cantidad de partidos ganados por cada
uno de los participantes.

#### Ejercicio 4

Dado el siguiente esquema de base de datos relacional, 

<pre>
AVION      (<b>idAvion</b>, marca, modelo)
VUELO      (<b>nroVuelo</b>, fecha_salida, <u>codAeptoOrigen</u>, <u>codAeptoDestino</u>, <u>idAvion</u>)
AEROPUERTO (<b>codAepto</b>, nombreaepto)
PASAJERO   (<u><b>tipoDoc</b></u>, <b>nroDoc</b>, nombre, apellido)
TIPO_DOC   (<b>tipoDoc</b>, descTipoDoc)
UBICACIÓN  (<b>nroAsiento</b>, <b>fila</b>, <u>idClase</u>, <u>idAvion</u>)
CLASE      (<b>idClase</b>, descClase)
TARIFA     (<b><u>codAeptoOrigen</u></b>, <b><u>codAeptoDestino</u></b>, precioClaseTurista, <u>fechaDesde</u>, fechaHasta)
PASAJE     (<b><u>tipoDoc</u></b>, <b><u>nroDoc</u></b>, <b><u>nroVuelo</u></b>, <u>nroAsiento</u>, <u>fila</u>)
</pre>

A - btener al menos un diagrama ER del cual se haya podido derivar.

B - En el diagrama incluir los siguientes cambios solicitados:

>Nota: Se debe dibujar un único DER que contemple los cambios

* Una misma persona puede comprar más de un pasaje en un mismo vuelo. Esto nos pasó con una persona muy grandota que como no había lugar en primera clase, reservó dos asientos contiguos en la clase turista para viajar cómodo.
* Queremos ofrecerle a todos nuestros pasajeros una promoción en la cual puedan sumar millas con cada viaje que hagan en nuestra aerolínea. Necesitamos registrar cuantas millas otorga cada viaje (según origen, destino y clase) y cuantas millas llevan acumuladas nuestros pasajeros.
* Hasta el momento el precio de un pasaje en primera clase siempre era un 80% más caro que el precio de la clase turista y por tal motivo no era necesario que lo tengamos almacenado. Pero queremos cambiar esto ya que vamos a definir nuevos precios para la primera clase que no dependan del precio de la clase turista.

