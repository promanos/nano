![Powered By](http://www.ros.org/wp-content/uploads/2013/10/rosorg-logo1.png)
<IMG SRC="http://manumuve.com/wp-content/uploads/2014/09/arduino_logo.png" ALT="Arduino" WIDTH=220 HEIGHT=120>

# Nano Robot Project

## Arduino & ROS code for "The Nano" project
* Code *pending
* Wiki *pending
* Architecture Diagram *pending

LINUX
<br>
Sistema: LINUX (UBUNTU 14.04 LTS Trusty)
<br>
Para realizar la instalación del sistema operativo Linux usamos un pendrive booteable, en el cual creamos una imagen usando el software live_cd que nos permite crear imágenes ISO, Con esta imagen creada podemos empezar la instalación. 
Reiniciar el ordenador y arrancar desde el pendrive booteable. 
<br>
1.	Al arrancar el primer paso es cambiar la configuración del idioma para la instalación.
<br>
2.	Se deben seguir las siguientes recomendaciones, ya que si alguna de ellas no está presente no podremos realizar la instalación satisfactoria del sistema operativo.
*	Conectar la computadora a la fuente de energía.
*	Asegúrese de contar con el espacio suficiente para la instalación, un mínimo de 15 GB
*	Se recomienda descargar las últimas actualizaciones al momento de la instalación para no tener problemas de falta de librerías o deprecadas
*	Se debe contar con una conexión a internet, sea por wifi o cable Ethernet

ROS
<br>
Sistema: ROS Indigo
<br>
ROS es una plataforma que permite desarrollar software para robots y que opera de manera parecida a un sistema operativo.
<br>
Para comenzar es necesario abrir la utilidad de Terminal.
<br>
1.	Configurar repositorios de Ubuntu
A continuación preparamos el sistema para que acepte los paquetes de información de la página del repositorio packages.ros.org ("restricted," "universe," and "multiverse"), para ello usamos la función correspondiente a nuestro sistema.

sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu precise main" > /etc/apt/sources.list.d/ros-latest.list'

Tras introducir la función anterior, nos pedirá la contraseña de usuario para confirmar que queremos aceptar esta función, y el terminal volverá a modo espera.
<br>
2.	Configurar repositorios de sources.list 
A continuación preparamos el sistema para que acepte los paquetes de información de la página del repositorio packages.ros.org. Para ello usamos la función correspondiente al sistema que tenemos instalado, en nuestro caso Trusty (14.04)

sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

Tras introducir la función anterior, nos pedirá la contraseña de usuario para confirmar que queremos aceptar esta función, y la terminal volverá a modo espera.
<br>
3.	Importar la clave del repositorio
Dado que cuando se quiere agregar repositorios extras al fichero fuente a veces apt alega que los paquetes no están firmados ó que no puede encontrar la clave para verificarlos, es necesario importar la clave del repositorio.

sudo apt-key adv --keyserver hkp://pool.sks-keyservers.net --recv-key 0xB01FA116
<br>
4.	Instalación del SO
Una vez preparado el sistema para instalar ROS se procede a la instalación del sistema operativo, para ello usamos la función que nos descargará el sistema por completo.

sudo apt-get install ros-indigo-desktop-full

Con sólo presionar la tecla Enter el programa se pondrá a funcionar descargando todo lo necesario para que el sistema funcione.
<br>
5.	Inicializar rosdep
Antes de poder utilizar ROS, es necesario inicializar rosdep. Rosdep permite instalar fácilmente las dependencias del sistema fuente que se quiere compilar y que se requieren para ejecutar algunos componentes básicos en ROS.
A continuación iniciamos el programa rosdep y comprobamos que esté actualizado, para ello usamos primero la función:
sudo rosdep init
Y luego la función:
rosdep update

Luego de esto, ya tenemos ROS instalado en nuestro sistema Ubuntu y ahora solo nos quedaría añadir un par de configuraciones más que son recomendables.
<br>
6.	Configuración del ambiente
La primera configuración recomendada es para que las variables de entorno que creemos se añadan automáticamente a nuestra sesión, para ello usamos la función:
echo “source /opt/ros/groovy/setup.bash” >> ~/.bashrc
Y luego:
source ~/.bashrc
<br>
7.	Obtener rosinstall
También es conveniente instalar rosinstall, que es un añadido que nos permitirá descargarnos fácilmente el código fuente de muchos añadidos con solo un comando, para ello usamos el comando:

sudo apt-get install python-rosinstall

Tras esto ya tendremos nuestro sistema listo para trabajar con él.

Referencia: http://wiki.ros.org/indigo/Installation/Ubuntu

ARDUINO IDE
A continuación de detallan los pasos para cómo configurar el IDE de Arduino para utilizar rosserial.
Usando el paquete rosserial_arduino, se puede utilizar ROS directamente con el Arduino IDE. rosserial proporciona un protocolo de comunicación ROS que funciona sobre UART del Arduino.
<br>
Notas: Para poder utilizar las bibliotecas rosserial se debe incluir en el código #include <ros.h> antes de incluir cualquier otro include; de lo contrario el Arduino IDE no será capaza de localizarlo.
<br>
1.	Instalación de la estación de trabajo ROS
Para instalar rosserial para Arduino ejecutamos:
sudo apt-get install ros-indigo-rosserial-arduino
sudo apt-get install ros-indigo-rosserial
<br>
2.	Instalación de ros_lib en el ambiente Arduino
Con la instalación del paso anterior se creó ros_lib el cual debe ser copiado en el ambiente de desarrollo de Arduino para permitir que los programas de Arduino puedan interactuar con ROS.

cd <sketchbook>/libraries
rm -rf ros_lib
rosrun rosserial_arduino make_libraries.py .


LOQUENDO
Se instaló el WINE desde las librerías oficiales.
Se descarga de la siguiente página el loquendo para linux
http://www.mediafire.com/download/t29517xqkhv5zdz/Loquendo+Linux.zip
Pasos para instalar el loquendo: .....
