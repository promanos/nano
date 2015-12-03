![Powered By](http://www.ros.org/wp-content/uploads/2013/10/rosorg-logo1.png)
<IMG SRC="http://manumuve.com/wp-content/uploads/2014/09/arduino_logo.png" ALT="Arduino" WIDTH=220 HEIGHT=120>

# Nano Robot Project

## Arduino & ROS code for "The Nano" project
* Code *pending
* Wiki *pending
* Architecture Diagram *pending
<br><br>
https://realpython.com/blog/python/face-detection-in-python-using-a-webcam/
<br><br>

LINUX
<br>
Sistema: LINUX (UBUNTU 14.04 LTS Trusty)
<br>
Para realizar la instalación del sistema operativo Linux usamos un pendrive booteable, en el cual creamos una imagen usando el software live_cd que nos permite crear imágenes ISO, Con esta imagen creada podemos empezar la instalación. 
Reiniciar el ordenador y arrancar desde el pendrive booteable. 
<br><br>
1.	Al arrancar el primer paso es cambiar la configuración del idioma para la instalación.
<br><br>
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
<br><br>
1. Configurar repositorios de Ubuntu
<br>
A continuación preparamos el sistema para que acepte los paquetes de información de la página del repositorio packages.ros.org ("restricted," "universe," and "multiverse"), para ello usamos la función correspondiente a nuestro sistema.
<br>
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu precise main" > /etc/apt/sources.list.d/ros-latest.list'
<br>
Tras introducir la función anterior, nos pedirá la contraseña de usuario para confirmar que queremos aceptar esta función, y el terminal volverá a modo espera.
<br><br>
2. Configurar repositorios de sources.list
<br>
A continuación preparamos el sistema para que acepte los paquetes de información de la página del repositorio packages.ros.org. Para ello usamos la función correspondiente al sistema que tenemos instalado, en nuestro caso Trusty (14.04)
<br>
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
<br>
Tras introducir la función anterior, nos pedirá la contraseña de usuario para confirmar que queremos aceptar esta función, y la terminal volverá a modo espera.
<br><br>
3. Importar la clave del repositorio
<br>
Dado que cuando se quiere agregar repositorios extras al fichero fuente a veces apt alega que los paquetes no están firmados ó que no puede encontrar la clave para verificarlos, es necesario importar la clave del repositorio.
<br>
sudo apt-key adv --keyserver hkp://pool.sks-keyservers.net --recv-key 0xB01FA116
<br><br>
4. Instalación del SO
<br>
Una vez preparado el sistema para instalar ROS se procede a la instalación del sistema operativo, para ello usamos la función que nos descargará el sistema por completo.
<br>
sudo apt-get install ros-indigo-desktop-full
<br>
Con sólo presionar la tecla Enter el programa se pondrá a funcionar descargando todo lo necesario para que el sistema funcione.
<br><br>
5. Inicializar rosdep
<br>
Antes de poder utilizar ROS, es necesario inicializar rosdep. Rosdep permite instalar fácilmente las dependencias del sistema fuente que se quiere compilar y que se requieren para ejecutar algunos componentes básicos en ROS.
A continuación iniciamos el programa rosdep y comprobamos que esté actualizado, para ello usamos primero la función:
sudo rosdep init
Y luego la función:
rosdep update

Luego de esto, ya tenemos ROS instalado en nuestro sistema Ubuntu y ahora solo nos quedaría añadir un par de configuraciones más que son recomendables.
<br><br>
6. Configuración del ambiente
<br>
La primera configuración recomendada es para que las variables de entorno que creemos se añadan automáticamente a nuestra sesión, para ello usamos la función:
echo “source /opt/ros/groovy/setup.bash” >> ~/.bashrc
Y luego:
source ~/.bashrc
<br><br>
7. Obtener rosinstall
<br>
También es conveniente instalar rosinstall, que es un añadido que nos permitirá descargarnos fácilmente el código fuente de muchos añadidos con solo un comando, para ello usamos el comando:

sudo apt-get install python-rosinstall

Tras esto ya tendremos nuestro sistema listo para trabajar con él.

Referencia: http://wiki.ros.org/indigo/Installation/Ubuntu
<br><br>
ARDUINO IDE
<br>
A continuación de detallan los pasos para cómo configurar el IDE de Arduino para utilizar rosserial.
Usando el paquete rosserial_arduino, se puede utilizar ROS directamente con el Arduino IDE. rosserial proporciona un protocolo de comunicación ROS que funciona sobre UART del Arduino.
<br>
Notas: Para poder utilizar las bibliotecas rosserial se debe incluir en el código #include <ros.h> antes de incluir cualquier otro include; de lo contrario el Arduino IDE no será capaza de localizarlo.
<br><br>
1.	Instalación de la estación de trabajo ROS
<br>
Para instalar rosserial para Arduino ejecutamos:
sudo apt-get install ros-indigo-rosserial-arduino
sudo apt-get install ros-indigo-rosserial
<br><br>
2.	Instalación de ros_lib en el ambiente Arduino
<br>
Con la instalación del paso anterior se creó ros_lib el cual debe ser copiado en el ambiente de desarrollo de Arduino para permitir que los programas de Arduino puedan interactuar con ROS.
<br>
cd <sketchbook>/libraries
<br>
rm -rf ros_lib
<br>
rosrun rosserial_arduino make_libraries.py .

<br>
LOQUENDO
<br>
Se instaló el WINE desde las librerías oficiales.
Se descarga de la siguiente página el loquendo para linux
http://www.mediafire.com/download/t29517xqkhv5zdz/Loquendo+Linux.zip
Pasos para instalar el loquendo:
<br>
1. Descargar de la siguiente página el loquendo para linux
http://www.mediafire.com/download/t29517xqkhv5zdz/Loquendo+Linux.zip
(archivo subido al google drive)
<br>
2. Ejecutar el archivo llamado Ejecutame y seguir los pasos de instalacion.
<br>
3. Copiar los archivos LoqTTS6.dll y LoqTTS6_util.dll y pegarlo en Program Files \ Loquendo \ LTTS para dejar loquendo instalado y crackeado
<br>

ENCODER
<br>
Se diseñó un encoder de aluminio para cada rueda de 3 mm de espesor y 2 mm en los bordes con 72 perforaciones para el lector óptico.
<br>

ARDUINO
<br>
Mega 2560
<br>
Con Hummer moto shield
<br>

OpenCV 2.4.12.3
<br>
Paquetes requeridos:
*	GCC 4.4.x or later
*	CMake 2.6 or higher
*	Git
*	GTK+2.x or higher, including headers (libgtk2.0-dev)
*	pkg-config
*	Python 2.6 or later and Numpy 1.5 or later with developer packages (python-dev, python-numpy)
*	ffmpeg or libav development packages: libavcodec-dev, libavformat-dev, libswscale-dev
*	[optional] libtbb2 libtbb-dev
*	[optional] libdc1394 2.x
*	[optional] libjpeg-dev, libpng-dev, libtiff-dev, libjasper-dev, libdc1394-22-dev
<br>
[compiler] sudo apt-get install build-essential
<br>
[required] sudo apt-get install cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
<br>
[optional] sudo apt-get install python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libdc1394-22-dev
<br>
1. Crear directorio temporal
Se creó un directorio temporal <cmake_binary_dir> donde se alojarán los archivos generados, objetos y archivos binarios.
<br><br>
2. Ingresar al directorio
<br><br>
3. Ingresar al directorio make
<br>
sudo make install
<br><br>
KINECT
<br>
Kinect es un dispositivo que, conectado a la consola de videojuegos de Microsoft, reconoce los movimientos del cuerpo y la voz para realizar comandos sin necesidad de tener controles. Cuenta con una cámara (lo que lo hace un dispositivo RGB-D, o sea, que puede obtener una imagen en RGB con profundidad), un micrófono y un pivote motorizado. Su uso no está limitado al juego con la consola Xbox360, sino que se puede conectar a una computadora y usarla como cualquier otro sensor.
<br>
CONEXIÓN DEL KINECT<br>
Para hacer funcionar el sensor Kinect en ROS, es necesario instalar los controladores del mismo. Existe una variedad de controladores desarrollados por diversas compañías y entidades no lucrativas. De todos ellos, el que ofrece un mayor control sobre las capacidades del Kinect es el controlador llamado “openni”, por lo tanto, será éste el que se instale en el sistema escribiendo en una terminal:
<br><br>
sudo apt-get install ros-groovie-openni-kinect
<br><br>
Una vez instalado y conectado el Kinect, se verifica que aparezca la información del sensor de profundidad escribiendo en la terminal lo siguiente:
<br><br>
roslaunch openni_camera openni_node.launch
<br><br>
Luego, en una terminal diferente se abre rviz:
<br><br>
rosrun rviz rviz
<br><br>
NOTA: <rviz> es una herramienta de visualización en 3D para ROS, en ella se puede observar todo tipo de tópicos visuales publicados en el master de ROS.
<br><br>
Ya en rviz se ingresa a Global Options y se modifica la opción Fixed Frame a /openni_camera que es el tópico que publica los datos de profundidad. Después, se añade una instancia PointCloud2 y se selecciona el tópico /camera/rgb/points. Ahora debe poder verse una imagen con datos de profundidad con un código  de colores en 3D
<br><br>
http://linuxg.net/install-guvcview-on-ubuntu/

Guvcview
<br>
versión 2.0.2
<br>
Guvcview is an open source application, developed in GTK+, which enables the users to record videos or take photos via the webcam, set up the video and audio codecs to be used, or set the audio input.
Se debe instalar Guvcview y los paquetes relacionados. Para ello, será necesario seguir los siguientes pasos:
<br>
1. Agregar el repositorio PPA
<br>
$ sudo add-apt-repository ppa:pj-assis/testing
<br>
2. Actualizar el repositorio local 
<br>
$ sudo apt-get update
<br>
3. Instalaci[on del guvcview
<br>
$ sudo apt-get install guvcview
<br>
<br>
# We need to clone the following version of the code due to an error with gstream
https://github.com/Itseez/opencv/tree/2.4.12.3
<br>
