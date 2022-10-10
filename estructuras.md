# class, object, case class

Una clase define una estructura de datos y operaciones, llamadas metodos, sobre esta estructura
````scala
class Complex (real: Double, imaginary: Double) {
    val r = real
    val i = imaginary

    def add (other: Complex): Complex = new Complex (this.r + other.r, this.i + other.i)

    def + (other: Complex): Complex = this.add (other)
}

val c1 = new Complex (1.0, 0.0)
println (s"Complex: real:${c1.r} img: ${c1.i}")
val c2 = new Complex (0.0, 2.0)

val c3 = c1 + c2
````

val c1: Complex = Complex@308498a8

Complex: real:1.0 img: 0.0

val c2: Complex = Complex@358bbbe2

val c3: Complex = Complex@2ab91b65

````scala
val c1b =   new Complex (1.0, 0.0)

c1b == c1
````

val res7: Boolean = false


**No se recomienda usar clases en Scala, excepto para interoperar con las clases de Java.  Es mucho mejor usar case class**

````scala
case class Complex (r: Double, i: Double) {
    def add (other: Complex): Complex = new Complex (this.r + other.r, this.i + other.i)

    def + (other: Complex): Complex = this.add (other)
}

val c1 = Complex (1.0, 0.0)

val c1b = Complex (1.0, 0.0)

val c2 = Complex (0.0, 2.0)

val c3 = c1 + c2

val esIgual = c1 == c1b
````

val c1: Complex = Complex(1.0,0.0)

val c1b: Complex = Complex(1.0,0.0)

val c2: Complex = Complex(0.0,2.0)

val c3: Complex = Complex(1.0,2.0)

val esIgual: Boolean = true

**nota:** El compilador de Scala genera varios metodos utiles para los case class.  Como el toString () y el "==", usados en el ejemplo anterior y el copy() usado en el siguiente ejemplo.

````scala
val c4 = c1.copy (i = 20.0)
````

val c4: Complex = Complex(1.0,20.0)


Un Object es un representante unico de una clase

````scala
object complexI extends Complex (r = 0.0, i = 1.0)

complexI + c1
````

object complexI

val res10: Complex = Complex(1.0,1.0)

La tendencia actual en OOP es separar la data de la logica (o sea, no usar mas la encapsulacion).  Muchas veces, los objetos de Scala son usados para implementar funciones.

````scala
object ComplexOps {
    def sum (c1: Complex, c2: Complex) = c1.add (c2)

    def abs (c: Complex) = scala.math.sqrt (c.r * c.r + c.i * c.i)
}

import ComplexOps._

val absI = abs (complexI)

val absc1 = abs (c1)
````

val absI: Double = 1.0

val absc1: Double = 1.0
