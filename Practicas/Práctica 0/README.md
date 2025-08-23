# Práctica 0 - preliminares

## Parte 1 – Terminal de Linux | Bash Scripting

### 1. comandos de información

**a)** **`whoami`** : imprime el nombre de usuario asociado al ID de usuario efectivo   


**b)** **`uname`** : imprime cierta información del sistema (como el nombre del sistema). <br />
**`uname -a`** (--all) imprime toda la información del so.


**c)** **`id`** imprime la información de usuario y grupo para cada USUARIO especificado, o (cunado se omite el USUARIO) para cada proceso actual 


**d)** **`ps`** : reporta una instantanea de los procesos actuales (cómo el PID). Muestra info sobre una selección de procesos activos. <br />
Y **`ps -e`** selecciona todos los procesos.


**e)** **`top`** : proporciona una vista dinamica en tiempo real del sistema en funcionamiento. Puede mostrar información resumida del sistema, asi como una lista de los procesos o subprocesos actualmente gestionados por el linux kernel. <br />
Y **`top -n 10`** especifica el máximo número de iteraciones, o frames, que top debe producir antes de finalizar


### 2. inspeccionar archivos y directorios

Al trabajar en una terminal de LINUX siempre estamos trabajando dentro de un directorio, por defecto comenzamos en home. 


> **`$ pwd`** : obtiene la ruta absulta del actual directorio de trabajo


> **`$ ls`** : lista todos los archivos y6 directorios del directorio actual.

>Para ver los archivos y directorios dentro de cualquier directorio, se puede pasar el path como argumento: <br /> **`$ ls [PATH TO DIRECTORY]`**


**i.**  Al ejecutar `ls /` obtenemos una lista de los archivos y directorios que se encuentran en el directorio raiz del so.

**ii.** Para observar el contenido del directorio bin podemos escribir lo siguiente: **`ls /bin`**

> Para imprimir una lista más larga de archivos con información adicional: **`ls -l`**

**iii.** ls lista todo los directorios y archivos. Pero ls más: 

| Opción | Descripción |
|--------|-------------|
|   -a   | **-all**  no ignora las entradas o directorios que empiecen con "." |
|   -d   | **--directory** lista los directorios en si, no su contenido |
|   -h   | **--human-readable** con -l y -s, imprime el tamaño como 1K, 234M 2G etc|
|   -l   | Utiliza un formato de lista más extendida |
|   -S   | ordena según el tamaño del archivo, el más grande primero |
|   -t   | ordena por tiempo, el más reciente primero |
|   -r   | **--reverse** orden inverso al ordenar |


**iv)** **`ls -la /etc`** lista todos los archivos/subdirectorios de forma extendida, incluyendo los ocultos, que se encuentran en la carpeta /etc.

### Creando archivos y directorios

**a)**  

> `$ mkdir nuevoDirectorio` este comando se usa para crear un nuevo directorio.

Creamos un archivo llamado scripts y verificamos con ls su existencia.

**b)** 
> **`$ cd nombreDirectorio`** para cambiar el directorio de trabajo actual a otro directorio

Con esto entramos al nuevo directorio scripts. Verificamos con pwd para ver si estamos ahí. (efectivamente)

> **`$ cd`** si escribimos cd sin argumento nos devulve de regreso a HOME

> **`$ cd ..`** nos lleva al directorio padre de nuestro actual directorio de trabajo

Simbolos para navegar a paths especiales:
|**Símbolo**| **Path al que refiere**|
|-----------|------------------------|
| **~** | Directorio Home |
| **/** | Directorio Root |
| **.** | Directorio actual|
|**..**| Directorio padre|

**c)** 

> **`$ touch archivoNuevo`** sirve para crear archivos nuevos en el directorio actual de trabajo.

Creamos un archivo vacío llamado miarchivo.txt en home. Verificamos con ls (efectivamente). <br />

En caso de que el archivo ya existiese de antes, el comando **touch** actualiza el *timestamp* del último acceso o la fecha de la última modificación. Para ver esta info: <br />

```bash
$ stat miarchivo.txt`
```

### 4. Manejo de Archivos y directorios 

a) 

> **`$ find`** se usa para buscar archivos en un directorio. Se puede buscar por nombre, tipo, dueño, tamaño o timestamp. 

Este comando busca en el árbol de directorios a partir del directorio dado. Por ejemplo para encontrar todos los archivos .txt en el directorio **/etc** y todos sus subdirectorios.  

```bash
$ find /etc -name "*.txt"
```

**b)**

> **`$ rm`** este comando sirve para borrar archivos. Y con la opción **-i** pide confirmación antes de borrar nada.

Borramos mi archivo.txt: 

```bash
$ rm -i miarchivo.txt
``` 
Confirmamos con ls si se borró (efectivamente lo hizo)

**c)**

> **`rm -r`**: elimina directorios con todo su contenido. 

Creamos un directorio carpeta1, entramos a la carpeta y creamos varios archivos. 
**`$ touch a.txt b.txt x.txt d.txt`**
Volvemos al directorio de carpeta1 y la eliminamos.

```bash
rm -r carpeta1
```

**iii)** <br /> 
La diferencia entre **`rm -r`** y **`rmdir`**, es que rmdir elimina solo carpetas vaciás en cambio el otro elimina todo sin importar si esta vacia o no.

**d)** 

> **`$ mv`** se puede usar este comando para mover archivos de un directorio a otro y/o renombrarlo.

Creamos un archivo llamado `usuarios.txt` , **CUIDADO**: si movés un archivo a una carpeta donde hay otro archivo con el mismo nombre lo va a SOBREESCRIBIR. <br /> 
Podes cambiar el nombre con el mismo comando:

```bash
$ mv usuarios.txt info-user.txt
```

ahora movemos el archivo al directorio **`/tmp`**

```bash
$ mv info-user.txt /tmp
```
Con `ls` vemos que ya no esta en el directorio actual, y con **`ls -l /tmp`** vemos con màs detalle que se encuentra en el directorio **tmp**


**e)** 

> **`$ cp`** este comando sirve para copiar un archivo de un directorio a nuestro directorio actual.

```bash
$ cp /tmp/info-user.txt info-user.txt
```

### Ver y modificar permisos de acceso


