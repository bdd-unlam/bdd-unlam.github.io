---
layout: practica
title:  "Práctica de Ejercicios Optimización de Consultas"
date:   2017-09-03 18:26:49 -0300
categories: practicas optimizacion-consultas
---
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

Referencias:

* <b>Clave Primaria​</b>, 
* <u>Clave Foránea</u>, 
* <b><u>Clave Primaria y Foránea al mismo tiempo</u></b>

#### Ejercicio 1

Dada la siguiente base de datos:

<pre>
BANCO	(<b>id</b>, nombre, país)                          200 Tuplas
CUENTA	(monto, <b><u>idBanco</u></b>, <b><u>idMoneda</u></b>, <b><u>idPersona</u></b>)     5.000 Tuplas
MONEDA	(<b>id</b>, descripción, valorOro, valorPetroleo)   20 Tuplas
OPERA	(<b><u>idBanco</u></b>, <b><u>idMoneda</u></b>, cambioComp, cambioVta)  600 Tuplas
PAÍS 	(<b>id</b>, nombre)                                  8 Tuplas
PERSONA	(<b>pasaporte</b>, codigofiscal, nombre, país) 300.000 Tuplas
</pre>

Para las siguientes consultas consultas, arme el árbol canónico y luego busque optimizar. 

1. 
    ```sql
    SELECT b.nombre, m.descripcion, p.nombre
    FROM banco b, moneda m, opera o, país p
    WHERE b.id = o.idbanco AND b.pais = p.id AND o.idmoneda=m.id
    AND o.cambioComp > 4.5 AND m.descripcion LIKE 'dolar%'
    AND p.nombre IN ('ARG', 'URU', 'BRA')
    ```

1. 
    ```sql
    SELECT  p.nombre, pp.pasaporte, pp.nombre, c.monto, b.nombre
    FROM pais p, persona pp, cuenta c, banco b
    WHERE b.id = c.idbanco AND p.nombre = 'ARG' AND pp.pais = p.id
    AND c.idpersona = p.pasaporte AND p.pasaporte BETWEEN 15.000.00 AND 30.000.000
    ```

1. 
    ```sql
    SELECT c.monto, b.nombre, p.nombre, pp.pasaporte, pp.nombre
    FROM pais p, persona pp, cuenta c, banco b
    WHERE b.id = c.idbanco AND p.nombre = 'ARG' AND pp.pais = p.id
    AND c.idpersona=p.pasaporte AND p.pasaporte BETWEEN 11.000.00 AND 45.000.000
    ```
 
1. 
    ```sql
    SELECT b.nombre, m.descripcion, p.nombre
    FROM banco b, moneda m, opera o, país p
    WHERE b.id = o.idbanco AND b.pais = p.id AND o.idmoneda = m.id
    AND o.cambioComp > 4.5 AND m.descripcion LIKE 'dolar%'
    AND p.nombre IN ('FRANCIA', 'UCRANIA', 'BRASIL')
    ```

#### Ejercicio 2

Dada la siguiente base de datos:

<pre>
Cliente     (<b>idCliente</b>, nombre, mail)           200 Tuplas
Venta       (<b><u>idCliente</u></b>, <b><u>idTorta</u></b>, fecha)        5000 Tuplas
Torta       (<b>idTorta</b>, nombre, precio)             5 Tuplas
Receta      (<b><u>idTorta</u></b>, <b><u>idIngrediente</u></b>, cantidad)   75 Tuplas
Ingrediente (<b>idIngrediente</b>, descripcion, peso)   10 Tuplas
</pre>

Para las siguientes consultas consultas, arme el árbol canónico y luego busque optimizar. 

1. 
    ```sql
    SELECT c.nombre, c.mail
    FROM cliente c JOIN venta v ON c.id_cliente = v.id_cliente
    JOIN torta t ON t.id_torta = v.idTorta JOIN receta r ON t.id_torta = r.id_torta
    JOIN ingrediente i ON i.idIngrediente = r.idIngrediente
    WHERE i.descripcion = 'Chocolate'
    AND v.fecha BETWEEN '01/01/2011' AND '31/12/2011';
    ```
 
1. 
    ```sql
    SELECT c.nombre, c.mail
    FROM venta v, torta t, receta r, ingrediente i
    WHERE v.id_torta = t.id_torta AND r.id_torta = t.id_torta
    AND r.idIngrediente = i.idIngrediente
    AND v.fecha > '12/01/2007'
    AND t.precio IN (5, 10, 15)
    AND i.peso = 55;
    ```

#### Ejercicio 3

Dada la siguiente base de datos:

<pre>
Sandwich     (<b>id</b>, nombre, precio)                      50 Tuplas
Proveedor    (<b>nro</b>, razonSocial, tel, dir, codProv)    200 Tuplas
Provincia    (<b>cod</b>, descripción)                        20 Tuplas
Ingrediente  (<b>cod</b>, nombre)                            100 Tuplas
CompuestoPor (<b><u>sandwichId</u></b>, <b><u>ingredienteCod</u></b>)            4000 Tuplas
Provee       (<b><u>ingredienteCod</u></b>, <b><u>proveedorNro</u></b>, precio) 18000 Tuplas
</pre>

Para las siguientes consultas consultas, arme el árbol canónico y luego busque optimizar. 

1. 
    ```sql
    SELECT s.nombre, i.nombre, p.razon_social
    FROM Provee pe, compuestoPor cp, Proveedor p, Sandwich s, ingrediente i
    WHERE pe.proveedor_nro=p.nro 
    AND p.telefono > 5000000 
    AND pe.ingredienteCod = i.cod 
    AND i.nombre = 'tomate' 
    AND cp.ingredienteCod = pe.ingredienteCod 
    AND cp.sandwichId = s.id and s.precio < pe.precio
    ```

1. 
    ```sql
    SELECT p.razon_social, i.nombre, p.dirección, pr.descripcion
    FROM ingrediente i NATURAL JOIN proveedor p NATURAL JOIN provee pe NATURAL JOIN provincia pr
    WHERE i.cod = pe.ingredienteCod AND pe.proveedorNro = p.cod AND p.codProv = pr.cod
    AND pe.precio IN (10, 20)
    ```

#### Ejercicio 4

Dada la siguiente base de datos:

<pre>
Chofer   (<b>Legajo</b>(8), NyA(18), FechaNac(8),Dir(24), Loc(20), Tel(16), Sueldo(6)) 330 Tuplas
Vehículo (<b>Patente</b>(8), Marca(16), Modelo(20), Año(4))                            160 Tuplas 
Asignado (<b><u>Legajo</u></b>(8), <b><u>Patente</u></b>(8), FechaDesde(8), FechaHasta(8))                 1200 Tuplas
</pre>

Para las siguientes consultas consultas, arme el árbol canónico y luego busque optimizar.

1. 
    ```sql
    SELECT C.Legajo, C.Sueldo, V.Patente, A.FechaDesde, A.FechaHasta
    FROM Chofer C, Vehículo V, Asignado A
    WHERE C.legajo = A.legajo AND V.Patente = A.Patente 
    AND C.Localidad NOT IN ('Laferrere') AND C.sueldo = 4500
    ```

1. 
    ```sql
    SELECT c.legajo, NyA, v.Marca, v1.Marca
    FROM Chofer C, Vehículo V, Asignado A, Asignado B, Vehículo V1
    WHERE C.legajo = A.legajo AND V.Patente = A.Patente 
    AND C.legajo = B.legajo AND V1.Patente = B.patente 
    AND V.patente != V1.patente
    ```

#### Ejercicio 5

Dada la siguiente base de datos:

<pre>
Cliente (<b>codCli</b>(4), nomCli(32), tel(12), fecAlta(8), ciudad(18)) 1800 Tuplas
Factura (<b>tipoFac</b>(1), <b>nroFac</b>(6), <u>codCli</u>(4), fechaEmision(8), fechaVto(8), importe(6), <u>nroSuc</u>(3), <u>nroVend</u>(4)) 6000 Tuplas
</pre>

Para las siguientes consultas consultas, arme el árbol canónico y luego  busque optimizar.

1. 
    ```sql
    SELECT *
    FROM   Factura
    WHERE  (tipoFac = 'A' AND importe > 100 )
    OR     (tipoFac = 'B' AND nroSuc = 5 )
    ```

1. 
    ```sql
    SELECT c.codCli, c.nomCli, c.tel, f.fechaEmision, f.importe
    FROM   Factura f INNER JOIN Cliente c ON f.codCli = c.codCli
    WHERE  f.nroSuc IN (4, 6, 7)
    ```

#### Ejercicio 6

<pre>
ALUMNO  (<b>dni</b>, nombre, apellido, fecha_nac, teléfono, email)
MATERIA (<b>cod</b>, descripcion, <u>codCarrera</u>)
CURSA   (<b><u>dniAlumno</u></b>, <b><u>codMat</u></b>, <b><u>nroAula</u></b>, <b>anioLectivo</b>)
AULA    (<b>nro</b>, capacidadMaxima, <u>codSector</u>)
</pre>

>Nota: La tabla ``Alumno`` ocupa 100 bloques. La tabla ``Materia`` ocupa 6 bloques. La tabla ``Cursa`` ocupa 30 bloques.
La tabla ``Aula`` ocupa 9 bloques.
 
Se pide: Para la siguiente consulta SQL, armar el árbol optimizado. Justifique el orden elegido para las juntas.

```sql
SELECT  alu.dni, alu.apellido, aul.*, mat.descripcion
FROM    Alumno alu, Cursa cur, Aula aul, Materia mat
WHERE   p.id_proy = a.id_proy
AND     a.legajo = e.legajo
AND     a.cod_cargo = c.cod_cargo
AND     a.fecha_desde >= '01-01-2013'
AND     c.cod_categoria > 3
```

#### Ejercicio 7

Dada la relación <code>R ( <b>a</b>(4), b(12),  c(4) )</code> y la siguiente fórmula de Costo de Escritura:

$$
\mathsf{ {Costo Escritura} = \frac{1}{32} \times (1 + T_R) } 
$$

Se pide:

Indique a cuál de las siguientes consultas SQL corresponde la fórmula dada.
 
1. 
    ```sql
    SELECT a, b FROM R WHERE a = 10 AND c > 50
    ```
1. 
    ```sql
    SELECT * FROM R WHERE a > 10 OR c > 50
    ```
1. 
    ```sql
    SELECT a, c FROM R WHERE a = 10 OR c > 50
    ```
1. 
    ```sql
    SELECT b FROM R WHERE a > 10 AND c > 50
    ```
 
Tamaño del bloque = 128 bytes

>Nota: Los valores que se muestran entre paréntesis, junto a cada atributo de la relación, indican su tamaño en bytes.

#### Ejercicio 8

Dada la siguiente fórmula de Costo Total (inputs + outputs):

$$
\mathsf{ {Costo Total} = B_R + \frac{T_R}{2 \times V(B,R) \times FB_R} + B_S + \frac{B_R}{2 \times V(B,R)} + \frac{B_R}{2 \times V(B,R)} } 
$$

Sabiendo que:

* No hay índices
* <code>B<sub>S</sub></code> < Memoria < <code>B<sub>R</sub></code>
* <code>R ( <u>A</u> , B,  <u>C</u> )</code>   y   <code>S ( <u>C</u> , E)</code>
 
Se pide: Indique a cuál de las siguientes consultas SQL corresponde la fórmula dada.
 
1. 
    ```sql
    SELECT * FROM R, S WHERE R.C = S.C AND R.A = 100 AND R.B = 200
    ```

1. 
    ```sql
    SELECT S.* FROM R, S WHERE R.C = S.C AND R.A = 100 OR R.B = 200
    ```

1. 
    ```sql
    SELECT R.* FROM R, S WHERE R.C = S.C AND R.A = 100 OR R.B > 200
    ```

1. 
    ```sql
    SELECT S.* FROM R, S WHERE R.C = S.C AND R.A = 100 AND R.B > 200
    ```

1. 
    ```sql
    SELECT R.* FROM R, S WHERE R.C = S.C AND R.A > 100 AND R.B = 200
    ```

#### Ejercicio 9

Dada la siguiente base de datos:

<pre>
Empleado(<b>codEmp</b>(8), nombre(24), Sueldo(4), jobCode(5), sexo(1), tel(14), fechaNacimiento(8) )
</pre>

Sabiendo: 

* ``Te = 6500 tuplas``
* ``V(job_code, e) = 40``
* ``V(fecha_nacimiento, e) = 450``
* ``V(sueldo,e) = 10``
* Índice No Cluster en ``e.job_code``.
* Índice Cluster en ``e.fecha_nacimiento``.
* Índice No Cluster en ``sueldo``.
* Tamaño del bloque = 1000 bytes
* Memoria = 2 bloques

y la siguiente consulta:  

```sql
SELECT e.*
FROM Empleado e
WHERE (e.job_code IN ('12112', '45505')) 
AND (e.fecha_nacimiento > '1978-01-01' OR e.Sueldo = 1500)
```

Indique y justifique cuál es el menor costo válido para la respectiva consulta:
 
1. 434
1. 22
1. 867
1. 163
1. 326

#### Ejercicio 10

Dada la siguiente base de datos:

<pre>
GaleríaDeArte (<b>id</b>, nombre, disponible, calle, nro, localidad) 100 Tuplas
Obra          (<b>id</b>, nombre, material, <u>idTipo</u>, <u>idAutor</u>)        1000 Tuplas
TipoDeObra    (<b>id</b>, descripción)                                10 Tuplas
Temática      (<b>id</b>, descripción)                                10 Tuplas
Exposición    (<u>idGaleria</u>, <b><u>idObra</u></b>, <b><u>idTematica</u></b>, <b>fecha</b>, sala)   5500 Tuplas
Autor         (<b>id</b>, nya, fech_nacimiento)                       50 Tuplas
</pre>

Para las siguiente consulta arme el árbol canónico y luego optimise teniendo en cuenta el MR planteado en el ejercicio anterior. Indicar además el tamaño en bloques de cada tabla para justificar el árbol Optimizado.

```sql
SELECT O.nombre, A.nya, T.descripcion, E.fecha, TO.descripcion
FROM exposicion E, tematica T, autor A, tipoDeObra TO, obra O
WHERE T.id = E.id_tematica AND A.id = E.id_autor 
AND TO.id = O.id_tipo AND O.id = E.id_obra 
AND T.descripcion = 'ABSTRACTO' AND A.nya = 'PIET MONDRIAN'
```