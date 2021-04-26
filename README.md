# Practica 3. Compilacion Del Kernel De Linux.
## 1. ¿Cómo hacer un respaldo de una máquina virtual? y ¿cómo levantar ese respaldo?
Para realizar una copia de seguridad de una máquina virtual, primero se tiene que abrir Virtual box y dirigirse a la pestaña de "Archivo > Exportar" servicio virtualizado.

![1.1](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

Posteriormente se selecciona la máquina virtual a respaldar.

![1.2](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

Después se selecciona el nombre del archivo de la copia de seguridad con extensión .ova y se exporta sin realizar cambios en las preferencias de servicio virtualizado.

![1.3](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

Una vez exportada la máquina virtual, se podrá ver un archivo .ova que contiene la máquina virtual con su configuración en la ubicación donde se guardó. Si se desea importar, se selecciona dicho archivo y se le da doble click, o en su defecto ir a virtual box y seleccionar "Archivo > Importar" servicio virtualizado para seleccionar el archivo deseado.

![1.4](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

En la ventana de importar servicio virtualizado, se pueden seleccionar las preferencias deseadas para la máquina virtual que se importará. Finalmente se da click en “Importar”.

![1.5](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

Al terminar el proceso de importación, se mostrará directamente en Virtual Box la máquina importada.

## 2. Explicar la nomenclatura del kernel.

El Kernel en nomenclatura, se divide en 3 campos separados cada uno por un punto:

* **Primer campo:** Se encuentra el número de la versión del Kernel.
* **Segundo campo:** Se le conoce como sub-versión. Es una versión, dentro de la versión del primer campo. Si este número es par, la versión será estable; si es impar, ésta será inestable.
* **Tercer campo:** Se refiere a la corrección de bugs y actualizaciones.

![2.1](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

En la imagen presentada, se muestra que la versión de Kernel de Linux es la 5, la sub-versión es la 8, y el ajuste de bugs y actualizaciones es la 0. El -43 hace referencia al número de parche en el que se encuentra. Sin embargo, la forma convencional es con los 3 números separados por un punto.

## 3. Enlistar paquetes requeridos para la compilación y ¿cómo instalarlos desde terminal?

Para la compilación se necesitan los paquetes de:
* Las dependencias 
* Los prerrequisitos
* Las fuentes 
* Las librerías ncurses-dev libncurses-dev flex bc bison openssl libssl-dev dkms libelf-dev libudev-dev libpci-dev libiberty-dev autoconf.

Primero abres la terminal y a partir de este punto tienes que seguir los puntos uno a uno e ir copiando los comandos en orden para poder instalar el kernel de manera efectiva.

Para poder instalar los paquetes requeridos para la compilacion desde la terminal se aplica el comando ***sudo apt-get -y install build-essential libncurses-dev libncurses-dev flex bc bison openssl libssl-dev dkms libelf-dev libudev-dev libpci-dev libiberty-dev autoconf***

![3.1](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

## 4. ¿Cómo descargar una versión de kernel desde terminal? 

Las versiones de kernel pueden variar, pero en este tutorial se muestra como instalar la versión 5.10.13.

Para descargar esta versión de kernel desde terminal se tiene que aplicar el comando.

***wget "https://cdn.kernel.org/pub/linux/kernel/v5.x/linux-5.10.13.tar.xz"***

![4.1](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

Esperamos que termine la descarga y ese comando nos deja un archivo comprimido del kernel.

## 5. ¿Cómo extraer el código comprimido del kernel desde terminal?

Una vez aplicado el paso 4 tendremos que extraer el código del kernel, para hacer esto se tiene que aplicar el comando tar avxf linux-5.10.13.tar.xz en la terminal.

![5.1](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

## 6. ¿Cómo configurar el kernel?

Una vez completado el paso 5 podremos configurar el kernel, para ello el primero paso es acceder al directorio de la versión de kernel que acabamos de descomprimir en el paso anterior, lo que se logra ejecutando el comando ***cd linux-5.10.13/*** en la terminal.

![6.1](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

Estando ahí ya podremos acceder a configurar el kernel aplicando el comando ***make menuconfig***

![6.2](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

Este comando nos desplegara un menú con colores.

![6.3](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

En la configuración del kernel tendremos que guardar un archivo .config para poder compilar el código del kernel es importante no cambiar el nombre ni modificar nada simplemente basta con darle ok para guardar y después salir como se pueden ver en las siguientes imágenes.

![6.4](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

![6.5](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

Una vez completando lo anterior le damos ***Exit*** para regresar a la terminal.

![6.6](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

## 7. ¿Cómo compilar el código del kernel?

En esta versión de kernel tenemos que hacer un pequeño cambio para poder compilar el código de kernel.

Primero usamos el comando ***nano .config*** para acceder al archivo ***.config*** que guardamos en el punto anterior.

![7.1](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

Una vez ahí tendremos que buscar la siguiente línea de código que dice **CONFIG_SYSTEM_TRUSTED_KEYS** y borrarla para poder compilar el código. (NOTA: esa línea de código se encuentra casi hasta el final de todo el código).

![7.2](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

Una vez borrada la línea salimos del código y guardamos los cambios con ***ctrl+x*** y salimos para regresar a la terminal.

Estando en la terminal solo basta con aplicar el comando ***make*** o mas recomendable el comando make -j (+Procesadores), ejemplo: ***make -j 3***, esto si se le asigno mas procesadores a la maquina virtual, pero si no se asignaron más procesadores se puede hacer perfectamente solo con el comando **make**.

![7.3](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

Este paso puede tardar varias horas y es completamente normal ya que por eso es recomendable asignarle mas procesadores para poder hacer este paso un poco más rápido.

## 8. ¿Cómo instalar módulos?

Una vez terminado de compilar el kernel instalaremos los módulos, para esto primero hay que aplicar el comando ***make modules*** en la terminal pera verificar que todo este en orden.

![8.1](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

Después de esto solo aplicamos el comando ***sudo make modules_install*** en la terminal para poder instalar los módulos.

![8.2](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

## 9. ¿Cómo instalar el kernel?

Una vez llegado a este punto ya podremos instalar el kernel simplemente aplicando el comando ***sudo make install*** en la terminal y con esto ya tendremos instalada la versión de kernel 5.10.13.

![9.1](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

## 10. ¿Cómo indicarle a la computadora con cuál kernel debe iniciar? 

Para indicar a la computadora con que kernel se debe de iniciar se utilizan los comando ***sudo update-initramfs -c -k 5.10.13*** (este para indicarle cual kernel) y después ***sudo update -grub***

![10.1](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

Otro método es haciendo boot con el kernel de Linux, para hacer esto al momento de arrancar la maquina presionamos la tecla shift para entrar al menú de grub y nos metemos a opciones avanzadas y ahí elegimos el kernel para iniciar.

## 11. ¿Cómo verificar el cambio de kernel a partir de consola?
 
Para verificar el cambio de kernel de manera sencilla simplemente aplicar le comando ***uname -a*** o ***uname -mrs*** en la terminal para ver que versión de kernel tenemos instalada y poder verificarla.

Como se puede ver esta imagen aplicamos el comando ***-uname a*** antes de reiniciar.

![11.1](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

Después aplicamos el comando ***sudo update-grub*** para que asuma el nuevo kernel y después se usa el comando ***shutdown -r now*** para reiniciar.

![11.2](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

Finalmente después de reiniciar aplicamos el comando ***uname -a*** nuevamente para verificar que ahora el kernel es el 5.10.13 y antes era el  5.8.0-50-generic.

![11.3](https://github.com/Enrique290/Practica1.Manejo.De.Discos./blob/main/ImagenesSO/2.1.png)

