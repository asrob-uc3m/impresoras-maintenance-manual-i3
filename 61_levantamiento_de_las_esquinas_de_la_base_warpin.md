# 6.1 Levantamiento de las esquinas de la base (Warping)

El levantamiento de las esquinas de la base un problema común al imprimir piezas de gran sección. Las esquinas tiendan a levantarse por **contracción**. Esta contracción es movidada por el contacto del plástico extruido a gran temperatura, con la cama caliente que está a una temperatura muy por debajo.

Para evitar el warping se recomienda mantener la **cama caliente** siempre a una **temperatura adecuada**, entre 50-60ºC, y **precalentarla** unos 15 minutos antes de la impresión. De igual modo, es importante el uso de laca, o de cualquier otro método de **fijación**, para garantizar que las esquinas se adhieran completamente a la mesa y no se levanten.

Como método alternativo, se pueden añadir **[soportes circulares](https://cdn.shopify.com/s/files/1/1099/7842/files/1Sin-titulo_large.png?8300428630535949442)** a las esquinas de la pieza a modo de fijación extra.

Si este problema ocurre en piezas de **no** gran sección, probablemente nuestro problema tenga origen en la **calibración** de la impresora. Si la base en la que se apoya la pieza no está bien **nivelada**, lo más seguro es que esta se despegue durante la impresión. Es conveniente, por lo tanto, dedicar unos minutos a comprobar que nuestra cama caliente está totalmente horizontal y que la distancia entre esta y el hot-end es la adecuada.

A nivel de software, se pueden activar dos funciones que nos ayudarán a evitar este problema:

* **Brim:** Básicamente es un método para combatir la tracción en la pieza basado en reforzar la fijación de la primera capa mediante la creación de una superficie a su alrededor. Se puede activar siguiendo las siguientes instrucciones:

*Slicer>Configure>PrintSettings>SkirtAndBrim>Brim>BrimWidth*

* **Raft:** Esta función se encarga de crear una superficie poco robusta debajo de la pieza para que el levantamiento lo sufra esta superficie, y no la pieza. Se puede activar siguiendo las siguientes instrucciones:

*Slicer>Configure>PrintSettings>SupportMaterial>Raft>RaftLayers*