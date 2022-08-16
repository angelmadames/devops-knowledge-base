---
title : "Estrategias de despliegue"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "entrega-continua"
weight: 704
toc: true
---

Las estrategias de despliegue son prácticas utilizadas para cambiar o actualizar una instancia en ejecución de una aplicación, o en otras palabras, el comportamiento del lanzamiento.

Las siguientes secciones explicarán seis (6) estrategias de despliegue diferentes. A modo resumen, serán:

- Reemplazo
- Progresiva
- Recreación
- Canario
- Azul-verde
- Sombra
- Pruebas A/B

## Estrategias

### Reemplazo

En la estrategia de reemplazo, o como es frecuentemente conocida, "*despliegue básico*", todos los nodos dentro de un entorno de destino se actualizan al mismo tiempo con una nueva versión de servicio o artefacto. Debido a esto, los despliegues básicos no son a prueba de interrupciones y ralentizan los procesos o estrategias de reversión.

De todas las estrategias de despliegue compartidas, es la más arriesgada.

Las características que la destacan son:

- Simplicidad
- Rapidez
- Económica

Dentro de sus debilidades:

- Es la más riesgosa
- No es a prueba de interrupciones
- No permite reversiones de forma fácil

La estrategia de reemplazo es *ideal* para los siguientes escenarios:

1. La aplicación no representa un riesgo crítico para la misión o ingresos del negocio
2. Se realiza el despliegue en un ambiente menor, no productivo. Es decir, ambientes de prueba y validación
3. Hay restricciones de costos en las etapas iniciales del proyecto

### Progresiva

Una despliegue progresivo reemplaza lentamente las instancias de la versión anterior de una aplicación con instancias de la nueva versión de la aplicación. Por lo general, una despliegue progresivo espera a que las nuevas instancias estén listas para servir tráfico a través de una verificación de preparación antes de reducir el volumen de las versiones antiguas. Si se produce un problema importante, se puede cancelar el despliegue progresivo y asegurar la disponibilidad del servicio.

Las características que la destacan son:

- Simplicidad
- Capacidad de reversión automática
- Menor riesgo de impacto a la disponibilidad

Dentro de sus debilidades:

- Requiere servicios de orquestación que admitan versiones nuevas y antiguas de una instancia
- Ralentiza el tiempo de despliegue debido a las verificaciones que deben suceder
- La reversión de estructuras de base de datos puede representar un reto técnico

La estrategia progresiva es *ideal* para los siguientes escenarios:

1. No debe existir tiempo de inactividad durante la actualización del aplicaicón
2. La aplicación es compatible con la ejecución en paralelo de versiones distintas

> Un despliegue progresivo significa que tienen versiones antiguas y nuevas de la aplicación ejecutándose al mismo tiempo. Esto generalmente requiere que su aplicación maneje la **[compatibilidad N-1][N-1 Compatibility]**.

### Recreación

La estrategia de recreación es una forma rudimentaria en la que la versión anterior debe cerrarse antes de desplegar la versión más nueva. Esta técnica implica que se espera un tiempo de inactividad de despliegue del servicio y se ejecuta un ciclo de reinicio completo. Funciona en una infraestructura limitada donde la disponibilidad de la aplicación no es una preocupación importante.

En resumen, elimina la versión anterior y luego despliegue la versión nueva.

Las características que la destacan son:

- Simplicidad
- Facilidad de despliegue
- No hay necesidad de mantener la **[compatibilidad N-1][N-1 Compatibility]**

Dentro de sus debilidades:

- Impacto a los usuarios es considerable
- El tiempo de baja de las aplicaciones puede aumentar dependiendo de la capacidad de reinicio y escritura/lectura de disco

### Canario

La estrategia **canario** lanza una aplicación o servicio de forma incremental a un subconjunto de usuarios. Toda la infraestructura en un entorno de destino se actualiza en pequeñas fases (por ejemplo, *2%*, *25%*, *75%*, *100%*). Una versión canaria es la menos propensa a los riesgos, en comparación con todas las demás estrategias debido a este control.

Las características que la destacan son:

- Permite realizar pruebas en producción con usuarios reales y casos de uso y comparar diferentes versiones de servicios una al lado de la otra.
- Es rápido y seguro activar una reversión a una versión anterior de una aplicación.

Dentro de sus debilidades:

- Implica pruebas en producción y las implementaciones necesarias
- Su implementación puede ser **compleja**: la verificación o prueba manual puede llevar tiempo, y el monitoreo y la instrumentación necesarios para la prueba en producción pueden implicar investigación adicional

### Azul-verde

Los despliegues **azul-verde** implican ejecutar dos versiones de una aplicación al mismo tiempo y mover el tráfico de la versión en producción (la versión **verde**) a la versión más nueva (la versión **azul**).

Las características que la destacan son:

- Se tiene capacidad de retroceso de forma instantánea
- Menor tiempo de baja garantizado

Dentro de sus debilidades:

- Altos costos de infraestructura
- Lanzamiento de actualizaciones pequeñas puede no ser costo-efectivo

La estrategia azul-verde es *ideal* para los siguientes escenarios:

- Se puede tener una infraestructura grande y escalable (en términos técnicos y económicos)
- Se quiere despliegues sin tiempo de baja o inactividad
- La aplicación y base de datos tienen **[compatibilidad N-1][N-1 Compatibility]**.

### Sombra

La estrategia **sombra** es aquella en la que la nueva versión está disponible junto con la versión anterior, pero una copia o versión bifurcada del tráfico de la versión anterior se envía a la nueva versión para pruebas de producción.

Esta es una estrategia de despliegue bastante compleja, ya que durante el ciclo de despliegue, se debe mantener dos versiones y evitar que el tráfico de usuarios bifurcado genere solicitudes duplicadas.

En resumen, se ejecuta una aplicación ficticia junto con la real. La aplicación ficticia recibe una copia del tráfico de producción real para probar el rendimiento en un escenario realista.

Las características que la destacan son:

- Las pruebas realizadas permiten que la aplicación tenga un rendimiento y estabilidad bastante certero y predecible

Dentro de sus debilidades:

- Altos costos de infraestructura
- Requiere imitar servicios de terceros sensitivos como enlaces de pago
- Es una implementación compleja
- No se basa en pruebas que simulen compartimiento real de usuarios

La estrategia sombra es *ideal* para los siguientes escenarios:

- Se puede tener una infraestructura grande y escalable (en términos técnicos y económicos)
- Se necesita que la aplicación se pruebe con tráfico real de producción para rendimiento y estabilidad
- Bajo rendimiento de una nueva versión es inaceptable

### Pruebas A/B

La estrategia de despliegue de **pruebas A/B** se basa en datos estadísticos del mundo real para decidir sobre una despliegue o una reversión. Consiste en enrutar un subconjunto de usuarios a una nueva característica o funcionalidad bajo condiciones específicas y luego recopilar datos sobre este conjunto de usuarios para compararlos con el promedio general de la versión anterior. Sin embargo, esta estrategia tiene sus beneficios, si se combina con una despliegue canario, puede mejorar aún más la confiabilidad.

En resumen, pruebe la nueva función con un conjunto específico de usuarios (no al azar), sino en función de segmentos de parámetros comunes de los usuarios, como la ubicación geográfica o el tipo de dispositivo.

Las características que la destacan son:

- Se pueden probar múltiples versiones en paralelo
- Se puede tomar decisiones con datos estadísticos reales
- Provee resultados certeros sobre comportamiento de usuarios

Dentro de sus debilidades:

- Se necesita de un balanceador de carga inteligente (generalmente costoso)
- La complejidad del proceso es alta

La estrategia pruebas A/B es *ideal* para los siguientes escenarios:

- Se tiene una aplicación con **[compatibilidad N-1][N-1 Compatibility]**.
- Se quiere tener control granular sobre la distribución de tráfico de la aplicación

## Conclusiones

Hay múltiples estrategias de despliegue disponibles en el mundo de DevOps hoy en día y se tiene que elegir y tomar una decisión informada sobre lo que se adapta mejor a las necesidades del momento. Algunas estrategias pueden ser costosas para usar en entornos de prueba, mientras que los costos valen la pena en una implementación de producción.

<!-- Referencias -->
[N-1 Compatibility]: ../../referencias/enlaces#n-1-compatibility
