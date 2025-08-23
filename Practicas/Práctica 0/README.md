# Práctica 0 - preliminares

## Parte 1 – Terminal de Linux | Bash Scripting

### 1. comandos de información

**a)** **`whoami`** : imprime el nombre de usuario asociado al ID de usuario efectivo   


**b)** **`uname`** : imprime cierta información del sistema (como el nombre del sistema).
**`uname -a`** (--all) imprime toda la información del so.


**c)** **`id`** imprime la información de usuario y grupo para cada USUARIO especificado, o (cunado se omite el USUARIO) para cada proceso actual 


**d)** **`ps`** : reporta una instantanea de los procesos actuales (cómo el PID). Muestra info sobre una selección de procesos activos. 
Y **`ps -e`** selecciona todos los procesos.


**e)** **`top`** : proporciona una vista dinamica en tiempo real del sistema en funcionamiento. Puede mostrar información resumida del sistema, asi como una lista de los procesos o subprocesos actualmente gestionados por el linux kernel. 
Y **`top -n 10`** especifica el máximo número de iteraciones, o frames, que top debe producir antes de finalizar


### 2. inspeccionar archivos y directorios

Al trabajar en una terminal de LINUX siempre estamos trabajando dentro de un directorio, por defecto comenzamos en home. 


> **`$ pwd`** : obtiene la ruta absulta del actual directorio de trabajo


> **`$ ls`** : lista todos los archivos y6 directorios del directorio actual.

>Para ver los archivos y directorios dentro de cualquier directorio, se puede pasar el path como argumento:\ **`$ ls [PATH TO DIRECTORY]`**


**i.**  Al ejecutar `ls /` obtenemos una lista de los archivos y directorios que se encuentran en el directorio raiz del so.

**ii.** Para observar el contenido del directorio bin podemos escribir lo siguiente: **`ls /bin`**



