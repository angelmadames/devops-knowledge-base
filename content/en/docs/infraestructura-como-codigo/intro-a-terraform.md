---
title : "Introducción a Terraform"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "infraestructura-como-codigo"
weight: 806
toc: true
---

## Introducción

[HashiCorp Terraform][Terraform] es una herramienta de infraestructura como código que permite definir recursos locales y en la nube en archivos de configuración legibles por humanos que se pueden **versionar**, **reutilizar** y **compartir**. En base a esto, es posible usar un flujo de trabajo consistente para aprovisionar y administrar toda la infraestructura a lo largo de su ciclo de vida. Terraform puede administrar componentes de bajo nivel como recursos informáticos, de almacenamiento y de red, así como componentes de alto nivel como entradas de [DNS] y funciones de [SaaS].

## ¿Cómo funciona Terraform?

Terraform crea y administra recursos en plataformas en la nube y otros servicios a través de sus interfaces de programación de aplicaciones (`API`). Los proveedores permiten que Terraform funcione con prácticamente cualquier plataforma o servicio con una API accesible.

![M7-T06-S2](images/M7-T06-S2.png)

> Fuente: [What is Terraform, Hashicorp](https://www.terraform.io/intro#what-is-terraform)

HashiCorp y la comunidad de Terraform ya han contratado a más de 1700 proveedores para administrar miles de tipos diferentes de recursos y servicios, y este número continúa creciendo. Puede encontrar todos los proveedores disponibles públicamente en [Terraform Registry], incluidos Amazon Web Services (AWS), Azure, Google Cloud Platform (GCP), Kubernetes, Helm, GitHub, Splunk, DataDog y muchos más.

El flujo de trabajo principal de Terraform consta de tres etapas:

- **Write**: usted define los recursos, que pueden estar en múltiples proveedores y servicios en la nube. Por ejemplo, puede crear una configuración para implementar una aplicación en máquinas virtuales en una red de nube privada virtual (VPC) con grupos de seguridad y un balanceador de carga.
- **Plan**: Terraform crea un plan de ejecución que describe la infraestructura que creará, actualizará o destruirá en función de la infraestructura existente y su configuración.
- **Apply**: tras la aprobación, Terraform realiza las operaciones propuestas en el orden correcto, respetando las dependencias de los recursos. Por ejemplo, si actualiza las propiedades de una VPC y cambia la cantidad de máquinas virtuales en esa VPC, Terraform volverá a crear la VPC antes de escalar las máquinas virtuales.

![M7-T06-S3](images/M7-T06-S3.png)

> Fuente: [What is Terraform, Hashicorp](https://www.terraform.io/intro#what-is-terraform)

## ¿Por qué Terraform?

### Gestiona cualquier infraestructura

Encuentre proveedores para muchas de las plataformas y servicios que ya utiliza en [Terraform Registry]. También puedes escribir el tuyo propio. Terraform adopta un enfoque inmutable de la infraestructura, lo que reduce la complejidad de actualizar o modificar sus servicios e infraestructura.

### Seguimiento de infrastructura

Terraform genera un plan y le solicita su aprobación antes de modificar su infraestructura. También realiza un seguimiento de su infraestructura real en un [archivo de estado][Terraform State], que actúa como una fuente de verdad para su entorno. Terraform usa el archivo de estado para determinar los cambios a realizar en su infraestructura para que coincida con su configuración.

### Automatice los cambios

Los archivos de configuración de Terraform son declarativos, lo que significa que describen el estado final de su infraestructura. No necesita escribir instrucciones paso a paso para crear recursos porque Terraform maneja la lógica subyacente. Terraform crea un gráfico de recursos para determinar las dependencias de los recursos y crea o modifica recursos no dependientes en paralelo. Esto permite que Terraform aprovisione recursos de manera eficiente.

### Estandarizar configuraciones

Terraform admite componentes de configuración reutilizables llamados módulos que definen colecciones configurables de infraestructura, lo que ahorra tiempo y fomenta las mejores prácticas. Puede usar módulos disponibles públicamente desde Terraform Registry o escribir los suyos propios.

### Colaborar

Dado que su configuración está escrita en un archivo, puede enviarla a un Sistema de control de versiones ([VCS]) y usar Terraform Cloud para administrar de manera eficiente los flujos de trabajo de Terraform en todos los equipos. Terraform Cloud ejecuta Terraform en un entorno consistente y confiable y brinda acceso seguro a datos secretos y de estado compartidos, controles de acceso basados en roles, un registro privado para compartir módulos y proveedores, y más.

<!-- Referencias -->
[Terraform]: ./../referencias/enlaces#terraform
[Terraform Registry]: ./../referencias/enlaces#terraform-registry
[DNS]: ./../referencias/enlaces#dns
[SaaS]: ./../referencias/enlaces#software-as-a-service-saas
[Terraform State]: ./../referencias/enlaces#terraform-state
[VCS]: ./../referencias/enlaces#version-control-software
