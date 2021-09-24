# Instalación del JDK en el SO
Repositorio dedicado a la documentación de la instalación del jdk en kubuntu

## Introducción

El **JDK** es el acrónimo de Java development kit, osea, un kit de desarrollo de Java, que es el conjunto de utilidades, documentación y herramientas para el desarrollo de aplicaciones en Java.

La instalación de este programa no requiere de ningún paso extra, solo necesitamos un sistema operativo en base a Linux, en este caso yo usaré la distribución Kubuntu.

<div align="center">
<img width="50%" src="https://miro.medium.com/max/785/1*7fDw5W4a5WxJY9wQIgzNLQ.jpeg">
</div>

## Pasos

### Actualización de repositorios y descarga

Primero necesitamos actualizar los **repositorios** del sistema con
```
sudo apt-get update 
```
<div align="center">
<img width="100%" src="http://drive.google.com/uc?export=view&id=12wXjsq4td6atOWL7gpPdpnnFBGj5CDA-">
</div>

después podemos instalar la versión de java por defecto con 
```
sudo apt -get install defalult-jdk
```
<div align="center">
<img width="100%" src="http://drive.google.com/uc?export=view&id=1FF4ZXPCwbjwy5kG4nkepQ3iA1n706tzV">
</div>

cuando lo tengamos instalado podemos ver la versión descargada con
```
java -version
```
Por defecto se instalará la version **11.0.11**

<div align="center">
<img width="100%" src="http://drive.google.com/uc?export=view&id=1pB4q8F1ZeA8jzG7n9z7bJTkrU_BDMs3y">
</div>

### Instalación de otras versiones

El **JDK** tiene 3 versiones disponibles para estas distribuciones, la versión **11**(la por defecto), la **9** y la **8**(esta es la que nos interesa ahora mismo)

La versión **11** ya la tenemos instalada. Al intentar instalar la versión 9 con
```
sudo apt-get install openjdk-9-jdk
```
nos dará un error debido a que esta versión está descontinuada en linux

<div align="center">
<img width="100%" src="http://drive.google.com/uc?export=view&id=15LhxSSPBMla7wKdHGLRlCl0gMGDwdNDS">
</div>


Instalamos la versión **8** con 
```
sudo apt-get install openjdk-8-jdk
```
<div align="center">
<img width="100%" src="http://drive.google.com/uc?export=view&id=1U9qXAXzx_cbQV8O-e7Xh9nX2FLsevCf4">
</div>

### Configurar las variables de entorno

Para configurar las **variables de entorno**(direcciones de ubicación del programa de java), necesitamos ver que versiones tenemos instaladas con 
```
ls /usr/lib/jvm
```
<div align="center">
<img width="100%" src="http://drive.google.com/uc?export=view&id=1ZG0Rtc5BDaajPPke1W9egkAbp4FMyK0t">
</div>

Ahora hay que editar el fichero **profile** para cambiar a la versión de java que queremos, en este caso la **8** con
```
nano /etc/profile.d”
```
y ahora escribimos en el fichero **(teniendo en cuenta el nombre de la versión deseada)**:

<div align="center">
<img width="100%" src="http://drive.google.com/uc?export=view&id=1-r0fOlLWN8hiyCXVPR4shUhYaf7UI1d6">
</div>

Guardamos el archivo y recargamos con el comando
```
sudo update-alternatives –config java
```

Ahora, con el comando 
```
java -version 
```
nos debe aparecer la version **8**

<div align="center">
<img width="100%" src="http://drive.google.com/uc?export=view&id=1vQX-kZloqpr4PmwvgwW2s9ahbidZQhcU">
</div>

Y por ultimo comprobamos si la variable está correctamente definida con
```
echo $JAVA_HOME
```
<div align="center">
<img width="100%" src="http://drive.google.com/uc?export=view&id=12FDHecSQCdnanFGz4mGbl-VLSJ8fvHTS">
</div>

## Conclusión

Con estos pasos, podemos instalar el jdk en nuestro sistema operativo, para poder desarrollar con java.









