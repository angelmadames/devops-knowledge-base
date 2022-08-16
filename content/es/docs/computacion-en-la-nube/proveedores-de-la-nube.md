---
title : "Proveedores de la nube"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "computacion-en-la-nube"
weight: 303
toc: true
---

## Proveedores de servicios en la nube

Un [proveedor de servicios en la nube (CSP)][Cloud Service Providers], es una empresa que ofrece componentes de computación en la nube, por lo general uno de los servicios que ya hemos conversado:

- [Infraestructura como servicio (IaaS)][IaaS]
- [Software como servicio (SaaS)][SaaS]
- [Plataforma como servicio (PaaS)][PaaS]

Los proveedores de servicios en la nube utilizan sus propios [centros de datos][Data Center] para alojar servicios de plataforma e infraestructura basados en la computación en la nube.

Los servicios en la nube generalmente tienen un precio que utiliza varios modelos de suscripción de [pago por uso][PAYG]. A los clientes se les cobra solo por los recursos que consumen, como la cantidad de tiempo que se utiliza un servicio o la capacidad de almacenamiento o las máquinas virtuales (`VM`) utilizadas.

Para los productos **SaaS**, los proveedores de servicios en la nube pueden alojar y entregar sus propios servicios gestionados a los usuarios o pueden actuar como terceros, alojando la aplicación de un proveedor de software independiente.

Las plataformas de servicios en la nube más conocidas son:

- Amazon Web Services (AWS)
- Google Cloud Platform (GCP)
- Microsoft Azure

Conversemos un poco de cada una a continuación.

### Amazon Web Services (AWS)

[Amazon Web Services (AWS)][AWS] es una subsidiaria de Amazon que proporciona plataformas de computación en la nube bajo demanda a *individuos*, *empresas* y *gobiernos*, en una base de [pago por uso][PAYG] medido.

Uno de estos servicios es [Amazon Elastic Compute Cloud (EC2)][EC2], que permite a los usuarios tener a su disposición un clúster virtual de computadoras, disponible todo el tiempo, a través de Internet. Las computadoras virtuales de AWS emulan la mayoría de los atributos de una computadora real, incluidas:

- Las unidades de procesamiento central (CPU) de hardware
- Las unidades de procesamiento de gráficos (GPU)
- Memoria (RAM)
- Almacenamiento en disco duro (SSD)
- Una selección de sistemas operativo

Los servicios de AWS se entregan a los clientes a través de una red de granjas de servidores de AWS ubicadas en todo el mundo. Las tarifas se basan en una combinación de uso (conocido como modelo de "[pago por uso][PAYG]"), hardware, sistema operativo, software o funciones de red elegidas por el suscriptor que requiere disponibilidad, redundancia, seguridad y opciones de servicio.

### Microsoft Azure (Azure)

[Azure][Microsoft Azure] es un servicio de computación en la nube operado por [Microsoft] para la administración de aplicaciones. Proporciona [SaaS], [PaaS] e [IaaS], al igual que AWS.

### Google Cloud Platform (GCP)

[Google Cloud Platform (GCP)][Google Cloud Platform] es ofrecido por Google, es un conjunto de servicios de computación en la nube que se ejecuta en la misma infraestructura que Google usa internamente para sus productos de usuario final, como Búsqueda de Google, Gmail, Google Drive y YouTube.

Junto con un conjunto de herramientas de gestión, proporciona una serie de servicios modulares en la nube que incluyen computación, almacenamiento de datos, análisis de datos y aprendizaje automático. El registro requiere una tarjeta de crédito o datos de una cuenta bancaria.

Al igual que AWS y Azure, [Google Cloud Platform] proporciona proporciona [SaaS], [PaaS] e [IaaS].

[GCP][Google Cloud Platform] es parte de Google Cloud, que incluye la infraestructura de nube pública de GCP, así como también Google Workspace (G Suite), versiones empresariales de Android y Chrome OS, e interfaces de programación de aplicaciones (API) para aprendizaje automático y empresa.

<!-- Referencias -->
[Data Center]: ../../referencias/enlaces#data-center
[Cloud Service Providers]: ../../referencias/enlaces#cloud-service-providers
[PAYG]: ../../referencias/enlaces#pay-as-you-go
[AWS]: ../../referencias/enlaces#aws
[Microsoft]: ../../referencias/enlaces#microsoft
[Microsoft Azure]: ../../referencias/enlaces#microsoft-azure
[Google Cloud Platform]: ../../referencias/enlaces#google-cloud-platform
[EC2]: ../../referncias/README.md#aws-ec2
[IaaS]: ../../referencias/enlaces#infrastructure-as-a-service-iaas
[PaaS]: ../../referencias/enlaces#platform-as-a-service-paas
[SaaS]: ../../referencias/enlaces#software-as-a-service-saas
