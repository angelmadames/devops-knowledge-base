---
title : "Integración continua (CI)"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "integracion-continua"
weight: 602
toc: true
---

## Definición

La integración continua (CI) es la práctica de automatizar la integración de cambios de código de múltiples colaboradores en un solo proyecto de software.

De manera específica, permite fusionar (*merge*, en inglés) cambios de código con frecuencia en un repositorio donde luego se ejecutan las
pruebas de integración, que pueden ser:

- Compilaciones
- Pruebas de calidad de código
- Pruebas de estilo (convenciones y sintaxis)
- Pruebas automatizadas

Un sistema de control de versiones del código fuente es el corazón del proceso de CI.

## ¿Por qué se necesita la integración continua?

En el pasado, los desarrolladores de un equipo podían trabajar de forma aislada durante un período de tiempo prolongado y solo fusionar sus cambios en la rama principal una vez que se completaba su trabajo.

Al hacer esto, fusionar los cambios era una tarea tedioso y complicada, e implicaba una alta inversión de tiempo. De igual manera, resultaba en una acumulación de errores y fallas que al mezclar todos los cambios eran difíciles de identificar y corregir.

Todos estos factores dificultaban la entrega rápida de actualizaciones a los clientes.

## ¿Cómo funciona?

Con la integración continua, los desarrolladores suelen colaborar en un repositorio compartido mediante un sistema de control de versiones como Git.

Dentro del VCS, un servicio de integración continua crea y ejecuta automáticamente pruebas en los nuevos cambios de código para detectar de inmediato cualquier error.

Dependiendo el resultado, el equipo puede validar si efectivamente los cambios nuevos que se desean integrar cumplen con todas las pruebas necesarias de validación. De no cumplir, se deben corregir los errores y re-ejecutar las pruebas nuevamente. Si cumple, entonces se procede a realizar la fusión en la rama principal del repositorio.

### Servicio de integración de continua

El servicio de integración continua se configura directamente en el sistema de control de versiones, y en el repositorio de la aplicación.

La mayoría de los servicios de aplicación continua reciben su configuración y parametrización de archivos dentro del mismo repositorio.

Veamos algunos ejemplos de archivos de configuración:

- Para GitLab CI, el archivo se encuentra en la ruta raíz, y se nombra `.gitlab-ci.yml`.
- Para GitHub Actions, el archivo se encuentra en el directorio `.github/workflows/` y aunque el nombre es indiferente, deben llevar la extensión de los archivos `YAML`.
- Para CircleCI, el archivo es `config.yml` y se debe colocar en el directorio `.circleci/`.

> En el tema de [Herramientas de CI](03-herramientas-de-ci.md), veremos más detalles de cada uno.

## Beneficios

- **Productividad**: ayuda a su equipo a ser más productivo liberando a los desarrolladores de tareas manuales y fomentando comportamientos que ayudan a reducir la cantidad de errores y fallas que se envían a los clientes.
- **Identificación rápida de errores**: Con pruebas más frecuentes, su equipo puede descubrir y abordar errores antes de que se conviertan en problemas mayores más adelante.
- **Entrega más frecuentes**: ayuda a entregar actualizaciones al usuario final de forma más rápida y frecuente.

## Pilares de la integración continua

Al hablar de CI, existen algunos componentes o pilares que demostrarían una implementación exitosa de este proceso.

> Bueno saber: Cada uno de estos pilares de integración continua tiene su propio ecosistema de herramientas y filosofías.

- **[Gestión de versiones de control de código fuente](../03-ciclo-de-desarrollo-de-software/02-control-de-versiones.md):** Los productos de CI como servicio se centran en el sistema de control de versiones.
- **Pruebas automatizadas**: En general, cuando un desarrollador inserta código usando el sistema de control de versiones, un evento activará el conjunto de pruebas completo para que se ejecute automáticamente.
- **Automatización de compilación**: Las herramientas de CI ayudan a agilizar el proceso de compilación proceso de compilación.
- **Despliegues automatizados:** Cuando las compilaciones están listas para ser distribuidas, pasan por un proceso de despliegue que las habilita en el ambiente de producción.

## Ejemplos de CI/CD

### GitLab CI

En el caso de GitLab, podemos ver [el siguiente ejemplo][GitLab CI Example Node.js Semantic Release] de cómo se define un flujo automatizado:

```yaml
default:
  image: node:latest
  before_script:
    - npm ci --cache .npm --prefer-offline
  cache:
    key: ${CI_COMMIT_REF_SLUG}
    paths:
      - .npm/

workflow:
  rules:
    - if: $CI_COMMIT_BRANCH

variables:
  NPM_TOKEN: ${CI_JOB_TOKEN}

stages:
  - release

publish:
  stage: release
  script:
    - npm run semantic-release
  rules:
    - if: $CI_COMMIT_BRANCH == $CI_DEFAULT_BRANCH
```

### GitHub Actions

Así se ve [un archivo de "workflow" ejemplo][GitHub Actions Example Workflow] para GitHub Actions:

```yaml
name: 'Link Checker: All English'

on:
  push:
    branches:
      - main
  pull_request:

jobs:
  check-links:
    runs-on: "ubuntu-latest"
    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Setup node
        uses: actions/setup-node@v3
        with:
          node-version: 16.13.x
          cache: npm

      - name: Install
        run: npm ci

      - name: Link check (warnings, changed files)
        run: |
          ./script/rendered-content-link-checker.mjs \
            --language en \
            --max 100 \
            --check-anchors \
            --check-images \
            --verbose \
            --list $HOME/files.json

      - name: Link check (critical, all files)
        run: |
          ./script/rendered-content-link-checker.mjs \
            --language en \
            --exit \
            --verbose \
            --check-images \
            --level critical
```

<!-- Referencias -->
[GitLab CI Example Node.js Semantic Release]: ../../referencias/enlaces#gitlab-ci-example-node.js-semantic-release
[GitHub Actions Example Workflow]: ../../referencias/enlaces#github-actions-example-workflow
