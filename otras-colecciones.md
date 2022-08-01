# Otras colecciones



**Listas**

````
val monedas = "EUR" :: "CLP" :: "USD" :: Nil

monedas.head
monedas.tail
````

val monedas: List[String] = List(EUR, CLP, USD)

val res0: String = EUR

val res1: List[String] = List(CLP, USD)



**Mapas**

````scala
val moneda_region = Map ("EUR"-> "Europa", "USD" -> "America del Norte", "CLP" -> "America del Sur")
````

val moneda_region: Map[String, String] = Map(EUR -> Europa, USD -> America del Norte, CLP -> America del Sur)



**Opciones (manejo valores nulos o no definidos)**

CLP existe en el mapa anterior, moneda_region.get lo retorna

````scala
val region_clp = moneda_region.get ("CLP")
````

val region_clp: Option[String] = **Some**(America del Sur)

````scala
val region_not_found = moneda_region.get ("XYZ")
````

val region_not_found: Option[String] = **None**

````
val region = moneda_region.get ("XYZ").getOrElse ("no encontrada")
````

val region: **String** = no encontrada

