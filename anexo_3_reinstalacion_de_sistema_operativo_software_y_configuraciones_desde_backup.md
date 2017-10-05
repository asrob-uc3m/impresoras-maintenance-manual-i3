# ANEXO 3: Reinstalación de sistema operativo, software y configuraciones desde backup

Debido a un **cambio en uno de los equipos** del laboratorio, se va a proceder a un **cambio el sistema operativo** y en el software de control de la impresora.
Dado que el cambio de equipo llevado a cabo, ha sido la sustitución del equipo de control de Hija Resurection, por un equipo clon al de Blacky, con las misma especificaciones de Hardware, se ha llevado a cabo un clonado de disco duro con el fin de minimizar costes y tiempos.
Por lo tanto, las especificaciones de Hardware y Software de ambos equipos son idénticas.
Una vez realizado el check en ambos equipos, se ha procedido con un backup de seguridad en un único fichero, almacenando en el mismo, tanto el S.O, como el software instalado y configuraciones.
Por ello, en caso de suceder cualquier tipo de conflicto que no pueda ser resuelto con facilidad y se requiera un correcto funcionamiento del equipo en breve, se puede proceder con la reinstalación completa del equipo.

### 1- Herramientas de backup

Para el proceso de backup del sistema completo, se ha empleado la herramienta fsarchiver (fsa), la cual puede descargarse en caso de ser necesario desde el acceso ([descargar](http://www.fsarchiver.org/). A su vez, puede ejecutarse desde una distro Live de Ubuntu Xenial o anterior, facilitada en el link ([descargar](http://releases.ubuntu.com/16.04/).
Respecto al fichero backup a reinstalar, puede accederse en ( Pendiente ).

### 2- Restauración del S.O en una partición arrancable

## Crear una particion nueva a partir de la reducción de otra partición:

Lo primero que deberemos de tener es un sistema operativo booteable desde el USB para que pueda ejecutarse de forma independiente de los discos duros. De esta forma podremos modificar las particiones del disco duro sin ningún tipo de impedimento. Utilizaremos Ubuntu como S.O y lo instalaremos en un USB. Nada más arrancarlo, abrimos la terminal y escribimos setxkbmap es,es el cual nos permite configurar el teclado a nuestro idioma.
Lo siguiente que haremos será descargar gparted: sudo apt-get install gparted
Arrancamos escribiendo en la terminal: sudo gparted. Una vez abierto, seleccionamos la partición donde se encuentra instalado el S.O, nos vamos al menú principal y seleccionamos Partition > Resize/Move. En Free space preceding (MiB) indicamos el tamaño que queremos que tenga la nueva partición. En nuestro caso hemos decidido indicar una partición de aproximadamente 20 GiB (20.480 MiB). Una vez creada la nueva partición, la formateamos en el formato correspondiente pulsando sobre el menú Partition > Format to > ext3/ext4 y aplicamos los cambios pulsando sobre el tick verde. El formato a aplicar será ext3 o ext4 según el caso. Para saber cual tenemos que utilizar, nos fijaremos en el sistema de ficheros utilizado por la partición principal donde se encuentra instalado linux y utilizaremos el mismo sistema de ficheros para que no haya conflictos.

## Cómo instalar el S.O (copia) en la nueva partición

Pasaremos a restaurar la copia de seguridad en la partición que hemos formateado. Para ello utilizaremos el programa fsarchiver. Nos situamos en la ruta donde se encuentra el archivo de copia con extensión fsa. A partir de aquí, deberemos conocer cual es la partición sobre la que queremos restaurar la copia. Podemos conocer las particiones que disponemos con el tecleando el comando: sudo fdisk -l. En nuestro caso, la partición tendrá la nomenclatura /dev/sda3. Es importante que esta partición esté sin montar para que fsarchiver no nos dé errores.
Una vez conocemos la partición, utilizaremos el programa fsarchiver de la siguiente forma: sudo fsarchiver -v restfs /nombreCopia.fsa id=0,dest=/dev/sda3
Una vez creada la nueva copia de seguridad, tendremos que modificar los UUIDs. Para poder consultar los UUIDs de cada partición, utilizaremos el comando: sudo blkid. Al ejecutarlo, podremos observar que los UUIDs de las particiones /dev/sda1 y /dev/sda3 (partición principal y partición copia) contienen el mismo número de identificación. Cuando se clonan discos en linux, si hay un disco clonado habrá dos discos con UUIDs iguales, y esto confundirá a el grub. Esto es porque grub busca la raiz según el UUID de partición, al arrancar linux, realizando un arranque aleatorio de estas clonaciones, lo que	significa que nunca se sabrá cual de las dos particiones clonadas se arranco. Es por ello que deberemos de cambiar las UUIDs para solventar esto. Ejecutaremos por tanto la siguiente linea en el terminal: sudo tune2fs /dev/sda3 -U random la cual asignará un número de serie aleatorio a dicha partición (/dev/sda3). A continuación, confirmamos que el número de serie ha cambiado correctamente con el comando: sudo blkid.
Lo siguiente que deberemos hacer es añadir al menú de grub la nueva partición de arranque. Para esto, editaremos el fichero: /etc/grub.d/40_custom en el cual incluiremos las instrucciones necesarias que permitirán ser incorporadas posteriormente en el fichero de configuración de grub: /boot/grub/grub.cfg Un ejemplo de lo que debemos de incluir en el fichero /etc/grub.d/40_custom es lo siguiente:

---------------------------------------------------------------------------------------------------

menuentry ‘Lubuntu, 14.04.1‘{
insmod part_msdos
insmod ext2 
set root='(hd0,msdos6)’
search –no-floppy –fs-uuid –set 2f16be23-6dff-4872-a1c5-367d364c9f71
linux /boot/vmlinuz-2.6.32-5-686 root=UUID=2f16be23-6dff-4872-a1c5-367d364c9f71 ro quiet
initrd /boot/initrd.img-2.6.32-5-686
} 

-------------------------------------------------------------------------------------------------

− En Lubuntu, 14.04.1 pondremos el nombre que queramos que aparezca en el Grub
− En hd0,msdos6 habrá que poner el disco duro y la partición en la que se encuentra el S.O Linux, donde:
− hd0 sería el primer disco duro, o sea sda.
hd1 sería en segundo disco duro, o sea sdb y así sucesivamente
− msdos1 sería la primera partición del disco duro
msdos2 sería la segunda partición del disco duro y así sucesivamente
Por lo tanto hd0,msdos6 sería el primer disco duro y la sexta partición (sda6)
− En 2f16be23-6dff-4872-a1c5-367d364c9f71 pondríamos el UUID de la partición donde se encuentra el S.O Linux, que lo veríamos abriendo un terminal y usando el comando blkid
− Por último donde pone /boot/vmlinuz-2.6.32-5-686 y /boot/initrd.img-2.6.32-5-686 obviamente nos dirigiremos a la partición donde se encuentra el S.O Linux que queremos poner en el Grub, nos dirigiremos a el directorio /boot/ y pondremos el vmlinuz y el intrd.img con el número que corresponda (si lo tiene) aunque también nos valen los que se encuentran en la raíz del sistema de archivos.
Lo guardamos y cerramos. Ahora actualizaremos grub con el comando: sudo update-grub2

## Eliminar entradas residuales del menú de Grub

Si queremos que el menú de arranque de Grub aparezca más limpio (eliminar entradas repetidas del kernel o aquellas que no utilizamos) podemos hacerlo modificando el fichero: “/boot/grub/grub.cfg”, de forma que comentaremos el código de aquellas partes que corresponden a lineas que no queremos que aparezcan en el menú. ¡OJO! es muy importante realizar previamente una copia de este fichero, por si cometiésemos algún error en la modificación del mismo. Se recomienda comentar las lineas en vez de eliminarlas, por si tuviéramos que corregir alguna modificación.

Para más información, fuente ([UC3M Robots](http://robots.uc3m.es/index.php/Tutorial:_C%C3%B3mo_restaurar_un_S.O_en_una_partici%C3%B3n_arrancable).
