# Fundamentos de Linux

## Objetivo
Desarrollar habilidades en el uso de comandos básicos del sistema operativo (SO) Linux para su aplicación en el análisis bioinformático del gen _16S rRNA_, orientado a la identificación taxonómica de bacterias de interés ecológico a partir de distintas muestras fecales.

## Que es linux

Un SO es un conjunto de órdenes y programas que controlan los procesos básicos de una computadora y permiten el funcionamiento de otros programas.

Linux es un SO diseñado por cientos de programadores de todo el planeta. El principal responsable del proyecto es [Linus Tovalds](https://www.cisinformatica.cat/es/quien-es-linus-torvalds-el-padre-de-linux/).

Su principal objetivo es impulsar el software de libre distribución junto con su código fuente para que pueda ser modificado por cualquier persona.

## Línea de tiempo de los SO

<p align="center">  
  <img src="Figuras/TimelineOS.jpg? raw=true" alt="shell" width="1000" height="600">
</p>

Breve historia de los **[SO](https://techsnap.tv/operating-systems/a-brief-history-of-operating-systems/)**

## ¿Por qué usar Linux y no Windows?

| Ventajas de usar Windows                 | Ventajas de usar Linux                                                     |
|------------------------------------------|----------------------------------------------------------------------------|
| 1. Es fácil de Usar                      | 1. Software de libre distribución                                          |
| 2. Amplio catálogo de software comercial | 2. Aprovechamiento de hardware                                             |
| 3. Compatibilidad de hardware            | 3. Es seguro y fiable                                                      |
|                                          | 4. Completamente personalizable                                            |
|                                          | 5. Modular                                                                 |
|                                          | 6. Su desarrollo es independiente a los intereses de grandes corporaciones |
|                                          | 7. Multitarea y multiusuario                                               |
|                                          | 8. Administrador                                                           |


<p align="center">  
  <img src="Figuras/LinuxVsWindows.png? raw=true" alt="shell" width="1000" height="600">
</p>

## Hardware y software

Hardware: Conjunto de elementos físicos o materiales que constituyen una computadora.

Software: Programas para realizar determinadas tareas

<p align="center">  
  <img src="Figuras/HardwareSoftware.jpg? raw=true" alt="shell" width="1000" height="600">
</p>

## Kernel

El **[kernel](https://linuxsimply.com/what-is-kernel/)** es el componente de software encargado de controlar la computadora (hardware).

Controla el acceso a cada recurso (memoria, CPU, disco duro, tarjeta de vídeo).

Ordena el acceso a la(s) CPU(s) de los programas.

<p align="center">  
  <img src="Figuras/Kernel.png? raw=true" alt="shell" width="500" height="600">
</p>

<p align="center">  
  <img src="Figuras/HardwareSoftware2.png? raw=true" alt="shell" width="1000" height="600">
</p>

## Shell

El Shell permite interactuar con el sistema (vía el kernel).

Lee los comandos tecleados por el usuario y los ejecuta.
  
El shell puede servir como base para escribir scripts (tareas más complejas).

Existen varios Shell disponibles (lista no exhaustiva): 

* Bourne shell (sh)
* Korn shell (ksh)
* C shell (csh)
* Bash shell (bash)
* Z shell (zsh) 

<p align="center">  
  <img src="Figuras/shell.png? raw=true" alt="shell" width="1000" height="400">
</p>

## Las responsabilidades de shell

<p align="center">  
  <img src="Figuras/ActividadesShell.png? raw=true" alt="shell" width="1000" height="600">
</p>

## bash

Bash es amigable.

Las flechas ↑ y ↓ permiten navegar dentro del historial de los comandos.

La tecla ”tabulador” [TAB] permite auto-completar los nombres de los archivos y/o comandos.

Gestión de jobs en segundo plano (background).

Posibilidad de definir alias.

## Sistema de archivos

El sistema de archivos representa el método con el cual el sistema operativo organiza los datos. 

Incluye los archivos, y tambien los directorios ( o carpetas)

El referencial de todo el sistema de archivo de una máquina es el caracter **“/"**

<p align="center">  
  <img src="Figuras/EstructuraLinux.png? raw=true" alt="shell" width="1000" height="600">
</p>

## Tengo una PC que corre windows, ¿cómo puedo correr Linux en mi máquina? 

1. Puedes instalar Linux en una nueva partición (Lo más recomendable). descargas gratuitas de distribuciones desde:
   
=> 1. **[Ubuntu 22.04.1 LTS](https://ubuntu.com/download/desktop)**

=> 2. **[Centos](https://www.centos.org/download/)**

=> 3. **[Fedora](http://fedoraproject.org/es/)**


<p align="center">  
  <img src="Figuras/DistribucionesLinux.png? raw=true" alt="shell" width="600" height="600">
</p>

2. Puedes instalar **[MobaXterm](https://mobaxterm.mobatek.net/download.html)**, que proporciona una terminal para Windows con un servidor de ambiente gráfico X11, un cliente SSH para establecer sesiones remotas seguras con un servidor, diversas herramientas de red y más. 

<p align="center">  
  <img src="Figuras/MobaxTermn.png? raw=true" alt="shell" width="800" height="800">
</p>

## Uso de MobaXterm para establecer sesiones remotas a un servidor vía protocolo SSH

Para establecer una conexión remota vía SSH elige el protocol SSH (secure shell) y usa la IP, usuario y contraseña indicados en el taller

SSH es un protocolo que permite conectarse de forma segura a otro computador o servidor a través de una red (normalmente internet) para ejecutar comandos, transferir archivos o administrar sistemas de forma remota.

<p align="center">  
  <img src="https://github.com/Martinez-Gregorio-Hector/AnalisisGenomico-EcologiaFESIztacala/blob/main/Unidad1/Figuras/MobaXterm_Conexion.png? raw=true" alt="shell" >
</p>

Una vez establecida la sesión remota al servidor, estarán trabajando en él!

● El panel mostrado a la izquierda les sirve para navegar el sistema remoto,pero lo haremos desde la línea de comandos que nos ofrece la terminal (área negra).

● Pueden abrir más pestañas en la terminal. Estas serán sesiones locales (si no hacen ssh).


<p align="center">  
  <img src="https://github.com/Martinez-Gregorio-Hector/AnalisisGenomico-EcologiaFESIztacala/blob/main/Unidad1/Figuras/MobaXterm_2.png? raw=true" alt="shell" >
</p>

## Otras opciones

=> 1. Usar la terminal en entorno de Windows 10. Acceder a la terminal y comunicarnos con el servidor.

=> 2. Usar Rstudio, en la pestaña tools, seleccionar terminal. Acceder y comunicarnos con el servidor. (Opción más práctica del curso).

Usaremos el servidor del lab13 de la UBIMED de la FES Iztacala. $${\color{red}NOTA \space IMPORTANTE: \space no \space acceder \space después \space del \space curso}$$


El servidor es una máquina con 8 núcleos y 16G de RAM.

Esta máquina cuenta con los programas que se usarán en el curso.

## Tipos de Shell

<p align="center">  
  <img src="Figuras/LocalRemota.jpg? raw=true" alt="shell" width="1000" height="600">
</p>

## Terminal
<p align="center">  
  <img src="Figuras/shell2.jpg? raw=true" alt="shell" width="1000" height="600">
</p>

## Conexión remota

**ssh user@host**

ssh lab13@132.248.216.138

ssh hectormartinez@132.248.216.138

ssh felipevaca@132.248.216.138

ssh claraestela@132.248.216.138

ssh emiliocordoba@132.248.216.138

Vamos a acceder al servidor con la siguiente dirección **ip**

```
ssh lab13@132.248.216.138
```

Una vez que accedemos al servidor nos dirigimos a la carpeta de Ecologia2026

```
cd Documents/Ecologia2026
```
## Introducción a línea de comandos

```
command [-flag(s)] [-option(s)] [value] [argument(s)]
```

<p align="center">  
  <img src="Figuras/bash-cheat-sheet.webp? raw=true" alt="shell" width="800" height="600">
</p>


## ¿Dónde encuentro una descripción básica de los comandos disponibles? 


* En Wikipedia: **[Linux commands](http://en.wikibooks.org/wiki/Linux_Guide/Linux_commands)** y **[List of Unix programs](http://en.wikipedia.org/wiki/List_of_Unix_programs)**


* Un sencillo tutorial (caps 1-5): **[Unix](http://www.ee.surrey.ac.uk/Teaching/Unix/)**

* **[intro2linux](https://vinuesa.github.io/intro2linux/index.html)**

## comando cd

el comando **cd** (change directory) se usa para mover la sesión de shell a otro directorio del sistema de archivos de Linux. La sintaxis del comando cd es bastante simple: **cd destino**. El comando **cd** puede tener un solo parámetro, destino, que especifica el nombre del directorio al que se desea acceder. Si no se especifica un destino en el comando cd, lo llevará a su directorio personal.

```
cd
cd /home/lab13/Documents/Ecologia2026
```

El parámetro de destino se puede expresar mediante dos métodos diferentes. Un método utiliza una **ruta absoluta** o una **ruta relativa** al directorio.

<p align="center">  
  <img src="Figuras/Rutas.jpg? raw=true" alt="shell" width="600" height="600">
</p>

Supongamos que estoy en el directorio **dir_001** y quiero dirigirme a **dir_002**, se puede hacer de dos maneras, siguiento una **ruta absoluta** o una **ruta relativa**

```
## Ruta absoluta
cd /home/filogenomica/dir_002
## Ruta relativa
cd ../dir_002
```
Para nuestra actividad vamos a trabajar en el directorio de Ecologia2026, si todavía no estás en la carpeta puedes utilizar la siguiente **ruta absoluta** para que puedas llegar al directorio

```
cd /home/lab13/Documents/Ecologia2026
```

## comando pwd 

El comando **pwd** (print work directory) muestra la ubicación del directorio actual de la sesión de shell

```
pwd
## /home/lab13/Documents/Ecologia2026
```

## comando ls

El comando **ls** en su forma más básica muestra los archivos y directorios ubicados en su directorio actual. Ten en cuenta que el comando **ls** genera la lista en orden alfabético (en filas en lugar de columnas).

```
ls

## Alumnos  Equipo01  Equipo02  Equipo03  Equipo04  Equipo05
## Equipo06  Equipo07  Equipo08  Equipo09  Equipo10
```

El comando **ls** puede combinar con opciones, para ver esas opciones se corre **ls** con **help**

```
ls --help

## -a list all (lista archivo ocultos tipo .directorio o .archivo)
## -l long format (muestra permisos y otros atributos como usuario, grupo, tamaño del archivo y fecha de modificación)
## -t time sort (ordena por tiempo)
## -r reverse sort
## -R list subdirectories recursively
## -S size sort (ordena por tamaño)
## -h human readable (indica Kb, Mb, Gb …)
## etc ...
```

En los listados básicos, el comando **ls** no genera mucha información sobre cada archivo. Para obtener información adicional, otro parámetro popular es **-l**. El parámetro **-l** genera un formato de listado largo, que proporciona más información sobre cada archivo del directorio.

```
ls -lh

## drwxr-xr-x. 2 lab13 lab13 6 Apr 22 22:16 Alumnos
## drwxr-xr-x. 2 lab13 lab13 6 Apr 22 22:16 Equipo01
## drwxr-xr-x. 2 lab13 lab13 6 Apr 22 22:16 Equipo02
## drwxr-xr-x. 2 lab13 lab13 6 Apr 22 22:16 Equipo03
## drwxr-xr-x. 2 lab13 lab13 6 Apr 22 22:16 Equipo04
## drwxr-xr-x. 2 lab13 lab13 6 Apr 22 22:16 Equipo05
## drwxr-xr-x. 2 lab13 lab13 6 Apr 22 22:16 Equipo06
## drwxr-xr-x. 2 lab13 lab13 6 Apr 22 22:16 Equipo07
## drwxr-xr-x. 2 lab13 lab13 6 Apr 22 22:16 Equipo08
## drwxr-xr-x. 2 lab13 lab13 6 Apr 22 22:16 Equipo09
## drwxr-xr-x. 2 lab13 lab13 6 Apr 22 22:16 Equipo10
```

Vamos a entrar en la carpeta de **Alumnos**. Recuerden para entrar a la carpeta utilizamos el comando **cd**

```
cd Alumnos
```


## comando mkdir

Dentro de la carpeta Alumnos vamos a crear un directorio con nuestro nombre con el comando **mkdir**, por ejemplo, mi nombre es Hector Martinez, voy a crear un directorio con el nombre de HectorMartinez.

Algunas recomendaciones para nombrar directorio o archivos:

* Nombra todos tus archivos en minúsculas.
* En lugar de un espacio, usa un guion bajo (_) o un guion corto (–).
* Utiliza formatos de archivo consistentes. Usa jpg o jpg.
* Solo utiliza caracteres alfanuméricos, puntos, guiones bajos y guiones; no uses símbolos como % y $.
* Los nombres de los archivos deben ser cortos y descriptivos.

  Vamos a crear los siguientes directorio
  
```
mkdir Hector Martinez
mkdir HectorMartinez
```
Vamos a ver que carpetas tenermos en nuestros directorio

```
ls -lh

## drwxr-xr-x 2 magh staff 64 may  6 23:09 Hector
## drwxr-xr-x 2 magh staff 64 may  6 23:09 HectorMartinez
## drwxr-xr-x 2 magh staff 64 may  6 23:09 Martinez
```

## Comando touch

El comando touch se usa para crear archivos vacíos. Vamos a crear 



```
ls

## my_scrapt  my_scrept  my_script  my_scropt  my_scrupt

ls -l my_script

## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_script
```

El comando ls también reconoce caracteres comodín estándar y los utiliza para encontrar patrones dentro del filtro:
■ Un signo de interrogación (?) para representar un carácter
■ Un asterisco (*) para representar cualquier número de caracteres

```
ls -lh my_scr?pt

## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scrapt
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scrept
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_script
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scropt
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scrupt

ls -lh my*

## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scrapt
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scrept
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_script
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scropt
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scrupt
```

El asterisco busca tres archivos diferentes, comenzando con el nombre "my". Al igual que con el signo de interrogación, puede colocar los asteriscos en cualquier parte del filtro:

```
ls -lh my_s*t

## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scrapt
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scrept
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_script
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scropt
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scrupt

```

El uso del asterisco y el signo de interrogación en el filtro se denomina "globbing" de archivos. El "globbing" de archivos consiste en procesar la coincidencia de patrones mediante comodines. Los comodines se denominan oficialmente comodines de metacaracteres. Se pueden usar más comodines de metacaracteres para el "globbing" de archivos que solo el asterisco y el signo de interrogación. También se pueden usar corchetes.

```
ls -l my_scr[ai]pt

## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scrapt
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_script

ls -l my_scr[a-i]pt

## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scrapt
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scrept
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_script

```

También puedes especificar qué no debe incluirse en la coincidencia de patrones utilizando el signo de exclamación (!):

```
ls -l my_scr[!i]pt

## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scrapt
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scrept
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scropt
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:32 my_scrupt

```
## Manejo de archivos

De vez en cuando, es necesario crear un archivo vacío. Por ejemplo, a veces las aplicaciones esperan que exista un archivo de registro antes de poder escribir en él. En estas situaciones, se puede usar el comando *`touch`* para crear fácilmente un archivo vacío:

```
touch test_one
ls -l test_one

## --rw-r--r--. 1 lab13 lab13 0 Aug 11 00:51 test_one

```
## Copiando archivos

Copiar archivos y directorios de una ubicación a otra en el sistema de archivos es una práctica común para los administradores de sistemas. El comando *_cp_* proporciona esta función.

En su forma más básica, el comando cp utiliza dos parámetros: el objeto de origen y el objeto de destino: *_cp fuente destino_*  

```
cp test_one test_two
ls -lh test*

## -rw-r--r--. 1 lab13 lab13 0 Aug 11 00:51 test_one
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 07:26 test_two

```

El parámetro -R es una potente opción del comando cp. Permite copiar recursivamente el contenido de un directorio completo con un solo comando: *_cp -R Scripts/ Mod_Scripts_*

## Renombrando archivos

En Linux, renombrar archivos se llama mover archivos. El comando *_mv_* permite mover archivos y directorios a otra ubicación o a un nuevo nombre:

```
ls -lh f?ll

## -rw-r--r--. 1 lab13 lab13 0 Aug 11 07:33 fall
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 07:33 fell
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 07:33 fill

mv fall fzll
ls -lh f?ll

## -rw-r--r--. 1 lab13 lab13 0 Aug 11 07:33 fell
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 07:33 fill
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 07:33 fzll

```

## Eliminando archivos

Lo más probable es que en algún momento quieras poder eliminar archivos existentes. Ya sea para limpiar un sistema de archivos o para eliminar un paquete de software, siempre tienes la oportunidad de eliminar archivos.

En Linux, eliminar se llama remover. El comando para eliminar archivos en la shell bash es *_rm*_. La forma básica del comando _*rm_* es simple:


```
rm fzll 

ls -lh f?ll 

## -rw-r--r--. 1 lab13 lab13 0 Aug 11 07:33 fell
## -rw-r--r--. 1 lab13 lab13 0 Aug 11 07:33 fill

rm f?ll 
```

## Administración de directorios

Crear un nuevo directorio en Linux es fácil: solo use el comando *_mkdir*_

```
mkdir New_Dir
ls -ld New_Dir

## drwxr-xr-x. 2 lab13 lab13 6 Aug 11 07:44 New_Dir
```
El sistema crea un nuevo directorio llamado *_New_Dir*_. Observe que en la lista larga del nuevo directorio, su registro comienza con una d. Esto indica que *_New_Dir*_ no es un archivo, sino un directorio.

Puede crear directorios y subdirectorios en bloque si es necesario. Sin embargo, si intenta hacerlo solo con el comando mkdir, recibirá el siguiente mensaje de error.

```
mkdir New_Dir/Sub_Dir/Under_Dir
## mkdir: cannot create directory ‘New_Dir/Sub_Dir/Under_Dir’: No such file or directory
```

Para crear varios directorios y subdirectorios al mismo tiempo, debe agregar el parámetro *_-p*_:

```
mkdir -p New_Dir/Sub_Dir/Under_Dir

ls -R New_Dir

## New_Dir:
## Sub_Dir

## New_Dir/Sub_Dir:
## Under_Dir

## New_Dir/Sub_Dir/Under_Dir:

```
La opción -p del comando mkdir crea los directorios principales que faltan según sea necesario. Un directorio principal es un directorio que contiene otros directorios en el nivel inferior del árbol de directorios.

## Visualización del archivo

Si tiene un archivo de texto grande, quizás quiera ver su contenido. Linux cuenta con tres comandos diferentes que pueden ayudarle

El comando *_cat*_ es una herramienta útil para mostrar todos los datos dentro de un archivo de texto

```
cat SraAccList.txt 

## SRR31854929
## SRR31854928
## SRR31854929

```

Con _*cat*_ solo observamos el contenido del archivo de texto. Sin embargo, el comando cat tiene algunos parámetros que puede ayudar. El parámetro -n numera todas las líneas automáticamente:

```
cat -n SraAccList.txt 

##     1	SRR31854929
##     2	SRR31854928
##     3	SRR31854929

```
Esta función será útil al examinar scripts. Si solo desea numerar las líneas que contienen texto, el parámetro -b es ideal.

Por último, si no desea que aparezcan caracteres de tabulación, utilice el parámetro -T,.

```
## Examina MAGH_alineamiento.sh

cat MAGH_alineamiento.sh
cat -n MAGH_alineamiento.sh
cat -b MAGH_alineamiento.sh
cat -T MAGH_alineamiento.sh
```

## Una alternative de _*cat*_ es _*more*_, _*less*_, _*tail*_, _*head*_

Con _*head*_ y _*tail*_ puedes especificar con -n para ver cuantas líneas quieres ver en tu terminal

```
head -n 8 MAGH_alineamiento.sh 

## #!/bin/bash
## 
## ###############
## #Directorios
## ###############
## ref="/home/lab13/Reference/Reference/Human-Hg19/ucsc.hg19.fasta"
## 
## #Aliniamiento bwa

tail -n 8 MAGH_alineamiento.sh

##
## #Para hacer el call
## for file in *.segmetrics.cns; do
## id=${file%"segmetrics.cns"}
## call="${id}.segmetrics.call.cns"
## 
## cnvkit.py call $file -o $call
## done

```

## Trabajando con archivos de datos

Cuando se tiene una gran cantidad de datos, gestionar la información y hacerla útil puede ser difícil. Linux ofrece varias herramientas de línea de comandos para facilitar la gestión de grandes cantidades de datos. Esta sección abarca los comandos básicos que todo administrador de sistemas, así como cualquier usuario habitual de Linux, debería saber usar para simplificar su trabajo.



wget https://raw.githubusercontent.com/Martinez-Gregorio-Hector/AnalisisGenomico-EcologiaFESIztacala/refs/heads/main/Unidad1/Datos/flights.csv
# Después de descargar inspecciona el documento con los comandos que aprendiste durante la clase

# Ejecutar el comando sort para ordenar los datos, que observas?
sort flights.csv
```

An

```
# descargue el archivo con el que vamos a trabajar
wget https://raw.githubusercontent.com/Martinez-Gregorio-Hector/AnalisisGenomico-EcologiaFESIztacala/refs/heads/main/Unidad1/Datos/file2.txt
```

Si usas el parámetro -M, el comando sort reconoce la nomenclatura de tres caracteres del mes y ordena correctamente

```
sort -M file2.txt 
```

Vamos a seguir practicando para ordenar los datos

```
# Descarga el siguiente dato
wget https://raw.githubusercontent.com/Martinez-Gregorio-Hector/AnalisisGenomico-EcologiaFESIztacala/refs/heads/main/Unidad1/Datos/file3.txt
# Inspeccionar el archivo
head file3.txt




# Uso de variables

El shell bash utiliza una función llamada variables de entorno para almacenar información sobre la sesión del shell y el entorno de trabajo (de ahí el nombre de variables de entorno). Esta función también permite almacenar datos en memoria a los que cualquier programa o script que se ejecute desde el shell puede acceder fácilmente. Es una forma práctica de almacenar datos persistentes necesarios.

Existen dos tipos de variables de entorno en el shell bash:

* Variables globales

* Variables locales

Para ver las variables de entorno globales, utilice el comando _*env*_ o _*printenv*_

```
env | head -n 7

## TERM_PROGRAM=Apple_Terminal
## SHELL=/bin/zsh
## TERM=xterm-256color
## TMPDIR=/var/folders/lz/_pw1ngjd2b5gs47g9x2sy6pr0000gn/T/
## TERM_PROGRAM_VERSION=453
## TERM_SESSION_ID=04F1D001-5AF4-4EB5-9F0E-7A5CFF702EF7
## USER=magh

echo $USER

## magh
```
## Variables locales


Tras iniciar una shell bash (o generar un script de shell), se pueden crear variables locales definidas por el usuario, visibles en el proceso de shell. Se puede asignar un valor numérico o de cadena a una variable de entorno, asignándola a un valor con el signo igual:

```
my_variable=Hello 
echo $my_variable
```

Ejercicio 
```
Establece una variable: dias
Establece una variable: invitado

Imprime esta frase que diga
Mariana se reporto hace 10 dias

```

# Permisos

## Usuario, grupo y resto del mundo (User, Group, Others …) y permisos 

En sistemas UNIX y GNU/Linux cada archivo y directorio tiene unos permisos determinados de 

*lectura=𝑟

*escritura=𝑤

*ejecución=𝑥

para el usuario, grupo y resto del mundo, asignados en ese orden (UGO). Un archivo regular, escrito por el usuario tiene los siguientes permisos por defecto, como muestra el comando 𝑙𝑠−𝑙

```
ls -l | grep odp
-rw-r--r-- 1 vinuesa vinuesa 2993606 sep 30 10:52 intro_biocomputo_Linux_LCG.odp

```

Veamos lo que quiere decir. Para ello necesitamos separar la cadena de caracteres en los siguientes componentes

```
   U   G   O       usuario grupo
1  2   3   4  5    6       7
-|rw-|r--|r-- 1 vinuesa vinuesa

donde:

1. la posición 1 (-) indica que se trata de un archivo regular. Un directorio se indica con "d" y una liga simbólica con "l"
2. El grupo 2,3 y 4 de caraceres indican el "modo" del archivo (permisos) para el usuario (U), grupo (G) y otros (resto del mundo O), 
   separados por "|" para facilitar su visualización.
   En este caso el usuario tiene permisos de lectura (r) y escritura (w) sobre el archivo que no es ejecutable (-)
   El grupo y el resto del mundo sólo pueden leer el archivo, pero no modificarlo.
```

## Tabla de atributos de los permisos

La siguiente tabla resume los atributos que tienen los permisos 𝑟, 𝑤, 𝑥 sobre archivos regulares y directorios:

```
| Atributo | Archivos                                       | Directorios                                  |
|:--------:|------------------------------------------------|----------------------------------------------|
| r        | abrir y leer                                   | listar contenidos si tiene +x                |
| w        | editar pero no renombrar/borrar (atributo dir) | permite generar archivos en dir, si tiene +x |
| x        | permite ejecutra archivo (programa) si +r      | permite entrar al directorio                 |
```

## chmod - cambiar el modo (permisos) de un archivo o directorio

Hay dos maneras de hacerlo:

### 1 Usando notación simbólica para U|G|O y todos (a)


```
| Símbolo | Significado                                |
|:-------:|--------------------------------------------|
| u       | usuario, el dueño del archivo o directorio |
| g       | dueño del gruop                            |
| o       | otros (resto del mundo)                    |
| a       | todos (all); combinación de u,g,o          |

```

Ejemplos: 𝑐ℎ𝑚𝑜𝑑 𝑛𝑜𝑡𝑎𝑐𝑖ó𝑛 𝑎𝑟𝑐ℎ𝑖𝑣𝑜|𝑑𝑖𝑟

```
|  Notación  | Significado                                |
|:----------:|--------------------------------------------|
| u+x        | da permiso de ejecución a usuario          |
| u-x        | revoca permiso de ejecución a usuario      |
| o-r        | otros (resto del mundo) no puede leer      |
| +x         | equivale a a+x                             |
| o-rw       | quitar a otros permisos de rw              |
| u+x,go=-rx | asignar +x a U, revocar a O permisos de rx |
```

𝑐ℎ𝑚𝑜𝑑 𝑎+𝑟𝑥 𝑠𝑐𝑟𝑖𝑝𝑡.𝑠ℎ hace el archivo script.sh leíble y ejecutable para todos


### 2 Usando representación octal

Los sistemas de numeración 𝑜𝑐𝑡𝑎𝑙 (base 8) y su primo el ℎ𝑒𝑥𝑎𝑑𝑒𝑐𝑖𝑚𝑎𝑙 (base 16) se usan frecuentemente para expresar números en computadoras.

Los humanos usamos el sistama 𝑑𝑒𝑐𝑖𝑚𝑎𝑙 ya que (la mayoría) tenemos 10 dedos. Las computadoras en cambio “nacieron con un solo dedo”, por lo que cuentan usando el sistema 𝑏𝑖𝑛𝑎𝑟𝑖𝑜 (base 2) usando sólo 1s y 0s. Por tanto en binario, contamos así: 0,1, 10,11, 100,101, 110,111 …

En 𝑜𝑐𝑡𝑎𝑙, contamos así: 0,1,2,3,4,5,6,7, 10,11,12,13,14,15,16,17, 20,21 …

Usando una cadena de tres dígitos octales, podemos de manera muy conveniente definir el modo de un archivo para U|G|O acorde a la siguiente tabla

```
| octal | binario | modo del archivo |
|:-----:|---------|------------------|
| 0     | 000     | —                |
| 1     | 001     | –x               |
| 2     | 010     | -w-              |
| 3     | 011     | -wx              |
| 4     | 100     | r–               |
| 5     | 101     | r-x              |
| 6     | 110     | rw-              |
| 7     | 111     | rwx              |
```

De modo que combinando los octales

READ = 4

WRITE = 2

EXECUTE = 1

con las posiciones U|G|O, define los modos:

```
| USER  | GROUP | OTHERS | MODE |
|-------|-------|--------|------|
| r w x | r w x | r w x  | UGO  |
| 4 2 0 | 0 0 0 | 0 0 0  | 600  |
| 4 2 1 | 4 0 1 | 4 0 1  | 755  |
```

Ejercicio, como interpreto estos permisos?

```
𝑐ℎ𝑚𝑜𝑑 755 𝑠𝑐𝑟𝑖𝑝𝑡.𝑠ℎ
𝑐ℎ𝑚𝑜𝑑 700 𝑠𝑐𝑟𝑖𝑝𝑡.𝑠ℎ
𝑐ℎ𝑚𝑜𝑑 644 𝑠𝑐𝑟𝑖𝑝𝑡.𝑠ℎ
```
## Editor de script

* [Visual Studio Code](https://code.visualstudio.com/)
* [Atom](https://atom-editor.cc/)


## Edición de archivos con el editor de flujo sed (stream editor)

**sed** (stream editor) es un editor de flujo, una potente herramienta de tratamiento de texto para el sistema operativo UNIX que acepta como entrada un archivo, lo lee y modifica línea a línea de acuerdo a un script, mostrando el resultado por salida estándar (normalmente en pantalla, a menos que se realice una redirección). Sed permite manipular flujos de datos, como por ejemplo cortar líneas, buscar y reemplazar texto (con soporte de expresiones regulares ), entre otras cosas.

La sintaxis general de la orden **sed** es:

```
sed [-n] [-e'script'] [-f archivo] archivo1 archivo2 ...

# donde

-n indica que se suprima la salida estándar.
-e indica que se ejecute el script que viene a continuación. Si no se emplea la opción -f se puede omitir -e.
-f indica que las órdenes se tomarán de un archivo

```

## Ejemplos de uso básico de sed: sustituciones s///

Sustituciones **s///** de palabras **s/esto/aquello/** o caracteres en archivos de texto.

* cambia espacios sencillos por guiones bajos

```
## Bajar el archivo que vamos a ejecutar
wget https://raw.githubusercontent.com/vinuesa/intro2linux/refs/heads/master/data/linux_basic_commands.tab

head -1 linux_basic_commands.tab                 # usamos head -1 para ver la primera línea, que modificaremos con sed
## IEEE Std** 1003.1-2008 utilities Name 	Category 	Description 	First appeared
head -1 linux_basic_commands.tab | sed 's/ /_/'  # se sustituye sólo la primera instancia de espacio en blanco!
## IEEE_Std 1003.1-2008 utilities Name 	Category 	Description 	First appeared
head -1 linux_basic_commands.tab | sed 's/ /_/g' # ahora globalmente
## IEEE_Std_1003.1-2008_utilities_Name_	Category_	Description_	First_appeared
```

## Ejemplos de uso básico de sed: cambio de fuente: y///

* Cambia todas las minúsculas a mayúsculas de archivo:

```
head -1 linux_basic_commands.tab | sed 'y/abcdefghijklmnopqrstuvwxyz/ABCDEFGHIJKLMNOPQRSTUVWXYZ/'
## IEEE STD 1003.1-2008 UTILITIES NAME 	CATEGORY 	DESCRIPTION 	FIRST APPEARED
```

* Podemos combinar diversas acciones de sustitución, separándolas así: s///; s///

```
head -1 linux_basic_commands.tab | sed 'y/abcdefghijklmnopqrstuvwxyz/ABCDEFGHIJKLMNOPQRSTUVWXYZ/; s/ /_/g'
## IEEE_STD_1003.1-2008_UTILITIES_NAME_	CATEGORY_	DESCRIPTION_	FIRST_APPEARED
```

Otro ejemplo, descargar el archivo tomates.fasta y cambiar "Solanum lycopersicum" por "jitomate"

```
## Descargar el archivo
wget https://raw.githubusercontent.com/AliciaMstt/BioinfinvRepro/refs/heads/master/Unidad1/Prac_Uni1/Tomates/tomates.fasta

head tomates.fasta

sed 's/Solanum lycopersicum/jitomate/' tomates.fasta
```

#################################















# Editor de texto vim

El editor **vi** fue el editor original utilizado en sistemas Unix. Utilizaba el modo gráfico de consola para emular una ventana de edición de texto, lo que permitía ver las líneas de un archivo, navegar por él e insertar, editar y reemplazar texto.

Aunque posiblemente fuera el editor más complejo del mundo, ofrece numerosas funciones que lo han convertido en un elemento básico para los administradores de Unix durante décadas.

Cuando el Proyecto GNU adaptó el editor **vi** al mundo del código abierto, decidió realizar algunas mejoras. Dado que ya no se parecía al editor **vi** original disponible en Unix, los desarrolladores también lo renombraron como **vi** mejorado o **vim**.

## Explorando vim basico

El editor **vim** trabaja con datos en un búfer de memoria. Para iniciarlo, simplemente escriba el comando **vim** (o vi si hay un alias o un archivo vinculado) y el nombre del archivo que desea editar:

```
vim test1.sh
```

Si inicia **vim** sin un nombre de archivo, o si el archivo no existe, vim abre un nuevo búfer para su edición. Si especifica un archivo existente en la línea de comandos, **vim** lee todo el contenido del archivo en un búfer, donde está listo para su edición.

El editor vim tiene dos modos de funcionamiento:

■ Modo normal

■ Modo de inserción

Al abrir un archivo por primera vez (o crear uno nuevo) para editarlo, el editor **vim** entra en modo normal. En modo normal, el editor **vim** interpreta las pulsaciones de teclas como comandos (más información más adelante). 

En el modo de inserción, **vim** inserta cada tecla que pulsas en la posición actual del cursor en el búfer. Para entrar en el modo de inserción, pulsa la tecla **i**. Para salir del modo de inserción y volver al modo normal, pulsa la tecla **escape**.

Dentro del modo de línea de comandos -inserición- hay varios comandos para guardar el búfer en el archivo y salir de vim:

■ q para salir si no se han realizado cambios en los datos del búfer

■ q! Para salir y descartar cualquier cambio realizado en los datos del búfer.

■ w nombre_archivo para guardar el archivo con un nombre diferente.

■ wq para guardar los datos del búfer en el archivo y salir.

```
## Después de que hayas hecho un script, para salir presione **scape** y después **:wq**

Scrpt


:wq
```

[Tutorial para principantes vim](https://www.freecodecamp.org/espanol/news/como-usar-vim-tutorial-para-principiantes/)

# Editor de texto nano

Aunque **vim** es un editor muy complejo con muchas funciones potentes, **nano** es un editor muy sencillo. Para quienes necesitan un editor de texto en modo consola sencillo y fácil de usar, **nano** es la herramienta ideal. También es un excelente editor de texto para jóvenes que se inician en la línea de comandos de Linux.

El editor de texto **nano** es un clon del editor Pico de Unix. Aunque Pico también es un editor de texto ligero y sencillo, no tiene licencia GPL. El editor de texto nano no solo tiene licencia GPL, sino que también forma parte del proyecto GNU.

El editor de texto nano viene instalado por defecto en la mayoría de las distribuciones de Linux. Todo en el editor de texto nano es sencillo. Para abrir un archivo en la línea de comandos con nano:

```
nano test2.sh
```

Una vez que se termine de redactar el script o los comandos que se utilicen para cierta actividad o análisis se tiene que guardar. Observe que en la parte inferior de la ventana del editor nano se muestran varios comandos con una breve descripción. Estos comandos son los comandos de control nano. El símbolo de intercalación (^) representa la tecla Ctrl. Por lo tanto, ^X representa la secuencia de teclado Ctrl+X. Para salir ejecutamos estas secuencias.


<p align="center">  
  <img src="https://github.com/Martinez-Gregorio-Hector/AnalisisGenomico-EcologiaFESIztacala/blob/main/Unidad1/Figuras/nano1.png? raw=true" alt="shell" >
</p>

Posteriormente, nos va a salir otro menú y guardamos los cambios con la letra **Y**  para guardar el script o documentación que acabamos de realizar.

<p align="center">  
  <img src="https://github.com/Martinez-Gregorio-Hector/AnalisisGenomico-EcologiaFESIztacala/blob/main/Unidad1/Figuras/nano2.png? raw=true" alt="shell" >
</p>

# bash scripting básico

## Usando comandos múltiples

Hasta ahora has visto cómo usar la interfaz de línea de comandos (CLI) del shell para introducir comandos y ver sus resultados. La clave de los scripts de shell reside en la capacidad de introducir múltiples comandos y procesar los resultados de cada uno, incluso pudiendo pasar los resultados de un comando a otro. El shell permite encadenar comandos en un solo paso.

Si quieres ejecutar dos comandos a la vez, puedes introducirlos en la misma línea del prompt, separados com un **punto y coma**

```
date ; who 
```

Este sencillo script usa solo dos comandos de shell bash. El comando "date" se ejecuta primero, mostrando la fecha y hora actuales, seguido del comando "who", que muestra quién está conectado al sistema. Con esta técnica, puedes encadenar tantos comandos como desees, hasta el límite máximo de 255 caracteres de la línea de comandos.

Esta técnica es adecuada para scripts pequeños, pero tiene una desventaja importante: debes ingresar el comando completo en el símbolo del sistema cada vez que quieras ejecutarlo. En lugar de tener que ingresar manualmente los comandos en una línea de comandos, puedes combinarlos en un simple archivo de texto. Cuando necesites ejecutar los comandos, simplemente ejecuta el archivo de texto.

## Creando un bash scripting

Para colocar comandos de shell en un archivo de texto, primero debe usar un **editor de texto** para crear un archivo y luego ingresar los comandos.

Al crear un archivo de script de shell, debe especificar el shell que está usando en la primera línea del archivo. El formato es el siguiente:

```
#!/bin/bash
```

En una línea de shell scripting, el signo de almohadilla (#) se usa como línea de comentario. El shell no procesa una línea de comentario en un shell scripting. Sin embargo, la primera línea de un archivo de shell scripting es un caso especial, y el signo de almohadilla seguido del signo de exclamación le indica al shell en qué shell ejecutar el script. Haz un shell scripting usando la siguiente información, puedes guardarlo en una sesión que se llama **test3.sh** y **cambia el permiso del archivo creado: chmod u+x test3**

```
#!/bin/bash

# Este script muestra la fecha y la fecha de inicio de sesión.

date
who
```

## Visualización de imágenes

La mayoría de los comandos de shell generan su propia salida, que se muestra en el monitor de la consola donde se ejecuta el script. Sin embargo, a menudo querrá agregar sus propios mensajes de texto para que el usuario del script sepa qué sucede dentro del script. Puede hacerlo con el comando echo. El comando echo puede mostrar una cadena de texto simple si agrega la cadena después del comando:

```
echo This is a test
## This is a test

```

Tenga en cuenta que, por defecto, no es necesario usar comillas para delimitar la cadena que se muestra. Sin embargo, esto puede resultar complicado si se usan comillas dentro de la cadena:

```
echo Let's see if this'll work
## Lets see if thisll work

```

El comando **echo** utiliza comillas dobles o simples para delimitar cadenas de texto. Si las usa dentro de la cadena, debe usar un tipo de comillas dentro del texto y el otro para delimitar la cadena:

```
echo "This is a test to see if you're paying attention"
## This is a test to see if you're paying attention

echo 'Rich says "scripting is easy".'
## Rich says "scripting is easy".

```

Puede agregar declaraciones de **echo** en cualquier lugar de sus scripts de shell donde necesite mostrar información adicional:

Crea un archivo que se llame **test4.sh** y ejecuta el siguiente comando

```
#!/bin/bash

# This script displays the date and who's logged on

echo The time and date are:
date

echo "Let's see who's logged into the system:"
who
```

Eso está bien, pero ¿qué pasa si quieres repetir una cadena de texto en la misma línea que la salida de un comando? Puedes usar el parámetro **-n** de la sentencia **echo** para ello. Simplemente cambia la primera línea de la sentencia echo por lo siguiente:

```
#!/bin/bash

# This script displays the date and who's logged on

echo -n "The time and date are: "
date

echo "Let's see who's logged into the system:"
who
```

## Variables

Además de las variables de entorno, un script de shell permite configurar y usar variables propias dentro del script. Configurar variables permite almacenar datos temporalmente y usarlos en todo el script, lo que lo hace más similar a un programa real.

Las variables de usuario pueden ser cualquier cadena de texto de hasta 20 letras, dígitos o un guion bajo. Las variables de usuario distinguen entre mayúsculas y minúsculas, por lo que la variable **Var1** es diferente de la variable **var1**. Esta pequeña regla suele causar problemas a los programadores de scripts principiantes.

Los valores se asignan a las variables de usuario mediante el signo igual. No se permiten espacios entre la variable, el signo igual y el valor (otro problema para principiantes). A continuación, se muestran algunos ejemplos de asignación de valores a variables de usuario:

```
var1=10
var2=-57
var3=testing
var4="still more testing"
```

El script de shell determina automáticamente el tipo de dato utilizado para el valor de la variable. Las variables definidas dentro del script de shell mantienen sus valores durante toda su vida útil, pero se eliminan al finalizar.

Al igual que las variables de sistema, las variables de usuario pueden referenciarse mediante el símbolo de dólar:

Crear un shell scripting **test5.sh**

```
#!/bin/bash

# testing variables

days=10
guest="Katie"
echo "$guest checked in $days days ago"

days=5
guest="Jessica"
echo "$guest checked in $days days ago"
```

Cada vez que se hace referencia a la variable, se genera el valor que tiene asignado. Es importante recordar que al hacer referencia al valor de una variable se usa el símbolo de dólar, pero al hacer referencia a la variable para asignarle un valor, no se usa el símbolo de dólar. Aquí hay un ejemplo de lo que quiero decir:

Crear un shell scripting **test6.sh**

```
#!/bin/bash

# assigning a variable value to another variable

value1=10
value2=$value1

echo The resulting value is $value2
```

Si olvida el signo de dólar que pasaría

```
#!/bin/bash

# assigning a variable value to another variable

value1=10
value2=value1

echo The resulting value is $value2
```

Sin el signo de dólar, el shell interpreta el nombre de la variable como una cadena de texto normal, lo cual probablemente no sea lo que usted deseaba.

## Comando de sustitución

Una de las características más útiles de shell scripting es la capacidad de extraer información de la salida de un comando y asignarla a una variable. Después de asignar la salida a una variable, puede usar ese valor en cualquier parte del script. Esto resulta útil al procesar datos en sus scripts.

Hay dos maneras de asignar la salida de un comando a una variable:

■ El carácter de comillas invertidas (`)

■ El formato $()

Tenga cuidado con el carácter de comillas invertidas; no es la comilla simple que se usa habitualmente para las cadenas. Dado que no se usa muy a menudo fuera de los scripts de shell, es posible que ni siquiera sepa dónde encontrarlo en su teclado. Debería familiarizarse con él, ya que es un componente crucial de muchos shell scripting. Consejo: En un teclado estadounidense, suele estar en la misma tecla que la tilde (~).

La sustitución de comandos permite asignar la salida de un comando de shell a una variable. Aunque parezca insignificante, es un componente fundamental en la programación de scripts.

Debe rodear todo el comando de la línea de comandos con dos comillas invertidas:


```
testing='date'
```

o usa el formato $()

```
testing=$(date)
```

El shell ejecuta el comando dentro de los caracteres de sustitución de comandos y asigna la salida a la variable "testing". Observe que no hay espacios entre el signo igual de asignación y el carácter de sustitución de comandos. A continuación, se muestra un ejemplo de creación de una variable utilizando la salida de un comando de shell normal:. Crear un shell scripting **test7.sh**

```
#!/bin/bash

testing=$(date)

echo "The date and time are: " $testing
```

## Redireccionando input y output

A veces, es necesario guardar la salida de un comando en lugar de simplemente mostrarla en el monitor. El shell bash ofrece varios operadores que permiten redirigir la salida de un comando a una ubicación alternativa (como un archivo). La redirección se puede usar tanto para la entrada como para la salida, redirigiendo un archivo a un comando para la entrada. Esta sección describe cómo usar la redirección en los scripts de shell.

### redireccionando output

El tipo más básico de redirección consiste en enviar la salida de un comando a un archivo. El shell bash utiliza el símbolo mayor que (**>**) para ello:

```
command > outputfile
```

Todo lo que aparecería en el monitor a partir del comando se almacena en el archivo de salida especificado:

```
who > test8
```


A veces, en lugar de sobrescribir el contenido del archivo, puede que necesite añadir la salida de un comando a un archivo existente; por ejemplo, si está creando un archivo de registro para documentar una acción en el sistema. En este caso, puede usar el símbolo de mayor que (>>) para añadir datos:

```
who >> test8
```

## Redireccionando input

La redirección de entrada es lo opuesto a la redirección de salida. En lugar de tomar la salida de un comando y redirigirla a un archivo, la redirección de entrada toma el contenido de un archivo y lo redirige a un comando.

El símbolo de redirección de entrada es el símbolo menor que (<):

```
command < inputfile
```

A continuación se muestra un ejemplo del uso de la redirección de entrada con el comando wc:


```
wc < test8
```



## Comando for

Iterar una serie de comandos es una práctica común en programación. A menudo, es necesario repetir un conjunto de comandos hasta que se cumpla una condición específica, como procesar todos los archivos de un directorio, todos los usuarios de un sistema o todas las líneas de un archivo de texto.

La shell bash proporciona el comando for para crear un bucle que itera sobre una serie de valores. Cada iteración ejecuta un conjunto definido de comandos utilizando uno de los valores de la serie. Este es el formato básico del comando for de la shell bash:

```
for var in list
do
commands
done
```
La serie de valores utilizados en las iteraciones se proporciona en el parámetro de lista. Puede especificar los valores de la lista de varias maneras.

En cada iteración, la variable **var** contiene el valor actual de la lista. La primera iteración utiliza el primer elemento de la lista, la segunda, el segundo, y así sucesivamente hasta que se hayan utilizado todos los elementos de la lista.
Los comandos introducidos entre las sentencias **do** y **done** pueden ser uno o más comandos estándar de la shell bash. Dentro de los comandos, la variable $var contiene el valor actual del elemento de la lista para la iteración.

## Leyendo valores en una lista

El uso más básico del comando **for** es iterar a través de una lista de valores definidos dentro del propio comando for:

```
#!/bin/bash

for test in Alabama Alaska Arizona Arkansas California Colorado
do 
echo The next state is $test
done

```

Cada vez que el comando for itera la lista de valores proporcionados, asigna a la variable $test el siguiente valor de la lista. La variable $test puede usarse como cualquier otra variable de script dentro de las sentencias del comando for. Tras la última iteración, la variable $test sigue siendo válida durante el resto del script de shell. Conserva el valor de la última iteración (a menos que se modifique).

```
#!/bin/bash

for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo "The next state is $test"
done
echo "The last state we visited was $test"
test=Connecticut
echo "Wait, now we're visiting $test"
```

La variable $test conservó su valor y nos permitió cambiarlo y usarlo fuera del bucle del comando for, como lo haría cualquier otra variable.

Ejemplo con variables

```
#!/bin/bash

maullido=miau

for i in gato gatito gatón
do
echo El $i hace $maullido
done

```

## Leyendo valores complejos en una lista 

Las cosas no siempre son tan fáciles como parecen con el bucle for. A veces, se encuentran datos que causan problemas. Aquí hay un ejemplo clásico de lo que puede causar problemas a los programadores de scripts de shell:

```
#!/bin/bash

# another example of how not to use the for command

for test in I don't know if this'll work
do
echo "word:$test"
done
```

¡Ay, qué lástima! El shell vio las comillas simples dentro de los valores de la lista e intentó usarlas para definir un único valor de datos, y lo estropeó todo.

Tienes dos maneras de resolver este problema:

■ Usa el carácter de escape (la barra invertida) para escapar de las comillas simples.

■ Usa comillas dobles para definir los valores que las contienen.

```
#!/bin/bash

# another example of how not to use the for command

for test in I don\'t know if "this'll" work
do
echo "word:$test"
done
```

En el primer valor del problema, añadiste la barra invertida para escapar las comillas simples en el valor "don't". En el segundo valor del problema, encerraste el valor "this'll" entre comillas dobles. Ambos métodos funcionaron correctamente para distinguir el valor.

Otro problema que puedes encontrar son los valores de varias palabras. Recuerda que el bucle "for" asume que cada valor está separado por un espacio. Si tienes valores de datos que contienen espacios, te encontrarás con otro problema:

```
#!/bin/bash

# another example of how not to use the for command

for test in Nevada New Hampshire New Mexico New York North Carolina
do
echo "Now going to $test"
done
```

Vaya, eso no es exactamente lo que queríamos. El comando for separa cada valor de la lista con un espacio. Si hay espacios en los valores de datos individuales, debes escribirlos entre comillas dobles:

```
#!/bin/bash

# another example of how not to use the for command

for test in Nevada "New Hampshire" "New Mexico" "New York" "North Carolina"
do
echo "Now going to $test"
done
```

Ahora el comando "for" puede distinguir correctamente entre los diferentes valores. Además, tenga en cuenta que al usar comillas dobles alrededor de un valor, el shell no las incluye como parte del valor.

## Leyendo una lista de una variable 

Lo que suele ocurrir en un script de shell es que se acumula una lista de valores almacenados en una variable y luego es necesario iterarla. También se puede hacer esto con el comando for:

```
#!/bin/bash

# using a variable to hold the list

list="Alabama Alaska Arizona Arkansas Colorado"
list=$list" Connecticut"

for state in $list
do
echo "Have you ever visited $state?"
done
```

La variable **$list** contiene la lista de texto estándar de valores que se usarán en las iteraciones. Observe que el código también utiliza otra sentencia de asignación para añadir (o concatenar) un elemento a la lista existente en la variable **$list**. Este es un método común para añadir texto al final de una cadena de texto existente almacenada en una variable.

## Ejercicio1

Revisa este [manual de fastp](https://github.com/OpenGene/fastp) y establezca el ejercicio de [fastp1](https://sxh1136.quarto.pub/amrflows-metagenomic-data-analysis-course/9.%20For-loops.html) y [fastp2](https://sxh1136.quarto.pub/amrflows-metagenomic-data-analysis-course/9.5.%20Paired-End-Data.html)

* Haz una carpeta con el nombre de practica2

* Copia los archivos que están en la dirección **fastq.gz** que están en esta dirección /home/lab13/Documents/MAGH/Cahuantzi_Preneoplasias/PruebaEcologia

* Crea un bash scripting

* Genera un bucle for para procesar los archivos

* Haz la interpretación de los resultados 

## Explicación de los archivos fastqz

Esta información se puede encontrar [aqui](https://brouwern.github.io/lbrb/introducingFASTA.html). 

En bioinformática, el formato FASTA es un formato de texto para representar secuencias de nucleótidos o de aminoácidos (proteínas). En este formato, los nucleótidos o aminoácidos se representan mediante códigos de una sola letra. Este formato permite que los nombres de las secuencias y los comentarios precedan a las secuencias.

La simplicidad del formato FASTA facilita la manipulación y el análisis de secuencias mediante herramientas de procesamiento de texto y lenguajes de programación como R y Python.

La primera línea de un archivo FASTA comienza con el símbolo ">" (mayor que) y contiene información resumida sobre la secuencia, a menudo comenzando con un número de acceso único y seguido de información como el nombre del gen, el tipo de secuencia y el organismo del que proviene.

En la siguiente línea se encuentra la secuencia en una cadena estándar de una sola letra. Cualquier carácter que no sea válido se ignora (incluidos espacios, tabulaciones, asteriscos, etc.).

### FASTA

```
## >gi|186681228|ref|YP_001864424.1| phycoerythrobilin:ferredoxin oxidoreductase
## MNSERSDVTLYQPFLDYAIAYMRSRLDLEPYPIPTGFESNSAVVGKGKNQEEVVTTSYAFQTAKLRQIRA
## AHVQGGNSLQVLNFVIFPHLNYDLPFFGADLVTLPGGHLIALDMQPLFRDDSAYQAKYTEPILPIFHAHQ
## QHLSWGGDFPEEAQPFFSPAFLWTRPQETAVVETQVFAAFKDYLKAYLDFVEQAEAVTDSQNLVAIKQAQ
## LRYLRYRAEKDPARGMFKRFYGAEWTEEYIHGFLFDLERKLTVVK
```
### FASTQ

El formato FASTQ es un formato de texto que permite almacenar una secuencia biológica (generalmente una secuencia de nucleótidos) y sus correspondientes puntuaciones de calidad. Tanto la letra de la secuencia como la puntuación de calidad se codifican con un solo carácter ASCII para mayor brevedad.

Se desarrolló originalmente en el Wellcome Trust Sanger Institute para agrupar una secuencia con formato FASTA y sus datos de calidad, pero recientemente se ha convertido en el estándar de facto para almacenar los resultados de instrumentos de secuenciación de alto rendimiento, como el Analizador Genómico Illumina.

Un archivo FASTQ normalmente utiliza cuatro líneas por secuencia.

■ La línea 1 comienza con el carácter @ y va seguida de un identificador de secuencia y una descripción opcional (como una línea de título FASTA).

■ La línea 2 contiene las letras de la secuencia sin procesar.

■ La línea 3 comienza con el carácter + y, opcionalmente, va seguida del mismo identificador de secuencia (y cualquier descripción).

■ La línea 4 codifica los valores de calidad de la secuencia en la línea 2 del archivo y debe contener el mismo número de símbolos que letras de la secuencia.


A continuación se muestra un ejemplo del contenido de un archivo FASTQ

```
@M03468:54:000000000-JCR2C:1:1101:11196:1120 1:N:0:TGCAGCTA+NAGGCTAT
CCTACGGGGGGCAGCAGTGAGGAATATTGGTCAATGGACGAAGGTCTGAACCAGCCAAGCCGCGTGAAGGAAGAAGGTGCTGAGCATCGTAANCTTCTTTTGTCAGGGAACAAAATCGTGGATGCGTCCGCGAGTGAGTGTACCTGAAGAAAAAGCATCGGCTAACTCCGTGCCAGCAGCCGCGGTAATACGGAGGATGCGAGCGTTATCCGGATTTATTGGGTTTAAAGGGTGCGTAGGCGGGCTGTTAA
+
CCCCCGGGGGGGGGGGGFGGGGGGGGGEGGGGGGGGGG8FGGGGGGGGGGGGGGFFFGGGFFFG>F@FFGGGGGGGGGGGGGGGCF@CFGGG#:@BFGGGGGFGGGGGGGGGGGGFFFGGGGFGGGDE*=FEGGGGGGFGGGFGGGFFGGGGGGGGGGGGEGGGGGGFCGGGEGGGGGGGGGEGD5CCFFGF5AEGGFGFGGGGEGCGFFC;CDECFFGFG?FGDECC=FF*CG3C>?GFFFFGB;GGGG>
@M03468:54:000000000-JCR2C:1:1101:21975:1130 1:N:0:TGCAGCTA+AAGGCTAT
CCTACGGGTGGCAGCAGTGGGGGATATTGCACAATGGGGGGAACCCTGATGCAGCGACGCCGCGTGAGTGAAGGAGTACTTCGGTACGTAAAGCTCTATCAGCAGGGAAGAAGGGGGCGGGCTTGCCCGCCCGGACGGTACCTGACCAAGAAGCCCCGGCTAACTACGTGCCAGCAGCCGCGGTAATACGTAGGGGGCAAGCGTTATCCGGATTTACTGGGTGTAAAGGGAGCGTAGACGGCAAGGCAAGG
+
CCCCCGGGGGGGGGGGGGGGGGGEGGGGGGGGGGGGGGGGEGGGGGGGGGGFGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGGFGGGGGGGGGGGGGGGFGGGGFGGGGG@FGGGGGEGFGGFFEEDCEGEECDGGGCGGCC?FCCCFFFGG8EGG5CGFGG8CEECCCFC?FFGG5CGDE*ACFEFFFGGDGEECGFG8CECFFDD*9<FFCFGGG8E*0<CEBG*/9C5CEFC6:@;DFBD*>F*
```

[Checar código ascii y calidad](https://learn.gencore.bio.nyu.edu/ngs-file-formats/quality-scores/)





```
#!/bin/bash

# Creamos un arreglo con los archivos fastq
array=($(ls /home/lab13/Documents/Ecologia_AnalisisGenomico/HectorMartinez/FASTQ/*fastq.gz))
# Guardar el tamano del arreglo
tLen=${#array[@]}

# Bucle para correr de dos en dos los datos
# Inicia en i=0 y va aumentando de 2 en 2
# Sirve porque los archivos FASTQ vienen en pares (R1 y R2)
for (( i=0; i<${#array[@]}; i=i+2));
do
# Extraemos el nombre de los archivos
# RGP-0001_S1_L001_R1_001.fastq.gz
x=${array[$i]##*/}
echo "pear -f ${array[$i]} -r ${array[$i+1]} -o ensamblajes/${x%_S*} -j 8 -q 30"
done
```


# Evaluación de la calidad

## Archivos fasta o formato de Pearson
Antes de entender y analizar los archivos de la secuenciación masiva, vamos a revisar primero el formato **[fasta o Person](https://www.bioinformatics.nl/tools/crab_fasta.html)**

<p align="center">  
  <img src="Figuras/fasta.png? raw=true" alt="shell" width="1000" height="600">
</p>

## Características del archivo fastq

<p align="center">  
  <img src="Figuras/Fastq1.png? raw=true" alt="shell" width="1000" height="600">
</p>

<p align="center">  
  <img src="Figuras/Fastq2.png? raw=true" alt="shell" width="1000" height="600">
</p>

## Encabezado del archivo fastq

<p align="center">  
  <img src="Figuras/EncabezadoFastq.png? raw=true" alt="shell" width="1000" height="600">
</p>

## Información de la calidad de las lecturas crudas

<p align="center">  
  <img src="Figuras/ASCII.png? raw=true" alt="shell" width="1000" height="600">
</p>

## Nivel de calidad Phred 

<p align="center">  
  <img src="Figuras/Phred.png? raw=true" alt="shell" width="1000" height="600">
</p>

## Diagrama de cajas y bigotes

<p align="center">  
  <img src="Figuras/BoxPlot.svg? raw=true" alt="shell" width="600" height="600">
</p>

## Revisión de resultado FastQC y multiQC

**[FastQC](https://www.bioinformatics.babraham.ac.uk/projects/fastqc/)**

* **[FastQC_bueno](https://github.com/Martinez-Gregorio-Hector/MetodosDeInvestigacionLabII_EcologiaFESIztacalaUNAM_2026/tree/main/PresentacionesEnClase_Bioinformatica/FastQC_MultiQC/good_sequence_short_fastqc.html)**
* **[FastQC_malo](https://github.com/Martinez-Gregorio-Hector/MetodosDeInvestigacionLabII_EcologiaFESIztacalaUNAM_2026/tree/main/PresentacionesEnClase_Bioinformatica/FastQC_MultiQC/bad_sequence_fastqc.html)**

**[MultiQC](https://github.com/MultiQC/MultiQC)**

* **[MultiQC](https://github.com/Martinez-Gregorio-Hector/MetodosDeInvestigacionLabII_EcologiaFESIztacalaUNAM_2026/tree/main/PresentacionesEnClase_Bioinformatica/FastQC_MultiQC/multiqc_report_despues.html)**

