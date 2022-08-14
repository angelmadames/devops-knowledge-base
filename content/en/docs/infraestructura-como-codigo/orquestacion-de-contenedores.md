---
title : "Orquestación de contenedores"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "infraestructura-como-codigo"
weight: 805
toc: true
---

## Definición

La **orquestación de contenedores** es la automatización de gran parte del esfuerzo operativo necesario para ejecutar cargas de trabajo y servicios en contenedores.

Esto incluye una amplia gama de cosas que los equipos de software necesitan para gestionar el ciclo de vida de un contenedor, incluyendo:

- aprovisionamiento,
- despliegue,
- escalada (hacia arriba y hacia abajo),
- redes,
- balanceo de carga.

## ¿Por qué es necesaria la orquestación?

Debido a que los contenedores son livianos y efímeros por naturaleza, ejecutarlos en producción puede convertirse rápidamente en un esfuerzo enorme.

En particular, cuando se combina con microservicios, que generalmente se ejecutan en sus propios contenedores, una aplicación en contenedores puede traducirse en la operación de cientos o miles de contenedores, especialmente al construir y operar cualquier sistema a gran escala.

Esto puede presentar una complejidad significativa si se gestiona manualmente.

La orquestación de contenedores es lo que hace que la complejidad operativa sea manejable para el equipo, porque proporciona una forma declarativa de automatizar gran parte del trabajo.

Esto lo convierte en una buena opción para los equipos y la cultura de DevOps, que normalmente se esfuerzan por operar con mucha mayor velocidad y agilidad que los equipos de software tradicionales.

## Usos

Use la orquestación de contenedores para automatizar y administrar tareas como:

- Aprovisionamiento y despliegue
- Configuración y programación
- Asignación de recursos
- Disponibilidad de contenedores
- Escalar o eliminar contenedores en función del equilibrio de las cargas de trabajo en su infraestructura
- Equilibrio de carga y enrutamiento de tráfico
- Supervisión del estado del contenedor
- Configuración de aplicaciones en función del contenedor en el que se ejecutarán
- Mantener seguras las interacciones entre contenedores

## Beneficios

La orquestación de contenedores es clave para trabajar con contenedores y permite a las organizaciones desbloquear todos sus beneficios. También ofrece sus propios beneficios para un entorno en contenedores, que incluyen:

- **Operaciones simplificadas**: este es el beneficio más importante de la orquestación de contenedores y la principal razón para su adopción. Los contenedores introducen una gran cantidad de complejidad que puede salirse rápidamente de control sin la orquestación de contenedores para administrarla.
- **Resiliencia**: las herramientas de orquestación de contenedores pueden reiniciar o escalar automáticamente un contenedor o clúster, lo que aumenta la resiliencia.
- **Seguridad adicional**: el enfoque automatizado de la orquestación de contenedores ayuda a mantener seguras las aplicaciones en contenedores al reducir o eliminar la posibilidad de error humano.

## Funcionamiento

Si bien existen diferencias en las metodologías y capacidades entre las herramientas, la orquestación de contenedores es esencialmente un proceso de tres pasos (o ciclo, cuando forma parte de una canalización iterativa ágil o DevOps).

La mayoría de las herramientas de orquestación de contenedores admiten un modelo de configuración declarativo: un desarrollador escribe un archivo de configuración (en YAML o JSON según la herramienta) que define un estado de configuración deseado, y la herramienta de orquestación ejecuta el archivo usando su propia inteligencia para lograr ese estado. El archivo de configuración normalmente

- Define qué imágenes de contenedor componen la aplicación y dónde se encuentran (en qué registro)
- Aprovisiona los contenedores con almacenamiento y otros recursos
- Define y asegura las conexiones de red entre contenedores
- Especifica el control de versiones (para lanzamientos controlados o por fases)

La herramienta de orquestación programa la implementación de los contenedores (y las réplicas de los contenedores, para la resiliencia) en un host, eligiendo el mejor host en función de la capacidad de CPU disponible, la memoria u otros requisitos o restricciones especificados en el archivo de configuración.

Una vez que se implementan los contenedores, la herramienta de orquestación administra el ciclo de vida de la aplicación en contenedores en función del archivo de definición del contenedor (muy a menudo un Dockerfile). Esto incluye

- Administrar la escalabilidad (hacia arriba y hacia abajo), el equilibrio de carga y la asignación de recursos entre los contenedores;
- Garantizar la disponibilidad y el rendimiento mediante la reubicación de los contenedores en otro host en caso de una interrupción o escasez de recursos del sistema.
- Recopilación y almacenamiento de datos de registro y otra telemetría utilizada para monitorear el estado y el rendimiento de la aplicación.

## Herramientas de orquestación de contenedores

Las herramientas de orquestación de contenedores proporcionan un marco para administrar contenedores y arquitectura de microservicios a escala. Hay muchas herramientas de orquestación de contenedores que se pueden usar para la gestión del ciclo de vida de los contenedores. Algunas opciones populares son [Kubernetes], [Docker Swarm], [Apache Mesos] y [Nomad].

Kubernetes es una herramienta de orquestación de contenedores de código abierto que originalmente fue desarrollada y diseñada por ingenieros de Google. Google donó el proyecto Kubernetes a la recién formada Cloud Native Computing Foundation en 2015.

La orquestación de Kubernetes le permite crear servicios de aplicaciones que abarcan varios contenedores, programar contenedores en un clúster, escalar esos contenedores y administrar su estado a lo largo del tiempo.

Kubernetes elimina muchos de los procesos manuales involucrados en la implementación y escalado de aplicaciones en contenedores. Puede agrupar grupos de hosts, ya sean máquinas físicas o virtuales, que ejecuten contenedores de Linux, y Kubernetes le brinda la plataforma para administrar esos clústeres de manera fácil y eficiente.

En términos más generales, lo ayuda a implementar y confiar completamente en una infraestructura basada en contenedores en entornos de producción.

Estos clústeres pueden abarcar hosts en nubes públicas, privadas o híbridas. Por este motivo, Kubernetes es una plataforma ideal para alojar aplicaciones nativas de la nube que requieren un escalado rápido.

Kubernetes también ayuda con la portabilidad de la carga de trabajo y el equilibrio de carga al permitirle mover aplicaciones sin rediseñarlas.

## Kubernetes

Como se señaló anteriormente, Kubernetes es la plataforma de orquestación de contenedores más popular. Junto con otras herramientas en el ecosistema de contenedores, Kubernetes permite a una empresa ofrecer una plataforma como servicio (PaaS) altamente productiva que aborda muchas de las tareas y problemas relacionados con la infraestructura y las operaciones en torno al desarrollo de aplicaciones nativas de la nube, de modo que que los equipos de desarrollo puedan centrarse exclusivamente en la codificación y la innovación.

Las ventajas de Kubernetes sobre otras soluciones de orquestación se deben en gran medida a su funcionalidad más completa y sofisticada en varias áreas, que incluyen:

- **Despliegue de contenedores.** Kubernetes implementa una cantidad específica de contenedores en un host específico y los mantiene funcionando en el estado deseado.
- **Despliegues**. Un lanzamiento es un cambio en una implementación. Kubernetes le permite iniciar, pausar, reanudar o revertir implementaciones.
- **Descubrimiento de servicios.** Kubernetes puede exponer automáticamente un contenedor a Internet o a otros contenedores mediante un nombre de DNS o una dirección IP.
- **Aprovisionamiento de almacenamiento.** Los desarrolladores pueden configurar Kubernetes para montar almacenamiento persistente local o en la nube para sus contenedores, según sea necesario.
- **Equilibrio de carga y escalabilidad**. Cuando el tráfico a un contenedor aumenta, Kubernetes puede emplear el equilibrio de carga y el escalado para distribuirlo en la red para garantizar la estabilidad y el rendimiento. (También ahorra a los desarrolladores el trabajo de configurar un balanceador de carga).
- **Auto-reparación para alta disponibilidad**. Cuando falla un contenedor, Kubernetes puede reiniciarlo o reemplazarlo automáticamente. También puede derribar contenedores que no cumplan con los requisitos de su control de salud.
- **Soporte y portabilidad entre múltiples proveedores de nube**. Como se señaló anteriormente, Kubernetes disfruta de un amplio soporte en todos los proveedores de nube líderes. Esto es especialmente importante para las organizaciones que implementan aplicaciones en un entorno de nube híbrida o multinube híbrida.
- **Creciente ecosistema de herramientas de código abierto**. Kubernetes también tiene un conjunto de herramientas de red y usabilidad en constante expansión para mejorar sus capacidades a través de la API de Kubernetes. Estos incluyen Knative, que permite que los contenedores se ejecuten como cargas de trabajo sin servidor; e Istio, una red de servicios de código abierto.

<!-- Referencias -->
[Kubernetes]: ./../referencias/enlaces#kubernetes
[Docker Swarm]: ./../referencias/enlaces#docker-swarm
[Apache Mesos]: ./../referencias/enlaces#apache-mesos
[Nomad]: ./../referencias/enlaces#nomad
