# Evaluar expresiones usando scala-cli



Instalar scala-cli:  https://scala-cli.virtuslab.org/



Arrancar scala-cli en linea de comando

```bash
$ scala-cli console
```



Algunas expresiones simples

```Scala
val i = 0
```

val i: Int = 0

```scala
i + 1
```

val res0: Int = 1



La variable i es inmutable

````scala
i = i + 1
````

|^^^^^^^^^
  |Reassignment to val i
  |
  | longer explanation available when compiling with `-explain`
1 error found



Crea un arreglo.  Un arreglo es una de las colecciones estándares de Scala

```scala
val arr = Array (1, 2, 3, 4, 5)
```

val arr: Array[Int] = Array(1, 2, 3, 4, 5)



Calcula la suma de los elementos del arreglo. 

````scala
arr.sum
````

val res1: Int = 15



Aplica una "lógica" sobre cada elemento del arreglo y crea un nuevo arreglo

````scala
val arr2 = arr.map (entero => entero * 2)
````

arr2: Array[Int] = Array(2, 4, 6, 8, 10)



Filtra elementos del arreglo

````scala
val arr3 = arr.filter (entero => entero % 2 == 1)
````

val arr3: Array[Int] = Array(1, 3, 5)



Encadena la ejecución de los métodos.  Por ejemplo, obtiene la cantidad de elementos impares.

````scala
arr.filter (entero => entero % 2 == 1).size
````

val res2: Int = 3



````
val arr4 = arr.filter (entero => entero % 2 == 1).map (entero => entero * 2)
````

val arr4: Array[Int] = Array(2, 6, 10)



**Tipos de datos básicos** 

String

````scala
val desde = "Everis"
val hasta = "NTT-Data"
println (s"Nos fuimos de ${desde} hasta ${hasta}")
````

val desde: String = Everis

val hasta: String = NTT-Data

Nos fuimos de Everis hasta NTT-Data



Boolean

````scala
val vivimosEnChile = true
````

val vivimosEnChile: Boolean = true

````scala
val todosSomosChilenos = false
````

val todosSomosChilenos: Boolean = false



Double

````scala
val medicion = 105.7
println (s"La medicion es igual a ${medicion}")
````

val medicion: Double = 105.7

La medicion es igual a 105.7



**Expresiones básicas**

if

````scala
val msg = if (medicion > 100.0) "es inquietante" else "todo normal"
````

val msg: String = es inquietante



for

````scala
for (e <- arr if e % 2 == 1) println (s"${e} es impar")
````

1 es impar
3 es impar
5 es impar



for - yield

````scala
val impares = for (e <- arr if e % 2 == 1) yield e

println (impares.mkString (", "))
````

val impares: Array[Int] = Array(1, 3, 5)

1, 3, 5



match -  case

````
val moneda = "EUR"

val region = moneda match {
  case "USD" => "America del norte"
  case "CLP" => "Amercia del sur"
  case "EUR" => "Europa"
  case _ => "Resto del mundo"
}
````

val moneda: String = EUR

val region: String = Europa



Bloques.  La ultima expresión dentro del bloque es "·retornada" como "valor del bloque"

````scala
val resultado = {
   val i = 123
   val j = i * i + 200
   j - (i * 3)
}
````

val resultado: Int = 14960