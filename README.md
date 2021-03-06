
![Docker-Logo-White-RGB_Vertical-BG_0-444079282](https://user-images.githubusercontent.com/91874745/173307153-46d4f92c-157e-4b48-bb9a-2b9d69ef9e20.png)


#  Ejecutando contenedores en [***Docker***](https://www.docker.com)



## Apartado 1 examen (4 ejercicios realizado en PLAY WITH DOCKER)

1. Primer ejercicio
    
    * Descargar una imagen previa, para esto ejecutamos el comando `docker pull` + la imagen que queremos descargarnos, en este caso **ubuntu:18.04**. Quedaría de la siguiente forma `docker pull ubuntu:18.04`.
    * 
     ![1](https://user-images.githubusercontent.com/91874745/173306452-609aea33-32e5-482b-b037-c6ea123c8c8f.png)

   * Ahora creamos un contenedor ubuntu:18.04 y tendremos acceso a una shell en él, en Docker, cuando no tenemos la imagen descargada de manera previa, entonces lo primero que hace es descargarla. Para esto usaremos el comando `docker run ubuntu:10.04/bin/bash`.

![2](https://user-images.githubusercontent.com/91874745/173306564-14e969b7-63d0-4183-ab7f-ddabaa4f2bbe.png)

2. Segundo ejercicio

   *Creamos un contenedor  **centOs:18.04** y listaremos el contenido de la carpeta / esto lo hacemos con la instrucción `run centos:18.94 ls/l`. Podemos ber cómo aparece las carpetas del directorio raíz
   
   ![3](https://user-images.githubusercontent.com/91874745/173306634-757e1e6f-9f98-4dd5-a8f8-985a220fe840.png)

 
3. Tercer ejercicio

   *Creamos un contenedor de httpd (Servidor Apache), para esto ejecutamos el comando `docker run httpd`. Con esa orden crearemos un servidor Web Apache 2.4 en la ip mostrada y se nos muestra en pantalla el log del servicio

![eje3](https://user-images.githubusercontent.com/91874745/173306731-182d5dcb-d003-410a-b0cb-b3b9b0e84cd2.png)

   
4. Cuarto ejercicio

  *Creamos un contenedor debian 9 y mostramos el contenido de una carpeta establecida con el parámetro `-w`, para esto usaremos la instrucción `docker run -it -w /etc debian:9 ls`. Una vez que el contenedor ejecuta la orden ls desde el directorio /etc este se para

![4](https://user-images.githubusercontent.com/91874745/173306808-841c66c6-95c0-4ea8-8c31-b82bb1382d01.png)


  *Ahora vamos a ver cómo hacer un seguimiento de lo que tenemos en nuestro sistema, para eso usamos `docker ps` para ver aquellos contenedores en estado UP 

![5](https://user-images.githubusercontent.com/91874745/173306884-9e7cea99-3338-474f-bfca-dc74a3d400f0.png)


 *Pero para ver todos los contenedores, esten en estado UP  o EXITED, necesitaremos ejecutar `docker ps -a`
 
 ![6](https://user-images.githubusercontent.com/91874745/173306908-df180a1b-b545-4fef-9cc4-291d267de88a.png)
 
 Con esto finalizamos el primer apartado.

## Apartado 2 examen (DOCKERFILE Proyecto debian con Python, con PLAY WITH DOCKER)

 * En mi caso he creado una imagen a partir de un **Dockerfile**, primero creo un directorio donde tendré mis imagenes de Docker, una vez dentro creo el **Dockerfile** con `vi Dockerfile`, dentro escribo las instrucciones para una base debian y python, con las siguientes instrucciones como se ven en la imagen:
 
 ![1](https://user-images.githubusercontent.com/91874745/173312271-12f00b54-ccf4-4f1b-a8ed-8167631ed895.png)

  * Creación **Dockerfile**
  
![dockerfile](https://user-images.githubusercontent.com/91874745/173312441-746443e8-cc0b-4374-a195-2f34893cb729.png)


* Después de esto ejecutamos el comando `docker build --tag debianadalid .`, el punto es porque el **Dockerfile** está dentro del mismo directorio

![1](https://user-images.githubusercontent.com/91874745/173312547-8f2e2246-3bbb-4113-aed5-a3cb0de6ff36.png)

* Comprobamos con el comando `docker images` la creacion de nuestra imagen y hacemos un `tag usuario/nombreimagen` y a continuación un ´docker login´ y un ´docker push´.

* Por último comprobamos que se ha subido nuestra imagen a **Docker Hub*** y con esto finalizamos esta parte.


 ![3](https://user-images.githubusercontent.com/91874745/173313250-f933599a-f45a-47c2-b263-5e105954ff17.png)

ENLACE A IMAGEN/REPOSITORIO DOCKER EN DOCKER HUB: https://hub.docker.com/repository/docker/adalt/debianadalid
