# La impresora no suministra la cantidad de plástico necesaria (subextrusión)


Si la impresora no suministra la cantidad de plástico necesaria para la impresión, conviene focalizar el origen del problema, ya que puede deberse a motivos muy diversos:


### 1- **Diámetro del filamento**

Debemos indicar a nuestro software *Repetier-Host*el **diámetro correcto** de nuestro filamento. En el caso de las impresoras *Blacky* e *Hija Resurection*, el diámetro recomendado para su buen funcionamiento es de **1,75 mm**. Indicar un valor erróneo de este parámetro podría producir problemas de extrusión.


### 2- **Material del filamento**

Cada plástico que se use va a exigir unas determinadas condiciones de impresión. En el caso de utilizar **ABS**, se debe tener en cuenta que es un plástico sensible a los cambios de temperatura y que generalmente las temperaturas de trabajo van a ser relativamente altas (Extrusor: 230ºC; Plataforma base: 120ºC), y la impresión por lo tanto va a ser más lenta. Por otra parte, en el caso de utilizar **PLA**, debemos tener en cuenta que necesita temperaturas de producción más bajas y que se trata de un plástico más estable ante los cambios de temperatura, por lo que podemos ejecutar una impresión más rápida sin afectar al buen funcionamiento de nuestro extrusor. Puede encontrar más información al respecto en el siguiente apartado: *Importancia de las temperaturas*.

Se recomienda, por lo tanto, el uso de PLA sobre el de ABS en calidad de producción, mas se debe tener en cuenta la desventaja competitiva del primero sobre el segundo en referencia a postproducción, por tratarse este de un material frágil que no admite taladrado.

<img src="image1.JPG" alt="image1" height="250" width="250" align="middle">

*Figura 1: 3D Printer Filament PLA utilizado en el Despartamento de Sistemas y Automática para estas impresoras.*


### 3- **Velocidad de la impresora**

Es importante estimar la velocidad a la que nuestras impresoras trabajan de forma eficaz, pues una de las causas más comunes de una mala extrusión es una **velocidad excesiva** de impresión.

Los valores recomendados para el PLA se encuetran entre 2,5 y 5 mm^3/s. Igualmente, la mayoría de plasticos darán buenos resultados **por debajo de 5mm^3/s**.

Una fórmula útil para estimar la velocidad real de nuestra impresora es usar la siguiente fórmula:

*[diámetro de nozzle (mm)] x [altura de capa (mm)] x [Velocidad de extrusión (mm/s)] <=5mm3/s*


