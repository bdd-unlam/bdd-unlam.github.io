---
layout: practica
title:  "Práctica de Ejercicios Transacciones"
date:   2017-09-03 20:22:49 -0300
categories: practica transacciones
---

#### Ejercicio 1

Dadas las siguientes transacciones, resuelva

| Transacción 1 | Transacción 2 | Transacción 3 | Transacción 4 |
| :-: | :-: | :-: | :-: |
| | | | LL(A) |
| LE(B) | | | |
| LI(B) | | | |
| | | LL(C) | |
| | | LL(B) | |
| | | LI(B) | |
| | | LI(C) | |
| | | | LI(A) |
| | LE(B) | | |
| | LL(A) | | |
| | LI(A) | | |
| | LI(B) | | |
| | | | LE(B) |
| | | | LI(B) |
| LL(A) | | | |
| LI(A) | | | |

Realice el Grafo de Precedencia. Indique si la planificación es serializable. Justifique.

Nota: 

* ``LL`` Bloqueo de Lectura.
* ``LE`` Bloqueo de Escritura.
* ``LI`` Liberación del recurso.

#### Ejercicio 2

Suponga la siguiente ejecución entrelazada de ``T1`` y ``T2`` sobre el ítem ``A``:

| Transacción 1 | Transacción 2 |
|:-------------:|:-------------:|
| LE(A) |  |
|  | LE(A) |
| A:=A+1 |  |
|  | A:=A+1 |
|  | LI(A) |
| LI(A) |  |

Indique que fenómeno se da en la ejecución anterior. Justifique.
 
Nota: 

* ``LL`` Bloqueo de Lectura.
* ``LE`` Bloqueo de Escritura.
* ``LI`` Liberación del recurso.

#### Ejercicio 3

Indique si la siguiente ejecución es correcta. Justifique respuesta.

| Transacción 1 | Transacción 2 |
|:-------------:|:---------------:|
|  | SUMA = 0 |
| LE(A) |  |
| A = A – 50 |  |
| LI(A) |  |
|  | LL(A) |
|  | LL(B) |
|  | SUMA = SUMA + A |
|  | SUMA = SUMA + B |
|  | LI(A) |
|  | LI(B) |
| LE(B) |  |
| B = B + 50 |  |
| LI(B) |  |

Nota: 

* ``LL`` Bloqueo de Lectura.
* ``LE`` Bloqueo de Escritura.
* ``LI`` Liberación del recurso.

#### Ejercicio 4

Dada la siguiente ejecución entrelazada, indique si es serializable o no. Justificar

| Transacción 1 | Transacción 2 | Transacción 3 |
|:-------------:|:-------------:|:-------------:|
| LL(E) |  |  |
|  |  | LL(E) |
| LE(D) |  |  |
| LI(E) |  |  |
| LI(D) |  |  |
|  |  | LE(F) |
|  |  | LI(F) |
|  | LL(F) |  |
|  |  | LI(E) |
|  |  | LE(D) |
| LI(D) |  |  |
|  | LE(E) |  |
|  | LI(F) |  |
|  | LI(E) |  |
|  |  | LI(D) |

Nota: 

* ``LL`` Bloqueo de Lectura.
* ``LE`` Bloqueo de Escritura.
* ``LI`` Liberación del recurso.
