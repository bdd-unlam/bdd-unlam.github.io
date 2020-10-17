---
layout: practica
title:  "Práctica de Ejercicios DER"
date:   2020-09-27 09:30:49 -0300
categories: practicas der
type: post
---

## Diagrama de Entidad Relación

#### 1. Academia

Una academia dicta varios cursos, cada uno de los cuales tiene un código, un nombre y una cuota. La duración de los cursos varía de uno a cuatro días y es dictado por un único instructor. Un instructor puede dictar varios cursos y necesitamos registrar su nombre y nro. de teléfono. 

Los alumnos pueden tomar varios cursos al mismo tiempo, registrando el nombre y número telefónico de cada uno de nuestros alumnos. 

#### 2. Viviendas de la Provincia
La Secretaría de Vivienda de la Provincia de Buenos Aires desea almacenar información relacionada a los habitantes de la misma, las Viviendas donde residen las personas y los propietarios de las viviendas. 

De las Personas interesa almacenar su Tipo y Número de documento, su Nombre, Apellido, y Fecha de nacimiento. Cada persona debe vivir en un solo domicilio, el cual no necesariamente es de su propiedad y además una persona puede ser propietaria de varias viviendas en distintos Municipios de nuestra provincia. Cabe destacar que existen propiedades que tienen múltiples propietarios.

De las Viviendas interesa almacenar la dirección, la cantidad de metros cuadrados del terreno y la cantidad de metros cuadrados que se encuentran edificados. Respecto a los Municipios, deseamos almacenar su Nombre, superficie y cantidad de habitantes. 

#### 3. Partidos Jugados 
Se desea almacenar los resultados de los partidos del campeonato de futbol local. Se deben de almacenar los partidos (fecha y hora), los goles de cada equipo, quien es local y quien es visitante.  

#### 4. Préstamos de la Biblioteca
Nos interesa registrar los préstamos de la biblioteca, teniendo en cuenta que los usuarios que se llevan un libro prestado deben haber obtenido un carnet y pueden llevarse varios libros en préstamo simultáneamente hasta por una semana.

El material bibliográfico está compuesto por libros y revistas, y estas últimas actualmente sólo pueden consultarse en sala de lectura. Un libro o revista puede tener varios ejemplares.

#### 5. Video Club
El dueño de un video club quiere llevar registro de su material. A cada película le asigna un código específico; interesa saber su título y categoría (por ej: comedia, suspenso, drama, acción, ciencia ficción, etc.).

Suele haber varias copias de cada una de las películas y cada una de ellas tiene un número. Las copias pueden ser de distintos formatos. 

Frecuentemente nos solicitan películas protagonizadas por determinados actores.        Robert Downey Jr y Brad Pitt son algunos de los más solicitados. De manera tal que nos gustaría registrar los actores famosos que actúan en cada película. No todas nuestras películas tienen actores famosos. A los clientes también les gusta saber el             nombre real de cada actor y su fecha de nacimiento. Solo registramos aquellos actores que aparecen en las películas de nuestro inventario. 

Sólo le alquilamos videos a las personas que estén asociadas a nuestro video club. Para cada socio, se debe registrar su nombre y apellido, nro de teléfono y dirección. Y por supuesto, cada socio tiene su número de socio. 

Por último, necesitamos registrar que copias ha retirado cada cliente. Un cliente puede llevarse muchas películas al mismo tiempo. Sólo queremos registrar los alquileres actuales. No nos interesa llevar un registro histórico de los alquileres

#### 6. Modificar el Diagrama ER del ejercicio anterior (Video Club) para ajustarlo a los siguientes requerimientos adicionales:
Sería bueno llevar un registro histórico de nuestros alquileres. Cada vez que un socio alquile una copia, deberíamos guardar la fecha en que la retira y la fecha en que la devuelve. Todos los alquileres vencen al otro día, así que no sería necesario guardar la fecha de vencimiento.

Guardar un registro de todos los alquileres, nos permitiría poder analizar ciertos patrones. Podríamos determinar cuántas películas alquila cada socio y cuántas veces las devuelve tarde. También podríamos saber cuántas veces ha sido usada una copia y luego sabríamos cuándo descartarla, así como también conocer las preferencias de nuestros socios

#### 7. Artículos y encargos
Una base de datos para una pequeña empresa debe contener información acerca de clientes, artículos y pedidos. Hasta el momento se registran los siguientes datos en documentos varios:

Para cada cliente: Número de cliente, Direcciones de envío, Saldo, Límite de crédito, Descuento.

Para cada artículo: Número de artículo, Fábricas que lo distribuyen, Existencias de ese artículo en cada fábrica, Descripción del artículo.

Para cada pedido: Cada pedido tiene una cabecera y el cuerpo del pedido. La cabecera está formada por el número del cliente, dirección de envío y fecha del pedido y la cantidad.

Además, se ha determinado que se debe almacenar la información de las fábricas. Sin embargo, dado el uso de distribuidores, se usará: Número de la fábrica y Teléfono de contacto. También, por información estratégica, se podría incluir información de fábricas alternativas respecto de las que ya fabrican artículos para esta empresa.

#### 8. Alquiler de automóviles
Se desea diseñar una base de datos para almacenar las reservas de automóviles, teniendo en cuenta la siguiente información:

Un determinado cliente puede tener en un momento dado, varias reservas de vehículos. De cada cliente se desea almacenar su DNI, nombre, dirección y teléfono. Una reserva la realiza un único cliente pero puede involucrar a varios tipos de vehículos de la compañía.

Tenemos dos tipos de vehículos: Autos o Camionetas.

Cada una de las reservas se realiza en una determinada agencia. Es importante registrar la fecha de inicio y final de la reserva, el precio de alquiler de cada uno de los vehículos, y el precio total de la reserva. Finalmente, una vez que la reserva es ejecutada, es decir, se retira el o los tipos de vehículos reservados, se desea registrar:

La patente del vehículo asignado y los litros de nafta que posee el vehículo. No se mantienen los datos referidos a reservas anteriores.

Todo coche tiene siempre asignado un determinado garaje y no puede cambiar. De cada Garaje deseamos almacenar su código y dirección. De cada vehículo se desea almacenar el número de patente, la marca, el modelo y color.

#### 9. Tipos de Empleados
Una empresa ha definido dos tipos de empleados: contratados y efectivos. Para todos los empleados, almacenar su nro. de legajo, nombre, apellido y departamento en el que trabaja. Cada departamento tiene un código y una descripción. Para los empleados efectivos, se debe almacenar su salario. Para aquellos empleados contratados, almacenar el precio que cobra por hora común y por hora extra, y la Consultora a la que pertenecen. De cada consultora es necesario saber su nro. de CUIT y su Razón Social.

#### 10. Fabricantes de Muebles de Cocina
Actualmente trabajamos con una serie de fabricantes de muebles de cocina. De cada fabricante se desea almacenar un código, Razón Social, dirección y teléfono. Cada uno de ellos fabrica varios muebles de cocina.

De los muebles de cocina deseamos guardar un código, color, dimensiones (alto * largo * ancho). Además, cada mueble de cocina puede ser de una de las siguientes categorías excluyentes: Mueble alto, mueble bajo, panel o mesada. De los muebles bajos interesa saber la altura sobre el suelo y de las mesadas interesa saber su material (Mármol o aglomerado).

Cada fabricante puede trabajar con distintos distribuidores y cada distribuidor trabaja al menos con un fabricante. De un distribuidor deseamos almacenar un código, Razón Social, dirección y número de teléfono.

Una cocina la componen una serie de muebles de cocina y cada mueble de cocina solo podrá formar parte de una única cocina. De una cocina nos interesa saber el número de muebles que la componen, así como cuantos de ellos hay de cada tipo.

Cada cocina la puede vender un único distribuidor en una determinada fecha de venta, aunque cada distribuidor puede vender varias cocinas. Un distribuidor puede cederles cocinas a otros distribuidores para su posterior venta.
Cada cocina la debe colocar al menos un instalador y el mismo puede instalar varias cocinas. De un instalador nos interesa saber su DNI, nombre, apellido, dirección, teléfono y la cantidad de cocinas que ha instalado.
Cada cocina puede comprarla un cliente y el mismo cliente puede comprar varias cocinas. De un cliente nos interesa almacenar su DNI, nombre, dirección y teléfono


#### 11. Sistemas Batch
Un sistema ‘batch’ se trata de un conjunto de programas que tienen una determinada frecuencia de ejecución.

En una empresa existen diferentes sistemas batch, lo cuales utilizan programas que pueden ejecutarse en más de un sistema.

La frecuencia de ejecución de los programas dependerá del sistema que lo invoque para su ejecución.

A su vez, un programa puede hacer uso de diferentes archivos en alguno de los siguientes modos: Lectura, Escritura, Lectura-Escritura. Este modo de acceso dependerá del programa que lo utilice y del sistema en el que se encuentre ejecutando. Cabe aclarar que un mismo archivo puede ser usado por distintos programas.

A la Gerencia de Informática le interesa registrar el modo en que se accede a cada archivo, desde que programa se accede (Además de su frecuencia de ejecución), en el contexto de que sistema lo hace y el resultado de su ejecución (Correcto o con errores).

#### 12. Aumente la complejidad del ejercicio anterior, suponiendo que:
Algunos usuarios solicitan conocer el resultado de la ejecución de determinados programas y en función al sistema batch que lo invoca.

La gerencia de sistemas necesita almacenar la información vinculada a que usuarios tienen acceso a los resultados de la ejecución.

#### 13. Carrera facultad
Todas las materias tienen sus correspondientes correlativas. Existen profesores jefes de cátedra, y pueden serlo de varias asignaturas.Los profesores pueden dictar
diversas materias y compartir la comisión con otros profesores

Los alumnos pueden cursar distintas materias, en distintos horarios. 

Se necesita la siguiente información:

* Listado de materias rendidas por los alumnos (fecha y nota obtenida)
* Listado de alumnos inscriptos en materias (cursando)
* Listado de materias con aulas y horarios asignados.

#### 14. Grupo de Usuarios
Un grupo de Usuarios ha crecido enormemente en este último tiempo y necesita un sistema de información que los ayude a llevar registro.

Para cada miembro, necesitamos guardar su nombre, profesión, dirección, nro. de teléfono laboral y si está o no al día con las cuotas. Todos deben pagar una cuota anual que vence en el mes de enero.

Por otro lado, queremos saber en qué compañía trabaja cada miembro, pero sabemos que mantener actualizada esta información es muy difícil porque nuestros miembros cambian de compañía todo el tiempo. Sólo queremos registrar un solo empleador para cada miembro. Algunos de ellos están desempleados.

A lo largo del año realizan varios eventos y nos gustaría guardar cierta información de cada uno, como puede ser: lugar donde se realiza, oradores principales, nombre del evento, descripción de temas a tratar, cantidad de asistentes, costo de realización y los comentarios recibidos.

Nos gustaría registrar la fecha de cada evento, una descripción del mismo, la cantidad de asistentes, el lugar donde fue llevado a cabo, la cantidad de dinero gastada en él y los comentarios recibidos. Recibimos todos los comentarios como si vinieran de un emisor anónimo. Cada comentario es simplemente un texto libre de cualquier longitud.

A cada comentario recibido le ponemos un número y normalmente recibimos varios comentarios de cada evento.

También se quiere saber en qué áreas de aplicación está interesado cada miembro. Por ejemplo, contabilidad, recursos humanos, petróleo y gas, telecomunicaciones, sistemas de salud, etc.

#### 15. ART
En el grupo “Holding Bank” se ha decidido realizar un sistema que permita almacenar los datos de las ART que poseen los trabajadores de las diferentes empresas que componen el grupo. Se sabe que de cada trabajador es necesario saber nombre, apellido, tipo y número de documento, datos domiciliarios y fecha de ingreso a la empresa. Además, debemos conocer qué ART posee, pero debemos tener en cuenta que cada trabajador puede elegir una ART en un momento dado, pudiendo cambiar varias veces a lo largo del tiempo que trabaje en la empresa.

Se guardará historia por 10 años de todos los trabajadores que hayan pasado por las compañías, solamente que se le completará un dato relativo a la fecha de baja a aquellos trabajadores que hayan dejado de pertenecer. Aquí debemos tener en cuenta que un trabajador podría dejar de pertenecer a una compañía y luego de un tiempo darse de de alta en otra. En este caso se conservará el mismo legajo para el trabajador que poseía en la primera compañía. Todos los trabajadores deben poseer una ART.

#### 16. Sistema de ventas
Le contratan para diseñar una Base de Datos que permita apoyar la gestión de un sistema de ventas. La empresa necesita llevar un control de proveedores, clientes, productos y ventas.

Un proveedor tiene un CUIT, nombre, dirección, teléfono y página web. Un cliente tiene tipo y numero de documento, nombre, dirección, pero puede tener varios teléfonos de contacto. La dirección se entiende por calle, número, comuna y ciudad. Un producto tiene un id único, nombre, precio actual, stock y nombre del proveedor. Además, se organizan en categorías, y cada producto va sólo en una categoría. Una categoría tiene id, nombre y descripción. Por razones de contabilidad, se debe registrar la información de cada venta con un id, fecha, cliente, descuento y monto final. Además, se debe guardar el precio al momento de la venta, la cantidad vendida y el monto total por el producto.

#### 17. Capacitaciones internas
El departamento de formación de una empresa desea construir una base de datos para planificar y gestionar la formación de sus empleados.

La empresa organiza cursos internos de formación de los que se desea almacenar el código de curso, el nombre, una descripción, el número de horas de duración y el costo del mismo.

Un curso puede tener como prerrequisito, el haber finalizado otros previamente, y a su vez, la realización de un curso puede ser prerrequisito de otros. Un curso que es prerrequisito de otro, puede serlo de forma obligatoria o no.

Un curso posee diferentes ediciones, es decir, es impartido en diferentes lugares, fechas y horarios (Intensivo, de mañana o tarde). En una misma fecha de inicio sólo puede impartirse una edición de un determinado curso.

Los cursos son impartidos por personal de nuestra misma empresa. Un mismo empleado puede ser docente en una edición de un curso y alumno en otra edición pero nunca ambas cosas a la vez.

De los empleados que participan, se desea almacenar su legajo, nombre, apellido, dirección, interno, fecha de nacimiento, sexo y salario, así como saber si está capacitado para impartir cursos.

#### 18. Aerolínea
Una aerolínea maneja información de pasajeros, vuelos y personal. Para los pasajeros se considera de interés el pasaporte y el vuelo. Para los vuelos: el nro. de vuelo, fecha, hora, ciudad donde hace escalada, personal asignado, nro de avión. Para los aviones se considera modelo, fabricante, capacidad, hangar. Por último para el personal se tiene en cuenta el nombre y apellido, área asignada, y en particular para los pilotos se conoce la cantidad de horas de vuelo y el tipo de avión que pilotea.

#### 19. Club Social
Un Club social y deportivo desea automatizar la gestión sobre sus socios. Existen 4800 socios de diferentes edades y categorías de los cuales se lleva el siguiente registro; Número de socio, Nombre y apellido, antigüedad, sexo, Nro de documento y categoría.

Los socios pagan cuotas mensuales con un mismo importe, a excepción de los vitalicios que ya no pagan.

Deseamos conocer qué deportes practica en la institución cada socio. Los cadetes pueden competir en varios deportes, de acuerdo a donde estén federados.

Puede producirse la baja de un socio, (se registra con causa y fecha), por alguno de los siguientes motivos: Renuncia, Fallecimiento, Mora en más de “X” cuotas

#### 20. Aumente la complejidad del ejercicio anterior suponiendo lo siguiente:
La comisión del Club desea mantener información sobre las actividades que el socio realiza en la Institución:

Un socio puede practicar un deporte, muchos o ninguno, pero si practica deportes y éstos están arancelados, el importe de éstos deberá sumarse a la cuota social.

Se desea registrar lo siguiente: Deporte que practica, Horario, Arancel (si tiene) y Profesor asignado

#### 21. Cruceros
Cada embarcación tiene un nombre, una matrícula y una capacidad determinada de pasajeros. No nos interesa guardar el peso, la longitud, ni cualquier otro dato referente a las naves.

Cada año publicamos un folleto con información de cada uno de los cruceros que ofrecemos. Cada crucero tiene un nombre, una duración (en días) y una embarcación asignada.

Algunas personas sólo quieren viajar en embarcaciones nuevas, así que supongo que también necesitaremos guardar la antigüedad de cada barco.

Para cada crucero, debemos saber los distintos puertos en los cuales se detendrá. Un crucero de 3 días solo tendrá una parada, siempre en el segundo día, un crucero de 7 días tendrá 3 paradas y así sucesivamente.

Los puertos varían según de donde parte el crucero. Los cruceros de Los Angeles bajan a México y paran en los puertos de Cabo San Lucas y en el de la Ciudad de México, mientras que los cruceros de Miami van a Bahamas y luego a las Islas Vírgenes.

Los pasajeros que viajen con nosotros podrán elegir un determinado crucero, que tendrá una duración definida y que visitará una cantidad determinada de puertos.

Cuando elijan un crucero, podremos saber que habitaciones disponibles tiene. Cuando elijan la habitación, podremos decirle su precio. Este último depende de la capacidad de la habitación y de su categoría. Cuando una habitación es reservada, es eliminada de la lista de lugares disponibles, a menos que la misma no este completa y el pasajero desee compartirla con alguien más.

Luego de que los pasajeros hayan efectuado su reserva y nosotros hayamos recibido su depósito, procedemos a pagarle la comisión al agente de viajes que hizo la venta

#### 22. Good Bye Tours
Los productos comercializados por GBT son paquetes de servicios turísticos que se compran a operadores mayoristas. Es necesario almacenar información sobre los operadores, a saber: nombre, domicilio, localidad, país, teléfono, email, monto de la deuda a pagar por GBT.

Los paquetes se caracterizan por su código, itinerario, costo y precio. También se debe almacenar una descripción de cada recorrido. Periódicamente se arman contingentes de pasajeros que toman un mismo conjunto de paquetes. Los datos del contingente son nombre, nombre del guía, fecha de partida, duración, cupo máximo, cantidad de pasajeros.

Por cada pasajero se almacena su nombre, nro. de pasaporte, nacionalidad, sexo y edad.

Se emiten facturas a nombre de los pasajeros titulares. Cada factura tiene los datos corrientes de las facturas tipo A, B o C, según corresponda, además del vencimiento de la misma, forma de pago y la descripción de cada ítem facturado.

#### 23. Olimpiadas
Las sedes olímpicas se dividen en complejos deportivos. Los complejos deportivos se subdividen en aquellos en los que se desarrolla un único deporte y en los polideportivos. Los complejos polideportivos tienen áreas designadas para cada deporte con un indicador de localización (ejemplo: centro, esquina NE, etc.). Un complejo tiene una localización, un jefe de organización individual y un área total ocupada. Los dos tipos de complejos (deporte único y polideportivo) tendrán diferentes tipos de información. Para cada tipo de sede, se conservará el número de complejos junto con su presupuesto aproximado. Cada complejo celebra una serie de eventos (ejemplo: la pista del estadio puede celebrar muchas carreras distintas.). Para cada evento está prevista una fecha, duración, número de participantes, número de comisarios. Una lista de todos los comisarios se conservará junto con la lista de los eventos en los que esté involucrado cada comisario ya sea cumpliendo la tarea de juez u observador. Tanto para cada evento como para el mantenimiento se necesitará cierto equipamiento (ejemplo: arcos, pértigas, barras paralelas, etc).

#### 24. Rutas
Se necesita una base de datos para contener la información sobre todas las rutas del país, sabiendo que se deben cumplir las siguientes especificaciones:

* Las rutas están divididas en varias categorías: Provinciales, municipales, nacionales y autovías.
* Las rutas se dividen en tramos. Un tramo siempre pertenece a una única ruta y no puede cambiar de ruta.
* Un tramo puede pasar por varias localidades. Interesa conocer: el número de Km y localidad donde inicia el tramo y nro de Km y localidad donde finaliza el tramo.
* Para los tramos que suponen inicio o fin de una ruta, interesa saber si es que la ruta concluye físicamente o confluye en otra ruta distinta. En este caso, interesa conocer con qué ruta confluye, en qué número de kilómetro, tramo y localidad.

#### 25. Call Center
Se desea confeccionar un nuevo sistema para poder almacenar las llamadas que recibe el Call Center de la empresa “Compre YA S.A.”. Los llamados pueden corresponderse con compras de productos o bien reclamos que se realicen de los mismos. Cada llamada será registrada con una identificación que corresponderá con C ó R + Nro. Unívoco (por ejemplo, C101 corresponde a una compra 101 y R102 corresponde con un reclamo 102). Además, la llamada registra el número de teléfono del cual provino la llamada, la fecha y hora de llamado y número de línea interna por la ingresó el llamado. Otro de los datos a registrar, es la persona que ha realizado el llamado a la cual llamaremos Contacto. Todo contacto debe identificarse a través del tipo y número de documento y además, deberemos registrar su nombre, apellido, fecha de nacimiento y datos domiciliarios para poder enviar el pedido.

Tanto las compras como los reclamos se registrarán con una codificación unívoca para poder identificarlos ante un siguiente llamado.

Para el caso de los reclamos, se deberá registrar cada uno de los comentarios que realice el contacto en forma explícita. Si una persona vuelve a llamar para ver el avance de su reclamo, deberá indicarnos el número de reclamo y podremos verificar su estado (R: resuelto, E: en evolución, S: sin analizar). Si lo desea, el contacto podrá adjuntarnos un nuevo comentario de ese reclamo en cada una de las llamadas. Toda llamada, debe indicar el comentario que ha realizado sobre un determinado reclamo.

Para el caso de las compras, deberá indicar la fecha de realización de la compra, el medio de pago y si es necesario, persona autorizada para recibir el pedido. Si la compra se concreta se generará la factura indicando todos los productos que haya comprado. Se debe tener en cuenta que las facturas deben poseer un número unívoco, fecha de compra y datos que identifiquen a la persona que lo compró. Las llamadas son atendidas por operadores, los cuales poseen una identificación, fecha de ingreso a la empresa, nombre, apellido, tipo y número de documento. Existen operadores Junior y Senior. Cualquier operador podrá atender una llamada, pero sólo a los operadores Senior se le podrán derivar los reclamos para que luego realicen el
seguimiento. Existen operadores coordinadores, los cuales poseen un grupo de operadores a su cargo.

#### 26. Secretaría de Energía
La Secretaría de Energía desea almacenar información del servicio de energía eléctrica del país. Existen productores básicos de electricidad que se identifican por un nombre de los cuales nos interesa su producción media, máxima y fecha de entrada en funcionamiento. Estos productores básicos los son de una de las siguientes categorías: Hidroeléctrica, solar, nuclear o térmica. De una central hidroeléctrica nos interesa saber su ocupación, capacidad máxima y número de turbinas. De una solar nos interesa saber la superficie total ocupada por los paneles, la cantidad de paneles y la media anual de horas al sol. De una central nuclear nos interesa almacenar el número de reactores, el volumen de plutonio consumido y el de residuos nucleares que produce. De una central térmica nos interesa el número de hornos que posee, el volumen de carbón consumido y el volumen de emisiones de gases.

Además, por motivos de seguridad, nos interesa controlar el plutonio del que se provee a una central nuclear. Este control se refiere a la cantidad de plutonio que compra la central a cada uno de sus proveedores (De ellos, deseamos almacenar el Nombre y país) y que es enviado por un determinado transportista (De ellos deseamos almacenar el nombre y el número de matrícula internacional). Se debe considerar que un proveedor puede suministrar plutonio a diferentes centrales nucleares y que cada compra puede ser realizada por un transportista diferente.

Cada día, los productores entregan la energía producida a una o varias estaciones primarias, las cuales pueden recibir una cantidad distinta de cada uno de estos productores. Los productores siempre entregan el total de lo producido por día. Las estaciones primarias se identifican con un nombre, poseen una determinada cantidad de transformadores de baja, de alta tensión y son cabecera de una o varias redes de distribución.

Una red de distribución se identifica por un número de red y solo puede tener una estación primaria como cabecera. La propiedad de una red de distribución puede ser compartida por varias compañías eléctricas. A cada compañía eléctrica, se le identifica por su nombre.

La energía sobrante en una de las redes puede enviarse a otra red. Se registra el volumen total de energía intercambiada entre las 2 redes.

Una red está compuesta por una serie de líneas y cada línea se identifica por un número secuencial dentro del número de red. Además posee una determinada longitud. La menor de las líneas posibles, abastecerá al menos a dos subestaciones.

Una subestación es abastecida solo por una línea y distribuye a una o varias zonas de servicio. A tales efectos, las provincias (De ellos, deseamos almacenar solo código y el nombre) se encuentran divididas en zonas de servicio, aunque no puede haber zonas de servicio que pertenezcan a más de una provincia. Cada zona de servicio puede ser atendida por más de una subestación.

En cada zona de servicio se desea registrar el consumo medio y el número de consumidores finales de cada una de las siguientes categorías: Particulares, empresas e instituciones.

#### 27. Proyectos
Se registran los datos personales de cada empleado, como número de legajo, tipo y número de documento, nombre, dirección, teléfono, fecha de nacimiento, sueldo, y el número y nombre del departamento donde trabaja.

Algunos empleados son gerentes de departamento. En estos casos, se desea registrar la fecha de inicio en el cargo para cada empleado gerente. Un empleado no puede ser gerente de más de un departamento.

La organización desarrolla diferentes proyectos, y lleva el registro de los mismos a través de los datos: número de proyecto, nombre de proyecto, descripción y fecha de inicio del proyecto. Cabe señalar que un empleado puede trabajar en varios proyectos. Se desea registrar la cantidad de horas semanales (fija) que un empleado trabaja en cada proyecto.

Un departamento controla varios proyectos, y un proyecto es controlado por un único departamento. Es necesario conocer, por cada departamento la cantidad de proyectos que controla, y también, la cantidad total de empleados que tiene ese departamento. Por cada empleado se necesita registrar su edad, y los datos de los familiares-dependientes, como, por ejemplo, nombre, fecha de nacimiento, y el parentesco con el empleado.

#### 28. Administración de Siniestros
La Continental S.R.L. es una Compañía de Seguros de Automotores creada en 1990. Está ubicada en la ciudad de Rosario; tiene 5 sucursales en el interior del país y más de 15.000 clientes, cada uno de los cuales es propietario de uno o más vehículos. Esta empresa está totalmente informatizada y sus sistemas integrados en un 100%, en particular, el Sistema de Administración de Siniestros. Las tareas más habituales sobre dicho sistema son las siguientes: Añadir, eliminar ó modificar registros de clientes en la base de datos, buscar el número de accidentes en que se vieron implicados los distintos clientes desde que contrataron las respectivas pólizas, buscar el número total de personas cuyo coche estuvo implicado en algún accidente durante algún mes / año específico, crear vistas que contengan los clientes y sus accidentes registrados a partir del 2000, clientes de mayor riesgo, ranking de vendedores, ranking de clientes, ranking de tipos de siniestros, etc.

#### 29. Seguridad Informática
Una empresa decide crear un único entorno de ejecución que controle la seguridad de acceso para todas sus aplicaciones informáticas. Para ello considera conveniente dividir sus aplicaciones en subsistemas funcionales especializados y establecer el control de acceso al nivel de estos subsistemas. Se desarrollará un motor de ejecución que, tomando como parámetros los contenidos de la Base de Datos, controlará la ejecución de los subsistemas y el acceso a los mismos. Este motor, también se hará cargo de la navegación dentro de los subsistemas. De acuerdo a este enfoque, se establecen los siguientes requisitos:

La unidad básica de acceso a los subsistemas es el denominado perfil de acceso. Un usuario tendrá acceso a todos los subsistemas a los que permiten acceder a los distintos perfiles que le fueron asignados. Un usuario posee al menos un perfil. Un perfil permite el acceso de al menos un subsistema y para cualquier subsistema habrá siempre un perfil que permita acceder al mismo.

De los perfiles de acceso, lo mismo de los subsistemas, se mantiene un código y una descripción. De los subsistemas, se mantiene, además, la ventana en la que arranca el mismo.

Las Ventanas están compuestas por controles y toda ventana tendrá, al menos, un control que permitirá cerrarla. Todo control ha de emplearse en alguna de ventana y el mismo control puede ser empleado en distintas ventanas. De las ventanas y controles se mantiene, también, un código y una descripción.

Los controles pueden ser de dos tipos: Botones o ítems de menú. Para soportar la estructura jerárquica de menú pueden depender otros ítems pero no puede darse la situación que el mismo ítem dependa de varios ítems. En los ítems de menú se ha de mantener forzosamente el texto que se visualizará en pantalla. De los controles de tipo de botón se mantiene el nombre del ícono que opcionalmente se visualizará.

La activación de un control tiene como consecuencia la ejecución de una única acción (Todo control ejecutará, al menos, una acción). Una acción requiere siempre un control que pueda ejecutarla. De las acciones se mantiene el código y la descripción.

Las acciones pueden ser de dos tipos, de función y de llamada. Las acciones de función ejecutan una función interna del propio entorno (de la que se ha de almacenar el nombre). Las acciones de llamada invocan una única ventana.

#### 30. Aseguradora
Una compañía aseguradora de tipo Sanitario desea diseñar una Base de Datos para informatizar parte de su gestión Hospitalaria. Para esta primera etapa se obtuvo el siguiente relevamiento:

"Los Hospitales de la red pueden ser Propios o de Terceros. De ellos se desea almacenar su código, nombre, dirección y número de camas. Para los Hospitales propios se almacena, además, el presupuesto y el Tipo de Servicio. Una póliza se identifica por su número. La misma cubre a varios asegurados, los cuales se identifican por un número correlativo añadido al número de póliza, nombre, apellido y fecha de nacimiento.

Los asegurados cubiertos por una misma póliza pueden ser de distintas categorías. Los asegurados de “Primera categoría” pueden ser hospitalizados en cualquier hospital, en cambio, los asegurados de “Segunda categoría” sólo pueden ser hospitalizados en nosocomios propios.

Interesa saber en qué hospitales se han estado o están hospitalizados los asegurados, el médico que prescribió la internación, así como las fechas de inicio y fin de la misma.

Existen áreas geográficas, identificadas por un código y de las cuales se desea almacenar, también, su superficie y número de habitantes. Los hospitales tercerizados tienen que estar asignados a una única área y la misma no puede cambiar, mientras que los Hospitales propios no se encuentran asignados a ningún área en particular.

Los médicos se identifican por una matrícula y deseamos almacenar sus nombres, apellido, dirección y teléfono. Además, interesa saber a que área se encuentra destinado un médico. Existe además, una dependencia jerárquica entre médicos de forma que un médico tiene un único jefe."

#### 31. Jardinería
Esta empresa tiene jardineros empleados, de los que interesa conocer: documento, nombre y apellido, fecha de nacimiento, número de teléfono celular, categoría profesional y sueldo. El sueldo depende exclusivamente de la categoría salarial. Para realizar algunos tipos de trabajos, los jardineros se agrupan en cuadrillas, de las que interesa conocer: código de cuadrilla, denominación, zona en la que actúa, tipo de trabajos que realiza, número de jardineros que la componen y el jardinero responsable de la cuadrilla. Los tipos de trabajo que puede realizar una cuadrilla son: plantas de interior, plantas de exterior ó mixto. Una cuadrilla está compuesta por más de un jardinero, y un jardinero puede pertenecer, a lo largo del tiempo, a más de una cuadrilla, interesando la fecha de asignación a la cuadrilla. En una fecha dada, un jardinero pertenece a una única cuadrilla. La pertenencia a una cuadrilla no es obligatoria.

Los trabajos se realizan en jardines particulares, de los que interesa conocer: los datos del propietario, tipo de plantas (de interior, de exterior ó mixto), extensión y código de jardín (único por jardín). Una persona puede tener más de un jardín. Las tareas que se realizan en los jardines se definen con un código único, una descripción y un precio por hora. Estas tareas las pueden realizar jardineros en forma individual ó cuadrillas. Un jardinero ó una cuadrilla puede realizar más de una tarea en el mismo jardín. Un jardinero ó una cuadrilla puede realizar una ó más tareas en varios jardines. Interesa conocer la fecha en la que se realiza una tarea en un jardín, así como el tiempo empleado y si la tarea la realiza un jardinero ó una cuadrilla.

Algunos jardines tienen un Contrato de Mantenimiento con la empresa. Estos contratos son personalizados e interesa conocer de ellos, exclusivamente, la fecha de comienzo, la fecha de finalización, el costo y el tipo de mantenimiento (que se indica con 1, 2, 3, 4 ó 5).

#### 32. Dado el siguiente DER:

![Ejercicio 32](/images/practica-sql/ejercicio-32.png)

>Notas:
>
>* Este modelo de Base de Datos es sólo para pacientes ambulatorios de un determinado Hospital. Por ejemplo: un paciente que tiene una consulta con un cardiólogo, un paciente que se hace un tipo de estudio como por ejemplo un electrocardiograma, etc.
>* Las internaciones se manejan con otro sistema.
>* Las atenciones por Guardia también se manejan con otro sistema.

Realice las siguientes modificaciones del modelo dado. Se debe dibujar un nuevo DER completo que incluya todas las modificaciones.

1. Necesitamos registrar los Turnos que se le otorgan a cada Paciente. Los turnos tienen una Fecha y hora y un Médico determinado. Por ejemplo: el paciente Mateo Gonzalez tiene turno con la Dra. Nora Santos que es Pediatra el día 5/10/2017 a las 14:30 hs. 
    Luego, una vez que el paciente concurre al hospital y es atendido por el profesional, se registra efectivamente la Consulta Médica correspondiente. El Turno y la Consulta Médica son cosas independientes. Hay veces que algunos pacientes consultan Médicos sin tener turno y hay veces que sacan turno y luego no concurren a hacer la consulta.
    Luego de que el Paciente concurra o no, no borramos los turnos, los queremos dejar guardados como un registro histórico.
1. Para que un Paciente pueda hacerse un estudio, necesita previamente una Orden Médica de un Médico del Hospital que haya solicitado el estudio. No aceptamos órdenes de médicos externos.
    Necesitamos registrar estas órdenes para saber qué Médico solicitó que tipo de estudio y a qué paciente.
1. Para la mayoría de los tipos de estudios el paciente debe sacar Turno. Es un Turno distinto al que saca para los médicos, los llamamos Turnos para Estudio. Por ejemplo: el paciente Eduardo Perez sacó turno para una audiometría para el día 10/11/2017 a las 11:15 hs.
    Hay algunos tipos de estudios que no requieren turno previo, como por ejemplo: análisis de sangre, análisis de orina, etc.

**Solución**

![Solución ejercicio 32](/images/practica-sql/ejercicio-32-solucion.png)

#### 33. Dado el siguiente DER:

![Ejercicio 33](/images/practica-sql/ejercicio-33.png)

Realice un nuevo DER completo que incluya las siguientes modificaciones:

1. Un lote puede tener varios propietarios con determinados porcentajes. Por ejemplo, el lote 293 del barrio 14 es 60% de Ezequiel Villarreal y 40% de Facundo Tomaselli. Por otro lado, Facundo Tomaselli es dueño del 100% del lote 288 del mismo barrio. Queremos registrar todos los dueños de cada lote con su respectivo porcentaje.
1. Cada lote debe pagar una determinada cuota de expensas mensuales, cuyo valor se puede incrementar con el pasar de los meses. Queremos registrar el histórico mes a mes de la cuota que debe pagar cada lote, junto con la fecha de vencimiento y la fecha en que se hizo el pago. No se aceptan pagos parciales de cada cuota, es decir o se paga completa o se adeuda completa.
   Ejemplo:

   |Barrio|Lote|Mes|Importe Couta|Fecha Vencimiento|Fecha Pago|
|------|----|---|-------------|-----------------|----------|
|15|70|2017-10|2300|12/10/2017|10/10/2017|
|15|70|2017-11|2300|11/11/2017|10/11/2017|
|15|70|2017-12|2500|12/12/2017||

1. Queremos registrar los servicios que posee cada Barrio Cerrado. Por ejemplo: red de agua corriente, red de agua de pozo, cloacas, teléfono, electricidad con postes, electricidad subterránea, red de gas natural, red de gas envasado, etc.

**Solución**

![Solución ejercicio 33](/images/practica-sql/ejercicio-33-solucion.png)
