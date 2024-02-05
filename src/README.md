# Introductorio a tecnologías de contenedores: Apptainer y Docker.

En este material se presenta una introducción a las Tecnologías de Contenedores, enfocándose principalmente en Docker y Apptainer. 

Los Contenedores son producto de la integración varias caracteristicas del kernel, así como del sistema de archivos y de la red. Los Contenedores administran el software que unifican estas características.

De las características del kernel, nos interesa conocer las que son esenciales para aislar procesos. En particular:

* **Namespaces** : aislan los procesos del contenedor desde la perspectiva de las características del sistema operativo como el montaje del sistema de archivos, administración de procesos, y la configuración de red.
* **Control groups** (cgroups): limita el uso de los recursos del sistema y prioriza ciertos procesos sobre otros. 
* **Capabilities** : permite a los procesos ejecutar ciertas operaciones sensibles en el kernel así como llamadas al sistema.
* **Secure computing mode** : restringe el acceso a llamadas al sistema. 

Estas características son transparentes en los sistemas **Linux**. Por tal motivo, inicialmente abordaremos la forma cómo podemos interactuar con el sistema mediante el *shell* (la linea de comandos, *CLI*-command line interface). En particular, se presenta la forma cómo se administran paquetes, se configuran usuarios y grupos, se monitorean y controlan procesos y recursos, etc. 

# Contenido
El materíal está organizado de la siguiente manera:


* Introducción a Linux
    - Instalación de máquina virtual
    - Introducción a la linea de comandos
    - Administración de paquetes
    - Configuración de usuarios y grupos
    - Jerarquía de directorios
    - Almacenamiento y sistemas de archivos
    - Gestión de archivos
    - Monitoreo y control de procesos
    - Administración y monitoreo de uso de recursos
    - Introducción a programación shell

* Virtualización
    - Máquinas virtuales
    - Contenedores
        + Docker
        + Apptainer
