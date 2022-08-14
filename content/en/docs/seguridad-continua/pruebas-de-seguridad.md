---
title : "Pruebas de seguridad de aplicación"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "seguridad-continua"
weight: 1103
toc: true
---

## Prueba de seguridad de aplicaciones (AST)

Para implementar DevSecOps, las organizaciones deben considerar una variedad de herramientas de prueba de seguridad de aplicaciones (AST) para integrarlas en varias etapas de su proceso de CI/CD. Las herramientas AST de uso común incluyen

## Pruebas de seguridad de aplicaciones estáticas (SAST)

Las herramientas SAST escanean código patentado o personalizado en busca de errores de codificación y fallas de diseño que podrían conducir a debilidades explotables. Las herramientas SAST, se utilizan principalmente durante las fases de codificación, creación y desarrollo del SDLC.

## Análisis de composición de software (SCA)

Las herramientas SCA escanean el código fuente y los archivos binarios para identificar vulnerabilidades conocidas en componentes de código abierto y de terceros. También brindan información sobre los riesgos de seguridad y licencia para acelerar los esfuerzos de priorización y remediación. Además, se pueden integrar a la perfección en un proceso de CI/CD para detectar continuamente nuevas vulnerabilidades de código abierto, desde la integración de compilación hasta el lanzamiento de preproducción.

## Pruebas de seguridad de aplicaciones interactivas (IAST)

Las herramientas de IAST funcionan en segundo plano durante las pruebas funcionales manuales o automatizadas para analizar el comportamiento del tiempo de ejecución de la aplicación web.

## Pruebas dinámicas de seguridad de aplicaciones (DAST)

DAST es una tecnología de prueba de caja opaca automatizada que imita cómo un pirata informático interactuaría con su aplicación web o API. Prueba las aplicaciones a través de una conexión de red y examina la representación de la aplicación en el lado del cliente, como lo haría un probador de penetración.

Las herramientas DAST no requieren acceso al código fuente ni personalización; interactúan con su sitio web y encuentran vulnerabilidades con una baja tasa de falsos positivos.
