# Software de Control Autónomo de Embarcaciones de la Universidad de San Andrés

## Introduccion:
En búsqueda de avances punteros en tecnología marítima, la Universidad de San Andrés presenta con orgullo su Software de Control Autónomo de Embarcaciones. Desarrollado por un equipo de investigadores y ingenieros dedicados, este software representa un gran avance en el ámbito de la navegación marítima autónoma.

### Funcionamiento
El software funciona a través de varios ejes principales, primero utiliza como base [OpenMCT](https://nasa.github.io/openmct/). Sumado a esto usa distintos nodos de Ros2 HUmble y NodeJs para crear servidores en tiempo real e históricos.

### Desarrollo:
A la hora de desarrrollar hay algunas cosas que se deben en  tener en cuenta:
#### Distribucion de carpetas
/example-server: En esta carpeta es donde se va todo lo relacionado con el server side, ya sea websocket puerto, etc.

/assets: En Assets se guarda todo lo cosmetico para la pagina ya sean sonidos, imágenes, gif o cualquier otro archivo adicional que no tenga otra función que decorativa.

/plugins: Todos los plugins que se desarrollen de forma externa deben ser guardados en esta carpeta, cada plugin debe tenr una funcion principal útil de importar.

/styles: Dentro de esta de carpeta se guardan todas las clases que den estilos a la visual.

#### Correr el proyecto
Una vez clonado el projecto y luego de haber completado los pasos explicados en el [README](../README.md) principal, ejecutar los comandos:
```
npm install
npm start
```

##### Recursos utiles
Repositorio OpenMCT: https://github.com/nasa/openmct/blob/master/API.md
