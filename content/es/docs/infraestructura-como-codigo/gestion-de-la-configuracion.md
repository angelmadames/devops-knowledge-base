---
title : "Gestión de la configuración"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "infraestructura-como-codigo"
weight: 804
toc: true
---

## Definición

En el contexto de desarrollo de software, la gestión de la configuración se refiere al proceso mediante el cual se configuran y mantienen todos los entornos que alojan el software.

Cada flujo de desarrollo requiere múltiples entornos para múltiples propósitos:

- pruebas de integración,
- pruebas de aceptación,
- pruebas de carga,
- pruebas de usuario final, etc.

Estos entornos se vuelven cada vez más complejos a medida que las pruebas avanzan hacia entornos de preproducción y producción. La gestión de la configuración es un proceso automatizado que garantiza que la configuración de estos entornos sea **óptima**, **reproducible** y **constante**.

La configuración de los entornos de prueba es fundamental para el éxito de los equipos de aseguramiento de la calidad. La configuración precisa hace que todos los recursos (servidores, redes, centros de datos, sistemas operativos, activos de TI, archivos de configuración) funcionen como deben para facilitar el éxito.

Una gestión de configuración inadecuada puede provocar:

- interrupciones del sistema,
- pruebas inadecuadas, incompletas y superficiales.

El uso de la gestión de la configuración es imprescindible para equipos de trabajo que adoptan la cultura DevOps. Ayuda a automatizar tareas de mantenimiento rutinarias, lo que libera tiempo de desarrollo y operación. Esto aumenta la agilidad, tanto por parte de los desarrolladores individuales como de la organización en su conjunto.

## Componentes

En el pasado, la gestión de la configuración era un proceso realizado de manera totalmente manual. Gracias a `shell scripting`, se pudo obtener un siguiente nivel donde se automatizaban los procesos de configuración y despliegue de manera parcial debido a las limitantes de esta interfaz.

Con ayuda de lenguajes de programación modernos e interpretados, hoy día es posible encontrar herramientas diseñadas para automatizar de manera completa la gestión de la configuración. Tanto así, que es ya considerado como una práctica predominante definir la configuración de las aplicaciones en código, ejecutable por estas herramientas auxiliares.

A nivel general, podemos definir algunos elementos o componentes en común de la gestión de la configuración realizada bajo definiciones de código:

- **Scripts**: `scripting` nunca ha dejado de ser un protagonista en la gestión de la configuración. A pesar de que antes existían limitaciones, las herramientas modernas aún definen de manera estructurada y secuencial los pasos a ejecutar para configurar correctamente un etorno de aplicación dado los parámetros de entrada. Los scripts están bajo control de versiones lo que permite cumplir con la nececidad de control de cambios y gestión de versiones.
- **Repositorio de código fuente**: Ya que la gestión de la configuración implica también el proceso de compilación y gestión de artefactos, es también un componente el repositorio del código fuente de la aplicación. A través de éste es como se ejecutan las diferentes actividades necesarios para llevar una versión óptima a un repositorio de artefactos.
- **Repositorio de artefactos o imágenes**: Cuando nos referimos a artefactos o imágenes, hablamos de los archivos resultantes del proceso de compilación de una aplicación o su empaquetación para ejecución en contenedores.

> En el caso de las aplicaciones web, podemos obtener **archivos estáticos** (`static files` en inglés) consistentes de archivos no ejecutables servidos a través de un servidor web, usualmente en los formatos HTML (`.html`), CSS (`.css`) y JavaScript (`.js`). En el caso de las aplicaciones a nivel de [SSR], los binarios o archivos resultantes son ejecutados a través de un intérprete y se mantienen como `daemons` o `procesos` en el sistema operativo; siendo éstos finalmente publicados o protegidos con un [reverse proxy].

- **Inventario de servidores**: Dado que las aplicaciones son ejecutadas finalmente en servidores, los scripts de configuración son ejecutados en contra de un host o recurso configurable. En el caso de la nube, esto usalmente hace referencia a una instancia o máquina virtual pero con las tendencias `serverless` puede ser por igual simplemente una interfaz de un servicio tipo [FaaS] (como [AWS Lambda Functions] o [Azure App Functions]). El inventario hace referencia a estos recursos configurables, cuáles sean.

## Implementaciones

Si todas las configuraciones se gestionan adecuadamente, podemos tener dos tipos de implementaciones como resultados de dicho proceso:

- la infraestructura como código.
- la configuración como código.

> **Nota de interés:** Estas implementaciones nos permiten medir objetivamente la madurez y cobertura del proceso de gestión de configuración en los contextos que competan.

Abundemos un poco en ambas...

### Infraestructura como código (IaC)

En términos básicos, la infraestructura como código (`IaC`) se refiere a la existencia de código que configura automáticamente recursos de infraestructura.

No hace falta decir que esto es mucho más eficiente que la configuración de la infraestructura manual.

En este caso, el "entorno" se refiere a todos los recursos necesarios para las operaciones:

- servidores,
- redes,
- almacenamiento,
- aspectos de seguridad.

En fin, todo lo que comprende la infraestructura de TI.

Estos detalles se elaboran como una pieza de código en lugar de un documento. Este código empujado al sistema de control de versiones, se convierte en el modo singular de definir este entorno. También se puede utilizar para actualizar el entorno.

### Configuración como código

La configuración como código (`CaC`), como `IaC`, es un código que define la configuración de servidores o cualquier recurso informático. Como en IaC, este código se envía a un sistema de control de versiones.

Es importante notar la diferencia con IaC, puesto en uno el objetivo es definir la infraestructura y en otro es configurarla.

## Beneficios

- Reduce el riesgo de fallas impredecibles del sistema debido a la visibilidad y seguimiento de cada cambio realizado.
- Reduce los costos al disminuir la posibilidad de duplicar activos tecnológicos.
- Ofrece mayor agilidad y mejor resolución de incidencias gracias a la visualización de cambios (imprevistos o no) que hayan podido generar dichos problemas.
- Implementar una restauración más rápida de los servicios. Esto se debe a que la configuración, incluidos todos los cambios, está automatizada y documentada. No solo es más fácil detectar el problema, sino que también es más fácil revertir el entorno fallido a su última etapa funcional.

## Herramientas de la gestión de la configuración

Es común que las herramientas de gestión de configuración también incluyan automatización. Las herramientas populares son:

- [Ansible]
- [Chef]
- [Puppet]

## Gestión de la configuración vs. Gestión de cambios

La gestión de la configuración y la gestión del cambio son dos términos estrechamente relacionados pero diferentes.

La gestión de la configuración se ocupa del estado de cualquier infraestructura o sistema de software en un momento dado. La gestión de cambios, por el contrario, se ocupa de cómo se realizan los cambios en esas configuraciones.

Se puede ver de estar manera: la gestión de la configuración es la configuración en un momento dado, y la gestión de cambios es el proceso para proponer, revisar, implementar y posiblemente revertir cambios en esas configuraciones.

<!-- Referencias -->
[Ansible]: ../../referencias/enlaces#ansible
[Chef]:  ../../referencias/enlaces#chef
[Puppet]: ../../referencias/enlaces#puppet
