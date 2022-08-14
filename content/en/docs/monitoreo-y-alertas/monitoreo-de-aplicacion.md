---
title : "Monitoreo de aplicación"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "monitore-y-alertas"
weight: 903
toc: true
---

El monitoreo de aplicaciones es el proceso de medir el **rendimiento**, la **disponibilidad** y **[la experiencia del usuario][UX]** de las aplicaciones y utilizar estos datos para identificar y resolver los problemas de las aplicaciones antes de que afecten a los clientes.

El monitoreo de aplicaciones es difícil debido a la naturaleza dinámica de la nube. Los enfoques modernos más efectivos incorporan el monitoreo completo de la pila desde la experiencia del usuario de frontend hasta la infraestructura de backend para brindar una visibilidad completa del rendimiento de la aplicación.

## Herramientas de monitoreo de aplicaciones

Las herramientas de monitoreo de aplicaciones, cuyo proceso también es conocido como Application Performance Monitoring (APM) [en español, gestión del rendimiento de aplicaciones], proporcionan un medio visual para ver cómo se conectan los eventos a través del mapeo de dependencias y flujos.

El monitoreo de aplicaciones se puede lograr mediante herramientas dedicadas para monitorear aplicaciones, o mediante la recopilación y el análisis de registros mediante herramientas de administración de registros.

Con el monitoreo de aplicaciones, el objetivo principal es maximizar la disponibilidad y brindar a los clientes la mejor experiencia posible.

> Las herramientas de monitoreo de aplicaciones brindan alertas para eventos de anomalías en vivo y, a través del rastreo distribuido, brindan un medio para ver qué eventos forman una cadena causal que los llevó a través de múltiples servicios.

### Funciones de las herramientas de monitoreo de aplicaciones

Las principales funciones de las herramientas de monitorización de aplicaciones son:

- **Observar los componentes de la aplicación:** los componentes pueden incluir servidores, bases de datos y colas de mensajes o capturas.
- **Proporcionar alertas y paneles de aplicaciones:** los paneles brindan una descripción general, las alertas dirigen la atención a problemas específicos.
- **Detección de anomalías:** puede variar desde la simple detección de umbral hasta el reconocimiento avanzado de patrones de aprendizaje automático.
- **Seguimiento distribuido:** seguimiento de cómo un evento se conecta a través de múltiples nodos para detectar los orígenes de los errores.
- **Mapeo de dependencia y flujo:** una representación visual de cómo viajan las solicitudes entre servicios.

## Application Performance Monitoring (APM)

Se puede hacer referencia a **APM** como:

- Monitoreo del rendimiento de la aplicación
- Gestión del rendimiento de la aplicación
- Monitoreo de aplicaciones
- Rendimiento de la aplicación
- Monitoreo del rendimiento

El enfoque de la monitoreo del rendimiento de la aplicación está en **métricas** y **medidas específicas**.

## ¿Por qué se necesita APM?

Todos los días los usuarios comunes usan aplicaciones para:

- comprar,
- transmitir programas de TV y películas,
- conectarse a las redes sociales,
- administrar las finanzas y,
- trabajar.

En la era de trabajar desde casa, los usuarios confían más que nunca en estas aplicaciones para realizar actividades de su vida diaria. Cuando una aplicación *falla*, *tarda en cargarse* o *no se carga en absoluto*, los usuarios se sienten frustrados, lo que puede hacer que la empresa **sufra daños en la marca o pierda ingresos**. Cuando una aplicación comercial interna comienza a fallar, la empresa también puede ver reducida la productividad de los empleados.

Sin embargo, a los equipos digitales a menudo les resulta difícil encontrar la causa raíz de un problema de rendimiento de la aplicación. Las causas pueden abarcar un gran variedad:

- errores de codificación,
- ralentizaciones de la base de datos,
- problemas de alojamiento,
- rendimiento de la red,
- conflicto con el sistema operativo o el dispositivo específico que se utiliza, entre otros.

Las aplicaciones modernas, como las aplicaciones móviles, los sitios web y las aplicaciones comerciales, pueden parecer simples en la superficie, pero en realidad son muy complejas. Millones de líneas de código componen estas aplicaciones, e incluyen cientos de servicios digitales interconectados y soluciones de código abierto, y se ejecutan en entornos en contenedores alojados en múltiples servicios en la nube.

Los equipos digitales usan herramientas de **APM** para ver y abordar las muchas variables que pueden afectar el rendimiento de una aplicación. Sin estas herramientas, los equipos luchan por resolver los numerosos problemas que pueden surgir, lo que aumenta la probabilidad de que los clientes se sientan frustrados por la mala experiencia y abandonen la aplicación por completo.

### Funcionalidades de APM

**APM** se ha expandido rápidamente para abarcar una amplia gama de tecnologías y casos de uso.

Según [Gartner], "el monitoreo del rendimiento de las aplicaciones es un conjunto de software que comprende el monitoreo de la experiencia digital (DEM), el descubrimiento, el seguimiento y el diagnóstico de aplicaciones, y la inteligencia artificial especialmente diseñada para las operaciones de TI".

El [Magic Quadrant][Magic Quadrant] (cuadrante mágico)  de [Gartner] para [el Monitoreo del Desempeño de Aplicaciones][Application Performance Monitoring Magic Quadrant], un informe líder en la industria sobre **APM**, brinda una definición clara de las capacidades principales de **APM** a medida que han madurado.

Estas capacidades establecen el estándar para las soluciones APM modernas:

- **Detección y mapeo automáticos de la aplicación y sus componentes de infraestructura** para mantener la conciencia en tiempo real en entornos dinámicos
- **Observabilidad de extremo a extremo del comportamiento transaccional** HTTP/S completo de una aplicación para comprender el efecto en los resultados comerciales y la experiencia del usuario
- **Monitoreo de aplicaciones móviles y de escritorio en navegadores móviles y de escritorio** para rastrear la experiencia del usuario en todas las plataformas
- **Análisis de la causa raíz y el impacto de los problemas de rendimiento de las aplicaciones** y los resultados comerciales para una resolución de incidentes más rápida y confiable
- **Integración y automatización con herramientas de gestión de servicios y fuentes de terceros** para seguir el ritmo de una infraestructura en expansión y evolución
- **KPI comerciales y análisis del viaje del usuario** (por ejemplo, iniciar sesión para pagar) para optimizar las experiencias de los usuarios y proporcionar transparencia sobre cómo los cambios impactan en los KPI
- **Monitoreo de puntos finales** para comprender cómo las aplicaciones móviles impactan en los dispositivos finales e identificar problemas con esos dispositivos
- **Monitoreo de infraestructura de escritorio virtual (VDI)** para maximizar la productividad de los empleados que utilizan VDI

### Beneficios de APM

Debido a que brinda a las empresas una mayor visibilidad e inteligencia sobre el rendimiento de las aplicaciones y sus dependencias, **APM** ofrece una lista impresionante y en expansión de beneficios técnicos y comerciales.

#### Beneficios técnicos

Los equipos de negocios, operaciones, y desarrollo pueden esperar disfrutar de una serie de beneficios prácticos al adoptar prácticas y herramientas de APM, tales como:

- Mayor estabilidad de la aplicación y tiempo de actividad
- Reducción del número de incidentes de rendimiento
- Resolución más rápida de los problemas de rendimiento
- Lanzamientos de software más rápidos y de mayor calidad
- Mejora de la utilización de la infraestructura

#### Beneficios comerciales concretos

Los que están en la sala de juntas tienen tanto que ganar con la adopción de soluciones APM como los que están al frente de los esfuerzos de DevOps. Los beneficios comerciales incluyen:

- Mejora de la productividad operativa y del desarrollador
- Mayor tiempo dedicado a la innovación.
- Mejores experiencias de usuario
- Aumento de los ingresos
- Costos operativos reducidos
- Aumento de las tasas de conversión

#### Beneficios comerciales blandos

Los usuarios de APM desde hace mucho tiempo también informan que APM ha brindado a sus organizaciones algunas ventajas inesperadas pero impactantes.

El más destacado entre estos aspectos positivos es la capacidad de colaborar más fácilmente. Los nuevos conocimientos y la inteligencia confiable que ofrece una buena solución APM permite que los equipos de toda la organización tengan más confianza. A su vez, esta fuente única de inteligencia confiable en la que todas las partes pueden estar de acuerdo ayuda a los equipos de aplicaciones, operaciones y desarrollo a alinearse más rápido y más fácilmente cuando surgen problemas y a trabajar juntos de manera más efectiva.

Una colaboración más efectiva ayuda a los equipos a resolver problemas más rápido, lo que puede hacer que las salas de guerra frustrantes sean cosa del pasado. Como resultado, los líderes ven una mayor satisfacción laboral entre los miembros de su equipo, lo que lleva a una mayor retención del personal.

### Debilidades de APM

Las fuentes persistentes de dificultad para las herramientas APM:

- **Cambio continuo**: el modelo de entrega continua ofrece un mayor rendimiento en general, pero para el monitoreo, dificulta la determinación del contexto.
- **Complejidad**: millones de puntos de datos se distribuyen en una red cada vez más compleja de operaciones, relaciones y dependencias.
- **Datos limitados**: las herramientas solo de APM pueden perder los datos operativos y de configuración que se encuentran en los registros que no son de aplicaciones.
- **Marcas de tiempo no sincronizadas**: no incluir la configuración correcta o las dependencias de la plataforma dentro del análisis del marco de tiempo conduce a una comprensión incompleta.
- **Soluciones de monitoreo en silos**: los datos separados en varias soluciones ralentizan la detección de las causas raíz.

## Retos

A medida que aumenta el número de aplicaciones con el crecimiento de los microservicios y la migración a entornos de nube dispares, mantener **la observabilidad se ha vuelto más difícil con el tiempo.**

Sin el monitoreo centralizado, otras herramientas de monitoreo, como el monitoreo del rendimiento de la red, el monitoreo del servidor y el monitoreo del usuario, pueden recopilar un conjunto limitado de métricas en lugar de una herramienta de monitoreo de aplicaciones dedicada como APM, lo que da como resultado una imagen incompleta.

Las organizaciones que operan con un modelo de entrega continua tienen más dificultades para capturar y comprender las dependencias dentro de un entorno de aplicación. Cuando las herramientas APM se han adaptado para satisfacer las necesidades de un entorno dinámico, pueden sacrificar la capacidad de responder a incidentes en tiempo real.

<!-- Referencias -->
[UX]: ./../referencias/enlaces#ux
[Gartner]: ./../referencias/enlaces#gartner
[Magic Quadrant]: ./../referencias/enlaces#magic-quadrant
[Application Performance Monitoring Magic Quadrant]: ./../referencias/enlaces#application-performance-monitoring-magic-quadrant
