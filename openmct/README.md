# Software de Control Autónomo de Embarcaciones de la Universidad de San Andrés

## Introduccion:
En búsqueda de avances punteros en tecnología marítima, la Universidad de San Andrés presenta con orgullo su Software de Control Autónomo de Embarcaciones. Desarrollado por un equipo de investigadores y ingenieros dedicados, este software representa un gran avance en el ámbito de la navegación marítima autónoma.

## Funcionamiento:
El software funciona a través de varios ejes principales, primero utiliza como base [OpenMCT](https://nasa.github.io/openmct/). Sumado a esto usa distintos nodos de Ros2 HUmble y NodeJs para crear servidores en tiempo real e históricos. En este README se da por sentado información que se explica más detalladamente en este [tutorial](https://www.youtube.com/watch?v=Gg25GfA456o).

## Desarrollo:
A la hora de desarrrollar hay algunas cosas que se deben tener en cuenta:
### Distribucion de carpetas:
/example-server: En esta carpeta es donde se va todo lo relacionado con el server side, ya sea websocket puerto, etc.

/assets: En Assets se guarda todo lo cosmetico para la pagina ya sean sonidos, imágenes, gif o cualquier otro archivo adicional que no tenga otra función que decorativa.

/plugins: Todos los plugins que se desarrollen de forma externa deben ser guardados en esta carpeta, cada plugin debe tenr una funcion principal útil de importar.

/styles: Dentro de esta de carpeta se guardan todas las clases que den estilos a la visual.

## Correr el servidor de ejemplo:
Una vez clonado el projecto y luego de haber completado los pasos explicados en el [README](../README.md) principal, en el path de openmct ejecutar los comandos:
```
npm install
npm start
```

## Prueba de conexión por USB al microcontrolador:
Si es la primera ejecución tanto para el speaker como para el subscriber, en el workspace correspondiente de cada uno (aclarado más abajo) se debe ejecutar:
```
colcon build
```
### Correr el nodo speaker:
Dentro de nuestro workspace de Micro ROS (~/microros_ws) creado en el procedimiento explicado en el [README](../README.md) principal ejecutar:
Si es la primera ejecución (además del colcon build):
```
cd install/
source setup.bash
source local_setup.bash
cd ..
ros2 run micro_ros_setup build_firmware.sh
ros2 run micro_ros_setup create_agent_ws.sh
ros2 run micro_ros_setup build_agent.sh
```
Luego siempre:
```
source install/local_setup.bash
ros2 run micro_ros_agent micro_ros_agent serial --dev /dev/ttyUSB0
```
Una forma de ver que anda sin utilizar un nodo subscriber es ejecutar en otra terminal:
```
rqt_graph
```

### Correr el nodo subscriber:
En otra terminal en paralelo, dentro de nuestro workspace de ROS2 (~/ros2_ws) creado en el procedimiento explicado en el [README](../README.md) principal ejecutar:
```
cd install/
source setup.bash
source local_setup.bash
cd ..
ros2 run my_robot_controller subscriber
```

## Recursos utiles:
Repositorio OpenMCT: https://github.com/nasa/openmct/blob/master/API.md

Tutorial ROS2 Humble: https://www.youtube.com/watch?v=Gg25GfA456o
