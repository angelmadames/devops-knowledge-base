---
title : "Control de versiones"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "ciclo-de-desarrollo"
weight: 403
toc: true
---

Cuando se trabaja en el desarrolla de un sistema, es casi seguro que varias personas trabajarán de manera simultánea en éste. Quizás un grupo de ingenieros trabajará un componente mientras otro grupo otro componente totalmente diferente. Sin embargo, ambos grupos deberán agregar cambios a un mismo código fuente. Siendo aún más específicos, dentro de cada grupo, habrán varios ingenieros trabajando en el mismo componente.

Entonces la pregunta resulta: ¿Cómo pueden trabajar varias personas al mismo tiempo un mismo código fuente, sin que estos cambios entren en conflictos entre sí?

La respuesta es [control de versiones][Control de versiones].

El control de versiones es la práctica de rastrear y administrar los cambios en el código del software, esto ayuda a los equipos a rastrear cada cambio individual y a tener un historial que se pueda referenciar.

En la práctica, el control de versiones se implementa utilizando un sistema de control de versiones (VCS, Version Control System; por sus siglas en inglés).

En este tema abundaremos un poco sobre los sistemas de control de versiones y veremos `git`, uno de los más populares y usados en la actualidad.

> Para expandir más sobre control de versiones, puedes consultar el libro digital [Getting Started - About Version Control] de parte de [git-csm.com][Git].

## Sistema de control de versiones

Un [sistema de control de versiones][Software de control de versiones] (`VCS`) es una utilidad de software que rastrea y administra los cambios en un sistema de archivos. Es lo que permite integrar utilidades de colaboración a la práctica fundamental de control de versiones.

En el ámbito de los archivos de código fuente individuales, un VCS rastreará las adiciones, eliminaciones y modificaciones de las líneas de texto dentro de ese archivo.

Uno de los elementos más importantes de un VCS son los **repositorios.** Los repositorios representan un sistema de archivos manejados por un VCS, usualmente asociados al contexto de una única aplicación o sistema y su código fuente.

En el caso hipotética de que se trabaje, por ejemplo, en dos aplicaciones web. Cada una de estas aplicaciones tendría un **repositorio** individual donde se administraría su código fuente.

### ¿Por qué usar un `VCS`?

Un sistema de control de versiones es una herramienta invaluable con muchos beneficios para el flujo de trabajo de un equipo de software colaborativo. Cualquier proyecto de software que tenga más de un desarrollador que mantenga archivos de código fuente debe usar un VCS.

Podría decirse que no hay una razón válida para renunciar al uso de un VCS en cualquier proyecto de desarrollo de software moderno.

Podemos mencionar, a modo general, tres (3) razones principales:

- Resolución de conflictos
- Revertir y deshacer cambios en el código fuente
- Copia de seguridad del código fuente fuera del sitio

Expandamos un poco más cada una...

#### Resolución de conflictos

Como hemos mencionado, durante el ciclo de vida de un proyecto de software dirigido por un equipo, lo más probable es que varios miembros del equipo tengan la necesidad de realizar cambios en el mismo archivo de código fuente al mismo tiempo.

Un VCS rastreará y ayudará en los conflictos entre múltiples desarrolladores, dejando un rastro de auditoría que proporciona información sobre la historia de un proyecto y sus resoluciones

#### Revertir y deshacer cambios en el código fuente

Una vez que un VCS ha comenzado a rastrear un sistema de archivos de código fuente, mantiene un historial de cambios y el estado del código fuente a lo largo de la historia de un proyecto. Esto permite la posibilidad de "deshacer" o revertir un proyecto de código fuente a un último estado conocido.

Si se descubre un error en una aplicación en vivo, el código puede revertirse rápidamente a una versión estable conocida.

#### Copia de seguridad del código fuente fuera del sitio

Cuando se usa un VCS en colaboración, se debe crear una instancia remota del VCS para compartir los cambios entre los desarrolladores. Luego se convierte en una copia de seguridad externa segura.

En un escenario desafortunado como una computadora portátil robada, la instancia remota de VCS aún conservará una copia del código fuente.

### Tipos

Las herramientas de VCS vienen en dos tipos principales de arquitectura remota. Estos tipos de arquitectura son **centralizados** y **distribuidos**.

Cuando se analizan los pros y los contras de cada arquitectura, la función de copia de seguridad fuera del sitio es el principal punto de discusión.

Un VCS centralizado tiene un único punto de falla, que es la instancia de VCS central remota. Si se pierde esta instancia, puede provocar pérdida de productividad y datos, y deberá reemplazarse con otra copia del código fuente. Si deja de estar disponible temporalmente, evitará que los desarrolladores inserten, fusionen o reviertan el código. Una arquitectura de modelo distribuido evita estos peligros manteniendo una copia completa del código fuente en cada instancia de VCS. Si cualquiera de los escenarios de falla centralizados mencionados anteriormente ocurre dentro del modelo distribuido, se puede intercambiar una nueva instancia de VCS para liderar el desarrollo y mitigar cualquier caída grave en la productividad.

### Beneficios

La integración de un VCS en un proyecto de desarrollo de software permite una variedad de beneficios organizativos y de gestión. De manera predeterminada, un VCS por sí solo ofrece los beneficios técnicos discutidos anteriormente de resolución de conflictos en equipo y asistentes de colaboración. Un servicio de VCS alojado envuelve un VCS predeterminado y brinda funciones mejoradas. Este 'VCS mejorado' es increíblemente poderoso y brinda una visión transparente del proceso de desarrollo de software, que tradicionalmente puede ser un esfuerzo creativo opaco. Los siguientes puntos son algunos beneficios de alto nivel que ofrece un VCS alojado.

Los 4 beneficios principales son:

- Integraciones extendidas de terceros
- Comunicación del equipo
- Perspectiva, medición y rendición de cuentas
- Automatización de canalización de CI/CD

### Comparativas

La siguiente es una descripción general y una comparación de las opciones populares de VCS. Las principales observaciones de estas comparaciones son que las opciones de VCS que utilizan un modelo cliente-servidor no son compatibles con las soluciones de alojamiento de VCS modernas como Bitbucket. La industria de VCS se ha movido hacia un modelo distribuido.

#### Git

[Git] es un sistema de control de versiones distribuido gratuito y de código abierto diseñado para manejar todo, desde proyectos pequeños hasta proyectos muy grandes, con rapidez y eficiencia.

#### Mercurial

[Mercurial] es una herramienta de gestión de control de código fuente distribuida y gratuita. Maneja de manera eficiente proyectos de cualquier tamaño y ofrece una interfaz fácil e intuitiva.

#### SVN

Apache Subversion ([SVN]) es un sistema de control de versiones y revisión de software distribuido como código abierto bajo la Licencia Apache. Los desarrolladores de software usan Subversion para mantener versiones actuales e históricas de archivos como código fuente, páginas web y documentación.

#### CVS

El Sistema de Versiones Concurrentes ([CVS]) es un sistema de control de versiones para realizar un seguimiento de todas las modificaciones a los archivos de código fuente del proyecto. CVS es ampliamente utilizado en proyectos de desarrollo de software propietario y de código abierto y, en general, se considera que es la mejor herramienta de control de versiones con todas las funciones y disponible gratuitamente.

<!-- Refeferencias -->
[Control de versiones]: ../../referencias/enlaces#version-control
[Software de control de versiones]: ../../referencias/enlaces#version-control-software
[Getting Started - About Version Control]: ../../referencias/enlaces#version-control-getting-started
[Git]: ../../referencias/enlaces#git
[Mercurial]: ../../referencias/enlaces#mercurial
[SVN]: ../../referencias/enlaces#svn
[CVS]: ../../referencias/enlaces#cvs
