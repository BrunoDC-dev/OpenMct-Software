# Software de Control Autónomo de Embarcaciones de la Universidad de San Andrés

## Levantar el proyecto de forma local
Para iniciar el proyecto se recomienda levantarlo de forma local utlizando [Node Js](https://nodejs.org/en), [Ros 2 Humble](https://docs.ros.org/en/humble) y [micro-ROS](https://micro.ros.org/). 

Como sistema operativo se enfatiza el uso de Linux Ubuntu 22.04 ya que facilitará su uso y/o desarrollo.

Además, para que quede prestablecido Ros2, en una terminal ejecutar para abrir el archivo de configuración:
 
```
gedit ~/.bashrc
```
 
Ir al final y en líneas nuevas insertar y guardar el documento:
```
source /opt/ros/humble/setup.bash
source /usr/share/colcon_argcomplete/hook/colcon-argcomplete.bash
```

Para más detalles sobre el procedimiento consultar este [tutorial](https://www.youtube.com/watch?v=Gg25GfA456o).

Para correr el proyecto leer el [README](./openmct/README.md) en \openmct.

## Levantar el proyecto desde un contenedor de Docker
Para correr el proyecto desde un contenedor de Docker se debe tener instalado y corriendo el servicio de [Docker](https://docs.docker.com/get-docker/) y ejecutar los siguientes comandos desde la terminal en el path correspondiente a este proyecto:
``` 
docker build -t Nautilus .
```

> *Advertencia*: El build puede tardar varios minutos la primera vez que se corre. Se recomienda tener una buena conexión a internet.

Cuando finalice debe ejecutar:
```
docker run -p 8080:8080 Nautilus
```
