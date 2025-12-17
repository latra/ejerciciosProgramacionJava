# Ejercicios de Programación en Java
A continuación se proponen algunos ejercicios de Java para practicar distintas partes de la programación en Java.

En el apartado de Ayuda podréis encontrar:
- El archivo de [pistas](ayuda/1.pistas.md), que contiene solo los comentarios del código para que podáis rellenar
- El archivo de [solución](ayuda/2.solucion.md), que contiene las soluciones en código Java

Como con casi todo, ¡no hay una unica forma de resolver los ejercicios!

---

## Ejercicios de Condicionales

### Ejercicio

Haz un programa **Java** que pida al usuario:

* Dos números
* Una operación: **SUMA**, **RESTA**, **DIVISION** o **MULTIPLICACION**

El programa deberá ejecutar la operación indicada y mostrar el resultado por pantalla.

* Si la operación es una **división**, asegúrate de que el segundo número **no sea cero**.
* Si el segundo número es cero, muestra un mensaje de error por pantalla.

**EJEMPLO**
```
Indica el valor número 1
> 2
Indica la operación (*, /, + o -)
> *
Indica el valor número 2
> 5
10.0
```

---

## Ejercicios de Bucles y Condicionales

### Ejercicio

Haz un programa **Java** para jugar al **Piedra, Papel o Tijera** al mejor de **X**.

* El usuario indicará a cuántas victorias se juega.
* En cada ronda, el programa pedirá a cada jugador qué opción decide.
* Tras cada ronda, se deberá indicar el ganador.
* El juego continuará hasta que uno de los jugadores alcance el número de victorias indicado inicialmente.

**EJEMPLO**
```
Indica a cuantas victorias
> 2

Jugador 1, elije: piedra, papel o tijera?
> papel
Jugador 2, elije: piedra, papel o tijera?
> papel
¡Empate!
Jugador 1, elije: piedra, papel o tijera?
> tijera
Jugador 2, elije: piedra, papel o tijera?
> piedra
¡Victoria Jugador 2!
Jugador 1, elije: piedra, papel o tijera?
> piedra
Jugador 2, elije: piedra, papel o tijera?
> tijera
¡Victoria Jugador 1!
Jugador 1, elije: piedra, papel o tijera?
> papel
Jugador 2, elije: piedra, papel o tijera?
> tijera
¡Victoria Jugador 2!
```

---

## Ejercicios de Strings, Bucles y Condicionales

### Ejercicio 1

Haz un programa **Java** en el que el usuario introduzca una frase.

El programa deberá:

* Contar cuántas palabras tiene la frase
* Mostrar el resultado por pantalla

**Restricciones:**

* Debes iterar/recorrer el `String` utilizando bucles
* Debes usar la función `indexOf`
* **No** se permite utilizar `StringTokenizer` ni métodos similares

**EJEMPLO**
```
Introduce una frase
> ¡Hola! ¿Cómo estás? Yo estoy fenomenal la verdad.
Tu frase tiene 8 palabras
```
---

### Ejercicio 2

Haz un programa **Java** en el que el usuario introduzca una lista de **tags**, separados y terminados por coma.

El programa deberá:

* Mostrar cada tag en una línea diferente

**Restricciones:**

* Debes iterar/recorrer el `String` utilizando bucles
* Debes usar las funciones `indexOf` y `substring`
* **No** se permite utilizar `StringTokenizer` ni métodos similares

**EJEMPLO**
```
Introduce la lista de la compra
> patatas,tomates,huevos,pan,colacao,
Has introducido:
patatas
tomates
huevos
pan
colacao
```
---

## Ejercicios de Clases

### Ejercicio

Crea un programa de **gestión de stock** de 🏍️ **Midnight Energy** 🌟, una empresa de bebidas energéticas que comercializa actualmente tres tipos de bebida:

* **Original**
* **NegroLoco**
* **PinkExplosion**

El programa deberá gestionar el stock de latas del almacén y permitir saber cuántas latas hay de cada tipo, así como actualizar dicho número.

---

### Clase `Almacen`

La clase `Almacen` contendrá los siguientes atributos:

* `int classicInStock` → indica el número de latas **Classic** disponibles en el almacén
* `int negroLocoInStock` → indica el número de latas **Negro Loco** disponibles en el almacén
* `int pinkExplosionInStock` → indica el número de latas **Pink Explosion** disponibles en el almacén
* `int totalCapacity` → indica el tamaño total de latas que puede almacenar el almacén (este valor **no puede modificarse**)

---

### Funciones de la clase `Almacen`

* **Constructor del almacén**
  Al crear el almacén se deberá pasar un único valor: la **capacidad total de latas**.
  Al inicio habrá **0 latas de cada tipo**.

* **`countLatas()`**
  Cuenta el número total de latas, sumando los tres tipos de latas, y devuelve el valor.

  * A esta clase solo podrán acceder los otros métodos de la clase Almacen. 

* **`addLata()`**
  Recibe dos parámetros:

  * Un `String` con el tipo de lata (`classic`, `negroloco` o `pinkexplosion`)
  * Un `int` con el número de latas a añadir

  El método deberá:

  * Comprobar si hay espacio suficiente en el almacén. Utiliza la función `countLatas()` que has definido previamente.
  * Añadir las latas si es posible
  * Devolver `true` si se han podido añadir o `false` si no ha sido posible

* **`warehouseStatus()`**
  No recibe parámetros y debe mostrar por pantalla:

  * Cuántas latas hay de cada tipo
  * El tamaño total del almacén
  * El espacio disponible, puedes utiliozar la funcion `countLatas()`
  * El porcentaje de capacidad ocupada

---

### Clase `Programa`

Por otro lado, se creará la clase `Programa`, que contendrá el método `main`.

Esta clase deberá:

* Preguntar al usuario la **capacidad del almacén**
* Crear un objeto de tipo `Almacen`
* Preguntar al usuario qué acción desea realizar:

  * Añadir latas (1) - Tras ello, solicitaremos al usuario que indique, separado por una coma, el tipo y cantidad. Es decir, por ejemplo: `classic,20` añadiría 20 latas de tipo clásico. En caso que no se hayan podido añadir, informa al usuario.
  * Revisar el estado del almacén (2)
  * Salir del programa (0)

**EJEMPLO EJECUCION COMPLETO**
```
Indica el tamaño total del almacen: 
> 20
Indica que quieres hacer: 
0 - Salir 
1 - Añadir latas
2 - Revisar el estado
> 2
=== Status del Almacen ===
Classic: 0
Negro Loco: 0
Pink Explosion: 0
Espacio disponible: 20
Uso actual: 0%
==========================

Indica que quieres hacer: 
0 - Salir 
1 - Añadir latas
2 - Revisar el estado
> 1

Indica el tipo de lata y la cantida a almacenar: 
> classic,15

Latas añadidas correctamente

Indica que quieres hacer: 
0 - Salir 
1 - Añadir latas
2 - Revisar el estado
> 1

Indica el tipo de lata y la cantida a almacenar: 
> negroloco,3

Latas añadidas correctamente

Indica que quieres hacer: 
0 - Salir 
1 - Añadir latas
2 - Revisar el estado
> 2

=== Status del Almacen ===
Classic: 15
Negro Loco: 3
Pink Explosion: 0
Espacio disponible: 2
Uso actual: 90%
==========================

Indica que quieres hacer: 
0 - Salir 
1 - Añadir latas
2 - Revisar el estado
> 1

Indica el tipo de lata y la cantida a almacenar: 
pinkexplosion,3

No se han podido añadir: almacen lleno

Indica que quieres hacer: 
0 - Salir 
1 - Añadir latas
2 - Revisar el estado
> 2

=== Status del Almacen ===
Classic: 15
Negro Loco: 3
Pink Explosion: 0
Espacio disponible: 2
Uso actual: 90%
==========================

Indica que quieres hacer: 
0 - Salir 
1 - Añadir latas
2 - Revisar el estado


```
