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

* **CONFIGURACIÓN MANUAL DE REPETIER-HOST PARA VOLADORA V2**

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
  * Temperatura precalentamiento Extrusor: 180
  * Temperatura precalentamiento Plataforma: 50
  * Número de Extrusores: 1
  * Comprobar cada 3 segundos
  * Posición de Reposo X, Y, Z: 85, 170, 0
  * Añadir tiempo de Impresión: 8
  * Tener marcadas todas las casillas menos: Eliminar comandos M105 del Registro.

3. Pestaña Dimensiones Impresión

Extruder y Dimensiones impresora para Voladoras V2
Repetier config simple.jpg

De esta manera tenemos que configurar para las impresoras con un solo cabezal. 

Número de Extrusores: 1
Diameter: Aquí especificaremos de que tamaño es la salida del cabezal. Las Tumaker Voladoras se venden con boquilla de 0,4mm de diametro pero en caso de haber solicitado alguna especial habrá que anotarlo en esta casilla. 
Reposo: Las opciones del reposo x, reposo y, y reposo z tienen que estar como en la ilustración, Min, Max y 0 respectivamente.
Xmax, Ymax: Para indicar a la máquina donde esta el límite de movimiento de los ejes es importante definir Xmax= 220, Ymax= 210.
Anchura, profundidad y altura: La superficie imprimible es de 220 x 210 x 190






