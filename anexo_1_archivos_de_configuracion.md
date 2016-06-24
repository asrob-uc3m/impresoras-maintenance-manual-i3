# ANEXO 2: Configuración del software de impresión

Será necesario configurar el software de impresión para poder utilizar las impresoras. A continuación se detallan los procedimientos para configurar tanto *Cura* como *Repetier-Host*.


### 1- Configuración Cura

Antes de proceder a la configuración, debemos [descargar](https://github.com/tumaker/Config-files), si no los tenemos ya, unos **archivos .ini** con la configuración de las impresoras. Usaremos esos perfiles para la configuración, siguiendo los siguientes pasos:

1. Copiar los archivos de configuración de la impresora en la carpeta del programa que se ha creado en la instalación. Usualmente esta carpeta estará ubicada en el **disco C**, en *Archivos de programa (x86)*. Allí seguiremos las siguientes instrucciones: *Resources->**machine_profiles***. Dentro de esta última carpeta pegaremos los archivos copiados.

2. Abrimos Cura. En la guía de configuración que aparecerá, se nos pedirá que indiquemos el **modelo** de nuestra impresora. Entraremos en la pestaña *Machine* y seleccionaremos la opción *Other* y el modelo** Voladora V2** en nuestro caso (ya que nuestras impresoras tienen un único extrusor). 


### 2- Configuración Repetier-Host

Para la configuración de Repetier-Host en los nuevos PCs podremos hacer uso de los archivos de configuración presentes en el disco C: de los ordenadores antiguos.

Los archivos fundamentales que necesitaremos serán los siguientes **archivos de configuración de inicio**, que copiaremos en la **misma ubicación** de la cual los hemos obtenido, en el nuevo ordenador:

* *slic3r.ini* - Ubicado en: Repetier-Host
* *custom.ini* - Ubicado en: Repetier-Host -> data

Ambos archivos contiene la información de configuración que se indicó en su momento en el software de impresión con el que trabajábamos anteriormente.

* **CONFIGURACIÓN MANUAL DE REPETIER-HOST**

p





