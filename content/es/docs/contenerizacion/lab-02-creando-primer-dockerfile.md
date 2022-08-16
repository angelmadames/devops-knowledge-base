---
title : "Lab 4.2: Usando Dockerfiles"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "contenerizacion"
weight: 506
toc: true
---

> :warning: Este tutorial usa la versión `20.10.17-ce` de Docker. Si encuentra alguna parte del laboratorio incompatible con una versión futura, por favor cree un "**issue**" en el repositorio original.

## Requerimientos

- Capacidad de lectura del idioma inglés.
- Comodidad básica con la línea de comandos y el uso de un editor de texto.
- Uso básico de `docker` en modo ad-hoc, asumimos que luego de haber tomado el [Laboratorio 4.1 - Usando Docker](../lab-01-usando-docker-adhoc) ya se está preparado para tomar este laboratio.

### Creando una imagen simple con `nginx`

Es hora de crear una imágene de Docker, tal cual como la que usamos en el Lab 4.1. Para empezar, debemos crear un archivo en blanco con el nombre `Dockerfile`. Lo puedes hacer con tu editor de texto favorito, o con el terminal:

```shell
touch Dockerfile
```

Luego de esto, podemos editar nuestro Dockerfile:

```dockerfile
FROM nginx:latest

WORKDIR /usr/share/nginx/html

COPY index.html index.html
```

Ahora crearemos un pequeño achivo HTML para servir con nginx en nuestro Dockerfile. Similar a los pasos anteriores, ahora crea un nuevo archivo `index.html` y agrega el siguiente contenido en el:

```html
<!doctype html>
<html>
  <head>
    <title>Curso DevOps - Construyendo un Dockerfile</title>
  </head>
  <body>
    <h1>OK!</h1>
    <p>Bien hecho. Has construido tu primer <strong>Dockerfile</strong> exitosamente.</p>
  </body>
</html>
```

#### Construyendo la imagen con `docker build`

Ya hemos preparado todos los archivos que necesitábamos. Es hora de hacer magia. Con el mismo comando de `docker`, ejecutarmos el sub-comando de `build` para ayudarnos a construir la imagen.

```shell
$ docker build --tag nginx:local .
[+] Building 0.5s (8/8) FINISHED
 => [internal] load build definition from 01-basic-nginx.Dockerfile               0.0s
 => => transferring dockerfile: 51B                                               0.0s
 => [internal] load .dockerignore                                                 0.0s
 => => transferring context: 2B                                                   0.0s
 => [internal] load metadata for docker.io/library/nginx:latest                   0.4s
 => [internal] load build context                                                 0.0s
 => => transferring context: 267B                                                 0.0s
 => [1/3] FROM docker.io/library/nginx:latest@sha256:[...]                        0.0s
 => [2/3] WORKDIR /usr/share/nginx/html                                           0.0s
 => [3/3] COPY 01-index.html index.html                                           0.0s
 => exporting to image                                                            0.0s
 => => exporting layers                                                           0.0s
 => => writing image sha256:[...]                                                 0.0s
 => => naming to docker.io/library/nginx:local                                    0.0s
```

> Ampliando en el comando que acabámos de ejecutar, vemos que tenemos `--tag` seguido de `nginx:local` y finalmente un `.` (punto). Al construir imágenes, es importante indicarle a docker cuál es el contexto actual (en otras palabras, el lugar de trabajo raíz), y para eso es el `.`. `--tag` lo utilizamos para "nombrar" o "etiquetar" nuestra imagen resultante.

Ahora veamos la imagen resultante con `docker images`:

```shell
$ docker images
REPOSITORY   TAG       IMAGE ID       CREATED          SIZE
nginx        local     e22ea75a9045   55 seconds ago   135MB
```

#### Ejecutando la imagen con `docker run`

Finalmente, para la validar que nuestra imagen recien construida funciona como esperamos, procederemos a usar `docker run`:

```shell
doker run --rm --name nginx-web-server -p '80:80' nginx:local
```

En este comando `--rm` nos ayuda a auto eliminar el contenedor una vez termina su trabajo o le instruimos que se detenga. `-p` nos ayuda a "exponer" un puerto del contenedor y publicarlo en un puerto de nuestra máquina local.

En los logs del contenedor podemos ver lo siguiente:

```shell
$ doker run --rm --name nginx-web-server -p '80:80' nginx:local
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
[date] [notice] 1#1: using the "epoll" event method
[date] [notice] 1#1: nginx/1.23.1
[date] [notice] 1#1: built by gcc 10.2.1 20210110 (Debian 10.2.1-6)
[date] [notice] 1#1: OS: Linux 5.10.104-linuxkit
[date] [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
[date] [notice] 1#1: start worker processes
[date] [notice] 1#1: start worker process 31
[date] [notice] 1#1: start worker process 32
[date] [notice] 1#1: start worker process 33
[date] [notice] 1#1: start worker process 34
[date] [notice] 1#1: start worker process 35
[date] [notice] 1#1: start worker process 36
```

Oh, vaya, hay muchas líneas que no entendemos. Pero no debemos preocuparnos, esto es totalmente normal en la imagen tipo nginx pues son los pasos que se van ejecutando gracias a lo definido en nuestra imagen base (`FROM`). Para comprobar que todo ha ido bien, podemos dirigirnos a [localhost](http://localhost) y visualizar nuestro `index.html`.

![C1-M04-L402-001](images/C1-M04-L402-001.png)

---

¡Listo! :partying_face: Has creado tu primer Dockerfile a partir de una imagen simple de `nginx` y un `index.html` propio.
