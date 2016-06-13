# Relleno defectuoso

Si el relleno de la pieza no se está imprimiendo correctamente, y se está obteniendo un resultado similar al de la figura 10, se deben revisar los siguientes parámetros de la impresora:

<img src="Infill.jpg" alt="infill" height="270" width="400" align="middle">

*Figura 10: Relleno Honeycomb defectuoso de pieza cúbica.*
### 1- Velocidad de impresión del relleno

Si la velocidad de impresión del relleno es muy **alta**, este probablemente no se imprimirá de forma correcta. Podemos modificar la velocidad de impresión del relleno siguiendo las siguientes instrucciones:

*Slicer>Configure>PrintSettings>Speed>SpeedForPrintMoves>Infill*


### 2- Aumentar el flujo de plástico

Para este y otros problemas relacionados con la **deficiencia** en la extrusión, consultar el apartado *La impresora no suministra la cantidad de plástico necesaria (Subextrusión)* de este manual.


### 3- Tipo de relleno

No todas las piezas ofrecen los mismos resultados antes los mismos tipos de relleno. El software Repetier-Host ofrece **7 tipos** diferentes de relleno. 

Usualmente se recomienda el relleno **Honeycomb** o relleno de panal de abeja, debido a las propiedades que este confiere a la pieza, pero se debe tener en cuenta que en piezas donde el relleno es muy estrecho, quizás nos convenga más utilizar otro tipo de relleno más adecuado, como el rectilineo.