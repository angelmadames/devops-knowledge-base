---
title : "Pruebas de software"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "aseguramiento-de-calidad"
weight: 1002
toc: true
---

La prueba de software es el proceso de evaluar y verificar que un producto o aplicación de software hace lo que se supone que debe hacer. Los beneficios de las pruebas incluyen:

- la prevención de errores,
- la reducción de los costos de desarrollo y,
- la mejora del rendimiento.

## Antecedentes

Las pruebas de software llegaron junto con el desarrollo de software, que tuvo sus inicios justo después de la segunda guerra mundial. Al informático Tom Kilburn se le atribuye la escritura de la primera pieza de software, que debutó el 21 de junio de 1948 en la Universidad de Manchester en Inglaterra. Realizó cálculos matemáticos utilizando instrucciones de código de máquina.

La depuración era el principal método de prueba en ese momento y lo siguió siendo durante las siguientes dos décadas. En la década de 1980, los equipos de desarrollo miraban más allá de aislar y corregir errores de software para probar aplicaciones en entornos del mundo real. Estableció el escenario para una visión más amplia de las pruebas, que abarcaba un proceso de control de calidad que formaba parte del ciclo de vida del desarrollo de software.

“En la década de 1990, hubo una transición de las pruebas a un proceso más completo llamado garantía de calidad, que cubre todo el ciclo de desarrollo de software y afecta los procesos de planificación, diseño, creación y ejecución de casos de prueba, soporte para casos de prueba existentes y pruebas. entornos”, dice Alexander Yaroshko en su publicación en el sitio para desarrolladores de uTest.

“Las pruebas habían alcanzado un nivel cualitativamente nuevo, lo que condujo a un mayor desarrollo de metodologías, la aparición de herramientas poderosas para administrar el proceso de pruebas y herramientas de automatización de pruebas”.

### Pruebas continuas

Tradicionalmente, las pruebas de software se han separado del resto del desarrollo. A menudo se lleva a cabo más adelante en el ciclo de vida del desarrollo de software después de la etapa de construcción o ejecución del producto. Es posible que un probador solo tenga una pequeña ventana para probar el código, a veces justo antes de que la aplicación salga al mercado. Si se encuentran defectos, puede haber poco tiempo para volver a codificar o volver a probar. No es raro lanzar el software a tiempo, pero con errores y correcciones necesarias. O un equipo de pruebas puede corregir errores pero perder una fecha de lanzamiento.

Hacer actividades de prueba al principio del ciclo ayuda a mantener el esfuerzo de prueba al frente en lugar de como una ocurrencia tardía para el desarrollo. Las pruebas de software anteriores también significan que los defectos son menos costosos de resolver.

Muchos equipos de desarrollo ahora usan una metodología conocida como prueba continua. Es parte de un enfoque DevOps, donde el desarrollo y las operaciones colaboran durante todo el ciclo de vida del producto. El objetivo es acelerar la entrega de software mientras se equilibran los costos, la calidad y el riesgo. Con esta técnica de prueba, los equipos no necesitan esperar a que se construya el software antes de que comience la prueba. Pueden ejecutar pruebas mucho antes en el ciclo para descubrir defectos antes, cuando son más fáciles de corregir.

## Caso de prueba

En ingeniería de software, un caso de prueba es una especificación de las entradas, las condiciones de ejecución, el procedimiento de prueba y los resultados esperados que definen una sola prueba que se ejecutará para lograr un objetivo de prueba de software particular, como ejercitar una ruta de programa particular o verificar cumplimiento de un requisito específico.

Los casos de prueba subyacen a las pruebas que son metódicas en lugar de aleatorias. Se puede construir una batería de casos de prueba para producir la cobertura deseada del software que se está probando.

## Tipos de pruebas de software

Hay muchos tipos diferentes de pruebas de software, cada una con objetivos y estrategias específicos:

- **Pruebas de aceptación**: verificar si todo el sistema funciona según lo previsto.
- **Pruebas de integración**: Asegurar que los componentes o funciones del software operen juntos.
- **Pruebas unitarias**: Validar que cada unidad de software funcione como se espera. Una unidad es el componente comprobable más pequeño de una aplicación.
- **Pruebas funcionales**: Comprobación de funciones mediante la emulación de escenarios comerciales, en función de los requisitos funcionales. La prueba de caja negra es una forma común de verificar funciones.
- **Pruebas de rendimiento**: probar cómo funciona el software bajo diferentes cargas de trabajo. Las pruebas de carga, por ejemplo, se utilizan para evaluar el rendimiento en condiciones de carga reales.
- **Pruebas de regresión**: verificar si las nuevas características rompen o degradan la funcionalidad. Las pruebas de cordura se pueden utilizar para verificar menús, funciones y comandos a nivel superficial, cuando no hay tiempo para una prueba de regresión completa.
- **Prueba de estrés**: prueba de cuánta tensión puede soportar el sistema antes de que falle. Considerado como un tipo de prueba no funcional.
- **Pruebas de usabilidad**: validar qué tan bien un cliente puede usar un sistema o una aplicación web para completar una tarea.

En cada caso, la validación de los requisitos básicos es una evaluación crítica. Igual de importante, las pruebas exploratorias ayudan a un probador o equipo de pruebas a descubrir escenarios y situaciones difíciles de predecir que pueden conducir a errores de software.

Incluso una aplicación simple puede estar sujeta a una gran cantidad y variedad de pruebas. Un plan de gestión de pruebas ayuda a priorizar qué tipos de pruebas proporcionan el mayor valor, dado el tiempo y los recursos disponibles. La efectividad de las pruebas se optimiza ejecutando la menor cantidad de pruebas para encontrar la mayor cantidad de defectos.

## Importancia

Pocos pueden argumentar en contra de la necesidad de un control de calidad al desarrollar software. La entrega tardía o los defectos del software pueden dañar la reputación de una marca, lo que genera clientes frustrados y perdidos. En casos extremos, un error o defecto puede degradar los sistemas interconectados o causar fallas graves.

Aunque la prueba en sí misma cuesta dinero, las empresas pueden ahorrar millones por año en desarrollo y soporte si cuentan con una buena técnica de prueba y procesos de control de calidad. Las primeras pruebas de software descubren problemas antes de que un producto salga al mercado. Cuanto antes reciban los equipos de desarrollo los comentarios de las pruebas, antes podrán abordar problemas como:

- Defectos arquitectónicos
- Malas decisiones de diseño.
- Funcionalidad no válida o incorrecta
- Vulnerabilidades de seguridad
- Problemas de escalabilidad

Cuando el desarrollo deja un amplio espacio para las pruebas, mejora la confiabilidad del software y las aplicaciones de alta calidad se entregan con pocos errores. Un sistema que cumple o incluso supera las expectativas del cliente genera potencialmente más ventas y una mayor cuota de mercado.

## Enfoques de prueba

Existen varios enfoques posibles a la hora de realizar pruebas de software:

- Estático
- Dinámico
- Pasivo
- Exploratorio
- Enfoque de caja
  - Caja blanca
  - Caja negra
  - Caja gris

### Estático y dinámico

Las *revisiones*, *recorridos* o *inspecciones* se denominan **pruebas estáticas**, mientras que la ejecución de código programado con un conjunto determinado de *casos de prueba* se denomina **pruebas dinámicas**.

Las pruebas estáticas a menudo son implícitas, como la revisión, además cuando las herramientas de programación/editores de texto verifican la estructura del código fuente o los compiladores (precompiladores) verifican la sintaxis y el flujo de datos como análisis de programa estático. Las pruebas dinámicas tienen lugar cuando se ejecuta el propio programa. Las pruebas dinámicas pueden comenzar antes de que el programa esté completo al 100% para probar secciones particulares de código y se aplican a funciones o módulos discretos. Las técnicas típicas para estos son el uso de stubs/drivers o la ejecución desde un entorno de depuración.

Las **pruebas estáticas** implican *verificación*, mientras que las **pruebas dinámicas** también implican *validación*.

### Pasivo

Las pruebas pasivas significan verificar el comportamiento del sistema sin ninguna interacción con el producto de software. A diferencia de las pruebas activas, los probadores no proporcionan ningún dato de prueba, pero miran los registros y seguimientos del sistema. Buscan patrones y comportamientos específicos para tomar algún tipo de decisión. Esto está relacionado con la verificación del tiempo de ejecución sin conexión y el análisis de registros.

### Exploratorio

Las pruebas exploratorias son un enfoque para las pruebas de software que se describen de manera concisa como aprendizaje, diseño de pruebas y ejecución de pruebas simultáneos.

Cem Kaner, quien acuñó el término en 1984, define la prueba exploratoria como "un estilo de prueba de software que enfatiza la libertad personal y la responsabilidad del probador individual para optimizar continuamente la calidad de su trabajo al tratar la prueba- aprendizaje relacionado, diseño de pruebas, ejecución de pruebas e interpretación de resultados de pruebas como actividades de apoyo mutuo que se ejecutan en paralelo a lo largo del proyecto".

### Enfoque de caja

Los métodos de prueba de software se dividen tradicionalmente en pruebas de caja blanca y caja negra. Estos dos enfoques se utilizan para describir el punto de vista que adopta el probador al diseñar casos de prueba. Un enfoque híbrido llamado prueba de caja gris también se puede aplicar a la metodología de prueba de software.

Con el concepto de prueba de caja gris, que desarrolla pruebas a partir de elementos de diseño específicos, ganando importancia, esta "distinción arbitraria" entre pruebas de caja blanca y negra se ha desvanecido un poco.

#### Caja blanca

Verifica las estructuras internas o el funcionamiento de un programa, a diferencia de la funcionalidad expuesta al usuario final. En las pruebas de caja blanca, se utiliza una perspectiva interna del sistema (el código fuente), así como las habilidades de programación, para diseñar casos de prueba. El probador elige entradas para ejercitar rutas a través del código y determinar las salidas apropiadas.

Algunas técnicas usadas en las pruebas de caja blanca:

- **Pruebas de API**: prueba de la aplicación utilizando API públicas y privadas.
- **Cobertura de código**: creación de pruebas para satisfacer algunos criterios de cobertura de código.
- **Métodos de inyección de fallas**: introducción intencional de fallas para medir la eficacia de las estrategias de prueba.
- **Métodos de prueba de mutación**
- **Métodos de prueba estáticos**

#### Caja negra

Trata el software como una "caja negra", examinando la funcionalidad sin ningún conocimiento de la implementación interna, sin ver el código fuente. Los evaluadores solo conocen lo que se supone que debe hacer el software, no cómo lo hace.

Los métodos de prueba de caja negra incluyen:

- Partición de equivalencia
- Análisis de valor límite
- Prueba de todos los pares
- Tablas de transición de estado
- Prueba de tabla de decisión
- Prueba de caso de uso
