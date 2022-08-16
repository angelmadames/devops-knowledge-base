---
title : "Gestión de versiones"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "entrega-continua"
weight: 705
toc: true
---

## Gestión de versiones de software

La gestión de versiones supervisa las etapas involucradas en la planificación, programación y gestión de versiones o compilaciones de software desde el desarrollo y las pruebas hasta la implementación en varios entornos.

A medida que los procesos de desarrollo de software y los sistemas de software se utilizan más, requieren una mayor especialización y una mayor complejidad. Además, el creciente número de aplicaciones web se ejecutan en plataformas que aumentan en complejidad y evolucionan constantemente. Introduzca: gestión de liberación. El proceso permite que los equipos se centren en el desarrollo, las pruebas y los lanzamientos continuos de estas aplicaciones.

Basándose en la gestión de proyectos, el ciclo de vida de desarrollo de software (SDLC) y la biblioteca de infraestructura de TI (ITIL), la gestión de versiones aumenta la cantidad de versiones exitosas de una organización y reduce la cantidad de problemas de calidad.

## Notificaciones de versiones

Con cada nuevo lanzamiento, independientemente de si es mayor, menor o un parche, comunique los cambios a sus usuarios. Específicamente, hágales saber las siguientes cuatro cosas:

- Qué hay de nuevo
- Lo que ha sido arreglado
- Lo que se ha mejorado
- Lo que ha quedado en desuso

Esto se puede hacer de varias maneras, pero una de las mejores es incluirlo en las notas de la versión. Eso plantea la pregunta: ¿Cómo? Bueno, hay muchas maneras de escribir notas de lanzamiento, pero ProdPad tiene algunos consejos excelentes. Lo he resumido en las siguientes citas:

Las buenas notas de la versión están escritas para ser leídas, y describen claramente qué se ha mejorado y cómo benefician a los usuarios. A los clientes les encanta ese compromiso con la transparencia: les da una razón para confiar en usted. Nos han preguntado antes si publicamos notas de la versión, probablemente porque es un buen indicador de si estamos cumpliendo lo que prometimos en nuestra hoja de ruta.

Las notas de la versión son más fáciles de digerir cuando se dividen en secciones. Las secciones facilitan el escaneo para los usuarios. Escribir notas de lanzamiento claras y específicas lo ayuda a abrir un nivel de comunicación con sus clientes sobre el progreso que está logrando en su producto.

## Estrategias de versionado

### Versionado semántico

En el [versionado semántico][Semantic Versioning], dado un número de versión `MAYOR.MENOR.PARCHE`, se incrementa:

- Versión **MAYOR** cuando realiza cambios de API incompatibles,
- Versión **MENOR** cuando agrega funcionalidad de manera compatible con versiones anteriores, y
- Versión **PARCHE** cuando realiza correcciones de errores compatibles con versiones anteriores.

Las etiquetas adicionales para los metadatos de compilación y prelanzamiento están disponibles como extensiones del formato `MAYOR.MENOR.PARCHE`.

Ejemplos:

```shell
1.4.9
10.2.5
1.23.6
```

<!-- Referencias -->
[Semantic Versioning]: ../../referencias/enlaces#semantic-versioning
