---
title : "Lab 5.1: Introducción a GitHub Actions"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "entrega-continua"
weight: 707
toc: true
---

Solo necesita un repositorio de GitHub para crear y ejecutar un flujo de trabajo de acciones de GitHub. En esta guía, agregará un flujo de trabajo que demuestra algunas de las funciones esenciales de GitHub Actions.

El siguiente ejemplo muestra cómo se pueden activar automáticamente los trabajos de GitHub Actions, dónde se ejecutan y cómo pueden interactuar con el código en su repositorio.

## Creando el primer `workflow`

1. Cree un directorio `.github/workflows` en su repositorio en GitHub si este directorio aún no existe.
2. En el directorio `.github/workflows`, cree un archivo denominado `demo.yml` y copia el siguiente contenido dentro de el:

    ```yaml
    name: 00-demo

    on: [push]

    jobs:
      demo:
        runs-on: ubuntu-latest
        steps:
          - run: echo "🎉 Este job fue automáticamente lanzado por un evento tipo ${{ github.event_name }}."

          - run: echo "🐧 Este job está corriendo en un servidor ${{ runner.os }} manejado por GitHub!"

          - run: echo "🔎 El nombre de tu rama es ${{ github.ref }} y tu repositorio es ${{ github.repository }}."

          - name: Obteniendo el código de tu repositorio
            uses: actions/checkout@v3

          - run: echo "💡 El repositorio ${{ github.repository }} fue clonado en el agente."

          - run: echo "🖥️ El workflow está listo para probar tu código en el agente."

          - name: Listando todos los archivos del repositorio
            run: ls ${{ github.workspace }}
    ```

3. Crea un nuevo branch y agrega un commit con el nuevo archivo que acabas de crear. Al hacer esto se activa el evento `push` y automáticamente ejecuta el flujo de trabajo descrito en el archivo.

Tras ir a la pestaña de `Actions`, podemos observar lo siguiente:

![C1-M05-L501-001](images/C1-M05-L501-001.png)

A la izquierda podemos notar una lista general de todos los "**workflows**" que tenemos configurados para nuestro repositorio. Como solo agregamos un workflow, pues solo tenemos `00-demo` en esta lista.

> :bulb: El nombre de nuestro workflow es exactamente igual al que tenemos en nuestro archivo en la directiva `name`. Si deseas que tenga un nombre diferente, puedes hacerlo. ¡Intentalo!

Al dar click en nuestro workflow, podemos ver algo similar a esta vista:

![C1-M05-L501-002](images/C1-M05-L501-002.png)

De allí podemos ver información general de nuestro workflow, y finalmente, para ver los resultados del mismo, podemos entrar al "**job**" llamado `demo`:

![C1-M05-L501-003](images/C1-M05-L501-003.png)

Habrán `jobs` cuyos `steps` podrán decoplarse para ver información, como en este mismo ejemplo, donde podemos ver la lista de archivos listado en nuestro repositorio:

![C1-M05-L501-004](images/C1-M05-L501-004.png)

¡Felicidades! :partying_face: Has logrado desplegar tu primer flujo de trabajo en GitHub Actions. Estás ahora más cerca de poder diseñar flujos de integración más complejos.
