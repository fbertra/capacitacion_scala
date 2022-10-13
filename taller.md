# Taller 

Hands-on desarrollo [mini-app](mini-app.md) con:

- build tools (sbt)
- IDE: VSCode + Metals

Prerequisitos:

- Instalar SBT: https://www.scala-sbt.org/download.html
- Instalar VS-Code: https://code.visualstudio.com/download
- Instalar extension Metals para VS-Code: https://scalameta.org/metals/docs/editors/vscode

# Iniciar un proyecto

```bash
$ cd <algun directorio>
$ mkdir taller-scala
$ cd taller-scala/
$ sbt new scala/hello-world.g8
```

```
name [Hello World template]: junta_archivos
```

```bash
$ cd junta_archivos
.../junta_archivos$ sbt run
.../junta_archivos$ code .
```

Abrir build.sbt, cambiar nombre proyecto, organizacion y comentarios

Abrir src / main / scala / Main.scala

Ejecutar en VS-Code