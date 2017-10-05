# ANEXO 2: Configuración del software de impresión

Será necesario configurar el software de impresión para poder utilizar las impresoras. A continuación se detallan los procedimientos para configurar tanto *Cura* como *Repetier-Host*.


### 1- Configuración *Cura*

Antes de proceder a la configuración, debemos [descargar](https://github.com/tumaker/Config-files), si no los tenemos ya, unos **archivos .ini** con la configuración de las impresoras. Usaremos esos perfiles para la configuración, siguiendo los siguientes pasos:

1. Copiar los **archivos de configuración** de la impresora, si es que estos nos son útiles, en la carpeta del programa que se ha creado en la instalación. Usualmente, en Windows, esta carpeta estará ubicada en el **disco C**, en *Archivos de programa (x86)*. Allí seguiremos las siguientes instrucciones: *Resources->machine_profiles*. En Lubuntu seguiremos las siguientes instrucciones: */usr/share/cura/resources/machine_profiles*. Dentro de la carpeta ***machine profiles*** pegaremos los archivos copiados. (Si este archivo no nos es útil siempre podemos abrirlo y modificarlo manualmente, para así poder modificar todos los ajustes importantes de la impresora manualmente).

2. Abrimos *Cura*. En la guía de configuración que aparecerá, se nos pedirá que indiquemos el **modelo** de nuestra impresora. Entraremos en la pestaña *Machine* y seleccionaremos la opción *Other* y el modelo** Voladora V2** en nuestro caso (ya que nuestras impresoras tienen un único extrusor). 


### 2- Configuración *Repetier-Host*

Para la configuración de *Repetier-Host* en los nuevos PCs podremos hacer uso de los archivos de configuración presentes en el disco C: de los ordenadores antiguos.

Los archivos fundamentales que necesitaremos serán los siguientes **archivos de configuración de inicio**, que copiaremos en la **misma ubicación** de la cual los hemos obtenido, en el nuevo ordenador:

* ***slic3r.ini*** - Ubicado en: *Repetier-Host*
* ***custom.ini*** - Ubicado en: *Repetier-Host->data*
* ***config.ini*** - Se puede conseguir siguiendo las siguientes instrucciones dentro del programa *Repetier-Host*: *Slicer->Configure->File->ExportConfig...*

Ambos archivos contiene la información de configuración que se indicó en su momento en el software de impresión con el que trabajábamos anteriormente.

* **CONFIGURACIÓN MANUAL DE *REPETIER-HOST* PARA VOLADORA V2**

Desde dentro del programa, pulsaremos el botón de la esquina superior derecha *Configurar Impresora*. Encontraremos cuatro pestañas.

1. **Pestaña conexión:** 
 * Connector: Conexión Serie.
 * Puerto: Aquel en el que tengamos conectada la impresora.
 * Baudrate: 250000.
 * Protocolo de transferencia: Autodetect.
 * Reinicio al conectar: DTR low->high->low
 * Reiniciar en emergencia: Envia el comando de emergencia y reconecta.
 * Cache Recep: 63

2. **Pestaña Impresora (valores usados en el laboratorio):**
  * Velocidad Desplazamiento sin extruir: 4800
  * Velocidad Avance del Eje Z: 100
  * Temperatura precalentamiento Extrusor: 180 (Se recomienda no superar la temperatura de 240ºC, debido a las limitaciones físicas del extrusor)
  * Temperatura precalentamiento Plataforma: 50
  * Número de Extrusores: 1
  * Comprobar cada 3 segundos
  * Posición de Reposo X, Y, Z: 85, 170, 0
  * Añadir tiempo de Impresión: 8
  * Tener marcadas todas las casillas menos: Eliminar comandos M105 del Registro.

3. **Pestaña Dimensiones Impresión:**
  * Printer Type: Impresora cartesiana
  * Reposo X, Y, Z: (Min)
  * X,Y (Min): 0
  * X,Y (Max): 170
  * X,Y (Coord. Plat): 0
  * Anchura area de impresión: 190
  * Profundidad area de impresión: 170
  * Altura area de impresión: 180
  
4. **Pestaña Avanzado:**
  * Ruta de Filtrado y Parámetro: yourFilter #in #out
  * No marcar nada

Después de esto, salimos de la configuración de la impresora y en la **pestaña Slicer**, en el programa principal, indicamos lo siguiente:
   * Slice: Slic3r
   * Print Setting: Normal Print
   * Printer Settings: 0.4mm Extruder
   * Extrusor 1: PLA 1.75mm (si estamos trabajando con PLA)
   * Layer Height: 0.3mm
   * Infill Density: 25%
   * Infill Angle: 45º
   * Marcar: Override Slice3r Settings Y Enable Cooling
   * Resto de ajustes al gusto del usuario

El resto de ajustes se configurarian pulsando el **botón Configure** de la **pestaña Slicer**. Estos ajustes son los más extensos y se incluyen en el archivo ***slic3r.ini*** o ***config.ini*** que puede encontrarse en el [repositorio de ficheros de configuración](https://github.com/asrob-uc3m/impresoras-asrob) de las impresoras del Laboratorio de Robótica de la UC3M.






