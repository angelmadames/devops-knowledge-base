---
title : "Procesos y prácticas"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "fundamentos-de-devops"
weight: 207
toc: true
---
<!-- markdownlint-disable MD026 -->

En la mayoría de los recursos existentes sobre DevOps es fácil notar que hay muchas variaciones del entendimiento de lo que son los procesos de DevOps. En factor común, podemos notar que siempre se destacan los siguientes procesos:

- Integración continua
- Entrega continua

Lo cierto es que no existe una fórmula oficial sobre lo que realmente compete a procesos de DevOps, sin embargo, tras consolidar diferentes fuentes y recursos, y a su vez extender su alcance, en este curso trataremos los siguientes procesos:

- Flujo de desarrollo
- Provisionamiento de infraestructura
- Integración continua
- Entrega continua
- Despliegue continuo
- Pruebas continuas
- Monitoreo y alertas
- Seguridad integrada

A continuación detallaremos cada proceso de manera específica...

## Flujo de desarrollo

El flujo de desarrollo es uno de los procesos más vitales a tomar en consideración en DevOps, debido a que desde allí es donde empieza la generación de valor.

Usualmente, en un equipo tradicional de trabajo, el flujo de desarrollo está completamente aislado de las operaciones y de las pruebas de calidad. Sin embargo, tras adoptar la cultura DevOps el flujo de desarrollo se convierte en el lugar de trabajo principal de todos los miembros de equipo, sin barreras, con responsabilidades compartidas, y con un entendimiento bastante claro del valor que agrega cada miembro al producto que se construye.

El flujo de desarrollo por consiguiente compete principalmente a las siguientes actividades:

> Se asume, por la naturaleza de la metodología DevOps, que el flujo de desarrollo sucede en un entorno ágil.

- **Planificación**. La planificación compete a todo aquello que se realiza para organizar, priorizar, definir y estimar unidades de entregables relacionadas a funcionalidades del producto. De forma más llana, es aquí donde se decide qué se trabajará en el próximo ciclo de trabajo (sprint).
- **Gestión de cambios**. Con esto hacemos referencia principalmente a control de versiones y cómo se agregan nuevos cambios a la base del código fuente exitente. Lo mayormente aceptado en la comunidad como apoyo ideal para esta actividad es el uso de [git], un sistema de control de versiones distribuido diseñado para manejar a escala proyectos con rapidez y eficacia. En este curso, haremos un uso extensivo de [git].
  - **Modelo de ramificación** (`Branching Model`): es lo que define cómo se manejarán los cambios en el sistema de control de versiones.
- **Configuración de ambiente de desarrollo**. Es vital asegurar que los ingenieros de software poseen un ambiente adecuado para el desarrollo del producto. En sus dispositivos de trabajo, deben instalar todas las dependencias del sistema y de las aplicaciones que desarrollan. Así mismo, configurar sus editores de código y cualquiera otro software que les facilite su trabajo ya sea de índole preferencial o funcional. El ambiente de desarrollo debe poseer suficientes recursos a nivel de hardware para ejecutar sus procesos y herramientas.

### Flujo de desarrollo vs. SDLC

El flujo de desarrollo está estrechamente relacionado al ciclo de vida de desarrollo, pero no son lo mismo. El ciclo de vida es un marco a alto nivel, que describe procesos. El flujo de desarrollo es más práctico por naturaleza; describe un paso a paso de cómo se agrega valor al producto a través del código fuente.

## Integración continua (CI)

La [integración continua (CI)][Continuous Integration] es uno de los procesos característicos de DevOps; es la práctica de automatizar la integración de cambios de código de múltiples colaboradores en un solo proyecto de software.

Cuando decimos *"integración de cambios"*, nos referimos principalmente cuando los desarrolladores agregan cambios de código con frecuencia al repositorio y se ejecutan todas las pruebas requeridas *previo* a unificar esos cambios a la rama raíz, troncal o principal. En otras palabras, es agregar nuevos cambios a algo existente, pero sin antes validar su "integración" a través de pruebas y validaciones automáticas.

Para lograr esto, se utilizan herramientas de automatización y de integración continua. En la mayoría de los casos, se requiere de un sistema de control de versiones, puesto este sistema es quién sirve como agente de ejecución y en ocasiones de soporte, con automatizaciones y validaciones nativas.

## Entrega continua (CD)

La [entrega continua (CD)][Continuous Delivery] es la capacidad de introducir cambios de todo tipo (incluidas nuevas funciones, cambios de configuración, correcciones de errores y experimentos) en producción o en manos de los usuarios, de forma **segura**, **rápida** y **sostenible**.

El objetivo general es hacer que los despliegues, ya sea de un sistema distribuido a gran escala, un entorno de producción complejo, un sistema integrado o una aplicación, sean asuntos rutinarios y predecibles que se puedan realizar bajo demanda.

Esto es lograble asegurándonos de que el código esté siempre en un estado desplegable, incluso frente a equipos de miles de desarrolladores que realizan cambios a diario. Cuando se implementan diferentes ambientes menores (es decir, previos a producción), cuyos despliegues suceden de manera automática, de manera natural se garantiza que la aplicación está en un estado desplegable debido a que pasa por varias iteraciones del mismo proceso prodecible.

## Despliegue continuo

El despliegue continuo lleva la entrega continua a un paso más allá. Con esta práctica, cada cambio que pasa por todas las etapas del ciclo de vida, se entrega al ambiente de producción de manera automática. No hay intervención humana, y solo una prueba fallida evitará que se despliegue un nuevo cambio.

Es decir, no existe un proceso manual de aprobación ni nada similar; todo cambio que entra en el ciclo de vida es debido probado y validado y posteriormente lanzado a producción de manera totalmente autónoma.

El despliegue continuo es una excelente manera de acelerar el ciclo de retroalimentación con sus clientes y quitarle presión al equipo, ya que ya no hay un "día de lanzamiento". Los desarrolladores pueden concentrarse en crear software y ven su trabajo en vivo poco después de haber terminado de trabajar en el.

> El despliegue continuo es uno de los últimos procesos que se implementan en una cultura DevOps, y solo si el tipo de negocio lo permite. Se espera que esta sea la meta final, pero no es un indicador de madurez de gran impacto.

## Pruebas continuas

Las [pruebas continuas][Continuous Testing] son el proceso de ejecutar pruebas automatizadas como parte de la integración continua. Un proceso maduro de pruebas continuas implica de manera implícita que las pruebas también deben de desarrollarse en conjunto con las nuevas funcionalidades garantizando así que en su proceso de integración existen las validaciones apropiadas de lugar.

La prioridad de las pruebas automatizadas debe ser siempre enfocada en los flujos críticos para la operación del negocio. La "cobertura" de las pruebas ayuda a entender qué tan confiables son los nuevos cambios.

> Una cobertura del 100% es un objetivo irrealista para una aplicación en constante desarrollo, puesto la velocidad de desarrollo siempre será mayor a la de la realización de pruebas. Sin embargo, siempre se debe aspirar a estar lo más cerca posible.

## Monitoreo y alertas

El [monitoreo y las alertas][Monitoring and Alerting] son conceptos interrelacionados que juntos forman la base de un sistema de monitoreo. Tienen la capacidad de brindar visibilidad sobre el estado de sus sistemas, ayudar a comprender las tendencias en el uso o el comportamiento y comprender el impacto de los cambios que realiza. Si las métricas se encuentran fuera de los rangos esperados, estos sistemas pueden enviar notificaciones para solicitar a un operador que eche un vistazo, y luego pueden ayudar a mostrar información para ayudar a identificar las posibles causas.

La implementación de monitoreo y alertas como proceso garantiza **la observabilidad.**

## Seguridad integrada

La seguridad integrada en DevOps también es también visto mayormente como [DevSecOps]. Es tomar lo que ya hemos descrito sobre DevOps, pero ahora con un componente o silo adicional, Seguridad de la información. DevSecOps significa desarrollo, seguridad y operaciones. Es un enfoque de cultura, automatización y diseño de plataforma que integra la seguridad como una responsabilidad compartida a lo largo de todo el ciclo de vida de TI.

DevSecOps significa pensar en la seguridad de las aplicaciones y la infraestructura desde el principio. También significa automatizar algunas puertas de seguridad para evitar que el flujo de trabajo de DevOps se ralentice. Seleccionar las herramientas adecuadas para integrar continuamente la seguridad, como acordar un entorno de desarrollo integrado (IDE) con características de seguridad, puede ayudar a cumplir estos objetivos. Sin embargo, la seguridad efectiva de DevOps requiere más que nuevas herramientas: se basa en los cambios culturales de DevOps para integrar el trabajo de los equipos de seguridad más temprano que tarde.

<!-- Referencias -->
[git]: ../../referencias/enlaces#git
[Continuous Integration]: ../../referencias/enlaces#continuous-integration
[Continuous Delivery]: ../../referencias/enlaces#continuous-delivery
[Continuous Testing]: ../../referencias/enlaces#continuous-testing
[Monitoring and Alerting]: ../../referencias/enlaces#monitoring-and-alerting
[DevSecOps]: ../../referencias/enlaces#devsecops
