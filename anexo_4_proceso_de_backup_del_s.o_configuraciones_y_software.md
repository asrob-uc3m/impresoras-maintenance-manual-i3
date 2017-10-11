# ANEXO 4: Proceso de backup del Sistema Operativo, configuraciones y software

Con el fin de facilitar el proceso llevado a cabo para la realización del backup del s.o, configuraciones y software de los equipos del laboratorio de ASROB, se facilita el presente documento.

### 1- Herramientas de backup

Para llevar a cabo el proceso de backup del sistema completo, se ha empleado la herramienta Clonezilla. Clonezilla es un software libre de recuperación ante desastres, sirve para la clonación de discos y particiones. Clonezilla está diseñado por Steven Shaiu y desarrollado por el NCHC Labs en Taiwán.
Durante el proceso de backup, la versión empleada fué "stable - 2.5.2-31", sin embargo, para procesos posteriores de backup y/o restauración, puede emplearse la versión actual, dado que se trata de un sofware retrocompatible.
Clonezilla puede descargarse en caso de ser necesario desde el acceso ( [descargar](http://clonezilla.org/downloads.php) ). 

<img src="Clonezilla.png" alt="lub1" height="300" width="400" align="middle">

*Figura 1: Descarga de DVD Live Clonezilla*

### 2- Proceso de backup

Para poder llevar a cabo el proceso de backup correctamente, las instrucciones recomendadas a seguir serán las siguientes:

1. Descarga de la imagen de la distro Live de Clonezilla desde el acceso ( [descargar](http://clonezilla.org/downloads.php) ). 
2. Quemado de la imagen en un dispositivo que permita un arranque posteriormente, tales como USB, CD o DVD ( Permite el arrque desde partición de disco, arranque de red y semejantes, sin embargo requerirá de preconfiguración adicional ).
NOTA:
Se recomienda grabación en CD o DVD, debido a problemas de reconocimiento de los dispositvos modernos.

3. Insertar el DVD o CD en el ordenador.
4. Arranque del ordenador desde la unidad de CDROM.
5. El sistema arrancará cargando el CD Live. Debido a la leve capacidad de cómputo del PC, es normal que tarde alrededor de 30-40 segundos hasta aparecer la primera selección.

El proceso de backup
<img src="ubuntu_xenial.png" alt="lub1" height="300" width="400" align="middle">

*Figura 2: Ubuntu Xenial Live*

<img src="proceso_de_backup.png" alt="lub1" height="500" width="400" align="middle">

*Figura 3: Proceso de backup*
