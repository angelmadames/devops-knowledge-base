---
title : "Monitoreo de infraestructura"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "monitore-y-alertas"
weight: 902
toc: true
---

El monitoreo de la infraestructura es el proceso de recopilar y analizar datos de la **infraestructura**, **los sistemas** y los **procesos de TI**. Con esos datos, es posible la toma de decisiones que beneficien los resultados de negocio esperados y el proceso de entrega de valor en sí.

El monitoreo de la infraestructura recopila todos los datos necesarios para proporcionar una imagen completa de *la disponibilidad*, *el rendimiento* y *la eficiencia* de los recursos.

## Misión crítica

A medida que las empresas dependen más de las aplicaciones y los servicios para sus flujos de ingresos, el rendimiento del sistema se convierte en una misión crítica tanto para las personas (**usuario**) como para las organizaciones (**proveedor**).

El monitoreo de la infraestructura garantiza que las organizaciones puedan responder a los problemas de manera proactiva, evitando la pérdida de **tiempo** y **dinero**.

Esto hace que el monitoreo de la infraestructura sea la esencia de la misión crítica, brindando estas capacidades clave:

- La capacidad de optimizar los requerimientos comerciales y la experiencia del usuario.
- La flexibilidad y escalabilidad para ingerir datos de una variedad de fuentes y para manejar picos de tráfico planificados y no planificados.
- La capacidad de detectar y alertar sobre interrupciones, utilización de recursos y degradaciones del rendimiento para minimizar el tiempo de inactividad y aumentar la eficiencia operativa.
- La capacidad de identificación de la causa raíz para determinar con precisión dónde se origina un problema en la infraestructura o aplicación.
- La capacidad de profundizar en componentes de infraestructura defectuosos específicos y desencadenar la remediación.

## Funcionamiento

El monitoreo de infraestructura rastrea:

- la disponibilidad,
- el rendimiento y la utilización de recursos de hosts,
- contenedores, entre otros.

La forma usual de habilitar el monitoreo de infraestructura suele ser a través de la instalación de un software, denominado **agente**, en los **hosts**.

> Los **hosts** pueden incluir servidores físicos (servidores bare metal), o máquinas virtuales.

El **agente** recopila métricas de infraestructura de los **hosts** y envía esos datos a una plataforma de monitoreo para su *análisis* y *visualización*. El monitoreo de la infraestructura brinda visibilidad sobre el estado las aplicaciones, lo que permite garantizar que los servicios críticos estén disponibles para los usuarios y que funcionen como se esperan.

## Monitoreo en entornos dinámicos o efímeros

Tradicionalmente, las organizaciones administraban sus propios servidores físicos en sus instalaciones, que tenían direcciones IP fijas. En la nube, lo servidores se pueden activar o reemplazar en demanda.

La adopción de la infraestructura en la nube ha cambiado fundamentalmente la forma en que funciona el monitoreo de la infraestructura. En entornos tan dinámicos, a menudo se necesita monitorear componentes de infraestructura efímeros en lugar de hosts individuales estáticos.

De igual forma, también se pudiese necesitar información sobre subconjuntos significativos de la infraestructura, como hosts en una región específica. Debido a esto, existen herramientas de monitoreo nativas en la nube que se adaptan bastante bien a estas necesidades. Conversaremos sobre éstas más adelante.

## Métricas

El monitoreo, como se ha podido notar, depende mucho de la recolección de datos, de su análisis y visualización. Por tanto, existen unas métricas comunes que se buscan a la hora de efectuar estos análisis ya que no toda la data es útil a menos que cumpla con un propósito o se pueda tomar decisiones en base a ella.

A continuación listamos las métricas más comunes que las plataformas de monitoreo de infraestructura y sus operadores buscan conocer:

- **Utilización de CPU**
- **Utilización de memoria (RAM)**
- **Uso de almacenamiento**

Expandamos un poco más en cada una...

### Utilización de CPU

[La utilización de la CPU][CPU utilization] se refiere al uso de los recursos de procesamiento de una computadora, o la cantidad de trabajo manejado por una CPU. La utilización real de la CPU varía según la cantidad y el tipo de procesos administrados.

Un alto consumo de la utilización generalmente es un síntoma de una CPU bajo mucha carga de trabajo, lo que puede ocasionar los siguientes síntomas:

- La aplicación no responde con rapidez a la solitud de los usuarios
- La aplicación lanza errores de "tiempos de espera agotados" (`timeouts`)
- La aplicación no es accesible por los usuarios

En sentido general, esta métrica debe permanecer en porcentajes bajos para considerarla como **saludable**.

### Utilización de memoria

La métrica de [uso de memoria][Memory utilization] es una estadística de uso promedio derivada del porcentaje de memoria disponible en uso en un momento dado, promediado durante el intervalo de informe.

Cuando un host utiliza el 100% de su memoria disponible, ya no puede aceptar ni atender más solicitudes.

### Uso de almacenamiento

Indica la cantidad de disco que utiliza el host para almacenar archivos, imágenes y otros contenidos. Los elementos se pueden copiar del almacenamiento a la memoria a corto plazo cuando se necesitan para ejecutar un programa. Cuando un host se queda sin espacio en disco, puede perder datos o la aplicación subyacente puede fallar.

## Casos de uso de monitoreo de infraestructura

Las aplicaciones y los servicios de una organización solo pueden funcionar bien para los usuarios cuando la infraestructura está en buen estado. El monitoreo de la infraestructura permite detectar y prevenir problemas, lo que minimiza el tiempo de inactividad y la degradación del servicio para los usuarios.

Los equipos de operaciones, los ingenieros de DevOps y los ingenieros de confiabilidad de sitio (SRE) generalmente confían en el monitoreo de la infraestructura para ayudarlos a:

- **Solucionar problemas de rendimiento:** El monitoreo de la infraestructura se usa comúnmente para evitar que los incidentes se conviertan en *interrupciones*. Una herramienta de monitoreo de infraestructura puede mostrar qué hosts, contenedores u otros componentes fallaron o experimentaron latencia durante un incidente. Cuando ocurre una interrupción, se puede determinar qué recursos fueron responsables.
- **Optimizar el uso de la infraestructura:** El monitoreo de la infraestructura también se puede utilizar para reducir los costos de manera *proactiva*. Por ejemplo, si varios servidores están sobreaprovisionados o inactivos, se puede retirarlos y ejecutar las cargas de trabajo asociadas en menos hosts.
- **Previsión de requerimientos de aplicación** Las organizaciones pueden predecir el consumo futuro de recursos al revisar las métricas históricas de la infraestructura. Por ejemplo, si ciertos hosts se aprovisionaron de manera insuficiente durante el lanzamiento de un producto reciente, puede configurar más CPU y memoria en el futuro durante eventos similares para reducir la tensión en los sistemas clave y reducir la probabilidad de interrupciones que drenan los ingresos.

## Retos de el monitoreo de infraestructura

Dada la complejidad de los sistemas de muchas empresas, puede ser un desafío encontrar una herramienta de monitoreo de infraestructura adecuada, especialmente cuando una organización depende de la nube.

### Acceso a recursos de infraestructura en la nube

Las herramientas de monitoreo de infraestructura tradicionales se utilizan principalmente en entornos locales y tienden a centrarse en hosts individuales. Este enfoque *"centrado en el host"* funciona cuando el número de hosts y las direcciones IP son estáticos, pero no es adecuado para monitorear **contenedores**, **funciones sin servidor** y otros **componentes nativos de la nube** que aumentan o reducen (*en cantidad*) automáticamente en respuesta a la demanda.

Por ejemplo, en una arquitectura sin servidor, ni siquiera puede acceder a los servidores que ejecutan su código, por lo que **no hay ningún lugar para instalar un agente de monitoreo.**

La mayoría de las herramientas tradicionales no se integran con los servicios en la nube porque no pueden autenticar el acceso a las métricas basadas en la nube con una [API]. Incluso si existe una integración limitada, requieren que ingrese [SSH] manualmente a los servidores en la nube para recuperar las métricas de la infraestructura, lo que requiere mucho **tiempo** y **experiencia**.

### Visibilidad sobre monitoreo de aplicación

Si se usan diferentes herramientas de monitoreo para infraestruc†ura y aplicación, es posible que no se llegue a un acuerdo sobre sobre qué problemas de rendimiento solucionar y cómo solucionarlos. Particularmente si existe una clara división cultural entre desarrollo y operaciones.

> Los equipos pueden trabajar juntos de manera aún más fluida si la herramienta correlaciona las métricas de rendimiento de la infraestructura y la aplicación.

Para muchas organizaciones, el monitoreo de la infraestructura es solo una parte de una solución de monitoreo completa.

Para solucionar problemas de manera efectiva, a menudo necesita ver los datos de monitoreo de la infraestructura junto con los datos de sus aplicaciones, red y otros recursos de infraestructura. Una solución de monitoreo integral brindará contexto sobre la causa raíz de un problema, ya sea que se trate de **un host que consumió demasiados recursos**, **un error en el código de su aplicación**, **un problema de conectividad** o cualquier otra cosa.

## Beneficios de monitoreo de infraestructura

Entre los beneficios principales del monitore de infraestructura podemos destacar:

- Medición precisa sobre cumplimiento de los acuerdos de nivel de servicio (SLA) y disponibilidad
- Aceleración de el análisis de la causa raíz de problemas identificados
- Mejora en los esfuerzos proactivos de resolución de incidentes
- Análisis de las tendencias de rendimiento de manera continua
- Validación de despliegues de aplicación
- Observabilidad de extremo a extremo con automatización integrada

## Datos de observabilidad

El monitoreo de su infraestructura **solo brindará información útil** si tiene las **herramientas adecuadas con acceso a la información correcta**. Debido a esto, existen diferentes fuentes de datos que comúnmente aporta un valor importante a la observabilidad:

> El monitoreo debe siempre tener un propósito u objetivo a cumplir, estos datos solo representan una base al cumplimiento de necesidades comunes. Para cualquier organización, esta lista puede verse **reducida** o **expandida**, *dependiendo de su realidad y objetivos de negocio*.

- **Métricas**: los *datos cuantitativos* son especialmente útiles para crear visualizaciones e identificar patrones en el rendimiento en función del tiempo.
- **Registros de eventos (logs)**: cada sistema y servicio genera registros de eventos, que pueden brindar información sobre lo que *está sucediendo* e *indicios de cómo solucionar problemas*.
- **Metadatos**: la información adicional, como *detalles de topología*, *espacios de nombres* y *datos de prioridad*, ayudan a comprender la importancia y el impacto de los eventos a medida que interactúan con otros componentes de la infraestructura.
- **Comportamiento del usuario (datos de [UX])**: Los datos de la experiencia del usuario, como los *tiempos de carga de la página* y *la latencia*, son vitales para relacionar el comportamiento de la infraestructura con el comportamiento del usuario dentro de la aplicación o aplicaciones.
- **Telemetría de código abierto**: hay muchas opciones de código abierto diseñadas para ayudarlo a lograr una mejor observabilidad en todo su entorno. Estas herramientas estándar de la industria incluyen *[OpenTelemetry]*, *[Prometheus]* y *[StatsD]*.
- **Integraciones en la nube**: la infraestructura moderna incluye infraestructura en la nube, por lo que las integraciones en la nube, pueden ser fuentes útiles de datos de observabilidad para el monitoreo de la infraestructura.

## Mejores prácticas

Como toda herramienta, servicio o tecnología, existen buenas y malas prácticas. De acuerdo con la experiencia de muchos, ésta es la lista de las mejores prácticas implementadas más comúnmente en cualquier tipo de monitoreo de infraestructura:

- **automatización**: las herramientas de monitoreo de infraestructura que cuentan con capacidades de automatización son vitales para obtener *observabilidad* completa de extremo a extremo en toda la pila de aplicaciones.
- **Alertas específicas**: cuando las alertas son específicas, es menos probable que den emitan resultados falsos positivos.
- **Priorización de alertas**: se debe *organizar y priorizar las notificaciones* para que no se pierdan las alertas más importantes, en particular las que informan impactos en la experiencia del usuario.
- **Paneles de visualización orientado a roles**: la data recolectada por el monitoreo de ifnraestructura debe habilitar una variedad de paneles personalizados (*dashboards*) que varios equipos dentro de la organización encuentren útiles para dar seguimiento a los [KPI] que son importantes para ellos.
- **Pruebas al monitoreo**: debemos asegurarnos de que las herramientas de monitoreo de infraestructura funcionen como se espera antes de comenzar a confiar en ellas día a día. Intencionalmente hacer que un sistema falle y validar que el monitoreo captura este evento y envía las alertas adecuadas es un buen punto de partida.
- **Revisión periódica de las métricas**: a medida que cambian los objetivos de negocio y evoluciona la infraestructura, también lo harán las métricas y los [KPI] que necesita monitorear.

<!-- Referencias -->
[CPU utilization]: ./../referencias/enlaces#cpu-utilization
[Memory utilization]: ./../referencias/enlaces#memory-utilization
[API]: ./../referencias/enlaces#api
[SSH]: ./../referencias/enlaces#ssh
[OpenTelemetry]: ./../referencias/enlaces#opentelemetry
[Prometheus]: ./../referencias/enlaces#prometheus
[StatsD]: ./../referencias/enlaces#statsd
[KPI]: ./../referencias/enlaces#kpi
[UX]: ./../referencias/enlaces#ux
