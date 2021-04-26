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
