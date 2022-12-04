# Proyecto del curso:  CBIR

## Sobre el proyecto

 Consiste en diseñar un Content Based Image Retrieval (CBIR), que corresponde a una interfáz de consulta de queries a una base de datos de imágenes, es decir, se pasa una imagen a buscar y el CBIR retorna un top de las figuras que más se parecen.
 
 ![alt text](https://github.com/mvarasg/EL5206/blob/main/Proyecto/CBIR.png?raw=true)
 
 Se pide realizar dos métodos de extracción de caracterísiticas, uno handcrafted (LBP, HOG, etc) y otro clásico como puede ser una red pre-entrenada. Se calculan rankings para comparar los desempeños y se pide optimizar la función de busqueda considerando desempeño, memoria de uso y tiempo de consulta.


## Descarga de los datasets
Para correr el proyecto se deben descargar 2 bases de datos. La primera corresponde a la ```INRIA```, que se divide en dos archivos que, para el correcto fumcionamiento del proyecto, deben extrarse en carpetas llamadas ```jpg1``` y ```jpg2```. La segunda base de datos ```GPR1200``` se debe extraer en una carpeta llamada ```ìmages```.


Para descargar las bases de datos con las imágenes de **INRIA**, se deben descargar desde consola utilizando el comando `wget` en el notebook:

Lo primero es descargar `wget` en la consola de anaconda:
```
pip install wget
```
Luego, en el documento de notebook se deben correr los siguientes comandos:
```
!python -m wget ftp://ftp.inrialpes.fr/pub/lear/douze/data/jpg1.tar.gz
!python -m wget ftp://ftp.inrialpes.fr/pub/lear/douze/data/jpg2.tar.gz
```

Para descargar la base de datos con 12000 imágenes de la base `GPR1200`, se debe descargar mediante el siguiente [Enlace](https://visual-computing.com/files/GPR1200/GPR1200.zip).
## Implementación

Se implementan 3 métodos de extracción de características: HOG, LBP y mediante la red [MobileNetV2](https://keras.io/api/applications/mobilenet/) disponible en la librería `keras`. Se optimiza la función de busqueda reduciendo el tamaño de los vectores de caracterísiticas mediante PCA y normalizandolo. Se desarrollan funciones por separado para solucionar pequeñas sub-tareas.
