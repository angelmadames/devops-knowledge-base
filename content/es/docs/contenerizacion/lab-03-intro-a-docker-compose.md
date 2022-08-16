---
title : "Lab 4.3: Intro a Docker Compose"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "contenerizacion"
weight: 507
toc: true
---

> :warning: Este tutorial usa la versión `20.10.17-ce` de Docker. Si encuentra alguna parte del laboratorio incompatible con una versión futura, por favor cree un "**issue**" en el repositorio original.

## Requerimientos

- Capacidad de lectura del idioma inglés.
- Comodidad básica con la línea de comandos y el uso de un editor de texto.
- Uso básico de `docker` y manejo de `Dockerfiles`, asumimos que luego de haber tomado el [Laboratorio 4.2 - Creando primer Dockerfile](../lab-02-creando-primer-dockerfile) ya se está preparado para tomar este laboratio.

## Docker compose

Docker compose es una herramienta creada por el equipo de Docker para facilitar la tarea de crear y configurar varios contenedores en un entorno de desarrollo. La contraparte de `docker-compose` para el entorno de producción es `docker swarm`. Docker compose toma como entrada un archivo de configuración YAML y crea los recursos (*containers*, *networks*, *volumes*, etc.) comunicándose con el demonio de docker a través de la API de Docker.

## Introducción

`Compose` es un proyecto de código abierto oficial de Docker y es responsable de la orquestación rápida de los contenedores de Docker.

El código actualmente está abierto en [github.com/docker/compose][Docker Compose GitHub].

A través de la introducción en la primera parte, sabemos que el uso de un archivo de plantilla de `Dockerfile` permite a los usuarios definir fácilmente un contenedor de aplicación independiente. Sin embargo, en el trabajo diario, a menudo se da el caso de que varios contenedores necesitan cooperar para completar una determinada tarea. Por ejemplo, para implementar un proyecto web, además del propio contenedor de servicios web, a menudo es necesario agregar un contenedor de servicios de base de datos back-end e incluso un contenedor de equilibrio de carga.

`Compose` satisface esta necesidad. Permite al usuario definir un conjunto de contenedores de aplicaciones asociados como un proyecto a través de un archivo de plantilla `docker-compose.yml` independiente (formato YAML).

Hay dos conceptos importantes en `Compose`:

- **Service**: un contenedor para una aplicación que en realidad puede incluir varias instancias de contenedor que ejecutan la misma imagen.

- **Project**: una unidad de negocio completa que consiste en un conjunto de contenedores de aplicaciones asociados, definidos en el archivo `docker-compose.yml`.

El objeto de administración predeterminado de `Compose` es un proyecto que proporciona una administración conveniente del ciclo de vida de un conjunto de contenedores en un proyecto a través de subcomandos.

El proyecto `Compose` está escrito en [Go] y la implementación llama a la API proporcionada por el servicio Docker para administrar el contenedor. Por lo tanto, siempre que la plataforma que se opera admita la API de Docker, puede usar Compose para administrarla.

## Archivo Compose de ejemplo

```yaml
---
services:
  web:
    image: nginx:alpine
    depends_on:
      - database
    ports:
      - "8080:8080"

  database:
    image: mariadb:10
    environment:
      MARIADB_ROOT_PASSWORD: example

  adminer:
    image: adminer
    depends_on:
      - database
    ports:
      - "8080:8080"
```

<!-- Referncias -->
[Docker Compose GitHub]: ../../referencias/enlaces#docker-compose-github
[Go]: ../../referencias/enlaces#go-progamming-language
