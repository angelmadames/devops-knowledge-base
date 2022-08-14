---
title : "Gestión de paquetes"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "ciclo-de-desarrollo"
weight: 404
toc: true
---

En esta etapa de tu carrera profesional, probablemente ya te encuentres familiarizado con términos como, librerías, paquetes, frameworks, entre otros.

Básicamente, en el desarrollo de software ya existen funcionalidades que fueron desarrolladas por otros que pueden cumplir perfectamente con tus requerimientos de aplicación actual; así que en vez de reescribir algo que ya existe, puedes referenciar ese recurso como dependencia y utilizarlo en tu aplicación. Aunque han habido muchos debates sobre las ventajas y desventajas de esta práctica, sin duda alguna ha sido adoptada en gran proporción gracias a la agilidad que habilita a los equipos de desarrollo.

Considero importante mencionar entonces la gestión de paquetes, puesto que en mi experiencia, conocer y entender este proceso colabora de manera inmensa en la correcta y apropiada implementación de los flujos de integración y entrega continua.

## Dependencias

Una dependencia es todo aquello requerido por tu aplicación que debe ser instalado desde una fuente externa. De manera más específica, es un software de terceros.

Un proyecto puede tener cualquier cantidad de dependencias, desde ninguna hasta muchas, y sus dependencias pueden incluir subdependencias que no instaló explícitamente; sus dependencias pueden tener sus propias dependencias.

Una dependencia puede ser tan pequeña y simple como puede ser grande y compleja. No hay límites establecidos más allá de los requerimientos del software.

## Gestor de paquetes

El [gestor de paquetes][Package management basics] es una herramienta de software que proporciona un método para instalar, manipular, o eliminar dependencias (también denominadas `paquetes`).

En teoría, es posible no utilizar un gestor de paquetes, y descargar y almacenar manualmente las dependencias de su proyecto, pero un gestor de paquetes abstraerías estas complejidades.

Si no sea usa un gestor de paquetes, se tendría que manejar manualmente lo siguiente:

- Descargarlos y colocarlos en las ubicaciones correctas en su proyecto.
- Referencias todos los archivos del paquete correctamente.
- Verificarlos para asegurarse de que no tengan ninguna vulnerabilidad conocida.
- Escribir el código para incluir los paquetes en su aplicación.
- Hacer lo mismo para todas las subdependencias de los paquetes, de las cuales podría haber decenas o cientos.
- Eliminando todos los archivos nuevamente si desea eliminar los paquetes.

Además, los gestores de paquetes manejan *dependencias duplicadas*.

## Contextos de instalación de dependencias

Las dependencias se pueden instalar de manera **global** o **localmente**.

Aunque suele haber más ventajas para la instalación global, las ventajas para la instalación local son más importantes, como la *portabilidad del código* y el *bloqueo de versiones*.

Por ejemplo, si su proyecto se basó en una dependencia con una determinada configuración, querrá asegurarse de que si instaló ese proyecto en otra máquina o volvió a él mucho más tarde, la configuración aún funcionaría. Si se instaló una versión diferente, es posible que no sea compatible. Para mitigar esto, las dependencias se instalan localmente en un proyecto.

## Dependencias del sistema

Las dependencias del sistema son aquellas que se instalan al nivel de sistema operativo. Las dependencias del sistema pueden ser, en el caso de los lenguajes de programación interpretados, todas las utilidades del lenguaje que permiten interpretarlo y ejecutarlo en un momento dado.

Un ejemplo de esto es el caso de [Node.js] en el ecosistema del lenguaje [JavaScript]. [Node.js] debe ser instalado en el sistema operativo antes de poder ejecutar aplicaciones basadas en [JavaScript], por tanto, se considera una dependencia del sistema.

## Dependencias de aplicación

Las dependencias de aplicación son aquellas que son instaladas en un contexto "local" para el proyecto de la aplicación dada. En el mismo ejemplo, si tenemos un proyecto de `JavaScript`, es probable que las dependencias de aplicación se instalen usando [npm] y esto produzca un directorio local relativo a la ruta del proyecto donde la aplicación encontraría las referencias que tiene definidas.

## Registro de paquete

Para que un gestor de paquetes funcione, necesita saber desde dónde instalar los paquetes, y esto viene en forma de un registro de paquetes. El registro es un lugar central en el que se publica un paquete y, por lo tanto, se puede instalar. npm, además de ser un administrador de paquetes, también es el nombre del registro de paquetes más utilizado para paquetes de JavaScript. El registro npm existe en [npmjs.com].

[npm] no es la única opción. Puede administrar su propio registro de paquetes: [GitHub ofrece un servicio de registro de paquetes][GitHub Packages].

Lo importante es que se asegure de haber elegido el mejor registro para usted. Muchos proyectos usarán npm, y nos ceñiremos a esto en nuestros ejemplos durante el resto del módulo.

<!-- Referencias -->
[Package management basics]: ../../referencias/enlaces#package-management-basics
[JavaScript]: ../../referencias/enlaces#javascript
[npm]: ../../referencias/enlaces#npm
[npmjs.com]: ../../referencias/enlaces#npmjs.com
[Node.js]: ../../referencias/enlaces#node.js
[GitHub Packages]: ../../referencias/enlaces#github-packages
