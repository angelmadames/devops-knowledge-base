---
title : "Herramientas de CD"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "entrega-continua"
weight: 706
toc: true
---

## Superposición con herramientas de CI

En realidad, las herramientas de integración continua (CI) se superponen con el propósito de entrega y despliegue continuo. Así que, es frecuente encontrar en diferentes fuentes la referencia de "herramientas de CI/CD" en vez de ser herramientas separadas.

La razón es simple: las herramientas de CI realmente son herramientas de automatización, esto significa que puedes definir y ejecutar cualquier tipo de proceso relacionado a tu aplicación o conjunto de aplicaciones.

Por tal razón, en esta sección nos enfocaremos en las herramientas de despliegue continuo que usan [GitOps](#gitops).

## GitOps

GitOps es una forma de implementar el despliegue continuo para aplicaciones nativas en la nube. Se enfoca en una experiencia centrada en el desarrollador cuando opera la infraestructura, mediante el uso de herramientas con las que los desarrolladores ya están familiarizados, incluida la herramienta Git.

La idea central de GitOps es tener un repositorio de Git que siempre contenga descripciones declarativas de la infraestructura deseada actualmente en el entorno de producción y un proceso automatizado para hacer que el entorno de producción coincida con el estado descrito en el repositorio. Si desea implementar una nueva aplicación o actualizar una existente, solo necesita actualizar el repositorio: el proceso automatizado se encarga de todo lo demás. Es como tener control de crucero para administrar sus aplicaciones en producción.

> GitOps: CI/CD versionado sobre infraestructura declarativa. Deje de hacer scripts y comience a enviar. — Kelsey Hightower

## Beneficios de GitOps

- Despliegue más rápido con más frecuencia
- Recuperación de errores
- Facilidad para gestión de credenciales
- Despliegues autodocumentados
- Conocimiento compartido en equipos

## Herramientas

### ArgoCD

[ArgoCD] es una herramienta declarativa de entrega continua de GitOps para Kubernetes.

Las definiciones, las configuraciones y los entornos de las aplicaciones deben ser declarativos y controlados por versión. El despliegue de aplicaciones y la gestión del ciclo de vida deben ser automatizadas, auditables y fáciles de entender.

### FluxCD

[Flux][FluxCD] es un conjunto de soluciones de entrega continua y progresiva para Kubernetes que son abiertas y extensibles.

### Jenkins X

[Jenkins X] automatiza y acelera la integración continua y la entrega continua para desarrolladores en la nube.

### werf

[werf] es una herramienta de entrega consistente. La herramienta CLI que une Git, Docker, Helm y Kubernetes con cualquier sistema CI para implementar CI/CD y giterminismo*.

### Helm

[Helm] ayuda a administrar las aplicaciones de Kubernetes: los gráficos de Helm lo ayudan a definir, instalar y actualizar incluso la aplicación de Kubernetes más compleja.

Los gráficos son fáciles de crear, versionar, compartir y publicar, así que comience a usar Helm y deje de copiar y pegar.

## Herramientas adicionales

### Spinnaker

[Spinnaker] es una plataforma de entrega continua multinube de código abierto que lo ayuda a lanzar cambios de software con alta velocidad y confianza.

<!-- Referencias -->

[ArgoCD]: ../../referencias/enlaces#argocd
[FluxCD]: ../../referencias/enlaces#fluxcd
[Jenkins X]: ../../referencias/enlaces#jenkins-x
[Spinnaker]: ../../referencias/enlaces#spinnaker
[werf]: ../../referencias/enlaces#werf
[Helm]: ../../referencias/enlaces#helm
