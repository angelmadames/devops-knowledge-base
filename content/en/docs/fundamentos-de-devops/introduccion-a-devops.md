---
title : "DevOps: Introducción"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "fundamentos-de-devops"
weight: 201
toc: true
---
<!-- markdownlint-disable MD026 -->

## Origen

Antes de definir de manera puntual lo que es [DevOps][Glosario - DevOps], es importante describir el origen de [DevOps][Glosario - DevOps] debemos hablar primero de Patrick Debois, a quién se le atribuye más comunmente ser el padre del término **[DevOps][Glosario - DevOps]**.

Nuestra historia empieza en `2008` donde Patrick presentó por primera vez el concepto de "infraestructura ágil" en una conferencia en Toronto llamada `Agile 2008`. En 2009, organizó la primera conferencia relacionada a [DevOps][Glosario - DevOps] llamada [DevOpsDays] donde el objetivo era traer a personas de desarrollo y operaciones a trabajar en conjunto.

Inicialmente el tema de la conferencia iba a ser "`Administración de Sistemas Ágil`" (Agile System Administration) pero para Patrick esto era in título muy largo, así que como el enfoque de la conferencia sería orientada a Desarrollo y Operaciones trabajando en conjunto, combinó estas dos palabras obteniendo entonces **DevOps**. Nunca hubo una gran intención o propósito detrás de dicho nombre, solo se quería un nombre más corto.

De acuerdo con el vídeo "[The Short History of DevOps]", luego de la primera instancia de [DevOpsDays], las personas que participaron siguieron conversando sobre este tema en diferentes lugares de la Internet, principalmente en [Twitter]. Una de las razones del rápido esparcimiento de la palabra **DevOps** se debió a que en Twitter las discusiones relacionadas a la conferencia fueron etiquetadas con el [hashtag] *#DevOpsDays*, pero debido a las limitantes de caracteres de Twitter por cada tuit en ese entonces, el [hashtag] evolucionó a ser simplemente *#DevOps*.

## Componentes

![M1-T01-S2](images/M1-T01-S2.png)

De leer la palabra **DevOps**, o de haberla escuchado de otra fuente, es común que te llegue a la mente "la unión de desarrollo (`Dev`) y operaciones (`Ops`)", y ésa es exactamente la etimología de la palabra. Antes de profundizar, primero estemos en la misma página en cuanto a qué es **Dev** y qué es **Ops**:

> :speech_balloon: Asumimos que ya sabes o tienes un indicio de lo que significan estos dos términos, la idea de definirlos nuevamente es solo para *reforzar* lo que ya sabemos, o para aclarar cualquier duda que pueda alterar la percepción de lo que es DevOps en lo adelante.

### Desarrollo (`Dev`)

![M1-T01-S3](images/M1-T01-S3.png)

> Por su traducción al inglés: [Software Development]

El desarrollo de software es el proceso crear, especificar, diseñar, programar, documentar, y probar programas de computadora. También incluye investigación, creación de prototipos, modificación, reutilización, reingeniería, mantenimiento o cualquier otra actividad que de como resultado "software".

El desarrollo de software, cuando se efectúa de manera programada, organizada  y estructurada, entonces se dice que se utiliza un enfoque sistemático. El uso de un enfoque sistemático para el desarrollo de software es comúnmente conocido como [ingeniería de software][Software Engineering].

#### Ciclo de vida de desarrollo de software (SDLC)

Cuando nos referimos a la ingeniería de software como proceso, es apropiado mencionar el [ciclo de vida de desarrollo de software (SDLC)][SDLC], que incluye un proceso en base a fases para crear productos de software que cumplan con las especificaciones técnicas y que sea de alta calidad. El SDLC posee una estructura similar al [método científico de investigación][Método de investigación].

Las etapas fundamentales del SDLC son:

1. Identificación de necesidades
2. Análisis de requerimientos
3. Diseño
4. Desarrollo e implementación
5. Pruebas
6. Despliegue y mantenimiento

> :thought_balloon: La mayoría de las organizaciones que desarrollan software an alguna capacidad lo utilizan. Es el proceso más popular en la actualidad. Más adelante en el [Módulo 3 - Desarrollo de software](../03-ciclo-de-desarrollo-de-software/README.md) ampliaremos más sobre el SDLC.

#### Tipos de software

Cuando hablamos de "software", podemos mencionar que hay tres tipos básicos:

- **Software del sistema**, para proporcionar funciones básicas como sistemas operativos, administración de discos, utilidades, administración de hardware y otras necesidades operativas.
- **Software de programación**, para brindar a los programadores herramientas como editores de texto, compiladores, enlazadores, depuradores y otras herramientas para crear código.
- **Software de aplicación** (aplicaciones o apps), para ayudar a los usuarios a realizar tareas. La suite de Office, los reproductores multimedia y navegadores web son ejemplos. Las aplicaciones también se refieren a aplicaciones web y móviles como las que se usan para comprar en Amazon.com, socializar con Facebook o publicar fotos en Instagram.

Un posible cuarto tipo es el **software integrado**. El software de sistemas integrados se utiliza para controlar máquinas y dispositivos que normalmente no se consideran computadoras: redes de telecomunicaciones, automóviles, robots industriales y más. Estos dispositivos y su software se pueden conectar como parte del [Internet de las cosas (IoT)][IoT].

¿Por qué es importante conocer los diferentes tipos de software? Esto es porque las prácticas de DevOps no distinguen del tipo de software, y no deberían. Sin embargo, el tipo de software mayormente compatible con dichas prácticas, y sin duda alguna el más popular, es el software de aplicación, específicamente el de **aplicaciones web**.

### Operaciones (de TI)

![M1-T01-S4](images/M1-T01-S4.png)

> Por su traducción al inglés: [IT Operations]

Las operaciones de tecnología de la información, u operaciones de TI, son el conjunto de todos los procesos y servicios que un personal de TI proporciona a sus clientes internos o externos y que utilizan ellos mismos para funcionar como un negocio.

El término se refiere a la aplicación de la gestión de operaciones a las necesidades tecnológicas de una empresa u organización.

Cada organización que utiliza computadoras tiene operaciones de TI definidas en alguna capacidad. Los objetivos de negocio más fundamentales de esta área competen a la utilización efectiva de los recursos y la optimización de costos.

En el esquema tradicional de trabajo, las operaciones de TI generalmente se consideran separadas del SDLC. Sin embargo, con DevOps, este paradigma se rompe y ahora las operaciones también son parte intrínseca del flujo de desarrollo, desde su concepción como idea hasta su despliegue como funcionalidad en un sistema nuevo o existente.

#### Puntos de decisión de TI

Los puntos de decisión que deben tenerse en cuenta para las operaciones de TI son:

- Ejecutar soluciones
- Administrar la infraestructura
- Administrar configuraciones
- Evolucionar la infraestructura
- Mitigar los desastres
- Optimizar los costos y la utilización de recursos

#### Tareas de las operaciones de TI

A modo general, las operaciones de TI se materializan en estas sub-áreas de trabajo:

- Infraestructura de red
- Administración de servidores y dispositivos
- Operaciones informáticas y mesa de ayuda

## DevOps: Definición

Ya que conocemos de que se tratan de manera independiente `Dev` y `Ops`, es hora de definir lo que realmente significa `DevOps` (o al menos, su etimología inicial):

En su forma más simple, DevOps no es más que **Desarrollo** y **Operaciones** trabajando en conjunto como **una única unidad**; donde tratan continuamente de reducir complejidad, eliminar esfuerzos innecesarios y trabajo manual, repetitivo y tedioso, compartir principios culturales y técnicos, todo esto utilizando las metodologías ágiles como su vehículo principal.

En un contexto más abierto, DevOps es un movimiento cultural que intenta romper sobre los ya establecidos paradigmas de **Desarrollo** y **Operaciones** en cuanto a objetivos de negocio, indicadores de rendimiento, gestión del trabajo, y entrega de valor y resultados.

*DevOps* como movimiento o metodología se basa en varios principios culturales que discutiremos en detalle más adelante:

- [Colaboración](2.principios-culturales.md#colaboración)
- [Automatización](2.principios-culturales.md#automatización)
- [Mejora continua](2.principios-culturales.md#mejora-continua)
- [Acción centrada al cliente](2.principios-culturales.md#acción-centrada-al-cliente)
- [Responsabilidad de extremo a extremo](2.principios-culturales.md#responsabilidad-de-extremo-a-extremo)
- [Crear con el objetivo en mente](2.principios-culturales.md#crear-con-el-objetivo-en-mente)

Un concepto erróneo sobre DevOps es "un conjunto de herramientas". Aunque si bien es cierto que existen herramientas esenciales, éstas son solo un medio para lograr objetivos específicos. Expanderemos sobre esto más adelante cuando veamos algunas de las herramientas que se usan en DevOps.

> :bulb: DevOps ha sido comumente asociado a herramientas, sin embargo, es importante tener presente que las herramientas no son más que recursos que se pueden utilizar para cumplir con algún objetivo (orientado a DevOps). Las herramientas son la parte más tangible de DevOps, y por consecuencia, lo que más llama a la atención.

<!-- Referencias -->
[Glosario - DevOps]: ../../glosario/terminos-generales.md#devops
[Método de investigación]: ../../referencias/README.md#metodo-de-investigacion
[IoT]: ../../referencias/README.md#iot
[DevOpsDays]: ../../referencias/README.md#devopsdays
[Twitter]: ../../referencias/README.md#twitter
[hashtag]: ../../referencias/README.md#hashtag
[The Short History of DevOps]: ../../referencias/README.md#the-short-history-of-devops
[SDLC]: ../../referencias/README.md#sdlc
[Software Development]: ../../referencias/README.md#software-development
[Software Engineering]: ../../referencias/README.md#software-engineering
[IT Operations]: ../../referencias/README.md#it-operations
