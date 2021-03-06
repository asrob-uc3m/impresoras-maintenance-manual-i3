# 3.1 La base de la pieza no se imprime de forma homogénea

Si hay **grietas** o **lineas muy visibles** que incluso se levantan de la base en la capa inferior de nuestra pieza, tal y como ocurre en la figura 11, tendremos que revisar una serie de ajustes en nuestra impresora.

<img src="mal.JPG" alt="mal" height="300" width="400" align="middle">

*Figura 11: Capa inferior no uniforme de pieza impresa con la impresora Blacky.*

### 1- Altura de la primera capa

Si la cama caliente está **demasiado lejos** de la boquilla del extrusor (Hot-end), el plástico no se aplastará bien sobre la base y la lineas quedarán separadas, luego no tendremos como resultado una superficie de aspecto homogéneo. Conviene **ajustar el eje Z** de nuestra impresora siguiendo las *Recomendaciones Previas* de este manual.

### 2- Temperatura de impresión

Otro causante de que queden lineas separadas en la base de nuestra figura es una **temperatura de trabajo insuficiente**. Se recomienda, al trabajar con PLA, mantener la mesa alrededor de los 50ºC y el hot-end alrededor de los 180ºC, teniendo siempre en cuenta las pequeñas variaciones que puede exigir cada fabricante.

### 3- Ancho de linea en la primera capa

**Aumentando** el ancho de linea en la primera capa podremos evitar esos espacios indeseables entre lineas en la base de la figura impresa. Podemos modificar el ancho de linea de la primera capa siguiendo las siguientes instrucciones:

Slicer>Configure>PrintSettings>Advanced>ExtrusionWith<FirstLayer


### 4- Altura de la primera capa

Si la altura de la primera capa es demasiado alta, tendremos problemas con la homogeneización de esta. Conviene que esta altura **no** exceda los **0,3 mm**. Esta altura se puede modificar siguiendo las siguientes instrucciones:

*Slicer>Configure>PrintSettings>LayersAndPerimeters>FirstLayerHeight*

---


Una **impresión correcta** de la capa inferior debería tener un aspecto similar al mostrado en la figura 12. Si no logra que su impresora realice una impresión correcta de la base de la pieza siguiendo las indicaciones anteriores, contacte con el **personal de mantenimiento**.

<img src="bien.JPG" alt="bien" height="300" width="400" align="middle">

*Figura 12: Capa inferior uniforme de pieza impresa con la impresora Hija Revolution.*