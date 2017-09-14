---
layout: practica
title:  "Práctica de Ejercicios DER"
date:   2017-08-26 09:30:49 -0300
categories: practicas der
---

## Diagrama de Entidad Relación

#### Ejercicio 1

Identificar las entidades con sus atributos y relaciones, según los siguientes requerimientos de información:

“Soy el gerente de una empresa de capacitación que brinda cursos relacionados con la
informática. Dictamos varios cursos, cada uno de los cuales tiene un código, un
nombre y una cuota. Introducción a UNIX y Programación C son dos de nuestros
cursos más populares. La duración de los cursos varía de uno a cuatro días. Un
instructor puede dictar varios cursos. Pablo Basile y Daniel Abadi son dos de nuestros
mejores profesores. Registramos el nombre y el nro. de teléfono de cada instructor.
Cada curso es dictado por un único instructor. Primero creamos un curso y luego le
asignamos un instructor.
Los alumnos pueden tomar varios cursos al mismo tiempo, y muchos de ellos lo
hacen. ¡Mariana Carpovich de AT&T se anota en cada curso que ofrecemos!. También
registramos el nombre y nro. telefónico de cada uno de nuestros alumnos. Algunos
alumnos e instructores no nos dan sus nros. de teléfono.”

#### Ejercicio 2

Identificar las entidades con sus atributos y relaciones, según los siguientes requerimientos de información:

La Secretaría de Vivienda de la Provincia XXX desea almacenar información
relacionada a los habitantes y las Viviendas donde residen los mismos.
De las Personas interesa almacenar su Tipo y Número de documento, su Nombre,
Apellido, y Fecha de nacimiento. Cada persona debe vivir en un solo domicilio, el cual
no necesariamente es de su propiedad y además una persona puede ser propietaria
de varias viviendas en distintos Municipios de nuestra provincia. Cabe destacar que
existen propiedades que tienen múltiples propietarios.
De las Viviendas interesa almacenar la dirección, la cantidad de metros cuadrados del
terreno y la cantidad de metros cuadrados que se encuentran edificados. Respecto a
los Municipios, se desea almacenar su Nombre y el nombre y apellido del Intendente
actual.

#### Ejercicio 3

Identificar las entidades con sus atributos y relaciones, según los siguientes requerimientos de información:

Los profesores de la cátedra de Administración 1 desean organizar sus listados,
utilizando una base de datos relacional, por lo cual nos encargaron diseñar el DER
para administrar los datos básicos de los alumnos que cursan la materia este año, los
trabajos prácticos que entregan (solo habrá trabajos prácticos individuales) y las notas
de los parciales (y recuperatorios) que rindan.

#### Ejercicio 4

Identificar las entidades con sus atributos y relaciones, según los siguientes requerimientos de información:

Los profesores de Administración 1 cambiaron de opinión y desean que se incluya la
posibilidad de que los trabajos prácticos sean grupales (cada alumno pertenecerá a un
solo grupo durante todo el año). Y ahora habrá una nota grupal y una nota individual a
determinar por el profesor a cargo. Por lo tanto rediseñe el DER realizado para el
enunciado ejercicio anterior para adaptarlo a esta nueva necesidad.

#### Ejercicio 5

Realizar el Diagrama ER para la siguiente situación:

Una empresa ha definido dos tipos de empleados: contratados y efectivos. Para todos
los empleados, almacenar su nro. de legajo, nombre, apellido y departamento en el
que trabaja. Cada departamento tiene un código y una descripción. Para los
empleados efectivos, se debe almacenar su salario. Para aquellos empleados
contratados, almacenar el precio que cobra por hora común y por hora extra, y la
Consultora a la que pertenecen. De cada consultora es necesario saber su nro. de
CUIT y su Razón Social.

#### Ejercicio 6

Identificar las entidades con sus atributos y relaciones, según los siguientes requerimientos de información:

Se desea diseñar una base de datos para almacenar las reservas de una empresa
dedicada al alquiler de automóviles, teniendo en cuenta la siguiente información:
Un determinado cliente puede tener en un momento dado, varias reservas de
vehículos. De cada cliente se desea almacenar su DNI, nombre, dirección y teléfono.
Cada cliente puede ser avalado por uno o varios clientes de la empresa.
Una reserva la realiza un único cliente e involucra a un unico vehículo de la compañía.
Cada reserva se realiza en una determinada agencia.

Es importante registrar la fecha de inicio y final de la reserva, el precio de alquiler de
cada uno de los coches, los litros de nafta que posee el mismo al momento de
disponer de la reserva, el precio total de la reserva y un indicador de si el coche o los
coches han sido entregados.

Todo coche tiene siempre asignado un determinado garaje y no puede cambiar. De
cada Garaje deseamos almacenar su código y dirección. De cada vehículo se desea
almacenar el número de patente, la marca, el modelo y color.

#### Ejercicio 7

Identificar las entidades con sus atributos y relaciones, según los siguientes requerimientos de información:

“Soy el dueño de un pequeño video club. Tenemos más de 3000 cintas sobre las
cuales queremos llevar registro.
Cada cinta tiene un número. Para cada película, necesitamos saber su título y
categoría (por ej: comedia, suspenso, drama, acción, ciencia ficción, etc.).
Tenemos varias copias de muchas de nuestras películas. A cada película le ponemos
un código específico, y luego registramos qué película contiene una cinta. Las cintas
pueden ser de formato Beta o VHS. Siempre tenemos al menos una cinta de cada
película. Nuestras cintas son muy largas, y no tenemos ninguna película que necesite
más de una cinta.

Frecuentemente nos solicitan películas protagonizadas por determinados actores. Tom
Hanks y Brad Pitt son algunos de los más solicitados. De manera tal que nos gustaría
registrar los actores famosos que actúan en cada película. No todas nuestras películas
tienen actores famosos. A los clientes también les gusta saber el nombre real de cada
actor y su fecha de nacimiento. Solo registramos aquellos actores que aparecen en las
películas de nuestro inventario.
Tenemos un montón de clientes. Sólo le alquilamos videos a las personas que estén
asociadas a nuestro video club. Para cada socio, nos gustaría registrar su nombre y
apellido, nro de teléfono y dirección. Y por supuesto, cada socio tiene su número de
socio.

Por último, necesitamos registrar que cintas ha retirado cada cliente. Un cliente puede
llevarse muchas cintas al mismo tiempo. Sólo queremos registrar los alquileres
actuales. No nos interesa llevar un registro histórico de los alquileres.”

#### Ejercicio 8

Modificar el Diagrama ER del ejercicio 7 (Video Club) para ajustarlo a los siguientes requerimientos adicionales:

“Ahora que lo pienso bien, sería bueno llevar un registro histórico de nuestros
alquileres. Cada vez que un socio alquile una cinta, deberíamos guardar la fecha en
que la retira y la fecha en que la devuelve. Todos los alquileres vencen al otro día, así
que no sería necesario guardar la fecha de vencimiento.
Guardar un registro de todos los alquileres, nos permitiría poder analizar ciertos
patrones. Podríamos determinar cuántas películas alquila cada socio y cuántas veces
las devuelve tarde. También podríamos saber cuántas veces ha sido usada una copia
y luego sabríamos cuándo descartarla. También podríamos conocer las preferencias
de nuestros socios.”

#### Ejercicio 9

Modelizar la biblioteca de la universidad utilizando el Diagrama ER.

Existen dos tipos de usuario: sin carnet (sólo pueden realizar consultas en sala de
lectura) y con carnet (pueden llevarse libros en préstamo hasta por una semana).
Interesa registrar todos los préstamos. El material bibliográfico está compuesto por
libros y revistas, y estas últimas sólo pueden consultarse en sala de lectura.
Un libro o revista puede tener varios ejemplares.

Describir las entidades con sus correspondientes atributos, identificar las claves e
interrelaciones con su clasificación.

#### Ejercicio 10

Realizar un Diagrama ER para la siguiente situación:

En una línea de producción trabajan varios obreros. Cada obrero trabaja en una
máquina de esa línea.

Los obreros están capacitados para usar varios tipos de máquinas, por lo que pueden
estar asignados a una u otra máquina en distintas líneas de producción. Todos los
días se asignan las líneas de producción y dentro de ellas, las máquinas y los obreros.
Las máquinas dentro de las líneas se identifican por un número. En el inventario
realizado por la compañía (Todos los días inventariamos las máquinas y
comprobamos el estado de las mismas), las máquinas tienen un código que las
identifica, tipo, descripción y estado. Las maquinarias se pueden cambiar de línea y/o
reemplazar otras maquinarias por problemas y desperfectos. Si una máquina tiene
dentro del mes menos de 10 días de servicio se la reemplaza por una nueva.

#### Ejercicio 11

Realizar un Diagrama ER según el siguiente relevamiento.

Actualmente trabajamos con una serie de fabricantes de muebles de cocina. De cada
fabricante se desea almacenar un código, Razón Social, dirección y teléfono. Cada
uno de ellos fabrica varios muebles de cocina.

De los muebles de cocina deseamos guardar un código, color, dimensiones (alto *
largo * ancho). Además, cada mueble de cocina puede ser de una de las siguientes
categorías excluyentes: Mueble alto, mueble bajo, panel o mesada. De los muebles
bajos interesa saber la altura sobre el suelo y de las mesadas interesa saber su
material (Mármol o aglomerado).

Cada fabricante puede trabajar con distintos distribuidores y cada distribuidor trabaja al
menos con un fabricante. De un distribuidor deseamos almacenar un código, Razón
Social, dirección y número de teléfono.

Una cocina la componen una serie de muebles de cocina y cada mueble de cocina
solo podrá formar parte de una única cocina. De una cocina nos interesa saber el
número de muebles que la componen, así como cuantos de ellos hay de cada tipo.

Cada cocina la puede vender un único distribuidor en una determinada fecha de venta,
aunque cada distribuidor puede vender varias cocinas. Un distribuidor puede cederle
cocinas a otros distribuidores para su posterior venta.

Cada cocina la debe colocar al menos un instalador y el mismo puede instalar varias
cocinas. De un instalador nos interesa saber su DNI, nombre, apellido, dirección,
teléfono y la cantidad de cocinas que ha instalado.

Cada cocina puede comprarla un cliente y el mismo cliente puede comprar varias
cocinas. De un cliente nos interesa almacenar su DNI, nombre, dirección y teléfono.

#### Ejercicio 12

​Realizar el Diagrama Entidad­-Relación correspondientes al siguiente relevamiento:

Un sistema está formado por un conjunto de programas que tienen una
determinada frecuencia de ejecución.

Un programa puede ejecutarse en más de un sistema y su frecuencia
dependerá del sistema en que se ejecute.

A su vez, un programa puede usar varios archivos en distintos modos (Input,
Output, Input­Output), y este modo de acceso dependerá del programa que lo
utilice y en que Sistema se encuentre ejecutando dicho programa. Además, un
mismo archivo puede ser usado por varios programas durante sus ejecuciones.

A la Gerencia de Informática le interesa registrar el modo de acceso de cada
archivo y la frecuencia para cada programa que se ejecute.

#### Ejercicio 13

Aumente la complejidad del ejercicio anterior, suponiendo que:
Cada usuario del sistema tiene acceso sólo a determinados sistemas, y dentro
de ellos a determinados programas. La Gerencia necesita, por razones de
seguridad, conocer los permisos de acceso de sus usuarios.

#### Ejercicio 14

Realizar el Diagrama Entidad­-Relación correspondientes al siguiente relevamiento:

En una carrera de ciencias informáticas de una determinada facultad existen tres
especialidades. De las materias que se dictan, algunas son comunes entre las
especialidades.

Todas las materias tienen sus correspondientes correlativas.
Existen profesores jefes de cátedra, y pueden serlo de varias asignaturas.
Los profesores pueden dictar varias materias, y compartir la cátedra con otros
profesores.

Los alumnos pueden cursar distintas materias, en distintos horarios.

Se necesita la siguiente información:
* Listado de materias rendidas por los alumnos (fecha y nota obtenida)
* Listado de alumnos inscriptos en materias (cursando)
* Listado de materias con aulas y horarios asignados.
* Listado de profesores a cargo de la cátedra. (Jefes de cátedra)

#### Ejercicio 15

Realizar un Diagrama ER para la siguiente situación:

“Nuestro Grupo de Usuarios MySQL de Argentina ha crecido enormemente en este
ultimo tiempo. Somos una organización conformada enteramente por voluntarios, y
nuestros archivos son un desastre. Necesitamos un sistema de información que nos
ayude a llevar registro de nuestros asuntos.
Definitivamente necesitamos automatizar los registros de nuestros miembros. Para
cada miembro, necesitamos guardar su nombre, profesión, dirección, nro. de teléfono
laboral, tipo de miembro (individuo u organización), y si está o no al día con las cuotas.
Todos deben pagar una cuota anual que vence en el mes de enero.
Por otro lado, queremos saber en qué compañía trabaja cada miembro, pero sabemos
que mantener actualizada esta información es muy difícil porque nuestros miembros
cambian de compañía todo el tiempo. Sólo queremos registrar un solo empleador para
cada miembro. Nuestros miembros vienen de distintas empresas como por ejemplo,
Quilmes, Arcor y Loma Negra. Algunos de ellos están desempleados. Para cada
compañía, queremos almacenar su razón social, dirección y rubro al que se dedica.
Tenemos una lista estándar de rubros. Sólo guardamos la dirección principal de cada
empresa.

A lo largo del año realizamos varios eventos y nos gustaría guardar cierta información
de cada uno. Algunos de nuestros eventos anuales son la Reunión de Septiembre, la
Reunión de Noviembre, el Día de Capacitación anual en Enero, la Reunión de Abril,
etc. También nos gustaría guardar los eventos especiales de cada año. Por ejemplo,
tuvimos un día especial dedicado a las herramientas CASE el mes pasado, en el cual
Ruben Rodriguez dio una conferencia. Nuestros eventos son llevados a cabo en
diferentes lugares de la ciudad, como ser, la sede central de la IEEE, el hotel Sheraton
y la facultad de Ingeniería de la UBA.

Nos gustaría registrar la fecha de cada evento, una descripción del mismo, la cantidad
de asistentes, el lugar donde fue llevado a cabo, la cantidad de dinero gastada en él y
los comentarios recibidos. Recibimos todos los comentarios como si vinieran de un
emisor anónimo. Cada comentario es simplemente un texto libre de cualquier longitud.
A cada comentario recibido le ponemos un número y normalmente recibimos varios
comentarios de cada evento.

También queremos registrar a cuáles eventos asisten nuestros miembros. Algunos de
ellos son muy activos y otros participan en muy pocos eventos o simplemente disfrutan
recibir nuestro newsletter.

Adicionalmente, nos gustaría registrar qué tipo de plataforma usan nuestros miembros.
Tenemos una lista única con un código determinado para cada plataforma existente.
Por ejemplo, 001 es el código de Linux, 030 es Windows NT, 031 es Windows 2000,
050 es Solaris, 060 es HP­UX, etc.

También queremos saber en qué áreas de aplicación está interesado cada miembro.
Por ejemplo, contabilidad, recursos humanos, petróleo y gas, telecomunicaciones,
sistemas de salud, etc.”

#### Ejercicio 16

En el DER del ejercicio 12 (grupo de usuarios ``MySQL``) hay una relación N­-N
entre los ``Miembros`` y sus ``Plataformas``. Revise esa relación según los siguientes
requerimientos corregidos:

“En realidad, no necesitamos saber qué plataforma usa cada miembro. Lo que
verdaderamente nos interesa es saber qué productos MySQL (Database Server,
MySQL Control Center, MySQL Administrator, MaxDB, etc.) usa cada miembro y sobre
cuál plataforma los usan. No nos interesa saber el nro. de versión de cada producto,
sólo el nombre.”

#### Ejercicio 17

Realizar un Diagrama ER según el siguiente relevamiento.

En el grupo “Holding Bank”, se ha decidido realizar un sistema que permita almacenar
los datos de las ART que poseen los trabajadores de las diferentes empresas que
componen el grupo. Se sabe que de cada trabajador es necesario saber nombre,
apellido, tipo y número de documento, datos domiciliarios y fecha de ingreso a la
empresa. Además, debemos conocer qué ART posee, pero debemos tener en cuenta
que cada trabajador puede elegir una ART y puede trabajar en cualquier empresa del
grupo.

Se guardará historia por 10 años de todos los trabajadores que hayan pasado por las
compañías, solamente que se le completará un dato relativo a la fecha de baja a
aquellos trabajadores que hayan dejado de pertenecer. Aquí debemos tener en cuenta
que un trabajador podría dejar de pertenecer a un compañía y luego de un tiempo
darse de de alta en otra. En este caso se conservará el mismo legajo para el
trabajador que poseía en la primera compañía.

Los trabajadores poseen un puesto de trabajo asociado según la empresa a la cual
pertenezca actualmente y dicho puesto posee una clasificación de riesgo: Bajo, Medio
o Alto. Esto permitirá clasificar el tipo de ART que se necesite contratar. Todo nuestros
trabajadores deben poseer una ART.

#### Ejercicio 18

Realizar un Diagrama ER según el siguiente relevamiento.

La empresa "Mi Stock SA" necesita registrar las compras que realizan los diversos
clientes en la empresa.

La compra de productos, resulta la operación más importante de la empresa.
Aunque cuando el cliente efectúa la compra no necesariamente se abonará en el
momento, sino que podría retrasarse. Solo en el momento de abonar la factura se
dará por finalizada la compra.

Cada factura siempre hará referencia a una compra realizada.

Toda factura tendrá un número correlativo, una fecha de vencimiento y fecha de pago
y el medio de pago (Efectivo, Tarjeta, Cheque).
Todo cliente se identificará unívocamente. De los mismos se desea almacenar la
razón social, el cuit y los datos domiciliarios.
Los productos que comercializa la empresa pueden ser de diferentes rubros. De cada
uno de los productos se almacenará el código unívoco y una descripción.

Los productos son provistos por proveedores nacionales e internacionales, pero para
éstos últimos se les cobrará una comisión especial, además de almacenar el país de
origen y el país de distribución.

De los proveedores, también se almacenará la Razón social, CUIT y datos
correspondientes al domicilio.

#### Ejercicio 19

Realizar un Diagrama ER según el siguiente relevamiento.

“El departamento de formación de nuestra empresa desea construir una base de datos
para planificar y gestionar la formación de sus empleados.
La empresa organiza cursos internos de formación de los que se desea almacenar el
código de curso, el nombre, una descripción, el número de horas de duración y el
costo del mismo.

Un curso puede tener como prerrequisito, el haber finalizado otros previamente, y a su
vez, la realización de un curso puede ser prerrequisito de otros. Un curso que es
prerrequisito de otro, puede serlo de forma obligatoria o no”.

Un mismo curso posee diferentes ediciones, es decir, es impartido en diferentes
lugares, fechas y horarios (Intensivo, de mañana o tarde). En una misma fecha de
inicio solo puede impartirse una edición de un determinado curso.

Los cursos son impartidos por personal de nuestra misma empresa.
De los empleados que participan, se desea almacenar su legajo, nombre, apellido,
dirección, interno, fecha de nacimiento, sexo y salario, así como saber si está
capacitado para impartir o no, cursos y la cantidad de horas que posee como docente.

Un mismo empleado puede ser docente en una edición de un curso y alumno en otra
edición pero nunca ambas cosas a la vez.”

#### Ejercicio 20

Realizar un Diagrama ER según el siguiente relevamiento.

Una aerolínea maneja información de pasajeros, vuelos y personal. Para los pasajeros
se considera de interés el pasaporte y el vuelo. Para los vuelos: el nro. de vuelo,
fecha, hora, ciudad donde hace escalada, personal asignado, nro de avión. Para los
aviones se considera modelo, fabricante, capacidad, hangar. Por último para el
personal se tiene en cuenta el nombre y apellido, área asignada, y en particular para
los pilotos se conoce la cantidad de horas de vuelo y el tipo de avión que pilotea.

#### Ejercicio 21

Realizar un Diagrama ER según el siguiente relevamiento.

Un Club social y deportivo desea automatizar la gestión sobre sus socios.
Existen 4800 socios de diferentes edades y categorías de los cuales se lleva el
siguiente registro:
* ­Número de socio
* ­Nombre y apellido
* ­antigüedad
* ­sexo
* ­Tipo y Nro de documento
* ­categoría

Las categorías pueden ser: Activo, Vitalicio, Cadete.

Los socios pagan 12 cuotas mensuales con un mismo importe, a excepción de los
vitalicios que no pagan.

Puede producirse la baja de un socio, que se registra con causa y fecha, puede
deberse a los siguientes motivos:
* ­Renuncia
­* Fallecimiento
­* Mora en más de 3 cuotas

La comisión del Club desea la siguiente información:
­* Listado de socios morosos con 2 cuotas impagas para darles un aviso de posible baja.
* ­Listado de socios por antigüedad y categoría
­* Listado de socios dados de baja en determinada fecha.

#### Ejercicio 22

Aumente la complejidad del ejercicio anterior suponiendo lo siguiente:

La comisión del Club desea mantener información sobre las actividades que el socio
realiza en la Institución:

Un socio puede practicar un deporte, muchos o ninguno, pero si practica deportes y
éstos están arancelados, el importe de éstos deberá sumarse a la cuota social.
Se desea registrar lo siguiente:
* ­Deporte que practica (natación, football, basquet, tenis, etc.)
* ­Horario
* ­Arancel (si tiene)
* ­Profesor asignado

Cada uno de los profesores, de los cuales se desea registrar sus datos personales,
está asignado a un sólo deporte, aunque un mismo deporte puede practicarse con
hasta dos profesores distintos.

#### Ejercicio 23

Realizar un Diagrama ER según el siguiente relevamiento.

“Soy Carlos Acosta de Cruceros Atlantis. Hemos decidido que nuestro sistema manual
de registro de pasajeros colapsará cuando incorporemos nuestra nueva embarcación.
Pasaremos a tener dos embarcaciones y esperamos expandirnos a 5 o 6 en el año 2005. Cada embarcación tiene un nombre, una matrícula y una capacidad
determinada de pasajeros. No nos interesa guardar el peso, la longitud, ni cualquier
otro dato referente a las naves.

Cada año publicamos un folleto con información de cada uno de los cruceros que
ofrecemos. Cada crucero tiene un nombre, una duración (en días) y una embarcación
asignada.

Algunas personas sólo quieren viajar en embarcaciones nuevas, así que supongo que
también necesitaremos guardar la antigüedad de cada barco.
Para cada crucero, debemos saber los distintos puertos en los cuales se detendrá. Un
crucero de 3 días solo tendrá una parada, siempre en el segundo día, un crucero de 7
días tendrá 3 paradas y así sucesivamente.

Los puertos varían según de donde parte el crucero. Los cruceros de Los Angeles
bajan a Méjico y paran en los puertos de Cabo San Lucas y en el de la Ciudad de
Méjico, mientras que los cruceros de Miami van a Bahamas y luego a las Islas
Vírgenes.

Los pasajeros que viajen con nosotros podrán elegir un determinado crucero, que
tendrá una duración definida y que visitará una cantidad determinada de puertos.
Cuando elijan un crucero, podremos saber que habitaciones disponibles tiene. Cuando
elijan la habitación, podremos decirle su precio. Este último depende de la capacidad
de la habitación y de su categoría. Cuando una habitación es reservada, es eliminada
de la lista de lugares disponibles, a menos que la misma no este completa y el
pasajero desee compartirla con alguien más.

Luego de que los pasajeros hayan efectuado su reserva y nosotros hayamos recibido
su depósito, procedemos a pagarle la comisión al agente de viajes que hizo la venta.”

#### Ejercicio 24

​Diseñar una base de datos para “Good Bye Tours”, una empresa de viajes y turismo, utilizando el Modelo ER. 

Del análisis de requerimientos de ha determinado lo siguiente:

* Los productos comercializados por GBT son paquetes de servicios turísticos que
se compran a operadores mayoristas. Es necesario almacenar información sobre
los operadores, a saber: nombre, domicilio, localidad, país, teléfono, email, monto
de la deuda a pagar por GBT.
* Los paquetes se caracterizan por su código, itinerario, costo y precio. También se
debe almacenar una descripción de cada recorrido. Periódicamente se arman
contingentes de pasajeros que toman un mismo conjunto de paquetes. Los datos
del contingente son nombre, nombre del guía, fecha de partida, duración, cupo
máximo, cantidad de pasajeros.
* Por cada pasajero se almacena su nombre, nro. de pasaporte, nacionalidad, sexo
y edad.
* Se emiten facturas a nombre de los pasajeros titulares. Cada factura tiene los
datos corrientes de las facturas tipo A, B o C, según corresponda, además del
vencimiento de la misma, forma de pago y la descripción de cada ítem facturado.
* Un contingente puede contratar uno o más paquetes y un paquete puede estar
programado en varios contingentes en fechas diferentes.
* Cada paquete pertenece a un único operador.
* Cada pasajero participa a lo sumo de un contingente.

#### Ejercicio 25

Diseñar una base de datos, utilizando el Diagrama ER, para el Instituto KCC, de enseñanza de computación, con el fin de sistematizar sus actividades académicas. 

Del análisis de requerimientos de obtuvo lo siguiente:
* Un curso se caracteriza por una sigla de 4 letras, nombre, fecha de inicio, duración,
cupo y arancel.
* Cada alumno se describe por un legajo, nombre, domicilio y teléfono.
* Cada ítem de horario se representa de la forma día de la semana, horario (desde,
hasta) y aula. Por ejemplo: Lu, 15, 18, 305, lo que representa el ítem lunes de 15 a
18 en el aula 305.
* Los cargos se almacenan como numero de cargo, categoría y sueldo.
* Cada cargo pertenece a un único profesor y a un único curso, pero un profesor
puede tener varios cargos y un curso puede tener asignados varios cargos.
* Un ítem de horario corresponde a un único curso pero puede haber varios horarios
para el mismo curso (uno por cada clase semanal).
* Los alumnos pueden inscribirse en varios cursos.

#### Ejercicio 26

Realizar un Diagrama ER según el siguiente relevamiento.

Una fábrica de aparatos de televisión desea automatizar el sector de stock y el sector
ventas.

En el sector stock existe un archivo de productos terminados (televisores listos para la
venta).

Los insumos son provistos por proveedores nacionales y extranjeros, los que
suministran artículos diferentes. Los insumos nacionales son provistos por más de un
proveedor, esto no sucede en el caso de los importados.

Existen 10 modelos distintos, y cada uno de ellos posee: un número de serie que está
impreso en la tapa posterior del aparato.

Se desea contar con la siguiente información:
* ­Cantidad de aparatos disponibles para su venta.
­* Cantidad de artículos importados y nacionales comprados a determinada fecha.
* Los clientes de esta empresa son mayoristas y están ubicados en distintas provinciasy en capital federal.

Se desea registrar la cantidad de televisores vendidos por cliente y la fecha en que se
realizó la venta.

Los clientes del interior tiene un recargo en el precio, pues la mercadería se les envía
a domicilio.

Se necesita emitir un listado con el total de las ventas realizadas por cliente.

#### Ejercicio 27

Realizar un Diagrama ER según el siguiente relevamiento.

En una biblioteca se desea implantar un sistema de bases de datos.

La biblioteca cuenta con aproximadamente 10000 volúmenes y de varios de ellos
existen varios ejemplares.

La información sobre cada libro se agrupa por tema en 3 grandes áreas:
1. ­General
1. ­Literatura
1. Técnica

Dentro de cada área los libros se clasifican en temas y dentro de cada tema por autor
y título.

Un libro tiene muchos autores y un autor escribe muchos libros.

Cada libro tiene un nro de inventario que es el mismo para todos los ejemplares de un
mismo libro, y se le agrega un número que identifica el ejemplar:

    Ejemplo nro de inventario: 1222/1, 1222/2, 1222/3

Existe un código de ubicación que está compuesto por 4 dígitos, los 2 primeros indican
la estantería donde se encuentra el libro y los 2 restantes el estante.

    Ejemplo: E120 (estantería E1, estante 20)

Se desea responder a las siguientes consultas:
* ­Dado un tema, mencionar todos los libros existentes, ordenados por autor
­* Dado un título, encontrar su ubicación (estantería y estante)

#### Ejercicio 28

Aumente la complejidad del ejercicio anterior suponiendo lo siguiente:

La biblioteca cuenta con un registro de socios que posee los siguientes datos:

* ­Número de socio
­* Nombre y apellido
­* Dirección
­* Teléfono

Se registran además los préstamos de los libros a los socios, y los pagos realizados
(12 cuotas) por los mismos.

No se prestan libros a no socios ni a socios que no estén al día con los pagos.
Se necesita lo siguiente:

*­ Listado de socios morosos (por pagos)
* ­Listado de socios morosos (por libros no devueltos en fecha)
* ­Listado de libros prestados con su fecha.

#### Ejercicio 29

Realizar un Diagrama ER según el siguiente relevamiento.

“Se desea confeccionar un nuevo sistema para poder almacenar las llamadas que
recibe el Call Center de la empresa “Compre YA S.A.”. Los llamados pueden
corresponderse con compras de productos o bien reclamos que se realicen de los
mismos. Cada llamada será registrada con una identificación que corresponderá con C
ó R + NroUnívoco (por ejemplo, C101 corresponde a una compra 101 y R102
corresponde con un reclamo 102). Además, la llamada registra el número de teléfono
del cual provino la llamada, la fecha y hora de llamado y número de línea interna por la
ingresó el llamado. Otro de los datos a registrar, es la persona que ha realizado el
llamado a la cual llamaremos Contacto. Todo contacto debe identificarse a través del
tipo y número de documento y además, deberemos registrar su nombre, apellido,
fecha de nacimiento y datos domiciliarios para poder enviar el pedido.
Tanto las compras como los reclamos se registraran con una codificación unívoca para
poder identificarlos ante un siguiente llamado.

Para el caso de los reclamos, se deberá registrar cada uno de los comentarios que
realice el contacto en forma explícita. Si una persona vuelve a llamar para ver el
avance de su reclamo, deberá indicarnos el número de reclamo y podremos verificar
su estado (R: resuelto, E: en evolución, S: sin analizar). Si lo desea, el contacto podrá
adjuntarnos un nuevo comentario de ese reclamo en cada una de las llamadas. Toda
llamada, debe indicar el comentario que ha realizado sobre un determinado reclamo.

Para el caso de las compras, deberá indicar la fecha de realización de la compra, el
medio de pago y si es necesario, persona autorizada para recibir el pedido. Si la
compra se concreta se generará la factura indicando todos los productos que haya
comprado. Se debe tener en cuenta que las facturas deben poseer un número
unívoco, fecha de compra y datos que identifiquen a la persona que lo compró. No
todas las compras pudieron haber generado la factura, ya que al derivarse al sector de
compras, analizarán y autorizarán la compra.

Las llamadas son atendidas por operadores, los cuales poseen una identificación O +
Nro. de los mismos se poseen los datos de fecha de ingreso a la empresa, nombre,
apellido, tipo y número de documento. Existen operadores Junior y Senior. Cualquier
operador podrá atender una llamada, pero sólo a los operadores Senior se le podrán
derivar los reclamos para que luego realicen el seguimiento. Existen operadores
coordinadores, los cuales poseen un grupo de operadores a su cargo.”

#### Ejercicio 30

Realizar un Diagrama ER según el siguiente relevamiento.

“La Secretaría de Energía desea almacenar información del servicio de energía
eléctrica del país. Existen productores básicos de electricidad que se identifican por un
nombre de los cuales nos interesa su producción media, máxima y fecha de entrada
en funcionamiento. Estos productores básicos los son de una de las siguientes
categorías: Hidroeléctrica, solar, nuclear o térmica. De una central hidroeléctrica nos
interesa saber su ocupación, capacidad máxima y número de turbinas. De una solar
nos interesa saber la superficie total ocupada por los paneles, la cantidad de paneles y
la media anual de horas al sol. De una central nuclear nos interesa almacenar el
número de reactores, el volumen de plutonio consumido y el de residuos nucleares
que produce. De una central térmica nos interesa el número de hornos que posee, el
volumen de carbón consumido y el volumen de emisiones de gases.

Además, por motivos de seguridad, nos interesa controlar el plutonio del que se
provee a una central nuclear. Este control se refiere a la cantidad de plutonio que
compra la central a cada uno de sus proveedores (De ellos, deseamos almacenar el
Nombre y país) y que es enviado por un determinado transportista (De ellos deseamos
almacenar el nombre y el número de matrícula internacional). Se debe considerar que
un proveedor puede suministrar plutonio a diferentes centrales nucleares y que cada
compra puede ser realizada por un transportista diferente.

Cada día, los productores entregan la energía producida a una o varias estaciones
primarias, las cuales pueden recibir una cantidad distinta de cada uno de estos
productores. Los productores siempre entregan el total de lo producido por día. Las
estaciones primarias se identifican con un nombre, poseen un determinada cantidad
de transformadores de baja, de alta tensión y son cabecera de una o varias redes de
distribución.

Una red de distribución se identifica por un número de red y solo puede tener una
estación primaria como cabecera. La propiedad de una red de distribución puede ser
compartid por varias compañías eléctricas. A cada compañía eléctrica, se le identifica
por su nombre.

La energía sobrante en una de las redes puede enviarse a otra red. Se registra el
volumen total de energía intercambiada entre las 2 redes.
Una red está compuesta por una seria de líneas y cada línea se identifica por un
número secuencial dentro del número de red. Además posee una determinada
longitud. La menor de las líneas posibles, abastecerá al menos a dos subestaciones.
Una subestación es abastecida solo por una línea y distribuye a una o varias zonas de
servicio. A tales efectos, las provincias (De ellos, deseamos almacenar solo código y el
nombre) se encuentran divididas en zonas de servicio, aunque no puede haber zonas
de servicio que pertenezcan a mas de una provincia. Cada zona de servicio puede ser
atendida por más de una subestación.

En cada zona de servicio se desea registrar el consumo medio y el número de
consumidores finales de cada una de las siguientes categorías: Particulares, empresas
e instituciones”

#### Ejercicio 31

Realizar un Diagrama ER según el siguiente relevamiento.

“Una empresa decide crear un único entorno de ejecución que controle la seguridad de
acceso para todas sus aplicaciones informáticas. Para ello considera conveniente
dividir sus aplicaciones en subsistemas funcionales especializados y establecer el
control de acceso al nivel de estos subsistemas. Se desarrollará un motor de ejecución
que, tomando como parámetros los contenidos de la Base de Datos, controlará la
ejecución de los subsistemas y el acceso a los mismos. Este motor, también se hará
cargo de la navegación dentro de los subsistemas. De acuerdo a este enfoque, se
establecen los siguientes requisitos:

La unidad básica de acceso a los subsistemas es el denominado perfil de acceso. Un
usuario tendrá acceso a todos los subsistemas a los que permiten acceder a los
distintos perfiles que le fueron asignados. Un usuario posee al menos un perfil. Un
perfil permite el acceso de al menos un subsistema y para cualquier subsistema habrá
siempre un perfil que permita acceder al mismo.

De los perfiles de acceso, lo mismo de los subsistemas, se mantiene un código y una
descripción. De los subsistemas, se mantiene, además, la ventana en la que arranca
el mismo.

Las Ventanas están compuestas por controles y toda ventana tendrá, al menos, un
control que permitirá cerrarla. Todo control ha de emplearse en alguna de ventana y el
mismo control puede ser empleado en distintas ventanas. De las ventanas y controles
se mantiene, también, un código y una descripción.

Los controles pueden ser de dos tipos: Botones o ítems de menú. Para soportar la
estructura jerárquica de menú pueden depender otros ítems pero no puede darse la
situación que el mismo ítem dependa de varios ítems. En los ítems de menú se ha de
mantener forzosamente el texto que se visualizará en pantalla. De los controles de tipo
de botón se mantiene el nombre del ícono que opcionalmente se visualizará.

La activación de un control tiene como consecuencia la ejecución de una única acción
(Todo control ejecutará, al menos, una acción). Una acción requiere siempre un control
que pueda ejecutarla. De las acciones se mantiene el código y la descripción.

Las acciones pueden ser de dos tipos, de función y de llamada. Las acciones de
función ejecutan una función interna del propio entorno (de la que se ha de almacenar
el nombre). Las acciones de llamada invocan una única ventana.”

#### Ejercicio 32

Realizar el Diagrama ER de acuerdo a la siguiente información

Una compañía aseguradora de tipo Sanitario desea diseñar una BD para informatizar
parte de su gestión Hospitalaria. Para esta primera etapa se obtuvo el siguiente
relevamiento:

“Los Hospitales de la red pueden ser Propios o de Terceros. De ellos se desea
almacenar su código, nombre, dirección y número de camas. Para los Hospitales
propios se almacena, además, el presupuesto y el Tipo de Servicio.
Una póliza se identifica por su número. La misma cubre a varios asegurados, los
cuales se identifican por un número correlativo añadido al número de póliza, nombre,
apellido y fecha de nacimiento.
Los asegurados cubiertos por una misma póliza pueden ser de distintas categorías.
Los asegurados de “Primera categoría” pueden ser hospitalizados en cualquier
hospital, en cambio, los asegurados de “Segunda categoría” sólo pueden ser
hospitalizados en nosocomios propios.

Interesa saber en que hospitales se han estado o están hospitalizados los asegurados,
el médico que prescribió la internación, así como las fechas de inicio y fin de la misma.
Existen áreas geográficas, identificadas por un código y de las cuales se desea
almacenar, también, su superficie y número de habitantes. Los hospitales
mercerizados tienen que estar asignados a una única área y la misma no puede
cambiar, mientras que los Hospitales propios no se encuentran asignados a ningún
área en particular.

Los médicos se identifican por una matrícula y deseamos almacenar sus nombres,
apellido, dirección y teléfono. Además, interesa saber a que área se encuentra
destinado un médico. Existe además, una dependencia jerárquica entre médicos de
forma que un médico tiene un único jefe.”
