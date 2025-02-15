Comando Linux

Teorico:

- la shell es una interfaz que permite la comunicacion entre el usuario y el ordenador ¿ a trabes de un sistema operativo.
- (típica ventana o pantalla de letras blancas/verdes con fondo negro).
- nos permite (crear carpetas, borrar carpetas, ver archivos, etc)
- El sistema operativo indica que se encuentra a la espera de órdenes en el shell cuando
  muestra el prompt($) del sistema seguido del cursor.
- Los comandos son una serie de órdenes que ejecutadas que permite lanzar una serie de mecanismos que devuelvan al usuario el objetivo esperado; pueden tener parámetros;
- Para acceder a variables de entorno o configuraciones, los nombres simpre van con mayuscula y las palabras separadas por guiguines bajos( \_ )

- una ruta es una secuencia de directorios que especifica la ubicación de un archivo o directorio en el sistema de archivos.
- Un árbol de directorios es una estructura jerárquica que muestra la organización de los directorios en el sistema de archivos.
- Una ruta absoluta especifica la ubicacion de un archivo o directorio desde el directorio raiz del sistema de archivos.
- Una ruta relativa especifica la ubicacion de un archivo o directorio en relacion con el directorio actual.

  - el directorio actual se presenta con " . " y el directorio padre con " .. "

  ***

  Comandos :

Ayuda:

- man nombreDelComando => ver el manual de un comando
- apropos terminoDeBusqueda (copy) => Busca comandos relacionados con un termino de busqueda especifico(en manual)

Rutas y directorios:

- pwd => Muestra la ruta completa del directorio actual.

- ls => Lista los archivos y directorios en el directorio actual( ls NOMBRE_CARPETA)

  - ls -l => para mostrar informacion detallada
  - ls -a => para mostrar archivos ocultos
  - ls -al => me alista todos los archivos hasta los ocultos, con ls solamente los publicos
  - ls img => listaria a todos los archivos y directorios llamdos img y ubicados en la ruta actual

- cd => Cambia de directorio (cd NOMBRE_CARPETA => cd /usr/bin )

- mkdir => Crea un nuevo directorio vacio en el sistema de archivo(mkdir nombreDirectorio => mkdir nuevoDirectorio)

- rm => Elimina directorios y archivos en el sistema de archivos.( rm nombreArchivo => rm archivo.txt)

- rmdir => Elimina directorios vacios en el sistema de archivos.(rmdir nombreDirector => rmdir directorioVacio)

- cp => Copia archivos y directorios en el sistema de archivos.(cp nombreArchivo nuevoDirectorio => cp archivo.txt nuevoDirectorio)

- mv => Mueve archivos y directorios en el sistema de archivos.(mv nombreArchivo nuevoDirectorio => mv archivo.txt nuevoDirectorio)

Gestion Del Software:

- apt o atp-get => gestor de paquetes en sistemas basados en Dabian y Ubuntu. Actualiza; Instala; Elimina paquetes de Software

  - sudo atp update => Actualiza la lista de paquetes Disponibles
  - sudo apt install nombrePaquete => Instala un nuevo paquete de software
  - sudo atp upgrade => Actualiza todos los paquetes instalados
  - sudo apt remove nombrePaquete => Elimina un paquete de software
  - sudo apt purge nombrePaquete => elimina un paquete junto con sus archivos de configuracion.

- wget => Descarga desde la web

  - wget URL => Descarga desde una url espesifica.

- tar => Crea, despomprime yt maniputa archivos tar

  - tar -cvf archivo.tar directorio => crea un archivo tar con los archivos del directorio
  - tar -xvf archivo.tar => descomprime el archivo tar

- zip => Comprime Archivos rn formato ZIP

  - zip -r nombreZip directorio => comprime el directorio en formato zip
  - unzip => Descomprime archivos zip

- rar => Comprime y descomprime archivos en formato RAR

  - rar a archivo.rar archivo => comprime el directorio en formato rar
  - rar x archivo.rar => Descomprime el archivo rar

Gestion de hardware:

- lshw => Muestra informacion detallada del hardware dek sistema.

  - sudo lshw => muestra toda la informacion detallada del hardware

- lspci => Muestra informacion detallada de los dispositivos PCI del sistema.

- lsusb => Muestra informacion detallada de los dispositivos USB del sistema.

- free => Muestra la cantidad de memoria lubre y utilizada por el sistema.

  - free -h => muestra la cantidad de memoria en un formato mas legible.

- df => Muestra el espacio libre y utilizado en los sitemas de archivos montados.

  - df -h => Lo hace en formato mas legible

Acceso a informacion de archivos:

- touch => Crea un Archivo de texto vacio. (touch archivo.txt)

- cat => Muestra el contenido del o de los archivos en la pantalla. (cat archivo.txt)

- more => Muestra el contenido de manera paginada(more archivo.txt)

- grep => Comando que busca patrones en archivos de texto

  - grep palabra archivo.txt => Busca la palabra "palabra" en el archivo
  - grep -r PATRON directorio => Busca recursivamente el patron de todos los archivso dentro del directorio
    <!-- - grep -c PATRON archivo.txt => Cuenta la cantidad de veces que aparece el. -->
      <!-- - grep -n PATRON archivo.txt => Muestra la linea en la que aparece el. -->
      <!-- - grep -v PATRON archivo.txt => Muestra las lineas que no contienen el. -->
      <!-- - grep -h PATRON archivo.txt => Muestra el patron en el archivo sin mostrar el -->
      <!-- - grep -q PATRON archivo.txt => Busca el patron en el archivo y muestra un  -->

- wc => Comando que cuenta palabras, lineas y caractere en archivos de texto.

  - wc archivo.txt => muestra el numero de lineas, palabras y caracteres en el archivo.
  - wc -l archivo.txt => Cuenta la cantidad de lineas en el archivo
  - wc -w archivo.txt => Cuenta la cantidad de palabras en el archivo
  - wc -c archivo.txt => Cuenta la cantidad de caracteres en el archivo

Redireccion de la salida de un comando y combinacion de comandos:

Redirecciones:

- " < " => Redirige la entrada estandar de un comando desde un archivo

  - ls -l < directorio.txt => lista el contenido del directorio especificado dentro del archivo

- " > " => Redirige la salida estandar de un comando hacia a un archivo, sobreescribiendo su contenido

  - ls > listaArchivos.txt => guarda la lista de archivos en listaArchivos.txt

- " >> " => Redirige la salida estandar de un comando hacia a un archivo pero añade la salida final sin borrar su contenido previo
  - echo "nueva linea" >> archivo.txt => añade "nueva linea" al final del archivo sin borrar el contenido previo

Pipes => | :

- | => Permite tomar la salida estandar de un comando y usarla como entrada para otro.
  - ls | grep . txt => muestra solo los archivos que tienen la extension .txt

Usuarios y permisos:

- leer ==> read = r
- escribir ==> write = w
- ejecutar ==> execute = x

- 3 categorias de usuario

- user = u
- group = g
- otros - others = o

---

- nano NOMBRE_DEL_ARCHIVO =>

pwd # => miro en el directorio donde me encuentro
mkdir cursoLinux # => Creo la carpeta cursoLinux

cd cursoLinux/ # => es para entrar al directorio

# cd .. => es para volver al directorio anterior

mkdir subCarpeta1

# cd subCarpeta1/

# cd /home/cursoLinux/subCarpeta1 # => ir a la subCarpeta1 directamente

# pwd

# touch listUsers.txt # => crear archivos

# nano data.txt => edita archivos a trabes de la shell
