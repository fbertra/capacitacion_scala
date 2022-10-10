# Evaluar expresiones usando scala-cli



Instalar scala-cli:  https://scala-cli.virtuslab.org/



Arrancar scala-cli en linea de comando

```bash
$ scala-cli console --scala 2.13.6
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

**String**

````scala
val desde = "Everis"
val hasta = "NTT-Data"
println (s"Nos fuimos de ${desde} hasta ${hasta}")
````

val desde: String = Everis

val hasta: String = NTT-Data

Nos fuimos de Everis hasta NTT-Data


Concatenacion simple de String's
````scala
val concat1 = "uno" + " " + "dos"
````

val concat1: String = uno dos

Interpolacion
````scala
val i1 = 1
val i2 = 2
val d3 = 3.0
val sz4 = "4 de cuatro"

val concat2 = s"uno: $i1, dos: $i2, tres: $d3, cuatro: $sz4"
````
val i1: Int = 1

val i2: Int = 2

val d3: Double = 3.0

val sz4: String = 4 de cuatro

val concat2: String = uno: 1, dos: 2, tres: 3.0, cuatro: 4 de cuatro

Multiples metodos utiles
````scala
val frase = "Los perros aman a los gatos"

val contiene = frase.contains ("perros")

val parte = frase.substring (11, 15)
````
val frase: String = Los perros aman a los gatos

val contiene: Boolean = true

val parte: String = aman


**Boolean**

````scala
val vivimosEnChile = true
````

val vivimosEnChile: Boolean = true

````scala
val todosSomosChilenos = false
````

val todosSomosChilenos: Boolean = false

Operaciones sobre boolean's: negacion
````scala
val hayExtranjerosEnChile = ! todosSomosChilenos 
````
val hayExtranjerosEnChile: Boolean = true

Operaciones sobre boolean: AND: &&  OR: ||
````scala
val esUnaFraseSobreAmorAnimal = (frase.contains ("perro") || frase.contains ("serpiente")) && frase.contains ("ama")
````
val esUnaFraseSobreAmorAnimal: Boolean = true


**Double**

````scala
val medicion = 105.7
println (s"La medicion es igual a ${medicion}")
````

val medicion: Double = 105.7

La medicion es igual a 105.7


Operaciones sobre Double: + - / *
````scala
val medicion2 = 205.1

val promedioPonderado = (medicion * 1.2 + medicion2 * 1.3) / 2.0
````

val promedioPonderado: Double = 196.735

Comparaciones < <= > >=
````scala
val estaSubiendo = medicion2 > medicion
````
val estaSubiendo: Boolean = true



**Expresiones básicas**

**if**

````scala
val msg = if (medicion > 100.0) "es inquietante" else "todo normal"
````

val msg: String = es inquietante


**for**

````scala
for (e <- arr if e % 2 == 1) println (s"${e} es impar")
````
1 es impar

3 es impar

5 es impar

````scala
for (i <- 0 until 5) println (s"${i}")
````
0

1

2

3

4

**for - yield**

````scala
val impares = for (e <- arr if e % 2 == 1) yield e

println (impares.mkString (", "))
````

val impares: Array[Int] = Array(1, 3, 5)

1, 3, 5


**match -  case**

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



**Bloques** La ultima expresión dentro del bloque es "·retornada" como "valor del bloque"

````scala
val resultado = {
   val i = 123
   val j = i * i + 200
   j - (i * 3)
}
````
val resultado: Int = 14960

````scala
val esInferiorPromedio = if (medicion < (medicion + medicion2) / 2.0) {
  println (s"$medicion < promedio")
  true 
} else {
  println (s"$medicion >= promedio")
  false
}
````
105.7 < promedio

val esInferiorPromedio: Boolean = true


