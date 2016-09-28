# Problemas relativos a la instalación de Lubuntu


La instalación del OS Lubuntu en ciertos equipos puede ocasionar problemas relacionados, principalmente, con el buen funcionamiento del monitor.

### 1- **Monitor fuera de rango**

Si aparece el mensaje "monitor out of range" o " monitor fuera de rango" cada vez que se inicia el equipo, impidiéndonos entrar en el sistema con normalidad, se deberá proceder como se explica a continuación:

1. Mantener pulsado ESC mientras se inicia el equipo hasta que salgan varias opciones relacionadas con el arranque de Lubuntu.
2. Entrar al sistema operativo desde el modo *Recovery*, haciendo un *boot* normal.
3. Abrir el terminal de Lubuntu y escribir lo siguiente:
 1. ls 
 2. nano /etc/grub.d/10 linux
4. En el código que saldrá en pantalla a continuación, debemos encontrar las lineas que se muestran en la figura 21 y comprobar que el codigo es **idéntico** a este. Lo que habremos de modificar será la parte en la que incluiremos el *vga=normal nomodeset \$vt_handoff*.

<img src="lub3.JPG" alt="lub3" height="100" width="400" align="middle">

*Figura 21: Código terminal Lubuntu para solucionar problema de monitor fuera de rango*

Después de estos ajustes el problema no debería persistir; si persiste, póngase en contacto con el personal especializado.



---


### 2- **Resolución del monitor**

Otro de los errores con los que nos podemos encontrar es con una baja resolución de pantalla (*640x480 píxeles*), sin opción de modificación mediante el procedimiento convencional (*preferences -> monitor settings*).

Una de las opciones más simples y rápidas, llevada a cabo existosamente en el equipo que opera con la impresora *Blacky*, es la que se detalla a continuación:


1. Ejecutar el terminal.
2.  Escribir: ***sudo leafpad /etc/default/grub***.
3. Cambiar (solo para grub-pc) *♯GRUB_TERMINAL=console* por ***GRUB_TERMINAL=console*** para desactivar terminal gráfica.
4. Activar escribiendo: ***sudo update-grub***.
5. Reiniciar ordenador.

Esta solución resolverá el problema de resolución del monitor con el único y poco significativo inconveniente de la desaparición del logotipo de Lubuntu al inicio del sistema.






