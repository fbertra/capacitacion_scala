# mini-app: Small Files problem

La demo consiste en crear una aplicacion que concatena archivos chicos.  Suponiendo que:
- algun sistema genera un archivo por minuto,
- guarda estos archivos debajo de un directorio,
- y queremos generar un archivo por dia.

El nombre de cada archivo sigue el patron data_<AAAAMMDDHHmm>.csv, donde AAAA=año, MM: mes, DD: dia del mes, HH: hora, mm: minuto

````bash
$ ls -l data
total 0
-rw-r--r-- 1 francois francois 20 Oct 11 15:53 data_202209201000.csv
-rw-r--r-- 1 francois francois 13 Oct 11 16:32 data_202209201100.csv
-rw-r--r-- 1 francois francois 13 Oct 11 15:56 data_202209201200.csv
-rw-r--r-- 1 francois francois 27 Oct 11 15:56 data_202209211300.csv
````


Pasos

1.- Crear estructura proyecto usando una plantilla SBT,

2.- Recibir el nombre del directorio como parametro desde linea de comando, validar si es un directorio,

3.- Abrir directorio y listar los archivos,

4.- Determinar los dias distintos en la lista de archivos y asociarles los archivos correspondientes, (1)

5.- Concatenar los archivos por dia,

6.- Guardar la salida

(1) En el ejemplo anterior, hay 2 dias: 20220920 y 20220921

Para el dia 20220920, hay 3 archivos:
- data_202209201000.csv, 
- data_202209201100.csv,
- data_202209201200.csv

Para el dia 20220921, hay un solo archivo archivo: data_202209211300.csv

