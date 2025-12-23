## Instalación de Windows 11

Una vez hemos acabado la configuración de windows 11, simplemente debemos hacer la gran tarea de hacer click a `Siguiente` varias veces, esto hasta llegar al apartado del disco.

![img1](img/instWIN/inwin-img1.png)

Una vez en el apartado del disco, notamos que no nos aparece ningún disco, esto se debe ya que windows no es capaz de detectar el tipo de disco que tenemos, por lo que vamos a instalar el driver de virtio, para poder detectar el disco e instalar el SO, por lo que para ello, le damos a `Cargar Controlador`.

![img2](img/instWIN/inwin-img2.png)

Una vez dentro, Vamos a seleccionar el disco `virtio-win-X.X.XXX` Dentro de este haremos click en `amd64`>`w11` y le damos a `aceptar`. 

![img3](img/instWIN/inwin-img3.png)

Instalamos el driver y ahora nos aparecerá el disco. Ya podemos seguir con el proceso de instalación normal hasta llegar al apartado de crear una cuenta online.

![img4](img/instWIN/inwin-img4.png)

![img5](img/instWIN/inwin-img5.png)

Procedemos como siempre. 

![img6](img/instWIN/inwin-img6.png)

Ahora estamos en el apartado de crear una cuenta online o conectarla con una ya existente, por lo que si queremos, simplemente instalamos el driver como hemos hecho antes, pero en este caso vamos a bypasear la cuenta online. Para ello hacemos click a las teclas `SHIFT + F10`. Este nos abrira un cmd.

![img7](img/instWIN/inwin-img7.png)

Dentro de este CMD ejecutaremos el siguiente comando `oobe\BypassNRO.cmd` (en mi caso solo escribo bypa y hago `TAB` ). Pulsamos Enter para ejecutarlo.

![img8](img/instWIN/inwin-img8.png)

Despues de esto se nos va a reiniciar el ordenador y volvemos a hacer el setup de nuevo, como si nada. Hasta llegar al apartado de `Vamos a conectarte a una red` .

![img9](img/instWIN/inwin-img9.png)

Una vez aqui, vemos que tenemos opción de seleccionar la opción `No tengo internet`.

![img10](img/instWIN/inwin-img10.png)

Despues de esto nos va a dejar crear una cuenta ofline.

![img11](img/instWIN/inwin-img11.png)

Acabamos de configurar los ultimos pasos.

![img12](img/instWIN/inwin-img12.png)

Y ya estamos dentro de nuestra maquina virtual. Ahora solo nos queda instalar drivers, GPU passthrough, CPU pinning y por ultimo Paginación de memoria (casi nada). por lo que para instalar los drivers, simplemente entramos en el explorador de archivos y entramos dentro de la unidad de virtio drivers

![img13](img/instWIN/inwin-img13.png)

Dentro de la raiz del disco, ejecutamos las guest tools.

![img14](img/instWIN/inwin-img14.png)

 Hacemos click a siguiente e instalar.

![img15](img/instWIN/inwin-img15.png)

Una vez instalado le damos a close y ya podemos cerrar todo eso.

![img16](img/instWIN/inwin-img16.png)

Ahora para poder agilizar nuestro windows 11, vamos a ejecutar powershell como administrador.

![img17](img/instWIN/inwin-img17.png)

Una vez dentro, vamos a ejecutar el siguiente comando `irm christitus.com/win | iex`.
Este es un script que nos permite tanto instalar como desinstalar aplicaciones del sistema, en este caso lo utilizo para poder instalar firefox sin tener que entrar en edge y `aceptar los terminos y condiciones`.

![img18](img/instWIN/inwin-img18.png)

Una vez dentro, selecciono Firefox y le doy a `Install/Upgrade Applications`. En este caso aparte de firefox tambien instalará `winget` que es como un gestor de paquetes en terminal para windows. Algo asi como `apt`.

![img19](img/instWIN/inwin-img19.png)

Una vez haya terminado de instalarse, veremos que nos aparece firefox en nuestro escritorio. Aún dentro del script vamos al apartado `Tweaks`.

![img20](img/instWIN/inwin-img20.png)

Dentro de aqui vamos a seleccionar todo lo qe deseamos eliminar y le damos a `Run Tweaks`. Esto me ha permitido pasar de windows sin nada de background ocupar 4gb de ram (en un sistema de 8gb) y 12% de cpu, a 1,2gb de ram y 2% de cpu.

![img21](img/instWIN/inwin-img21.png)

Una vez acabado, podemos cerrarlo y ahora solo voy a eliminar el botón del escritorio de `Mas información`.

![img22](img/instWIN/inwin-img22.png)

Si quereis eliminarlo Entra dentro del directorio `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\HideDesktopIcons\NewStartPanel key`

Creamos una nueva `DWORD (32-bit)` llamada `{2cc5ca98-6485-489a-920e-b3e88a6ccce3}` y le ponemos de valor en hexadecimal de 1. Y ya esta, si volvemos al escritorio no lo encontraremos. 

![img23](img/instWIN/inwin-img23.png)
