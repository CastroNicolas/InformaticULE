# Comandos Linux

## Teoría

- **La Shell** es una interfaz que permite la comunicación entre el usuario y el ordenador a través de un sistema operativo.
- Generalmente, se presenta como una ventana con letras blancas/verdes sobre fondo negro.
- Permite realizar tareas como: crear carpetas, borrar archivos, listar archivos, etc.
- El sistema operativo indica que está esperando órdenes en la Shell cuando muestra el **prompt (\$)** seguido del cursor.
- Los **comandos** son órdenes que ejecutan acciones específicas y pueden tener **parámetros**.
- Las **variables de entorno** o configuraciones se escriben en **mayúsculas** y con palabras separadas por guiones bajos (`_`).

### Rutas y Directorios

- Una **ruta** es una secuencia de directorios que especifica la ubicación de un archivo o directorio en el sistema de archivos.
- Un **árbol de directorios** es una estructura jerárquica que muestra la organización de los directorios en el sistema de archivos.
- **Ruta absoluta:** especifica la ubicación de un archivo o directorio desde el directorio raíz.
- **Ruta relativa:** especifica la ubicación de un archivo o directorio en relación con el directorio actual.
- **Atajos de navegación:**
  - `.` representa el **directorio actual**.
  - `..` representa el **directorio padre**.

---

## Comandos

### Ayuda

- `man <comando>` → Muestra el manual de un comando.
- `apropos <término>` → Busca comandos relacionados con un término específico en los manuales.

---

### Rutas y Directorios

- `pwd` → Muestra la ruta completa del directorio actual.
- `ls` → Lista los archivos y directorios en el directorio actual.
  - `ls -l` → Muestra información detallada.
  - `ls -a` → Muestra archivos ocultos.
  - `ls -al` → Lista todos los archivos, incluidos los ocultos.
  - `ls <nombre_carpeta>` → Lista los archivos en la carpeta especificada.
- `cd <nombre_carpeta>` → Cambia de directorio.
- `mkdir <nombre_directorio>` → Crea un nuevo directorio vacío.
- `rm <nombre_archivo>` → Elimina archivos.
- `rmdir <nombre_directorio>` → Elimina directorios vacíos.
- `cp <archivo> <directorio>` → Copia archivos y directorios.
- `mv <archivo> <directorio>` → Mueve archivos y directorios.

---

### Gestión del Software

- `apt` o `apt-get` → Gestor de paquetes en Debian/Ubuntu.
  - `sudo apt update` → Actualiza la lista de paquetes.
  - `sudo apt install <paquete>` → Instala un paquete.
  - `sudo apt upgrade` → Actualiza todos los paquetes.
  - `sudo apt remove <paquete>` → Elimina un paquete.
  - `sudo apt purge <paquete>` → Elimina un paquete y sus archivos de configuración.
- `wget <URL>` → Descarga archivos desde la web.
- `tar` → Manipulación de archivos `.tar`.
  - `tar -cvf <archivo.tar> <directorio>` → Crea un archivo `.tar`.
  - `tar -xvf <archivo.tar>` → Extrae un archivo `.tar`.
- `zip -r <archivo.zip> <directorio>` → Comprime un directorio en formato ZIP.
- `unzip <archivo.zip>` → Descomprime un archivo ZIP.
- `rar a <archivo.rar> <directorio>` → Comprime un directorio en formato RAR.
- `rar x <archivo.rar>` → Descomprime un archivo RAR.

---

### Gestión de Hardware

- `lshw` → Muestra información detallada del hardware.
  - `sudo lshw` → Información completa.
- `lspci` → Muestra información sobre dispositivos PCI.
- `lsusb` → Muestra información sobre dispositivos USB.
- `free` → Muestra la cantidad de memoria libre y utilizada.
  - `free -h` → Muestra la información en formato legible.
- `df` → Muestra el espacio libre y utilizado.
  - `df -h` → Muestra la información en formato legible.

---

### Acceso a Información de Archivos

- `touch <archivo>` → Crea un archivo vacío.
- `cat <archivo>` → Muestra el contenido de un archivo.
- `more <archivo>` → Muestra el contenido de manera paginada.
- `grep <patrón> <archivo>` → Busca un patrón en un archivo.
  - `grep -r <patrón> <directorio>` → Búsqueda recursiva en un directorio.
- `wc <archivo>` → Cuenta palabras, líneas y caracteres en un archivo.
  - `wc -l` → Cuenta líneas.
  - `wc -w` → Cuenta palabras.
  - `wc -c` → Cuenta caracteres.

---

### Redirección y Pipes

- `<` → Redirige la entrada de un comando desde un archivo.
  - `ls -l < directorio.txt` → lista el contenido del directorio especificado dentro del archivo.
- `>` → Redirige la salida a un archivo (sobreescribe).
  - `ls > lista.txt` → guarda la lista de archivos en listaArchivos.txt.
- `>>` → Añade la salida a un archivo sin borrar contenido previo.
  - `echo "texto" >> archivo.txt` → añade "nueva linea" al final del archivo sin borrar el contenido previo
- `(Pipes) = | ` → Conecta la salida de un comando con la entrada de otro.
  - `ls | grep .txt` → muestra solo los archivos que tienen la extension .txt.

---

### Usuarios y Permisos

#### Categorías de usuarios

- **u** → Usuario (propietario).
- **g** → Grupo.
- **o** → Otros.

#### Permisos

- **r (4)** → Lectura.
- **w (2)** → Escritura.
- **x (1)** → Ejecución.

Para cada grupo de usuario (`u`, `g`, `o`), se suma el valor de los permisos asignados:

- **0** → Sin permisos (`---`)
- **1** → Solo ejecución (`--x`)
- **2** → Solo escritura (`-w-`)
- **3** → Escritura y ejecución (`-wx`)
- **4** → Solo lectura (`r--`)
- **5** → Lectura y ejecución (`r-x`)
- **6** → Lectura y escritura (`rw-`)
- **7** → Todos los permisos (`rwx`)

#### Modificación de permisos

- `chmod <permisos> <archivo>` → Cambia permisos.
- **Modo simbólico:**
  - `+ (agrega), - (elimina), = (establece perimisos explicitamente; lo que supone eliminar los que no se indiquen, si es que los tenia)`
  - `chmod u+x archivo` → Agrega permiso de ejecución al propietario.
  - `chmod u=rw,g=r,o= archivo.txt`
  - `chmod ug+rw archivo.txt`
- **Modo octal:**
  - `chmod 777 archivo.txt` → Todos los permisos para todos.
  - `chmod 755 archivo.txt` → Permisos completos para usuario, solo lectura/ejecución para grupo y otros.
  - `chmod 644 archivo.txt` → Lectura/escritura para usuario, solo lectura para grupo y otros.

### Gestión de Procesos

- `ps` → Muestra procesos en ejecución.
  - `ps aux` → Lista extendida de procesos.
  - `ps -ef` → Lista estándar de procesos.
- `kill <PID>` → Mata un proceso por su ID.
- `top` → Muestra procesos en ejecución en tiempo real.
- `pstree` → Muestra procesos en forma de árbol.

---

## Practica 1: Comandos del sistema operativo

### Ayuda:

- Ejercicio 1: Utiliza man para obtener información sobre el comando ls. → `man ls`
- Ejercicio 2: Busca información sobre un comando relacionado con archivos utilizando apropos. → `apropos file`

### Rutas y directorios:

- Ejercicio 3: Utiliza pwd para mostrar la ruta absoluta del directorio actual. → `pwd`
- Ejercicio 4: Crea un directorio llamado practica en el directorio actual usando mkdir. → `mkdir practica`

### Gestión del software:

- Ejercicio 5: Actualiza la lista de paquetes disponibles utilizando sudo apt update. → `sudo apt update`
- Ejercicio 6: Instala el paquete "nano" utilizando sudo apt install nano. → `sudo apt install nano`

### Gestión de hardware:

- Ejercicio 7: Muestra información sobre la memoria libre en el sistema utilizando free. → `free` / `free -h` → mejor visualizacion
- Ejercicio 8: Lista los dispositivos USB conectados utilizando lsusb. → `lsusb`

### Acceso a información de archivos:

- Ejercicio 9: Muestra el contenido del archivo texto.txt utilizando cat. Si no
  existe, puedes crearlo con un editor de texto como nano haciendo nano
  texto.txt (rellénalo con la información que quieras y guarda los cambios). → `cat texto.txt`
- Ejercicio 10: Utiliza grep para buscar la palabra error en el archivo anterior.
  Después utiliza el mismo comando para buscar una palabra que sepas que sí
  contiene. → `grep error texto.txt`

### Redirección y combinación de comandos:

- Ejercicio 11: Redirige la salida del comando ls al archivo listaArchivos.txt
  utilizando >. Comprueba que ha funcionado correctamente abriendo el archivo o
  mostrando su contenido. → `ls > listaArchivos.txt`
- Ejercicio 12: Utiliza pipes (|) y el comando wc para contar el número de líneas de
  los archivos perros.txt y gatos.txt del directorio actual. Si los archivos no
  existen, créalos y rellénalos con varias líneas de tu elección. → `cat perros.txt gatos.txt | wc -l` / en caso de no existir `nano documento.txt`

### Usuarios y permisos:

- Ejercicio 13: Cambia los permisos del archivo documento.txt para que el
  propietario pueda leer y escribir utilizando chmod. Si no existe, puedes crearlo
  con un editor de texto, o utilizar otro archivo que exista. → `chmod 600 documento.txt` o bien `chmod u+rw documento.txt` / en caso de no existir `nano documento.txt`
- Ejercicio 14: Lista los permisos de todos los archivos en el directorio actual utilizando ls -l. → `ls -l`

### Gestión de procesos:

- Ejercicio 15: Muestra una lista de todos los procesos en ejecución utilizando ps. → `ps aux`
- Ejercicio 16: Utiliza top para mostrar los procesos en ejecución y su uso de recursos.→ `top`
