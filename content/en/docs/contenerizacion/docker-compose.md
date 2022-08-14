---
title : "Docker Compose"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "contenerizacion"
weight: 504
toc: true
---

## Compose

[Compose] es una herramienta para definir y ejecutar aplicaciones Docker de varios contenedores. Con [Compose], utiliza un archivo `YAML` para configurar los servicios de su aplicación. Luego, con un solo comando, crea e inicia todos los servicios desde su configuración. Para obtener más información sobre todas las funciones de [Compose], consulte la lista de funciones.

[Compose] funciona en todos los entornos: producción, puesta en escena, desarrollo, pruebas, así como flujos de trabajo de CI. Puede obtener más información sobre cada caso en [Casos de uso común][Docker Compose Common Use Cases].

El uso de [Compose] es básicamente un proceso de tres pasos:

- Defina el entorno de su aplicación con un `Dockerfile` para que pueda reproducirse en cualquier lugar.
- Defina los servicios que componen su aplicación en `docker-compose.yml` para que puedan ejecutarse juntos en un entorno aislado.
- Ejecute `docker compose up` y [el comando Docker compose][Docker Compose Command] inicia y ejecuta toda su aplicación. Alternativamente, puede ejecutar docker-compose up usando el binario docker-compose.

Un `docker-compose.yml` se ve así:

```yaml
services:
  web:
    build: .
    ports:
      - "8000:5000"
    volumes:
      - .:/code
      - logvolume01:/var/log
    links:
      - redis
  redis:
    image: redis
volumes:
  logvolume01: {}

```

[Compose] tiene comandos para administrar todo el ciclo de vida de su aplicación:

- Iniciar, detener y reconstruir servicios
- Ver el estado de los servicios en ejecución
- Transmita la salida de registro de los servicios en ejecución
- Ejecutar un comando único en un servicio

## Funcionalidades

Las características de Compose que lo hacen efectivo son:

- Múltiples entornos aislados en un solo host
- Conservar datos de volumen cuando se crean contenedores
- Solo recrear contenedores que hayan cambiado
- Variables y movimiento de una composición entre entornos

### Múltiples entornos aislados

[Compose] usa un nombre de proyecto para aislar los entornos entre sí. Puede hacer uso de este nombre de proyecto en varios contextos diferentes:

- en un host de desarrollo, para crear varias copias de un solo entorno, como cuando desea ejecutar una copia estable para cada rama de función de un proyecto
- en un servidor CI, para evitar que las compilaciones interfieran entre sí, puede establecer el nombre del proyecto en un número de compilación único
- en un host compartido o dev host, para evitar que diferentes proyectos, que pueden usar los mismos nombres de servicio, interfieran entre sí

El nombre del proyecto predeterminado es el nombre base del directorio del proyecto. Puede establecer un nombre de proyecto personalizado mediante la opción de línea de comando `-p` o la variable de entorno [COMPOSE_PROJECT_NAME].

El directorio del proyecto predeterminado es el directorio base del archivo Compose. Se puede definir un valor personalizado con la opción de línea de comando `--project-directory`.

### Conservar datos de volumen

Compose conserva todos los volúmenes utilizados por sus servicios. Cuando se ejecuta `docker-compose up`, si encuentra contenedores de ejecuciones anteriores, copia los volúmenes del contenedor anterior al contenedor nuevo. Este proceso garantiza que no se pierda ningún dato que haya creado en los volúmenes.

Si usa `docker-compose` en una máquina con Windows, consulte Variables de entorno y ajuste las [variables de entorno][Docker Composer Environment Variables] necesarias para sus necesidades específicas.

### Solo recrear contenedores que hayan cambiado

Compose almacena en caché la configuración utilizada para crear un contenedor. Cuando reinicia un servicio que no ha cambiado, Compose reutiliza los contenedores existentes. La reutilización de contenedores significa que puede realizar cambios en su entorno muy rápidamente.

### Variables y movimiento de una composición entre entornos

Compose admite variables en el archivo Compose. Puede usar estas variables para personalizar su composición para diferentes entornos o diferentes usuarios.

Puede extender un archivo Compose utilizando el campo `extends` o creando varios archivos Compose.

## Casos de uso común

Compose se puede utilizar de muchas maneras diferentes. A continuación se describen algunos casos de uso comunes.

### Entornos de desarrollo

Cuando desarrolla software, la capacidad de ejecutar una aplicación en un entorno aislado e interactuar con ella es crucial. La herramienta de línea de comandos `Compose` se puede utilizar para crear el entorno e interactuar con él.

El [archivo Compose][Compose File] proporciona una forma de documentar y configurar todas las dependencias del servicio de la aplicación (bases de datos, colas, cachés, API de servicios web, etc.). Con la herramienta de línea de comandos Compose, puede crear e iniciar uno o más contenedores para cada dependencia con un solo comando (`docker-compose up`).

Juntas, estas características brindan una manera conveniente para que los desarrolladores comiencen un proyecto. Compose puede reducir una "guía de inicio para desarrolladores" de varias páginas a un solo archivo de Compose legible por máquina y algunos comandos.

### Entornos de prueba automatizados

Una parte importante de cualquier proceso de implementación continua o integración continua es el conjunto de pruebas automatizado. Las pruebas automatizadas de extremo a extremo requieren un entorno en el que ejecutar las pruebas. Compose proporciona una forma conveniente de crear y destruir entornos de prueba aislados para su conjunto de pruebas. Al definir el entorno completo en un [archivo Compose][Compose File], puede crear y destruir estos entornos con solo unos pocos comandos:

```shell
 docker-compose up -d

 ./run_tests

 docker-compose down
```

### Implementaciones de host único

Compose se ha centrado tradicionalmente en los flujos de trabajo de desarrollo y prueba, pero con cada versión avanzamos en funciones más orientadas a la producción.

> **NOTA DE INTERÉS**: Para más información sobre Compose en producción, ver [Compose In Production]. En este curso no indagaremos en este contenido debido a que nos enfocaremos en los orquestadores de contenedores.

<!-- Referencias -->
[Compose]: ../../referencias/README.md#docker-compose
[Docker Compose Features]: ../../referencias/README.md#docker-compose-features
[Docker Compose Common Use Cases]: ../../referencias/README.md#docker-compose-common-use-cases
[Docker Compose Command]: ../../referencias/README.md#docker-compose-command
[Docker Composer Environment Variables]: ../../referencias/README.md#docker-compose-environment-variables
[Compose File]: ../../referencias/README.md#docker-compose-file
[Compose In Production]: ../../referencias/README.md#docker-compose-in-production
[COMPOSE_PROJECT_NAME]: ../../referencias/README.md#COMPOSE_PROJECT_NAME
