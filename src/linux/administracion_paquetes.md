# Administración de paquetes
## Distribuciones Linux
## Los paquetes y sus gestores
En cualquier distribución, los paquetes son el elemento básico para tratar las tareas de instalación
de nuevo software, actualización del existente o eliminación del no utilizado.
Básicamente, un paquete es un conjunto de archivos que forman una aplicación o una unión de
varias aplicaciones relacionadas, normalmente formando un único archivo (denominado paquete),
con un formato propio y normalmente comprimido.

Si bien un mismo programa puede estar disponible para miles de distribuciones, el paquete con el
cual se instala en cada una de ellas puede ser distinto. Cuando hablamos de paquete nos referimos
al formato o extensión del archivo, el cual es usado por el sistema operativo para instalar un
programa. Para que la distribución pueda usar ese archivo debe tener también un gestor de
paquetes, el cual posee las herramientas para instalar, modificar o eliminar dicho programa.

Algunos formatos de paquetes son:
* .deb: usado por Debian y sus derivados.
* RPM: (Red Hat Package Manager) originario de Red Hat y usado extensivamente por
muchas otras como Fedora, OpenSUSE, Mandriva, Mageia y otros.
* MO: de Slax.
* PUP y PET: Puppy Linux.
* .txz: Slackware

Y algunos de los gestores de paquetes más conocidos:
* APT (terminal) y Synaptic (gráfico): usado por Debian y sus derivados.
* Zypper (terminal) y YaST (gráfico): el gestor de OpenSUSE.
* YUM: Red Hat, Fedora, CentOS y Yellow Dog Linux.
* dpkg: creado originalmente por Debian.
* Urpmi: Mandriva y Mageia.
* slapt-get, slackpkg y swaret: diversas “herramientas” que usa Slackware para trabajar con paquetes tgz.

### Gestor de paquetes
El uso de paquetes facilita añadir o quitar software al considerarlo una unidad y no tener que
trabajar con los archivos individuales.
Normalmente, para la instalación de un paquete será necesario efectuar una
serie de pasos:
* Previo (preinstalación): comprobar que existe el software necesario, versiones correctas y dependencias.
* Descomprimir el contenido del paquete, copiando los archivos a sus localizaciones definitivas.
* Postinstalación: retocar los archivos necesarios, configurar posibles parámetros del software, adecuarlo al sistema, etc.

Dependiendo de los tipos de paquetes, estos pasos pueden ser automáticos en su mayoría (así es en el caso de RPM y DEB), o pueden necesitar hacerlos todos a mano (caso .tgz).

Dependiendo de la distribución encontramos diferentes gestores de paquetes: apt y dpkg para Debian y Ubuntu; dnf, yum y rpm para RHEL, Fedora y CentOS.

#### Gestores de paquetes de Debian y sus derivados (Ubuntu, Kali, etc): apt y dpkg

El gestor de software **apt** (Advanced Package Tool), permite gestionar los paquetes a través de una lista de paquetes actuales y disponibles a partir de varias fuentes de software. La configuración del sistema apt se efectúa desde los archivos disponibles en ```/etc/apt```, donde ```/etc/apt/sources.list``` es la lista de fuentes disponibles.

##### Algunas funciones básicas.
* Instalación:
```bash
apt-get install paquete
```
* Desinstalación:
```bash
apt-get remove paquete
```
* Borrado también de archivos de configuración:
```bash
apt-get purge paquete
```
* Actualización de la lista de paquetes:
```bash
apt-get update
```
* Actualización de la distribución, se pueden usar los pasos combinados:
```bash
apt-get update
apt-get upgrade
apt-get dist-upgrade
```
* Buscar:
```bash
apt-cache search paquete
```
* Paquetes instalados:
```bash
apt list --installed
```

El comando de más bajo nivel es **dpkg**. Pueden realizarse todo tipo de tareas, de información, instalación, borrado o cambios internos a los paquetes de software.

* Instalación:
```bash
dpkg -i paquete
```
* Desinstalación:
```bash
dpkg -r paquete
```
* Lista de todos los paquetes instalados:
```bash
dpkg -l
```
* Verifica si un paquete está instalado:
```bash
dpkg -l paquete
```
* Lista de archivos de un paquete ya instalado:
```bash
dpkg -L paquete
```

##### Instalación de R en el servidor
Para instalar R, ejecutamos las siguientes instrucciones:
```bash
sudo apt update
sudo apt-get install r-base-dev
```
##### Instalación de RStudio en el servidor (opcional)
Para instalar RStudio, ejecutamos las siguientes instrucciones:
```bash
sudo apt-get install gdebi-core
wget https://download2.rstudio.org/server/focal/amd64/rstudio-server-2023.12.0-369-amd64.deb
sudo gdebi rstudio-server-2023.12.0-369-amd64.deb
```

Verificamos el estatus del servicio de RStudio.
```bash
sudo rstudio-server status
```

Ajustamos el reenvío de puertos para poder consumir el servicio de RStudio mediante el protocolo HTTP.

Accedemos al recurso mediante la liga:
```bash
http://127.0.0.1:8787/
```

La siguiente liga es la guía para el administrador de RStudio:

https://s3.amazonaws.com/rstudio-server/rstudio-server-pro-0.99.484-admin-guide.pdf
