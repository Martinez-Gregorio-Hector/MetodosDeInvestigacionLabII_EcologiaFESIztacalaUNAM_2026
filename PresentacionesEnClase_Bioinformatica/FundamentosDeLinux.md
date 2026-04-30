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
Si queremos observar 


# NOS QUEDAMOS AQUI




Opciones de _𝑙𝑠_

Antes de crear una carpeta persona, vamos a utilizar el comando **ls** para listar que archivos se encuentran dentro de la carpeta **Ecologia2026**. Recuerda que ls tiene varias opciones que puedes convinar con el comando **ls**

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



