---
title : "Contenedores"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "contenerizacion"
weight: 502
toc: true
---

## Repaso

A pesar de que asumimos que ya tienes conocimiento técnico previo a este curso, creo importante que repasemos algunos conceptos básicos con el fin de que estemos en la misma página antes de entrar en materia en cuanto a `contenedores`.

### El kernel y el sistema operativo

Una computadora está construida sobre algunas piezas de hardware como:

- la unidad central de procesamiento (CPU),
- el almacenamiento persistente (unidad de disco, SSD)
- la memoria (RAM),
- la tarjeta de red, entre otros periféricos.

Para interactuar con este hardware, una pieza de software en el sistema operativo llamada **[kernel]** sirve como puente entre el hardware y el resto del sistema. El núcleo es responsable de programar la ejecución de procesos (programas), administrar dispositivos (leer y escribir direcciones en el disco y la memoria) y más.

El resto del sistema operativo sirve para iniciar y administrar el espacio del usuario, donde se ejecutan los procesos del usuario e interactuará constantemente con el kernel.

### Máquinas virtuales

Una máquina virtual, como lo indica su nombre, no es más que simular las operaciones de una computadora de manera virtual. Es como tener una computadora a la cual no tienes acceso físico, pero puedes aún así acceder a ella y realizar la mayoría de las cosas que normalmente harías.

> Máquina virtual, VM por sus siglas en inglés.

Una *VM* se compone de algún nivel de virtualización de **hardware** y **kernel** en el que se ejecuta un sistema operativo invitado.

> Se le dice sistema operativo invitado debido a que en inglés se diferencian entre "host" y "guest", siendo el primero el sistema operativo base y el último el virtualizado. "guest" en español significa "invitado" en españl.

Una pieza de software llamada **hipervisor** crea el hardware virtualizado que puede incluir el disco virtual, la interfaz de red virtual, la CPU virtual, entre otros periféricos requeridos. Las VMs también incluyen un **kernel invitado** que puede comunicarse con este hardware virtual.

El hipervisor se puede alojar, lo que significa que es un software que se ejecuta en el sistema operativo host. También puede ser bare metal, ejecutándose directamente en el hardware de la máquina (reemplazando su sistema operativo). De cualquier manera, el enfoque del hipervisor se considera pesado, ya que requiere virtualizar varias partes, si no todo el hardware y el kernel.

## Antecedentes

### cgroups

En `2006`, los ingenieros de [Google] inventaron los "*grupos de control*" de Linux, abreviados como **[cgroups]**. Esta es una característica del [kernel] de Linux que **aísla y controla el uso de recursos para los procesos del usuario.**

Estos procesos se pueden colocar en [namespaces], esencialmente colecciones de procesos que comparten las mismas limitaciones de recursos. Una computadora puede tener varios [namespaces], cada uno con las propiedades de recursos impuestas por el [kernel].

> La traducción a español de namespaces no es usual ni generalmente vista en términos técnicos. Por tanto, usarmoes `namespaces` de manera formal.

La asignación de recursos por [namespaces] se puede administrar para limitar la cantidad total de `CPU`, `RAM`, etc. que puede usar un conjunto de procesos.

Si bien no es una función original, [cgroups] en Linux finalmente se modificó para incluir una función llamada aislamiento de [namespaces].

## Contenedores de Linux

Los [cgroups] de Linux allanaron el camino para una tecnología llamada contenedores de Linux (LXC). [LXC] fue realmente la primera implementación importante de lo que hoy conocemos como un contenedor, aprovechando [cgroups] y el aislamiento del namespaces para crear un entorno virtual con un proceso y un espacio de red separados.

En cierto sentido, esto permite espacios de usuario independientes y aislados. La idea de los contenedores se deriva directamente de [LXC]. De hecho, las versiones anteriores de Docker se crearon directamente sobre [LXC].

## Contendores: Definición

Los contenedores son paquetes livianos del código de su aplicación junto con dependencias, como versiones específicas de lenguajes de programación y librerías necesarias para ejecutar sus servicios de software.

Los contenedores son paquetes de software que contienen todos los elementos necesarios para ejecutarse en cualquier entorno. De esta forma, los contenedores virtualizan el sistema operativo y se ejecutan en cualquier lugar, desde un centro de datos privado hasta la nube pública o incluso en la computadora portátil personal de un desarrollador.

## Beneficios

- **Separación de responsabilidades:** La contenerización proporciona una clara separación de responsabilidades, ya que los desarrolladores se centran en la lógica y las dependencias de la aplicación, mientras que los equipos de operaciones de TI pueden centrarse en la implementación y la gestión en lugar de los detalles de la aplicación, como versiones y configuraciones de software específicas.
- **Portabilidad de la carga de trabajo:** Los contenedores pueden ejecutarse prácticamente en cualquier lugar, lo que facilita enormemente el desarrollo y la implementación: en los sistemas operativos Linux, Windows y Mac; en máquinas virtuales o en servidores físicos; en la máquina de un desarrollador o en centros de datos locales; y por supuesto, en la nube pública.
- **Aislamiento de aplicaciones:** Los contenedores virtualizan los recursos de CPU, memoria, almacenamiento y red a nivel del sistema operativo, proporcionando a los desarrolladores una vista del sistema operativo aislada lógicamente de otras aplicaciones.

## Diferencias con máquinas virtuales

Los contenedores a menudo se comparan con máquinas virtuales (VM).

Al igual que las máquinas virtuales, los contenedores le permiten empaquetar su aplicación junto con bibliotecas y otras dependencias, proporcionando entornos aislados para ejecutar sus servicios de software.

Sin embargo, las similitudes terminan ahí, ya que los contenedores ofrecen una unidad mucho más liviana para que trabajen los desarrolladores y los equipos de operaciones de TI, lo que brinda una gran cantidad de beneficios.

- Los contenedores son mucho más ligeros que las máquinas virtuales
- Los contenedores se virtualizan a nivel del sistema operativo, mientras que las máquinas virtuales se virtualizan a nivel de hardware
- Los contenedores comparten el kernel del sistema operativo y usan una fracción de la memoria que requieren las máquinas virtuales

## Usos prácticos

Los contenedores ofrecen un mecanismo de empaquetado lógico en el que las aplicaciones pueden abstraerse del entorno en el que realmente se ejecutan.

Este desacoplamiento permite que las aplicaciones basadas en contenedores se implementen de manera fácil y consistente, independientemente de si el entorno de destino es un centro de datos privado, la nube pública o incluso la computadora portátil personal de un desarrollador.

De manera resumida:

- Desarrollo ágil
- Operaciones eficientes
- Ejecución en cualquier ambiente

## Contenerización

El software debe diseñarse y empaquetarse de manera diferente para aprovechar los contenedores, un proceso comúnmente conocido como **contenerización**.

Al contenerizar una aplicación, el proceso incluye empaquetar su versión compilada con sus variables de entorno relevantes, archivos de configuración, librerías y dependencias de software. El resultado es una imagen de contenedor que luego se puede ejecutar en una plataforma de contenedor.

> A pesar de que las variables de ambiente y archivos de configuración pueden estar dentro de la imagen del contendor, es una buena práctica abstraer esos recursos e inyectarlos a nivel de ejecución a través de un orquestador. Abundaremos más sobre este práctica en el resto del curso.

## Herramientas relacionadas

### Docker

**Docker** es la tecnología de contenedores más utilizada y realmente lo que la mayoría de la gente quiere decir cuando se refiere a los contenedores. Si bien existen otras tecnologías de contenedores de código abierto (como rkt de CoreOS) y grandes empresas que crean su propio motor de contenedores (como lmctfy en Google), **Docker** se ha convertido en el estándar de la industria para la contenerización. Todavía se basa en los cgroups y el espacio de nombres proporcionados por el kernel de Linux y, recientemente, también por Windows.

¡Aprenderemos más sobre **Docker** en el [siguiente tema de este módulo](02-docker.md)!

### Kubernetes

Desde la época de los contenedores de Linux, los usuarios han intentado implementar aplicaciones a gran escala en muchas máquinas virtuales donde cada proceso se ejecuta en su propio contenedor. Hacer esto requería poder implementar de manera eficiente decenas a miles de contenedores en potencialmente cientos de máquinas virtuales y administrar sus redes, sistemas de archivos, recursos, etc.

**Docker** hoy hace que esto sea un poco más fácil ya que expone abstracciones para definir redes de contenedores, volúmenes para archivos sistemas, configuraciones de recursos, etc.

Sin embargo, todavía se necesita una herramienta para:

- Tomar una especificación y asignar contenedores a las máquinas.
- Lidiar con actualizaciones/retrocesos/la naturaleza en constante cambio del sistema.
- Responder a fallas, como caídas de contenedores.

Este conjunto de problemas se relaciona con la orquestación de un sistema distribuido construido sobre un conjunto de contenedores (posiblemente transitorios o en constante cambio), y la gente ha construido algunos sistemas realmente milagrosos para resolver este problema.

Uno de estos, es **Kubernetes**, del cual hablaremos más a detalle en el [Módulo 07](../07-infraestructura-como-codigo/README.md).

<!-- Referencias -->
[kernel]: ../../referencias/enlaces#kernel
[namespaces]: ../../referencias/enlaces#namespaces
[LXC]: ../../referencias/enlaces#lxc
[Google]: ../../referencias/enlaces#google
[cgroups]: ../../referencias/enlaces#cgroups
