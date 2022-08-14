---
title : "Herramientas y automatización"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "fundamentos-de-devops"
weight: 206
toc: true
---
<!-- markdownlint-disable MD026 -->

DevOps es una práctica que implica un cambio cultural, nuevos principios de gestión y **herramientas** que ayudan a implementar mejores prácticas.

Cuando se trata de herramientas de DevOps, las organizaciones deben buscar herramientas que:

- Mejoren la colaboración,
- Reduzcan el cambio de contexto (reducir variabilidad),
- Hagan uso de la automatización y,
- Aprovechen la observabilidad y el monitoreo.

Existen todo tipo de herramientas bajo diferentes contextos o necesidades, a continuación listaremos algunas de las herramientas más populares en la comunidad DevOps de la actualidad:

## Herramientas de planificación

- [Jira Software]: la herramienta más popular para la gestión de proyectos de manara ágil es Jira Software. Es un producto propietario de la compañía Atlassian y permite manejar Scrum, Kanban, y otros modelos de gestión ágiles y no-ágiles.
- [Confluence]: Parte de la familia de Atlassian, es una solución de documentación centralizada.

## Mensajería y comunicación

- [Microsoft Teams]: herramienta de colaboración y mensajería propietaria de [Microsoft]. Se integra de forma nativa con [Outlook], [Sharepoint], [OneDrive] y otros productos de la misma suite de Microsoft.
- [Slack]: una de las herramientas de mensejaría más populares, se especializa en el uso de canales con una interfaz muy intuitiva. Tiene muchas [integraciones][Slack integrations] disponibles lo que lo hace una herramienta bastante flexible.

## Contenerización y orquestación

- [Docker]: es una plataforma que te permite crear, probar e implementar contenedores. Es el motor de contendores más popular y más usado.
- [Podman]: es una herramienta nativa de Linux, de código abierto y sin daemon (a contrario de Docker), diseñada para facilitar la búsqueda, ejecución, creación, uso compartido e implementación de aplicaciones usando contenedores.
- [Kubernetes]: es un motor de orquestación de contenedores de código abierto para automatizar la implementación, escalación y la administración de aplicaciones en contenedores.
- [Hashicorp Nomad]: es un programador y orquestador simple y flexible para administrar contenedores y aplicaciones no en contenedores en las instalaciones y en la nube a escala.

## Gestión de configuración

- [Ansible]:  herramienta de automatización para despliegue de aplicaciones, gestión de configuración y aprovisionamiento de software, de código abierto. Se ejecuta en muchos sistemas similares a Unix y puede configurar tanto sistemas similares a Unix como Microsoft Windows. Está hecho en Python y su versión "Enterprise" es soportada por [Red Hat].
- [Chef]: es una suite de herramientas, productos y servicios enfocados en la automatización. Hecho en Ruby.
- [Puppet]: es bastante similar a Ansible, puesto están enfocados en las mismas necesidades. Es una herramienta de automatización general enfocada en gestión de configuración y despliegue de aplicaciones.

## Infraestructura como código

- [Terraform]: es una herramienta de infraestructura como código (IaC) que permite construir, cambiar y versionar la infraestructura de manera segura y eficiente.
- [Pulumi]: es una herramienta para infraestructura de código abierto para crear, implementar y administrar infraestructura en la nube.

## Control de versiones

- [GitHub]: es una plataforma de gestión de versiones basada en [git]. Fue adquirada por [Microsoft] en 2018.
- [GitLab]: es una plataforma orientada a DevOps que permite el desarrollo seguro a través de [git]. Posee muchas integraciones y funcionalidades nativas de la metodología DevOps; por eso suelen denominarse así mismos como una plataforma DevOps. Es open-source, y ofrece planes de pago para funcionalidades y soporte empresarial.
- [BitBucket]: Bitbucket es también una herramienta de control de versiones que usa [git], siendo la solución nativa de Atlassian. Posee una alta afinidad con [Jira].

## Integración y entrega continua

- [BitBucket Pipelines]
- [CircleCI]
- [GitHub Actions]
- [GitLab CI]
- [Jenkins]

## Seguridad integrada

- [JFrog]
- [Snyk]
- [SonarQube]

## Proveedores de computación en la nube

- [AWS]
- [Google Cloud Platform]
- [Microsoft Azure]

## Monitoreo y alertas

- [DataDog]
- [Nagios]
- [New Relic]
- [Prometheus]
- [Sumo Logic]

---

[:rewind: Volver a Principios culturales](04-principios-culturales.md) | [:arrow_down: Inicio del módulo](../README.md) | [Procesos y prácticas :fast_forward:](06-procesos-y-practicas.md)

<!-- Referencias -->
[Ansible]: ../../referencias/enlaces#ansible
[AWS]: ../../referencias/enlaces#aws
[BitBucket Pipelines]: ../../referencias/enlaces#bitbucket-pipelines
[BitBucket]: ../../referencias/enlaces#bitbucket
[Chef]: ../../referencias/enlaces#chef
[CircleCI]: ../../referencias/enlaces#circleci
[Confluence]: ../../referencias/enlaces#confluence
[DataDog]: ../../referencias/enlaces#datadog
[Docker]: ../../referencias/enlaces#docker
[git]: ../../referencias/enlaces#git
[GitHub Actions]: ../../referencias/enlaces#github-actions
[GitHub]: ../../referencias/enlaces#github
[GitLab CI]: ../../referencias/enlaces#gitlab-ci
[GitLab]: ../../referencias/enlaces#gitlab
[Google Cloud Platform]: ../../referencias/enlaces#google-cloud-platform
[Hashicorp Nomad]: ../../referencias/enlaces#nomad
[Jenkins]: ../../referencias/enlaces#jenkins
[JFrog]: ../../referencias/enlaces#jfrog
[Jira Software]: ../../referencias/enlaces#jira-software
[Jira]: ../../referencias/enlaces#jira-software
[Kubernetes]: ../../referencias/enlaces#kubernetes
[Microsoft Azure]: ../../referencias/enlaces#microsoft-azure
[Microsoft Teams]: https://www.microsoft.com/en-us/microsoft-teams/group-chat-software
[Microsoft]: ../../referencias/enlaces#microsoft
[Nagios]: ../../referencias/enlaces#nagios
[New Relic]: ../../referencias/enlaces#new-relic
[OneDrive]: ../../referencias/enlaces#onedrive
[Outlook]: ../../referencias/enlaces#outlook
[Podman]: ../../referencias/enlaces#podman
[Prometheus]: ../../referencias/enlaces#prometheus
[Pulumi]: ../../referencias/enlaces#pulumi
[Puppet]: ../../referencias/enlaces#puppet
[Red Hat]: ../../referencias/enlaces#red-hat
[Sharepoint]: ../../referencias/enlaces#sharepoint
[Slack integrations]: ../../referencias/enlaces#slack-integrations
[Slack]: ../../referencias/enlaces#slack
[Snyk]: ../../referencias/enlaces#snyk
[SonarQube]: ../../referencias/enlaces#sonarqube
[Sumo Logic]: ../../referencias/enlaces#sumo-logic
[Terraform]: ../../referencias/enlaces#terraform
