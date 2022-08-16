---
title : "Lab 4.1: Usando Docker y Docker Compose"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "contenerizacion"
weight: 505
toc: true
---

Este laboratorio contiene una serie de varias secciones, cada una de las cuales explica un aspecto particular de Docker y su uso en modo ad-hoc.

> :warning: Este tutorial usa la versión `20.10.17-ce` de Docker. Si encuentra alguna parte del laboratorio incompatible con una versión futura, por favor cree un "**issue**" en el repositorio original.

## Requerimientos

- Capacidad de lectura del idioma inglés.
- Comodidad básica con la línea de comandos y el uso de un editor de texto.
- Uso de `git`, asumimos que luego de haber tomado el [Laboratorio 2.1 - Cómo usar git](../../computacion-en-la-nube/lab-01-crear-vm-en-aws) ya se está preparado para tomar este laboratio.

## Configurando el ambiente de trabajo

La guía de introducción a Docker tiene instrucciones detalladas [para configurar Docker en Mac, Linux y Windows][Docker install].

Una vez que haya terminado de instalar Docker, pruebe su instalación de Docker ejecutando lo siguiente:

```shell
$ docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.
```

---

## Hello world! :wave:

### Jugando con Busybox

Ahora que tenemos todo configurado, es hora de ensuciarse las manos. En esta sección, ejecutaremos un contenedor Busybox en nuestro sistema y probaremos el comando `docker run`.

Para comenzar, ejecutemos lo siguiente en nuestra terminal:

```shell
docker pull busybox
```

> :rotating_light: Dependiendo de cómo haya instalado Docker en su sistema, es posible que vea un error de permiso denegado después de ejecutar el comando anterior. Si está en una Mac, asegúrese de que el motor Docker esté funcionando. Si está en Linux, prefije los comandos de `docker` con `sudo`. Alternativamente, puede crear un [grupo de docker](https://docs.docker.com/engine/installation/linux/linux-postinstall/) para deshacerse de este problema.

El comando `pull` obtiene la imagen `busybox` del [registro de docker] y la guarda en nuestro sistema. Puede usar el comando `docker images` para ver una lista de todas las imágenes en su sistema.

```shell
$ docker images
REPOSITORY   TAG       IMAGE ID       CREATED       SIZE
busybox      latest    3c19bafed223   5 weeks ago   1.41MB
```

### `docker run`

¡Excelente! Ahora ejecutemos un contenedor Docker basado en esta imagen. Para hacer eso, vamos a usar el comando todopoderoso `docker run`.

```shell
docker run busybox
```

¡Espera, no pasó nada! ¿Es eso un error? Bueno, no. Detrás de escena, sucedieron muchas cosas. Cuando llama `run`, el cliente de Docker encuentra la imagen (`busybox` en este caso), carga el contenedor y luego ejecuta un comando en ese contenedor. Cuando ejecutamos `docker run busybox`, no proporcionamos un comando, por lo que el contenedor se inició, ejecutó un comando vacío y luego salió. Probemos algo más emocionante.

```shell
$ docker run busybox echo "hello from busybox"
hello from busybox
```

Bien, finalmente vemos algo de salida. En este caso, el cliente Docker ejecutó diligentemente el comando `echo` en nuestro contenedor busybox y luego lo cerró. Si te has dado cuenta, todo eso sucedió bastante rápido. Imagine iniciar una máquina virtual, ejecutar un comando y luego eliminarlo. Ahora es el momento de ver el comando `docker ps`. El comando `docker ps` muestra todos los contenedores que se están ejecutando actualmente.

```shell
$ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
```

Como no hay contenedores en ejecución, vemos una línea en blanco. Probemos una variante más útil: `docker ps -a`.

```shell
$ docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS                      PORTS     NAMES
7bd1e6ed9754   busybox   "echo 'hello from bu…"   14 minutes ago   Exited (0) 14 minutes ago             dazzling_poincare
1227171134d4   busybox   "sh"                     16 minutes ago   Exited (0) 16 minutes ago             frosty_jang
```

Entonces, lo que vemos arriba es una lista de todos los contenedores que ejecutamos. Observe que la columna `STATUS` muestra que estos contenedores salieron hace unos minutos.

Probablemente se esté preguntando si hay una forma de ejecutar más de un comando en un contenedor. Probemos eso ahora:

```shell
$ docker run -it busybox sh
/ # ls
bin   dev   etc   home  proc  root  sys   tmp   usr   var
/ # uptime
 19:47:33 up 36 min,  0 users,  load average: 0.00, 0.01, 0.00
/ # date
Sun Jul 17 19:47:33 UTC 2022
/ # exit
```

Ejecutar el comando `run` con las bandera `-it` nos adjunta a un **tty** interactivo en el contenedor. Ahora podemos ejecutar tantos comandos en el contenedor como queramos.

Eso concluye un recorrido relámpago por el poderoso comando `docker run`, que probablemente sea el comando que usará con más frecuencia. Tiene sentido pasar algún tiempo sintiéndose cómodo con él. Para obtener más información sobre `run`, utilice `docker run --help` para ver una lista de todos los indicadores que admite. A medida que avanzamos, veremos algunas variantes más de `docker run`.

Sin embargo, antes de seguir adelante, podremos rápidamente sobre la eliminación de contenedores. Vimos arriba que todavía podemos ver restos del contenedor incluso después de haber salido de `docker ps -a`. A lo largo de este tutorial, ejecutará `docker run` varias veces y dejará contenedores perdidos consumiendo espacio en disco. Por lo tanto, como regla general, limpie los contenedores una vez que termino con ellos. Para hacerlo, puede ejecutar el comando docker rm. Simplemente copie los `ID` de contenedor de arriba y péguelos junto con el comando.

```shell
$ docker rm 5d30f71b3f4e 3eb5f97e9851
5d30f71b3f4e
3eb5f97e9851
```

En la eliminación, debería ver los `ID` repetidos. Si tiene un montón de contenedores para eliminar de una sola vez, copiar y pegar `ID` puede ser tedioso. En ese caso, simplemente puede ejecutar:

```shell
$ docker container prune
WARNING! This will remove all stopped containers.
Are you sure you want to continue? [y/N] y
Deleted Containers:
320cfb506f0ed3d6e8aa64bc700d1fee9613d6f883727b8d54bdf9b8636369fb
d79102a642d705ba7a832617e0d520d66173a665d2f9db377a64f4f5affeba41

Total reclaimed space: 26B
```

Por último, también puede eliminar imágenes que ya no necesita ejecutando `docker rmi`.

Este comando elimina todos los contenedores que tienen un estado de `exited`.

## Aplicaciones web con Docker

Así que ahora hemos visto la ejecución de Docker, jugado con un contenedor de Docker. Armados con todo este conocimiento, ahora estamos listos para desplegar aplicaciones web con Docker.

### Sitios estáticos

Lo primero que vamos a ver es cómo podemos ejecutar un sitio web estático. Vamos a extraer una imagen de Docker de Docker Hub, ejecutar el contenedor y ver lo fácil que es ejecutar un servidor web.

La imagen que usaremos primero es la de `nginx`, un servidor web bastante popular, y cuya imagen ya se encuentra disponible en Docker Hub.

Podemos descargar y ejecutar la imagen directamente de una sola vez usando `docker run`.

```shell
docker run -d --rm -it --name 'web-server' -p '80:80' nginx:alpine
```

Al acceder a la URL [localhost:80](http://localhost), veremos el mensaje de bienvenida de `nginx`:

![C1-M04-L401-001](images/C1-M04-L401-001.png)

¡Genial! Pero... oh, vaya. Ahora hemos utilizado un comando más complejo que los anteriores. Pero sin preocuparse, que cada uno tiene una explicación bastante simple. Como ya conocemos `--rm` y `-it`, solo nos enfocaremos en explicar `--name`, `-d` y `-p`:

- `-d` separará nuestro terminal del contenedor que se ejecutará y lo enviará al "background",
- `-p` publicará un puerto expuesto del contenedor a un puerto de la máquina local,
- finalmente `--name` corresponde al nombre que queremos dar.

Para detener un contenedor desconectado, ejecute docker stop proporcionando la ID del contenedor. En este caso, podemos usar el nombre static-site que usamos para iniciar el contenedor.

Para detener un contenedor desconectado (tras usar `-d`), ejecute `docker stop` proporcionando el `ID` del contenedor. En este caso, podemos usar el nombre `web-server` que usamos para iniciar el contenedor.

```shell
$ docker stop web-server
web-server
```

Ahora que ha visto cómo ejecutar un servidor web dentro de una imagen de Docker, debe preguntarse: ¿cómo puedo crear mi propia imagen de Docker? Esta es la pregunta que exploraremos en la siguiente sección.

## Imágenes de Docker

Hemos visto imágenes antes, pero en esta sección profundizaremos en lo que son las imágenes de Docker y construiremos nuestra propia imagen. Empecemos.

Las imágenes de Docker son la base de los contenedores. En el ejemplo anterior, extrajimos la imagen de Busybox del registro y le pedimos al cliente de Docker que ejecutara un contenedor basado en esa imagen. Para ver la lista de imágenes que están disponibles localmente, use el comando `docker images`.

```shell
$ docker images
REPOSITORY    TAG       IMAGE ID       CREATED        SIZE
nginx         alpine    6721bbfe2e85   3 weeks ago    22.1MB
busybox       latest    3c19bafed223   5 weeks ago    1.41MB
hello-world   latest    46331d942d63   4 months ago   9.14kB
```

Lo anterior proporciona una lista de imágenes que henmos usado descargadas desde Docker Hub. `TAG` se refiere a una etiqueta particular de la imagen y `IMAGE ID` es el identificador único correspondiente para esa imagen.

Para simplificar, puede pensar en una imagen similar a un repositorio git: las imágenes se pueden "commit" con cambios y tener múltiples versiones. Si no proporciona un número de versión específico, el cliente de Docker se establece de manera predeterminada en el tag `latest` (la imagen más reciente). Por ejemplo, puede extraer una versión específica de la imagen de `ubuntu`:

```shell
docker pull ubuntu:22.04
```

Para obtener una nueva imagen de Docker, puede obtenerla de un registro (como Docker Hub) o crear la suya propia. Hay decenas de miles de imágenes disponibles en Docker Hub. También puede buscar imágenes directamente desde la línea de comandos mediante `docker search`.

Una distinción importante a tener en cuenta cuando se trata de imágenes es la diferencia entre **imágenes base** e **imágenes secundarias**.

- Las **imágenes base** son imágenes que no tienen una imagen principal, generalmente imágenes con un sistema operativo como ubuntu, busybox o debian.
- Las **imágenes secundarias** son imágenes que se basan en imágenes base y agregan funcionalidad adicional.

Luego están las imágenes oficiales y de usuario, que pueden ser tanto imágenes básicas como secundarias.

- Las imágenes oficiales son imágenes mantenidas y respaldadas oficialmente por la gente de Docker. Suelen tener una palabra de longitud. En la lista de imágenes anterior, las imágenes de `python`, `ubuntu`, `busybox` y `hello-world` son imágenes oficiales.
- Las imágenes de usuario son imágenes creadas y compartidas por usuarios como tú y yo. Se basan en imágenes base y agregan funcionalidad adicional. Por lo general, estos tienen el formato de `usuario/nombre-de-imagen`.

---

¡Bien hecho! :partying_face: Has completado existosamente el laboratorio introductorio de containers con Docker y su modo ad-hoc.

<!-- Referencias -->
[Docker Install]: ../../referencias/enlaces#docker-install
[Docker registry]: ../../referencias/enlaces#docker-hub
