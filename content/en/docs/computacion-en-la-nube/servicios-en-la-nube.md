---
title : "Servicios en la nube"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "computacion-en-la-nube"
weight: 302
toc: true
---

## La nube :cloud:

Entender el concepto de *la nube* es de suma importancia para cualquier profesional de TI. Es probable, que a esto punto, ya sepas con claridad lo que es exactamente. En cualquier caso, definamos la nube solo para asegurarnos que estamos en la misma página.

Cuando nos referimos a "la nube" (en inglés, *The Cloud*), hablamos simplemente de servidores que son accesibles a través de Internet y del software o datos que se alojan en esos servidores, y que son manejados en centros de datos en diferentes partes del mundo.

> Si bien el concepto  de "la nube" es más frecuente relacionado a servidores gestionados por un proveedor, al cual se le descarga la responsabilidad del provisionamiento y mantenimiento físico de estos centros, es totalmente posible tener una nube propietaria privada.

La principal idea de la nube es que no tienes que manejar servidores físicos directamente, ni que sea tu responsabilidad. Y que ésto no sea tu responsabilidad, no implica que no tengas control de estos recursos, es más bien una abstracción que te permite concentrarte en lo que realmente le importa a tu negocio o empresa: **la ejecución de sus sistemas y aplicaciones en un entorno de infraestructura confiable, seguro, disponible y escalable.**

### ¿Cómo funciona la computación en la nube? :thinking:

La computación en la nube es algo posible debido a la **virtualización**.

La virtualización permite la creación de una computadora "virtual" simulada que se comporta como si fuera una computadora física con su propio hardware. Como de seguro ya sabes, el término técnico para tal computadora es **máquina virtual**.

Cuando se implementan correctamente, las máquinas virtuales en la misma *máquina host* están aisladas unas de otras, por lo que no interactúan entre sí en absoluto, y los archivos y las aplicaciones de una máquina virtual no son visibles para las otras máquinas virtuales aunque estén en la misma máquina física.

Las máquinas virtuales también hacen un uso más eficiente del hardware que las aloja. Al ejecutar muchas máquinas virtuales a la vez, un servidor se convierte en muchos servidores y un centro de datos se convierte en una gran cantidad de centros de datos, capaces de atender a muchas organizaciones. Por lo tanto, los proveedores de la nube pueden ofrecer el uso de sus servidores a muchos más clientes a la vez de lo que podrían hacerlo de otra manera, y pueden hacerlo a un bajo costo.

Los servidores en la nube en general deben estar siempre en línea y disponibles. Al igual que respaldan sus servicios en múltiples máquinas y en múltiples regiones.

## Servicios y la nube

Los [servicios en la nube] (en inglés, Cloud Services) son **infraestructuras**, **plataformas** o **software** alojados por [proveedores][Proveedor] externos y puestos a disposición de los usuarios a través de Internet.

Los servicios en la nube promueven la creación de aplicaciones nativas de la nube. El flujo de datos es mucho más activo, disponible y frecuente debido a que los usuarios pueden conectarse a través de sus clientes de conexión (computadoras, tables, teléfonos inteligentes) a través de Internet.

Las limitaciones de los servicios tradicionales, como por ejemplo tener que estar presente en las oficinas para poder consumir un servicio interno, son cosas del pasado. Hoy en día la mayoría de las aplicaciones se desarrollan orientadas a la nube, lo que juega un papel importante en la popularidad que han tenido los métodos ágiles y DevOps, puesto están pensados para este tipo de entornos.

## Soluciones como servicio

En el apogeo de la computación y servicios en la nube, y en gran parte gracias a la flexibilidad que permiten, se ha definido una modalidad de negocio e implementación de soluciones que podemos definir a alto nivel como "*soluciones como servicio*".

En las soluciones como servicio existen 4 agrupaciones principales:

- **Infraestructura como servicio**: proporciona a los usuarios recursos informáticos, de red y de almacenamiento.
- **Plataforma como servicio**: proporciona a los usuarios una plataforma en la que se pueden ejecutar las aplicaciones, así como toda la infraestructura de TI necesaria para que se ejecute.
- **Software como servicio**: proporciona a los usuarios, esencialmente, una aplicación en la nube, la plataforma en la que se ejecuta y la infraestructura subyacente de la plataforma.
- **Función como servicio**: un modelo de ejecución basado en eventos, permite a los desarrolladores crear, ejecutar y administrar paquetes de aplicaciones como funciones sin mantener la infraestructura.

Las nubes son entornos de TI que extraen, agrupan y comparten recursos escalables en una red. Las nubes permiten la computación en la nube, que es el acto de ejecutar cargas de trabajo dentro de un entorno de nube. Las nubes son un tipo de [PaaS], porque el hardware y la plataforma de software de aplicaciones son proporcionados por un tercero.

### Infrastructura como servicio (IaaS)

> En inglés: Infrastructure as a Service

La [infraestructura como servicio (IaaS)][IaaS], también conocida como *servicios de infraestructura en la nube*, es un tipo de servicio de computación en la nube que ofrece recursos esenciales de cómputo, almacenamiento y redes en demanda, sobre una base de **pago por uso**.

El uso de las soluciones [IaaS] ayuda a:

- Reducir el mantenimiento de los centros de datos locales.
- Ahorrar dinero en costos de hardware y obtener información comercial en tiempo real.
- Escalar recursos de TI hacia arriba y hacia abajo en demanda.
- Aprovisionar rápidamente nuevos recursos y aplicaciones.

> El aspecto más atractivo de [IaaS] es que permite evitar el costo y la complejidad de comprar y administrar servidores físicos e infraestructura de centros de datos. Cada recurso se ofrece como un componente de servicio separado y solo paga por un recurso en particular durante el tiempo que lo necesite.

Un proveedor de servicios de computación en la nube administra la infraestructura, mientras que usted *compra*, *instala*, *configura* y *administra* su propio software, incluidos los sistemas operativos y las aplicaciones.

### Plataforma como servicio (PaaS)

> En inglés: Platform as a Service

La [plataforma como servicio (PaaS)][PaaS] es un modelo de computación en la nube en el que un proveedor externo ofrece herramientas de hardware y software a los usuarios a través de Internet. Un proveedor de PaaS aloja el hardware y el software en su propia infraestructura, por lo que el equipo no debe preocuparse de tener que instalar hardware y software internos para desarrollar o ejecutar una nueva aplicación.

Al igual que [IaaS], [PaaS] incluye infraestructura (`servidores`, `almacenamiento` y `redes`), pero también `middleware`, `herramientas de desarrollo`, `servicios de inteligencia comercial (BI)`, `sistemas de administración de bases de datos` y más.

[PaaS] está diseñado para admitir el ciclo de vida completo de la aplicación web: creación, prueba, implementación, administración y actualización.

Las herramientas [PaaS] tienden a promocionarse como **fáciles de usar** y **convenientes**. Una organización puede encontrar convincente el cambio a **PaaS** considerando los posibles ahorros de costos en comparación con las alternativas locales.

### Software como servicio (SaaS)

El [software como servicio (SaaS)][SaaS] es un modelo de distribución de software en el que un proveedor de la nube aloja aplicaciones y las pone a disposición de los usuarios finales a través de Internet. En este modelo, un proveedor de software puede contratar a un proveedor de nube externo para alojar la aplicación.

En lugar de instalar y mantener el software, simplemente se accede a él a través de Internet, liberándose de la compleja administración de software y hardware.

### Función como servicio (FaaS)

[FaaS] es un tipo de servicio de computación en la nube que permite a los desarrolladores crear, calcular, ejecutar y administrar paquetes de aplicaciones como funciones sin tener que mantener su propia infraestructura.

[FaaS] es un modelo de ejecución basado en eventos que se ejecuta en contenedores sin estado y esas funciones administran la lógica y el estado del lado del servidor mediante el uso de servicios de un proveedor de [FaaS].

Las soluciones [FaaS] están disponibles en las principales nubes públicas y se pueden aprovisionar en las instalaciones, lo que agrega nuevas capacidades significativas a la TI empresarial para el desarrollo de aplicaciones. Obtenga la guía de estrategia nativa de la nube para prepararse para implementar un enfoque sin servidor con [FaaS].

Algunos ejemplos de [FaaS] populares:

- IBM Cloud Functions
- Amazon's AWS Lambda
- Google Cloud Functions
- Microsoft Azure Functions (open source)
- OpenFaaS (open source)

#### FaaS y Serverless

[FaaS] es una forma de implementar la [computación serverless] en la que los desarrolladores escriben la lógica comercial que luego se ejecuta en contenedores Linux totalmente administrados por una plataforma.

Aunque por lo general es una plataforma de computación en la nube que utiliza servicios de computación en la nube, el modelo se está expandiendo para incluir también implementaciones locales e híbridas.

> Sin servidor, Serverless

Serverless abstrae las preocupaciones de la infraestructura, como la administración o el aprovisionamiento de servidores y la asignación de recursos de los desarrolladores, y los entrega a una plataforma, para que los desarrolladores puedan concentrarse en escribir código y brindar valor comercial.

Una función es una pieza de software que ejecuta la lógica empresarial en un sistema operativo. Las aplicaciones pueden estar compuestas por muchas funciones.

El uso de un modelo [FaaS] es una forma de crear una aplicación con una arquitectura serverless, pero con el aumento de la popularidad del paradigma serverless, los desarrolladores buscan soluciones que admitan la creación de microservicios serverless y contenedores sin estado.

<!-- Referencias -->
[Proveedor]: ../../referencias/enlaces#proveedor
[Servicios en la nube]: ../../referencias/enlaces#cloud-services
[computación serverless]: ../../referencias/enlaces#serverless
[IaaS]: ../../referencias/enlaces#infrastructure-as-a-service-iaas
[PaaS]: ../../referencias/enlaces#platform-as-a-service-paas
[SaaS]: ../../referencias/enlaces#software-as-a-service-saas
[FaaS]: ../../referencias/enlaces#function-as-a-service-faas
