---
title : "Herramientas de CI"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "integracion-continua"
weight: 604
toc: true
---

Para lograr con la ejecución de las pruebas definidas para CI/CD, necesitamos auxiliarnos de herramientas orientadas a la automatización de procesos. A estas herramientas le llamamos **herramientas de CI/CD**.

Hay muchísimas opciones de herramientas que puedes elegir para suplir las necesidades de integración continua. En este curso, solo haremos mención de las más populares y así evaluar qué éstas tienen en común. A continuación una pequeña comparativa de éstas.

## Jenkins

- **Resumen**: [Jenkins] es una herramienta de CI veterana con una larga trayectoria comprobada. Es de [código abierto][open-source] y está impulsado por actualizaciones de la comunidad. Jenkins está destinado principalmente a una instalación en premisa. Es una excelente opción cuando su organización necesita soporte local para manejar clientes confidenciales como los datos de cumplimiento de [HIPAA].

- **Características**:
  - Alojamiento local o en la nube (*on-premise*, *self-hosted*)
  - Código abierto (*[open-source]*)
  - Robusto ecosistema de componentes (plugins)

## GitHub Actions

- **Resumen**: [GitHub Actions] es la solución integrada de la plataforma GitHub para CI/CD. Facilita la automatización de flujos de trabajo de software (workflows). Al ser un servicio propietario e integrado, ofrece muchas funcionalidades para compilar, desplegar, automatizar pipelines directamente desde GitHub.

- **Características**:
  - Moderno y amplio ecosistema de extensiones (Actions)
  - Uso de "Runners" públicos y alojados por ti mismo (*self-hosted*)
  - Ejecución de pruebas en múltiples contenedores
  - Integración incluida de "Secretos"

## GitLab CI

- **Resumen**: Gitlab es una nueva [herramienta de CI][GitLab] que ofrece una experiencia completa de DevOps. Gitlab se creó con la intención de mejorar la experiencia general de Github. Gitlab ofrece una experiencia de usuario moderna con soporte para contenedores.

- **Características**:
  - Alojamiento local o en la nube
  - Pruebas de seguridad continuas
  - UX fácil de aprender

## CircleCI

- **Resumen**: [CircleCI] es una herramienta de CI que se combina con elegancia con Github, una de las herramientas de alojamiento en la nube del sistema de control de versiones más populares. CircleCI es una de las herramientas de CI más flexibles, ya que admite una matriz de sistemas de control de versiones, sistemas de contenedores y mecanismos de entrega. CircleCI se puede alojar en las instalaciones o utilizarse a través de una oferta en la nube.

- **Características**:
  - Desencadenadores de notificaciones de eventos de CI
  - Rendimiento optimizado para compilaciones rápidas
  - Fácil depuración a través de SSH y compilaciones locales
  - Análisis para medir el rendimiento de la compilación

## Azure Pipelines

- Resumen: Azure es la plataforma de infraestructura en la nube de Microsoft, el equivalente de Microsoft a Amazon Web Services. Al igual que el AWS CodePipeline mencionado anteriormente, [Azure ofrece una herramienta de CI][Azure Pipelines] que se integra completamente en el conjunto de herramientas de alojamiento de Azure.

- **Características**:
  - Integración con la plataforma [Microsoft Azure]
  - Soporte de plataforma Windows
  - Soporte de contenedores
  - Integración con GitHub

## BitBucket Pipelines

- **Resumen**: [Bitbucket Pipelines][BitBucket Pipelines] es una herramienta de CI integrada directamente en Bitbucket, un sistema de control de versiones en la nube ofrecido por Atlassian. Bitbucket Pipelines es el próximo paso sencillo para habilitar CI si su proyecto ya está en Bitbucket. Las canalizaciones de Bitbucket se administran como código para que pueda confirmar fácilmente las definiciones de canalización y comenzar las compilaciones. Bitbucket Pipelines, también ofrece CD. Esto significa que los proyectos creados con Bitbucket Pipelines también se pueden implementar en la infraestructura de producción.

- **Características**:
  - Fácil instalación y configuración
  - Experiencia unificada de Bitbucket
  - Nube por terceros

## AWS CodePipeline

- **Resumen**: Amazon Web Services es uno de los proveedores de infraestructura en la nube más dominantes del mercado. Ofrecen herramientas y servicios para todo tipo de infraestructura y tareas de desarrollo de código. CodePipeline es su oferta de herramientas de CI. [CodePipeline][AWS CodePipeline] puede interactuar directamente con otras herramientas de AWS existentes para brindar una experiencia de AWS perfecta.

- **Características**:
  - Totalmente en la nube
  - Integrado con los servicios web de Amazon
  - Compatibilidad con complementos personalizados
  - Control de acceso robusto

---

[:rewind: Volver a Pruebas de integración](02-pruebas-de-integracion.md) | [:arrow_down: Inicio del módulo](../README.md) | [Mejores prácticas de CI :fast_forward:](04-mejoras-practicas-de-ci.md)

<!-- Referencias -->
[open-source]: ../../referencias/enlaces#open-source
[HIPAA]: ../../referencias/enlaces#hipaa
[Jenkins]: ../../referencias/enlaces#jenkins
[GitHub Actions]: ../../referencias/enlaces#github-actions
[GitLab]: ../../referencias/enlaces#gitlab-ci
[Microsoft Azure]: ../../referencias/enlaces#microsoft-azure
[Azure Pipelines]: ../../referencias/enlaces#azure-pipelines
[Bitbucket Pipelines]: ../../referencias/enlaces#bitbucket-pipelines
[AWS CodePipeline]: ../../referencias/enlaces#aws-codepipeline
[CircleCI]: ../../referencias/enlaces#circleci
