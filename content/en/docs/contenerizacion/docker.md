---
title : "Docker"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "contenerizacion"
weight: 503
toc: true
---

## Plataforma Docker

Como mencionamos en el tema anterior, Docker es una de las plataformas más populares en cuanto a contenerización se refiere. Cuando decimos que Docker es una plataforma, es porque existen diferentes productos que resuelven diferentes necesidades y todos estos se encuentran accesibles bajo una misma entidad.

El producto más importante de esta plataforma es el [Docker Engine], que es nativo de Linux. Un producto comúnmente concido es [Docker Desktop]; el cual ofrece una forma simple y sencilla de instalar [Docker Engine] en los sistemas operativos Windows y macOS.

Según la documentación oficial de [Docker]:

> **Docker** es una plataforma abierta para desarrollar y ejecutar aplicaciones. Al aprovechar las metodologías de **Docker** para probar y desplegar el código rápidamente, puede reducir significativamente la demora entre escribir el código y ejecutarlo en producción.

## Usos de Docker

- **Entrega rápida y consistente de sus aplicaciones**: Docker agiliza el ciclo de vida del desarrollo al permitir que se trabaje en entornos estandarizados utilizando contenedores locales. Los contenedores son excelentes para los flujos de trabajo de integración continua y entrega continua (CI/CD).
- **Despliegue receptivo y escalado**: Docker permite cargas de trabajo portátiles. Los contenedores pueden ejecutarse en la computadora local de un desarrollador, en máquinas físicas o virtuales en un centro de datos, en proveedores de la nube o en una combinación de entornos.

  La portabilidad y la naturaleza liviana de Docker también facilitan la administración dinámica de cargas de trabajo, ampliando o eliminando aplicaciones y servicios según lo dicten las necesidades comerciales, casi en tiempo real.

- **Ejecución de más cargas de trabajo en el mismo hardware**: Docker es ligero y rápido. Proporciona una alternativa viable y rentable a las máquinas virtuales basadas en hipervisor, por lo que puede utilizar una mayor parte de su capacidad de cómputo para lograr sus objetivos comerciales.

> **NOTA:** Lo que puedes lograr con Docker lo puedes lograr con cualquier otro motor competitivo, sin embargo, Docker tiene mayor madurez en cuanto a los puntos mencionados a continuación, lo que lo hace la elección por defecto de la mayoría de organizaciones.

## Arquitectura de Docker

Docker utiliza una [arquitectura cliente-servidor]. El cliente de Docker se comunica con el [daemon], que hace el trabajo pesado de **crear**, **ejecutar** y **distribuir** los contenedores.

El cliente y el daemon de Docker pueden ejecutarse en el mismo sistema, o puede conectar un cliente a un daemon de remoto. El cliente y el daemon se comunican mediante una [REST API], a través de sockets UNIX o una interfaz de red.

Otro cliente de Docker es [Docker Compose], que permite trabajar con aplicaciones que consisten en un conjunto de contenedores.

## Docker daemon

El daemon de Docker (`dockerd`) escucha las solicitudes de la API de Docker y administra los objetos de Docker, como imágenes, contenedores, redes y volúmenes.

## Docker client

El cliente de Docker (`docker`) es la forma principal en que muchos usuarios interactúan con Docker. Cuando usa comandos como `docker run`, el cliente envía estos comandos a `dockerd`, que posteriormente los ejecuta.

## Docker Desktop

[Docker Desktop] es una aplicación fácil de instalar para su entorno Mac o Windows que le permite crear y compartir microservicios y aplicaciones en contenedores.

Docker Desktop incluye el daemon Docker (`dockerd`), el cliente Docker (docker), [Docker Compose], Docker Content Trust, Kubernetes y Credential Helper.

Como [Docker Engine] es nativo de linux, es necesario usar un intermediario que virtualize Linux y posteriorment exponga los recursos anteriormente mencionados. Este intermediario generalmente es una máquina virtual que es provisionada y adminsitrada por el mismo **Docker Desktop**.

> Para obtener más información, consulte el siguiente enlace: [Docker Desktop].

## Registros de Docker

Un registro de Docker almacena imágenes de Docker. [Docker Hub] es un registro público que cualquiera puede usar.Docker está configurado para buscar imágenes en [Docker Hub] de manera predeterminada.

Sin embargo, es posible ejecutar un registro privado. Y no necesariamente debe ser de Docker, ya que la mayoría de registros se rigen bajo un mismo estándar, [OCI], que les permite entenderse entre sí.

Cuando usa los comandos `docker pull` o `docker run`, las imágenes requeridas se extraen de su registro configurado. Cuando usa el comando `docker push`, su imagen se envía a su registro configurado.

## Objetos de Docker

Cuando usa [Docker], está creando y usando imágenes, contenedores, redes, volúmenes, complementos y otros objetos. Esta sección es una breve descripción de algunos de esos objetos.

### Imágenes

Una imagen es una plantilla de solo lectura con instrucciones para crear un contenedor.

A menudo, una imagen se basa en otra imagen, con alguna personalización adicional. Por ejemplo, puede crear una imagen que se base en la imagen de `Ubuntu`, pero instale el servidor web [Apache] y su aplicación, así como los detalles de configuración necesarios para ejecutar su aplicación.

Para construir una imagen, se debe crear un `Dockerfile` con una sintaxis simple para definir los pasos necesarios para crear la imagen y ejecutarla. Cada instrucción en un Dockerfile crea una capa en la imagen. Cuando cambia el Dockerfile y reconstruye la imagen, solo se reconstruyen las capas que han cambiado. Esto es parte de lo que hace que las imágenes sean tan livianas, pequeñas y rápidas, en comparación con otras tecnologías de virtualización.

### Contenedores

Un contenedor es una instancia ejecutable de una imagen. Puede crear, iniciar, detener, mover o eliminar un contenedor mediante la API o la CLI de Docker. Puede conectar un contenedor a una o más redes, adjuntarle almacenamiento o incluso crear una nueva imagen basada en su estado actual.

De forma predeterminada, un contenedor está relativamente bien aislado de otros contenedores y de su máquina host. Puede controlar qué tan aislado está la red, el almacenamiento u otros subsistemas subyacentes de un contenedor de otros contenedores o de la máquina host.

Un contenedor se define por su imagen, así como por cualquier opción de configuración que le proporcione al crearlo o iniciarlo. Cuando se elimina un contenedor, desaparece cualquier cambio en su estado que no esté almacenado en el almacenamiento persistente.

<!-- Referencias -->
[daemon]: ../../referencias/enlaces#daemon
[arquitectura cliente-servidor]: ../../referencias/enlaces#client-server-architecture
[Docker]: ../../referencias/enlaces#docker
[Docker Engine]: ../../referencias/enlaces#docker-engine
[Docker Desktop]: ../../referencias/enlaces#docker-desktop
[Docker Compose]: ../../referencias/enlaces#docker-compose
[Docker Hub]: ../../referencias/enlaces#docker-hub
[OCI]: ../../referencias/enlaces#oci
[REST API]: ../../referencias/enlaces#rest-api
[Apache]: ../../referencias/enlaces#apache
