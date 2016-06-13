# La impresora no suministra la cantidad de plástico necesaria (Subextrusión)


Si la impresora no suministra la cantidad de plástico necesaria para la impresión, conviene focalizar el origen del problema, ya que este problema en concreto puede deberse a motivos muy diversos:


### 1- **Diámetro del filamento**

Debemos indicar a nuestro software *Repetier-Host*el **diámetro correcto** de nuestro filamento. En el caso de las impresoras *Blacky* e *Hija Resurection*, el diámetro recomendado para su buen funcionamiento es de **1,75 mm**. Indicar un valor erróneo de este parámetro podría producir problemas de extrusión, ya que el valor de diámetro que especifiquemos en el software determinará la cantidad de filamento que la impresora va a extruir. Errores en su determinación pueden derivar en atascos del extrusor o bien en huecos en la pieza, dependiendo de si el error está por debajo o por encima del valor real.

Se recomienda comprobar el diámetro del filamento adquirido, pues la medida que se especifica en el producto -en nuestro caso 1,75 mm- hace referencia al diámetro de nuestro tubo extrusor, por lo que en teoría el diámetro del filamento debería estar por debajo de este valor.


### 2- **Material del filamento**

Cada plástico que se use va a exigir unas determinadas condiciones de impresión. En el caso de utilizar **ABS**, se debe tener en cuenta que es un plástico sensible a los cambios de temperatura y que generalmente las **temperaturas de trabajo** van a ser **relativamente altas** (Extrusor: 230ºC; Plataforma base: 120ºC), y la impresión por lo tanto va a ser más lenta. Por otra parte, en el caso de utilizar **PLA**, debemos tener en cuenta que necesita temperaturas de producción más bajas y que se trata de un plástico más **estable** ante los cambios de temperatura, por lo que podemos ejecutar una impresión más rápida sin afectar al buen funcionamiento de nuestro extrusor. 

Se recomienda, por lo tanto, el uso de PLA sobre el de ABS en calidad de producción, mas se debe tener en cuenta la desventaja competitiva del primero sobre el segundo en referencia a postproducción, por tratarse este de un material frágil que no admite taladrado.

<img src="image1.JPG" alt="image1" height="250" width="250" align="middle">

*Figura 4: 3D Printer Filament PLA utilizado en el Despartamento de Sistemas y Automática para estas impresoras.*


### 3- **Velocidad de la impresora**

Es importante estimar la velocidad a la que nuestras impresoras trabajan de forma eficaz, pues una de las causas más comunes de una mala extrusión es una **velocidad excesiva** de impresión.

Los valores recomendados para el PLA se encuetran entre 2,5 y 5 mm^3/s. Igualmente, la mayoría de plasticos darán buenos resultados **por debajo de 5mm^3/s**.

Una fórmula útil para estimar la velocidad real de nuestra impresora es usar la siguiente fórmula:

*[diámetro de nozzle (mm)] x [altura de capa (mm)] x [Velocidad de extrusión (mm/s)] <=5mm3/s*

Para comprobar o cambiar el **valor teórico** de la velocidad de impresión de nuestra impresora 3D, se deben seguir las siguientes instrucciones dentro del software:

*Slicer>Configure>PrintSettings>Speed*

Aquí encontraremos todos los parámetros relacionados con la velocidad y la aceleración de producción.


### 4- Temperaturas vs. Material/Presión

Es un requisito imprescindible que la temperatura de trabajo sea la adecuada tanto en relación al tipo de plástico como a la velocidad elegida.

Varios factores influyen en la elección de la temperatura correcta, teniendo en cuenta las siguientes premisas:

1. A **mayor velocidad** de impresión, **menor tiempo de calentamiento** del filamento. Luego a altas velocidades conviene elevar ligeramente la temperatura del extrusor.
2. Materiales especialmente viscosos, como puede ser el caso del PLA en comparación con el ABS, pueden exigir **presiones altas** para su extrusión, provocando de este modo problemas de subextrusión e incluso obstrucciones en la salida del filamento. En este caso también se recomienda elevar ligeramente la temperatura del extrusor para facilitar el flujo del plástico.
3. Temperaturas elevadas por encima de las recomendaciones del fabricante y velocidades altas son causa directa de **peor calidad** de impresión (encordados, voladizos...).

Téngase en cuenta que excederse en elevar la temperatura de determinados plásticos puede resultar en la modificación de sus propiedades, se pueden quemar y podemos obstruir la impresora.


### 5- Filamento viciado

Si el filamento tiene una curvatura muy acentuada, este puede provocar fricciones al recorrer el tubo del extrusor, lo que tendría como consecuencia una extrusión más entrecortada y dificultosa. Conviene, por lo tanto, asegurarse de que la curvatura de nuestro filamento no impide que la extrusión se realice correctamente y rectificar esta característica en la medida de los posible (no olvidemos que el PLA es un plástico muy frágil y no tolera bien esfuerzos de flexión en frío). 

### 6- Parámetro multiplicador del extrusor

Una de las posibles soluciones y a la vez posible fuente de error relacionada con la subextrusión es el valor concedido al parámetro multiplicador del extrusor.

Si consideramos que nuestra impresora, a pesar de tener todos los ajustes anteriores en un estado correcto, sigue sin extruir la cantidad de material necesaria, podemos variar la **cantidad de plástico** que **extruye** por defecto en el siguiente apartado de ajustes:

*Slicer>Configure>FilamentSettings>PrinterSettings>Filament>ExtrusionMultiplier*

Se debe tener en consideración que el valor normal de este parámetro asociado a los plásticos más comúnmente usados, PLA y ABS, son de 0,9 y 1 respectivamente.

