# package

En aplicaciones, el codigo se implementa en varios archivos fuentes con extension ".scala".  En una aplicacion tipica, la cantidad de archivos fuentes obliga a organizarlos en grupos llamados "package", similar a como se organiza archivos en directorios.

Nota: el siguiente codigo no funciona en la consola de scala-cli

````scala
package com.nttdata.chile.capacitacion.maths

case class Complex (r: Double, i: Double)
````


````scala
package com.nttdata.chile.capacitacion

import com.nttdata.chile.capacitacion.maths._

val c1 = Complex (1.0, 2.0) 
````
