---
title : "Lab 2.1: Crear una máquina virtual en AWS"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "computacion-en-la-nube"
weight: 304
toc: true
---

En este laboratorio crearemos una máquina virtual en el servicio de AWS llamado Compute Cloud (Amazon EC2). Aprenderemos a iniciar, conectarnos y usar una instanci de Linux. Una instancia es sinónimo de máquina virtual en AWS.

> :rotating_light: Es probable que esta actividad sea básica para personas con experiencia en la nube, de ser así, puede omitir esta actividad asumiendo la responsibilidad que esto representa.

## Requerimientos

- Capacidad de lectura del idioma inglés.
- Registrarse en AWS, en este laboratorio es posible sacar provecho de la cobertura gratuita de AWS EC2.
- Instalación y configuración del CLI de AWS.
- Haber completado el tutorial [Configuración para usar Amazon EC2](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/get-set-up-for-amazon-ec2.html).

> :warning: Si creaste tu cuenta de AWS hace más de 12 meses y ya expiraron los beneficios del nivel gratuito para Amazon EC2, te costará algo de de dinero completar este laboratorio. De ser así, al culminar con el laboratorio, procure eliminar todos los recursos creados.

## Paso 1: Lanzar una instancia

Puede lanzar una instancia de Linux utilizando la Consola de administración de AWS como se describe en el siguiente procedimiento. Este tutorial está destinado a ayudarlo a lanzar rápidamente su primera instancia, por lo que no cubre todas las opciones posibles. Para obtener información sobre las opciones avanzadas, consulte Lanzar una instancia con el nuevo asistente de instancia de lanzamiento. Para obtener información sobre otras formas de iniciar su instancia, consulte Lanzar su instancia.

Para lanzar una instancia:

1. [Abra el portal de AWS EC2](https://console.aws.amazon.com/ec2).
2. En el panel de control de la consola de EC2, elija "Launch instance" y, a continuación, elija "Launch instance" entre las opciones de capacidad que aparecen.

    ![C1-M02-L201-001](images/C1-M02-L201-001.png)

3. En las sección de "Name and tags", para "Name", ingrese un nombre descriptivo para la instancia.

    ![C1-M02-L201-002](images/C1-M02-L201-002.png)

4. En Imágenes de aplicaciones y SO (Imagen de Amazon Machine), haga lo siguiente:
    1. Elija "**Quick start**" y luego elija "**Ubuntu**". Este es el sistema operativo (SO) para la instancia.
    2. Desde "**Amazon Machine Image (AMI)**", seleccione una versión HVM de Ubuntu. Tenga en cuenta elegir una AMI que sea eligible para el Free Tier. Una imagen de máquina de Amazon (AMI) es una configuración básica que sirve como plantilla para su instancia.

    ![C1-M02-L201-003](images/C1-M02-L201-003.png)

5. En "**Instance type**", en la lista "**Instance type**", podemos seleccionar la configuración de hardware para la instancia. Elija el tipo de instancia `t2.micro`, que está seleccionado de forma predeterminada. El tipo de instancia `t2.micro` es elegible para el nivel gratuito. En las regiones donde `t2.micro` no está disponible, puede usar una instancia de `t3.micro` en el nivel gratuito. Para obtener más información, consulte la documentación [AWS Free Tier].

    ![C1-M02-L201-004](images/C1-M02-L201-004.png)

6. En "**Key pair (login)**", para "**Key pair name**", elija un key pair.

    ![C1-M02-L201-005](images/C1-M02-L201-005.png)

     Si no ha creado uno anterior a este laboratorio, puede crear uno nuevo al seleccionar "**Create new key pair**":

    ![C1-M02-L201-006](images/C1-M02-L201-006.png)

    > :warning: No seleccione *< Continuar sin un key pair (no recomendado) >*. Si inicia su instancia sin un key pair, no podrá conectarse a ella luego.

7. Junto a "**Network settings**", elija **Edit**. Para "**Security group name**", verá que el asistente creó y seleccionó un grupo de seguridad para usted. Puede usar este grupo de seguridad o, alternativamente, puede seleccionar un grupo de seguridad existente.

    ![C1-M02-L201-007](images/C1-M02-L201-007.png)
    ![C1-M02-L201-008](images/C1-M02-L201-008.png)

8. Mantenga las selecciones predeterminadas para los demás ajustes de configuración de su instancia.
9. Revise el resumen de la configuración de su instancia en el panel "**Summary**" y, cuando esté listo, elija "**Launch instance**".

    ![C1-M02-L201-009](images/C1-M02-L201-009.png)

Y luego de volver a la consola, ya debería estar inicializándose la instancia.

> La instancia puede tardar unos minutos en estar lista para que podamos conectarnos a ella.

## Paso 2: Conectarse a la instancia

El sistema operativo de su computadora local determina las opciones que tiene para conectarse desde su computadora local a su instancia de Linux.

### Si usas Linux o macOS

- [SSH client]
- [EC2 Instance Connect]
- [AWS Systems Manager Session Manager]

### Si usas Windows

- [PuTTY]
- [SSH client]
- [AWS Systems Manager Session Manager]
- [Windows Subsystem for Linux]

## Paso 3: Limpia la instancia

Una vez que haya terminado con la instancia que creó para este tutorial, debe limpiar terminando la instancia.

Si lanzó una instancia que no está dentro de la capa gratuita de AWS, dejará de incurrir en cargos por esa instancia tan pronto como el estado de la instancia cambie a `shutting down` o `terminated`. Para mantener la instancia para más tarde, pero no incurrir en cargos, puede detener la instancia ahora y luego iniciarla de nuevo más tarde.

Para terminar la instancia:

1. En el panel de navegación, elija "**Instances**". En la lista de instancias, seleccione la instancia que desea terminar.
2. Elija "**Instance state**", "**Terminate instance**".
3. Elija "**Terminate**" cuando se le solicite confirmación.

    Amazon EC2 se apaga y finaliza su instancia. Una vez que su instancia finaliza, permanece visible en la consola durante un breve período de tiempo y, luego, la entrada se elimina automáticamente. No puede eliminar la instancia terminada de la pantalla de la consola usted mismo.

<!-- Referencias -->
[SSH client]: ../../referencias/enlaces#ssh-client
[EC2 Instance Connect]: ../../referencias/enlaces#ec2-instance-connect
[AWS Systems Manager Session Manager]: ../../referencias/enlaces#aws-systems-manager-session-manager
[PuTTY]: ../../referencias/enlaces#putty
[Windows Subsystem for Linux]: ../../referencias/enlaces#windows-subsystem-for-linux
[AWS Free Tier]: ../../referencias/enlaces#aws-free-tier
