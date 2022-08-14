<!-- markdownlint-disable MD026 -->

<!-- omit in toc -->
# Herramientas y automatización

<!-- omit in toc -->
## Tabla de contenido :scroll:

- [Introducción](#introducción)
- [Herramientas de planificación](#herramientas-de-planificación)
- [Mensajería y comunicación](#mensajería-y-comunicación)
- [Contenerización y orquestación](#contenerización-y-orquestación)
- [Gestión de configuración](#gestión-de-configuración)
- [Infraestructura como código](#infraestructura-como-código)
- [Control de versiones](#control-de-versiones)
- [Integración y entrega continua](#integración-y-entrega-continua)
- [Seguridad integrada](#seguridad-integrada)
- [Proveedores de computación en la nube](#proveedores-de-computación-en-la-nube)
- [Monitoreo y alertas](#monitoreo-y-alertas)

---

# Introducción

DevOps es una práctica que implica un cambio cultural, nuevos principios de gestión y **herramientas** que ayudan a implementar mejores prácticas.

Cuando se trata de herramientas de DevOps, las organizaciones deben buscar herramientas que:

- Mejoren la colaboración,
- Reduzcan el cambio de contexto (reducir variabilidad),
- Hagan uso de la automatización y,
- Aprovechen la observabilidad y el monitoreo.

Existen todo tipo de herramientas bajo diferentes contextos o necesidades, a continuación listaremos algunas de las herramientas más populares en la comunidad DevOps de la actualidad:

# Herramientas de planificación

- [Jira Software]: la herramienta más popular para la gestión de proyectos de manara ágil es Jira Software. Es un producto propietario de la compañía Atlassian y permite manejar Scrum, Kanban, y otros modelos de gestión ágiles y no-ágiles.
- [Confluence]: Parte de la familia de Atlassian, es una solución de documentación centralizada.

# Mensajería y comunicación

- [Microsoft Teams]: herramienta de colaboración y mensajería propietaria de [Microsoft]. Se integra de forma nativa con [Outlook], [Sharepoint], [OneDrive] y otros productos de la misma suite de Microsoft.
- [Slack]: una de las herramientas de mensejaría más populares, se especializa en el uso de canales con una interfaz muy intuitiva. Tiene muchas [integraciones][Slack integrations] disponibles lo que lo hace una herramienta bastante flexible.

# Contenerización y orquestación

- [Docker]: es una plataforma que te permite crear, probar e implementar contenedores. Es el motor de contendores más popular y más usado.
- [Podman]: es una herramienta nativa de Linux, de código abierto y sin daemon (a contrario de Docker), diseñada para facilitar la búsqueda, ejecución, creación, uso compartido e implementación de aplicaciones usando contenedores.
- [Kubernetes]: es un motor de orquestación de contenedores de código abierto para automatizar la implementación, escalación y la administración de aplicaciones en contenedores.
- [Hashicorp Nomad]: es un programador y orquestador simple y flexible para administrar contenedores y aplicaciones no en contenedores en las instalaciones y en la nube a escala.

# Gestión de configuración

- [Ansible]:  herramienta de automatización para despliegue de aplicaciones, gestión de configuración y aprovisionamiento de software, de código abierto. Se ejecuta en muchos sistemas similares a Unix y puede configurar tanto sistemas similares a Unix como Microsoft Windows. Está hecho en Python y su versión "Enterprise" es soportada por [Red Hat].
- [Chef]: es una suite de herramientas, productos y servicios enfocados en la automatización. Hecho en Ruby.
- [Puppet]: es bastante similar a Ansible, puesto están enfocados en las mismas necesidades. Es una herramienta de automatización general enfocada en gestión de configuración y despliegue de aplicaciones.

# Infraestructura como código

- [Terraform]: es una herramienta de infraestructura como código (IaC) que permite construir, cambiar y versionar la infraestructura de manera segura y eficiente.
- [Pulumi]: es una herramienta para infraestructura de código abierto para crear, implementar y administrar infraestructura en la nube.

# Control de versiones

- [GitHub]: es una plataforma de gestión de versiones basada en [git]. Fue adquirada por [Microsoft] en 2018.
- [GitLab]: es una plataforma orientada a DevOps que permite el desarrollo seguro a través de [git]. Posee muchas integraciones y funcionalidades nativas de la metodología DevOps; por eso suelen denominarse así mismos como una plataforma DevOps. Es open-source, y ofrece planes de pago para funcionalidades y soporte empresarial.
- [BitBucket]: Bitbucket es también una herramienta de control de versiones que usa [git], siendo la solución nativa de Atlassian. Posee una alta afinidad con [Jira].

# Integración y entrega continua

- [BitBucket Pipelines]
- [CircleCI]
- [GitHub Actions]
- [GitLab CI]
- [Jenkins]

# Seguridad integrada

- [JFrog]
- [Snyk]
- [SonarQube]

# Proveedores de computación en la nube

- [AWS]
- [Google Cloud Platform]
- [Microsoft Azure]

# Monitoreo y alertas

- [DataDog]
- [Nagios]
- [New Relic]
- [Prometheus]
- [Sumo Logic]

---

[:rewind: Volver a Principios culturales](04-principios-culturales.md) | [:arrow_down: Inicio del módulo](../README.md) | [Procesos y prácticas :fast_forward:](06-procesos-y-practicas.md)

<!-- Referencias -->
[Ansible]: ../../referencias/README.md#ansible
[AWS]: ../../referencias/README.md#aws
[BitBucket Pipelines]: ../../referencias/README.md#bitbucket-pipelines
[BitBucket]: ../../referencias/README.md#bitbucket
[Chef]: ../../referencias/README.md#chef
[CircleCI]: ../../referencias/README.md#circleci
[Confluence]: ../../referencias/README.md#confluence
[DataDog]: ../../referencias/README.md#datadog
[Docker]: ../../referencias/README.md#docker
[git]: ../../referencias/README.md#git
[GitHub Actions]: ../../referencias/README.md#github-actions
[GitHub]: ../../referencias/README.md#github
[GitLab CI]: ../../referencias/README.md#gitlab-ci
[GitLab]: ../../referencias/README.md#gitlab
[Google Cloud Platform]: ../../referencias/README.md#google-cloud-platform
[Hashicorp Nomad]: ../../referencias/README.md#nomad
[Jenkins]: ../../referencias/README.md#jenkins
[JFrog]: ../../referencias/README.md#jfrog
[Jira Software]: ../../referencias/README.md#jira-software
[Jira]: ../../referencias/README.md#jira-software
[Kubernetes]: ../../referencias/README.md#kubernetes
[Microsoft Azure]: ../../referencias/README.md#microsoft-azure
[Microsoft Teams]: https://www.microsoft.com/en-us/microsoft-teams/group-chat-software
[Microsoft]: ../../referencias/README.md#microsoft
[Nagios]: ../../referencias/README.md#nagios
[New Relic]: ../../referencias/README.md#new-relic
[OneDrive]: ../../referencias/README.md#onedrive
[Outlook]: ../../referencias/README.md#outlook
[Podman]: ../../referencias/README.md#podman
[Prometheus]: ../../referencias/README.md#prometheus
[Pulumi]: ../../referencias/README.md#pulumi
[Puppet]: ../../referencias/README.md#puppet
[Red Hat]: ../../referencias/README.md#red-hat
[Sharepoint]: ../../referencias/README.md#sharepoint
[Slack integrations]: ../../referencias/README.md#slack-integrations
[Slack]: ../../referencias/README.md#slack
[Snyk]: ../../referencias/README.md#snyk
[SonarQube]: ../../referencias/README.md#sonarqube
[Sumo Logic]: ../../referencias/README.md#sumo-logic
[Terraform]: ../../referencias/README.md#terraform
