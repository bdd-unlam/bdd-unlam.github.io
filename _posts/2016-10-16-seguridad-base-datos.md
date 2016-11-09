---
layout: post
title:  "Seguridad en las Bases de Datos"
date:   2016-10-16 12:12:49 -0300
categories: apuntes seguridad
author: alf
---

## Introducción a la seguridad

La seguridad en las bases de datos está signada por varios factores. Primero, las leyes
definidas dentro del país donde se van a albergar los datos. Los cuales se ven afectados
conforme a lo almacenado como a lo que posteriormente puede ser consumido desde
nuestro almacén de datos. Estos datos, conocidos como datos sensibles de las personas,
que revelan origen racial y étnico, opiniones políticas, convicciones religiosas, filosóficas o
morales, afiliación sindical e información referente a la salud o a la vida sexual. Son los que
están amparados por el derecho de habeas data, por lo que no pueden ser almacenados sin
un fin justo y el uso de estos debe ser con fines amparados por la ética y la ley (Art. 43 Constitución Nacional Argentina).

Por otro lado, tenemos la seguridad signada por la organización donde estemos generando
este juego de datos, organización que definirá cuáles y cómo son los accesos a la
información. Sobre estos conceptos serán los que trabajaremos más profundamente.

Recordemos además, que no sólo es materia de seguridad el cuidado de la intromisión
sobre los datos, sino también el poder conservar en el tiempo los datos, aportando
durabilidad de los mismos.

### Seguridad desde el punto de vista del DBA
El administrador de la base de datos (Data Base Administrator) es quien debe determinar
que la información almacenada es la que debería ser y quien debe impedir que los ataques
maliciosos modifiquen u obtengan información de la base de datos que no debería ser
accesible.

Para lograr esto, el DBA debe
- Manejar cuentas de usuario
- Asignar privilegios a esas cuentas
- Definir niveles de seguridad

Con estas tres acciones el dba maneja las diferentes escalas de acceso al conjunto de
datos.

Para realizar estas tareas, se definió un subconjunto de instrucciones ANSI­SQL que se dió
en llamar Lenguaje de Control de Datos (en inglés: **D**ata **C**ontrol **L**anguage ­ DCL).

#### Administrar cuentas de usuario
El dba puede crear, inhabilitar o borrar un usuario.

De forma genérica, para acceder a una base de datos tenemos al usuario y al grupo al que
pertenece. Los permisos pueden asignarse a este usuario y/o al grupo al que pertenece.

Algunos Motores de bases de datos, dividen al usuario como Usuario de Acceso y usuario
de Base de datos, en lugar de usuario y grupo. Pudiendo además llamarse ambos de
distinta manera. Esto ocurre, por ejemplo en MS­SQL Server, cuando para crear un usuario
debemos hacer lo siguiente

{% highlight sql %}
CREATE LOGIN usuario WITH PASSWORD='clave'
CREATE USER mi_usuario FOR LOGIN usuario
{% endhighlight %}

Donde el “Login” es el usuario de acceso. Luego el “User” será la identidad dentro de la base
de datos.

En otras bases de datos, los usuarios se llaman “Roles”. Por ejemplo en Postgresql, cuando
debemos hacer lo siguiente

{% highlight sql %}
CREATE ROLE usuario WITH LOGIN PASSWORD 'clave' VALID UNTIL
'2013­01­01';
{% endhighlight %}

Con la particularidad que, como son Roles, los grupos también los llama roles. 
Mientras que en otros motores, como Oracle, podemos crear usuarios y roles, para
identificar a los primeros de forma puntual y los segundos de forma genérica.

{% highlight sql %}
CREATE USER usuario IDENTIFIED BY 'clave';
CREATE ROLE usuarios;
{% endhighlight %}

Para borrar usuarios, siempre podemos hacerlo mediante la instrucción DROP
Entonces, podemos definir accesos o denegarlos para un usuario o para un grupo,
aplicándolo a todos los que pertenecen a este grupo.

#### Privilegios en las bases de datos
Cada uno de los usuarios en la base de datos tiene privilegios y solo pueden operar con
esos datos cuando estén autorizados para hacerlo.

Los permisos pueden darse según

- el tipo de Acción
  - `Select`
  - `Update`
  - `Delete`
  - `Insert`
- el objeto usado
  - toda la tabla
  - Algún campo

Para analizar cómo se comportan estos permisos, analizaremos varios ejemplos.

Ejemplo 1. `Select`

{% highlight sql %}
SELECT *
FROM tabla1
{% endhighlight %}

Para que el usuario pueda ejecutar esta consulta, debería tener acceso a todos los campos
de la `tabla1`.

Ejemplo 2. `Select`

{% highlight sql %}
SELECT a, b
FROM tabla1
{% endhighlight %}

Para que el usuario pueda ejecutar esta consulta, debería tener acceso a la `tabla1` y solo los
campos de `a` y `b`.

Veamos ahora un ejemplo un poco más complejo

{% highlight sql %}
UPDATE tabla2
SET campoA = ‘b’
WHERE campoB IN
    (SELECT campo1
    FROM tabla1
    WHERE campo2 > 78)
{% endhighlight %}

Para poder realizar esta actualización, el usuario debería poder tener permisos de
actualización (`Update`) sobre el `campoA` de la `tabla2`, y de selección (`select`) sobre el
`campoB`.
Mientras que también debería tener permisos de selección (`select`) sobre los campos
`campo1` y `campo2` de la `tabla1`.

El no contar con alguno de estos privilegios haría que el usuario no pueda efectuar esta
consulta.

Ejemplo de borrado

{% highlight sql %}
DELETE FROM tabla1
WHERE campo2 NOT IN
(SELECT campoC FROM tabla2)
{% endhighlight %}

Los privilegios que debería tener el usuario para efectuar este borrado, debería ser, sobre la
`tabla1`, permisos de borrado y de selección sobre el `campo2`.
Mientras que para la `tabla2`, debería poder seleccionar sobre el `campoC`.

### Seguridad y auditoría de base de datos

Un aspecto interesante de las bases de datos es como poder hacer un seguimiento reactivo
respecto de la seguridad, manteniendo una auditoría de lo realizado por cada usuario o
grupo de usuarios en cada momento dentro de la base de datos.
Recordemos que para una base de datos, cualquier sistema que se conecta a ella es
considerado como un usuario.
Teniendo esto en cuenta, podemos decir que sería de sobrada utilidad, saber qué usuario o
sistema realiza cuál operación, con qué frecuencia, qué objetos se utilizaron de la base y si
se realizaron bloqueos sobre los mismos.

La herramienta que está a nuestra disposición para trabajar con esto es el log transaccional
de la base de datos. El cual, siempre mantiene las operaciones realizadas sobre los objetos.
Solo se debe contemplar, almacenar también quién es el usuario que realizó dicha tarea,
cuál fue la hora de inicio y cuál la de finalización. Además, guardar la sintaxis de lo realizado,
para así poder reproducirlo.

Es trabajo del DBA gestionar estas estadísticas, ponerlas a disposición y actuar en
consecuencia, para prevenir problemas en la seguridad de los datos.

Cada motor de bases de datos, cuenta con un manejo de auditoría diferente, ya que no hay
nada prefijado por un estándar para cubrir este aspecto de las bases de datos. Igualmente,
todos los motores se nutren de lo almacenado en el log transaccional.

### Seguridad y privacidad. Similitudes y diferencias
Cuando hablamos de seguridad en las bases de datos pensamos en distintos controles para
que los conjuntos de información sean usados para los fines que fueron ideados y no sean
alcanzados por quienes no deberían hacerlo. Sean personas o sistemas.

Mientras tanto, cuando pensamos en privacidad, nuestro pensamiento refiere directamente a
que parte de un conjunto de datos puede ser sensible.
Estos dos aspectos, se juntan en numerosos puntos. Sobre todo cuando cuando somos
conscientes de qué y por qué estamos dando seguridad a ciertos datos de la organización.

Por ejemplo, cuando pensamos en datos estratégicos para la organización, necesitamos
segurizarlos y darles privacidad. Que sean alcanzados por solo un conjunto de usuarios en
un momento determinado.

Estos dos conceptos se alejan cuando apuntamos la seguridad en los pilares de la
prevención de cambios en los datos, o controles de hardware, entre otros.

## Asignando y revocando permisos
Para trabajar con permisos, se definió un un lenguaje, conocido como lenguaje de control de
datos, o **DCL** por su sigla en inglés (**D**ata **C**ontrol **L**anguaje). Este lenguaje tiene tres
palabras reservadas

{% highlight sql %}
GRANT REVOKE DENY
{% endhighlight %}

De estas, `GRANT` es la que nos permite asignar permisos a un usuario o a un grupo de
usuarios, `REVOKE` es aquella que nos sirve para eliminar un permiso dado, mientras que
`DENY` sirve para denegar permisos sobre un objeto de la base de datos. Cabe destacar, que
la instrucción `DENY` no forma parte del estándar, lo cual hace que solo se incluya en algunos
motores de base de datos.

**Construcción de la línea básica para asignar permisos**

![Construcción de la línea básica para asignar permisos](/images/construccion-linea-basica-asignar-permisos.png)

**Construcción de la línea básica para revocar permisos**

![Construcción de la línea básica para revocar permisos](/images/construccion-linea-basica-revocar-permisos.png)

Veremos ahora algunos ejemplos de asignación de permisos.
Para darle permisos al usuario `BDD1` sobre la tabla `tablaEj`. Con este permiso le
permitiríamos acceder a todos los campos de dicha tabla.

{% highlight sql %}
GRANT SELECT ON tablaEj TO BDD1;
{% endhighlight %}

Mientras que si quisiéramos que solo tenga acceso a los campos `C1` y `C2` de dicha tabla

<table width='100%' border='1' style='border-collapse:collapse'>
    <tr>
        <td align='center' width='50%'>Postgresql</td>
        <td align='center' width='50%'>MS SqlServer</td>
    </tr>
    <tr>
        <td>
{% highlight sql %}
GRANT SELECT (C1, C2)
ON tablaEj TO BDD1;
{% endhighlight %}
        </td>
        <td>
{% highlight sql %}
GRANT SELECT
ON tablaEj (C1, C2) TO BDD1;
{% endhighlight %}
        </td>
    </tr>
</table>

Colocamos solo dos ejemplos de distintos motores, para que vean que el predicado, o lo
que acompaña al GRANT puede escribirse de distinta manera.

Si quisiéramos que el usuario BDD1, tenga permisos para acceder a la tabla y además
poder actualizar los datos deberíamos definir

{% highlight sql %}
GRANT SELECT, UPDATE
ON tablaEj TO BDD1;
{% endhighlight %}

Como vemos, cada acción que quisiéramos agregar para que el usuario pueda hacer, se
puede realizar haciendo la indicación de las columnas, asignando permisos sólo sobre
estas, o sin definirlas, teniendo permisos sobre todas las columnas.

Lo mismo sucede sobre que permiso estoy definiendo, puede ser de selección,
actualización, borrado, manejo de triggers, ejecución de funciones y/o procedimientos, entre
otros casos.

Veamos ahora, cómo asignarle permisos al usuario BDD1 sobre la columna C1 para hacer
un select y un permiso para hacer actualizaciones sobre la columna C2.

<table width='100%' border='1' style='border-collapse:collapse'>
    <tr>
        <td align='center' width='50%'>Postgresql</td>
        <td align='center' width='50%'>MS SqlServer</td>
    </tr>
    <tr>
        <td>
{% highlight sql %}
GRANT SELECT (C1),
UPDATE (C2)
ON tablaEj TO BDD1;
{% endhighlight %}
        </td>
        <td>
{% highlight sql %}
GRANT SELECT
ON tablaEj (C1) TO BDD1;
GRANT UPDATE
ON tablaEj (C2) TO BDD1;
{% endhighlight %}
        </td>
    </tr>
</table>

Por otro lado, si quisiéramos darle a un sistema que usa el usuario SIST1 permisos sólo
para insertar y borrar en la tabla tablaEj deberíamos hacer

{% highlight sql %}
GRANT INSERT, DELETE
ON tablaEj TO BDD1;
{% endhighlight %}

**Veremos ahora algunas revocaciones de permisos.**

Para revocarle los permisos al usuario BDD1 sobre la tabla tablaEj

{% highlight sql %}
REVOKE SELECT ON tablaEj FROM BDD1;
{% endhighlight %}

A diferencia de cuando asignamos permisos, que usamos la palabra reservada 'TO', como
diciendo darle este permiso A tal usuario, a la hora de revocar un permiso, usamos la
palabra reservada 'FROM', para indicar a qué usuario queremos removerle el permiso ya
dado.
Podemos revocar muchas veces un permiso, sin problemas a que nos de error.

Otro ejemplo que podemos ver, es si quisiéramos revocar el permiso que tenía sobre los
campos 'C1' y 'C2' de dicha tabla

<table width='100%' border='1' style='border-collapse:collapse'>
    <tr>
        <td align='center' width='50%'>Postgresql</td>
        <td align='center' width='50%'>MS SqlServer</td>
    </tr>
    <tr>
        <td>
{% highlight sql %}
REVOKE SELECT (C1, C2)
ON tablaEj FROM BDD1;
{% endhighlight %}
        </td>
        <td>
{% highlight sql %}
REVOKE SELECT
ON tablaEj (C1, C2)
FROM BDD1;
{% endhighlight %}
        </td>
    </tr>
</table>

Colocamos solo dos ejemplos de distintos motores, para que vean que el predicado, o lo
que acompaña al 'REVOKE' puede escribirse de distinta manera.

Como se ve, para revocar permisos, la estructura es similar que para asignarlos.

**Veremos ahora algunas denegaciones de permisos sobre objetos.**

En algunos motores, las instrucciones de 'DENY' o denegación explícita de permisos, no
existe. La forma de trabajar que utilizan es dar permisos en lugar de denegarlos.

Los motores tomados como ejemplo en los apartados anteriores, no nos sirven para
demostrar este caso. Postgresql no cuenta (hasta su versión 9, la última al momento de
escribir esto) con la primitiva 'DENY'. Así que reemplazaremos a Postgresql por oracle.


<table width='100%' border='1' style='border-collapse:collapse'>
    <tr>
        <td align='center' width='50%'>Oracle</td>
        <td align='center' width='50%'>MS SqlServer</td>
    </tr>
    <tr>
        <td>
{% highlight sql %}
DENY SELECT ON tablaEj
TO BDD1;
{% endhighlight %}
        </td>
        <td>
{% highlight sql %}
DENY SELECT ON tablaEj
TO BDD1;
{% endhighlight %}
        </td>
    </tr>
</table>

Insistimos en que esto es una breve muestra conceptual de la aplicación de permisos sobre
objetos. Lo cual no quiere decir que no existan otras combinaciones para aplicar en los
objetos de bases de datos.

### Aplicación de permisos en cascada

Si un usuario ha recibido algún tipo de permiso, puede asignarlo a otros usuarios, y así
sucesivamente. Lo cual hace, que se pueda crear una suerte de árbol de permisos.
Esta estructura o árbol, puede ser manejado por el primer usuario que asignó el permiso,
pudiendo revocar a la estructura que fue definida desde su nivel hacia abajo.
La forma en que se procesa esto, es mediante una sucesión de `GRANT` y luego aplicando
`REVOKE`.

En los casos que el permiso fuera asignado hacia otro usuario, el primer usuario debe usar
la palabra reservada `CASCADE` para poder revocar el permiso. Revocando a todos los que
forman parte de ese árbol que depende de ese permiso. Si no lo hace, no puede eliminar el
permiso, porque éste asignado hacia otro usuario.

Veremos ahora, breves ejemplos que nos grafican las diferentes formas de proceder a la
hora de tener estas alternativas.

![Aplicación de permisos en cascada](/images/asignacion-permisos-cascada.png)

## Seguridad Multinivel

Por ahora, hemos visto los diferentes permisos que pueden tener los usuarios respecto a
las consultas que pueden hacer sobre los diferentes objetos. Hablamos de cómo permitir y
restringir columnas (o campos) dentro de las tablas, todas las tablas, esquemas o bases de
datos. Hablaremos ahora de mecanismos para dar seguridad a la información que se
encuentra dentro de las tablas, para esto se crea la seguridad Multinivel.

Cuando empezamos a pensar en este tipo de seguridad, tenemos que considerar que cada
valor de los atributos de una instancia relación debe estar acompañado por un descriptor del
nivel de seguridad en que se encuentra ese dato.

Generalmente, los niveles de seguridad suelen estar asociados a una etiqueta (o Label en
inglés) que definirá cuan reservado es un valor de un campo en una tabla en un momento
dado. Estas etiquetas suelen ser:

![Seguridad Multinivel](/images/seguridad-multinivel.png)

Claramente, estas etiquetas son propuestas típicas. Cada solución tiene la posibilidad de
enmarcar sus propias etiquetas y su propio diseño de seguridad.

Si algo está definido en el nivel de **“confidencialidad de uso interno de la compañía”**,
todos los usuarios que tengan ese permiso o permisos superiores podrán ver esos datos,
más no podrán hacerlo aquellos que tengan un permiso público.

### Formato de Relación

Las relaciones deberán tener para cada uno de sus atributos, una etiqueta que identifique el
acceso al dato en cuestión, tupla a tupla, permitiendo así identificar quien tiene acceso a cual
dato.

**Representación de una tupla con etiquetas**

![Representación de una tupla con etiquetas](/images/representacion-tuplas-etiquetas.png)

**Ejemplos**

![Representación de una tupla con etiquetas](/images/ejemplo-representacion-tuplas-etiquetas.png)

![Representación de una tupla con etiquetas](/images/ejemplo2-representacion-tuplas-etiquetas.png)

Como vemos, el conjunto de datos siempre es el mismo, pero según los permisos del
usuario obtendrá más o menos información.

La implementación de estos esquemas depende de cada sistema gestor de bases de datos
(SGBD).

## SQL Injection: Como funciona y cómo prevenir
El método de ejecución de código SQL llamado SQL injection, o infiltración de código SQL
en castellano, refiere a la ejecución de código no deseado en base a la explotación de una
vulnerabilidad en un sistema informático.

Esto ocurre cuando el contenido de controles, tanto en sistemas escritorio o web, utilizan el
contenido generado por el usuario dentro de un control para realizar consultas a la base de
datos.

**Veamos un ejemplo**

![Ejemplo de SQL Injection](/images/ejemplo-sql-injection.png)

Como vemos, en el sistema, se tiene un cuadro de texto (o textbox) donde se pide ingresar
un valor numérico. Este valor numérico se incluye en un texto que se ejecutará en la base de
datos para obtener resultados.
Si en lugar de ponerse el valor buscado, se utiliza dicho cuadro de texto para cualquier otro
fin, se puede incurrir en graves errores de seguridad, como se plantea en el ejemplo.
Hay muchas formas de evitar esto. Algunas de ellas son

- validar todo el contenido de los cuadros de texto o lugares donde el usuario realice un
ingreso de texto,
- parametrizar los ingresos de consultas en sql,
- filtrado del ingreso, comprobando tipos de datos y utilizando transacciones.
