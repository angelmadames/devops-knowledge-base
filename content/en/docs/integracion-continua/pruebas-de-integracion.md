---
title : "Pruebas de integración"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "integracion-continua"
weight: 603
toc: true
---

Las pruebas de integración continua son pruebas enfocadas y ejecutadas durante el proceso de CI. Las pruebas en el proceso de CI permiten una retroalimentación rápida y, por diseño, detiene la progresión del artefacto si no se alcanza la calidad mínima.

En el SDLC, un lugar natural para comenzar a ejecutar ciertos pasos que fomenten la confianza del equipo en realizar iteraciones frecuentes, garanticen la calidad y la coherencia de los cambios, es la integración continua.

## Pruebas de integración

La repetibilidad es un concepto crucial en la creación y construcción de software. Tener la capacidad de crear o recrear en cualquier momento aumenta la confianza del equipo sobre el producto. Uno de los grandes beneficios de la integración continua es justo esa, la repetibilidad, y se logra gracias a las pruebas de integración.

Las pruebas de integración continua son pruebas enfocadas y ejecutadas durante el proceso de CI y orquestadas por herramientas de CI que dan cuenta de la creación, el empaquetado y la publicación de artefactos. Las pruebas en el proceso de CI permiten una retroalimentación rápida y, por diseño, detiene la progresión del artefacto si no se alcanza la calidad mínima.

Por lo general, las pruebas de CI se centran en el artefacto antes del despliegue en el primer entorno de integración.

Las pruebas de integración continua sirven como puertas de calidad durante cada uno de los tres pilares de CI, construcción, paquete y publicación de artefactos.

## Importancia de CI

La integración continua permite una mayor transparencia y visión de futuro en el proceso de desarrollo y entrega de software. No solo beneficia a los desarrolladores sino a todos los segmentos de la organización. Estos beneficios aseguran que la organización pueda hacer mejores planes y ejecutarlos siguiendo la estrategia de mercado.

Para comprender la importancia de la CI, estos son algunos de sus beneficios:

- **Reduce el riesgo**: Los defectos y errores del código se pueden detectar antes. Estos errores y fallas se pueden corregir fácilmente y tomar menos tiempo, lo que hace que el proceso general sea más económico. Acelera el mecanismo de retroalimentación, por lo que la comunicación es más fluida y efectiva.
- **Mejor comunicación**: Permite que colaborar bajo un repositorio sea fácil, regularizado, y transparente. A largo plazo, la velocidad de comunicación es más eficiente y asegura que todos en el equipo estén en sintonía.
- **Mayor calidad del producto**: Proporciona funciones como revisión de código y detección de calidad de código. Si el código no coincide con el nivel estándar, se le notificara al equipo de trabajo. La revisión de código ayuda a los desarrolladores a mejorar continuamente sus habilidades de programación.
- **Tiempo de espera reducido**:  El tiempo entre el desarrollo, la integración, las pruebas y la implementación de la aplicación se reduce considerablemente. CI se asegura de que todos estos procesos continúen sin importar qué.

## Pruebas On-process y Off-process

### On-process

Las pruebas que se pueden ejecutar en el agente/ejecutor del servicio de CI representan una prueba **on-process**.

> **On-process** significa "en proceso" en español, que puede interpretarse de manera que lo que se realiza está "dentro del proceso".

### Off-process

Un identificador distintivo de las pruebas **off-process** es enviar datos, código o un artefacto a un tercero fuera del proceso de integración continua. Por ejemplo, al escanear un contenedor, la imagen sería introspeccionada por un proceso externo en busca de vulnerabilidades.

No importa si la prueba está dentro o fuera del proceso, la cobertura de la prueba está diseñada para infundir confianza en los artefactos producidos. Hay varias metodologías de prueba que se pueden ejecutar en una canalización de integración continua y vale la pena implementar.

## Tipos de pruebas de integración

Recorriendo el inicio del proceso de CI, desde que se registra un cambio en el código, hasta un artefacto publicado en un ambiente de producción, existen varios tipos de pruebas de CI para ejecutar.

### Calidad de código

Las herramientas de calidad de código, como [SonarQube], se centran en el análisis de código estático y son prudentes durante los cambios de código.

El código por sí solo no se ejecuta y tiene en cuenta todas las variables de infraestructura y entorno que impulsan el software en ejecución, aunque con el análisis del código se puede inferir la calidad.

La búsqueda de **bloques muertos** (código que nunca se ha llamado o alcanzado), la calidad/estándares de la sintaxis y los posibles problemas de seguridad forman parte de las pruebas de calidad del código. Aunque la calidad del código no se centra en la funcionalidad real del código, que es donde entra en juego la prueba unitaria.

### Unitarias

Las pruebas por excelencia que se ejecutan con nuevas funciones se escriben o actualizan son las **pruebas unitarias**.

Las pruebas unitarias se enfocan en los bloques/métodos de código que cambiaron.

Las pruebas unitarias generalmente se encuentran en pruebas de procesos donde se crean objetos simulados y se verifican las afirmaciones.

Algunos ejemplos son [JUnit] en el mundo Java y [Mocha] en el mundo Node.js. Las pruebas unitarias están diseñadas para ser granulares y ejecutarse como una *suite*.

Por ejemplo, si está escribiendo una aplicación de calculadora y agregando una nueva función para la división de números enteros, una prueba unitaria podría ser cómo se maneja la división por cero o el resultado esperado de ejecutar esa división.

Si el caso de uso requiere métodos/partes externas para llamar, la cobertura de prueba unitaria no sería suficiente y la prueba de integración entraría en acción.

### Integración

Como se construyen múltiples piezas de funcionalidad, rara vez viven en el vacío. La aplicación de calculadora tiene más que solo división, y la división puede ser complicada, por ejemplo, decimales, precisión, etc.

Para las pruebas de integración en el contexto de la integración continua, se centrará en probar módulos cruzados de la aplicación.

Volviendo al ejemplo de la calculadora, una prueba de integración sería dividir y multiplicar al mismo tiempo.

Hay mucha superposición en las herramientas modernas de pruebas unitarias y de integración. Es posible encontrar una única herramienta que haga ambas pruebas, pero siempre se debe tener presente sus diferencias en la implementación actual.

Las pruebas de integración aportan al concepto de continuidad ya que considera que los cambios existentes versus las nuevas funciones y los nuevos cambios en el código deben funcionar, de manera adecuada, en conjunto.

### Seguridad

El adagio de que el software envejece más como la leche que el vino es cierto, especialmente en el software moderno que depende del código abierto de terceros, el equipo de ingeniería rara vez es el autor del `100%` de los bits que van a la distribución final. Con la “niebla del desarrollo”, no sería razonable que un ingeniero conociera todas las dependencias transitivas (dependencias que llaman a otras dependencias).

El propósito de las pruebas de seguridad/licencia es encontrar la exposición y el riesgo de usar ciertos paquetes. Las herramientas de análisis de seguridad/licencia, como [Blackduck], [Snyk] y [StackHawk], tienen diferentes métodos de introspección.

Algunas herramientas requieren el artefacto terminado, como una imagen acoplable, para ejecutar. Otras herramientas se integran a nivel de código introspeccionando archivos de compilación resultantes.

Un beneficio adicional con la ejecución de pruebas en procesos de CI es que se ejecutan con mayor frecuencia, lo que permite realizar pruebas continuas.

<!-- Referencias -->
[SonarQube]: ../../referencias/enlaces#sonarqube
[Blackduck]: ../../referencias/enlaces#blackduck
[Snyk]: ../../referencias/enlaces#snyk
[StackHawk]: ../../referencias/enlaces#stackhawk
[JUnit]: ../../referencias/enlaces#junit
[Mocha]:  ../../referencias/enlaces#mocha
