# Hilos gruesos entre piezas (Strining)

Este problema de impresión tiene un aspecto similar al *Hairy print*, problema detallado en el punto anterior de este manual.

El strining se caracteriza por la presencia de hilos gruesos, con excedente de filamento, distribuidos de forma horizontal. Puede aparecer, bien durante la impresión simultanea de varias piezas de forma, o bien durante la impresión de una única pieza que posea una morfología con espacios o partes diferenciadas.

Los orígenes de este problema son más claros que los del *Hairy print*. Se debe prestar atención a los siguientes aspectos de la impresora si se quiere evitar este encordado.


### **1- Velocidad y temperatura**

Como es habitual en la mayoría de problemas de impresión, los principales parámetros a revisar son la velocidad y la temperatura.

Para evitar la aparición del Strining se recomienda no trabajar a velocidades bajas y a temperaturas altas. De este modo evitaremos que se formen hilos gruesos y que haya excedente de material, respectivamente.


### 2- Retracción

Otro método efectivo para evitar el encordado en nuestra/s pieza/s es la activación de la retracción de nuestro extrusor. Activando esta función, la impresora retrae una pequeña parte del filamento antes de desplazarse por las zonas de la pieza en las que no tiene que extruir material.

En el software Repetier-Host, podemos activar esta función siguiendo las siguientes instrucciones:

*Slicer>Configure>PrinterSettings>General>Advanced>UseFirmwareRetraction*

También podemos activar la casilla de "retraer solo cuando se cruzan perímetros" siguiendo las siguientes instrucciones:

*Slicer>Configure>PrintSettings>Infill>Advanced>OnlyRetractWhenCrossingPerimeters*

