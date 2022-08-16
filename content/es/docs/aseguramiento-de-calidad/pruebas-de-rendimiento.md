---
title : "Pruebas de rendimiento"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "aseguramiento-de-calidad"
weight: 1004
toc: true
---

La prueba de rendimiento es una forma de prueba de software que se enfoca en cómo un sistema que ejecuta el sistema se desempeña bajo una carga particular. No se trata de encontrar errores o defectos de software. Diferentes tipos de pruebas de rendimiento miden de acuerdo con puntos de referencia y estándares. Las pruebas de rendimiento brindan a los desarrolladores la información de diagnóstico que necesitan para eliminar los cuellos de botella.

## Tipos de pruebas de rendimiento

### Pruebas de carga

Las pruebas de carga miden el rendimiento del sistema a medida que aumenta la carga de trabajo. Esa carga de trabajo podría significar usuarios o transacciones concurrentes. El sistema se monitorea para medir el tiempo de respuesta y el poder de permanencia del sistema a medida que aumenta la carga de trabajo. Esa carga de trabajo cae dentro de los parámetros de las condiciones normales de trabajo.

### Pruebas de estrés

A diferencia de las pruebas de carga, las pruebas de estrés, también conocidas como pruebas de fatiga, están destinadas a medir el rendimiento del sistema fuera de los parámetros de las condiciones normales de trabajo. El software recibe más usuarios o transacciones que se pueden manejar. El objetivo de las pruebas de estrés es medir la estabilidad del software. ¿En qué punto falla el software y cómo se recupera el software de la falla?

### Prueba de picos

La prueba de picos es un tipo de prueba de estrés que evalúa el rendimiento del software cuando las cargas de trabajo aumentan sustancialmente de forma rápida y repetida. La carga de trabajo está más allá de las expectativas normales por períodos cortos de tiempo.

### Pruebas de resistencia

La prueba de resistencia, también conocida como prueba de remojo, es una evaluación de cómo funciona el software con una carga de trabajo normal durante un período de tiempo prolongado. El objetivo de las pruebas de resistencia es comprobar si hay problemas en el sistema, como fugas de memoria. (Se produce una fuga de memoria cuando un sistema no puede liberar la memoria descartada. La fuga de memoria puede afectar el rendimiento del sistema o provocar que falle).

### Pruebas de escalabilidad

Las pruebas de escalabilidad se utilizan para determinar si el software está manejando de manera efectiva las cargas de trabajo cada vez mayores. Esto se puede determinar aumentando gradualmente la carga del usuario o el volumen de datos mientras se supervisa el rendimiento del sistema. Además, la carga de trabajo puede permanecer en el mismo nivel mientras se cambian los recursos, como las CPU y la memoria.

### Pruebas de volumen

Las pruebas de volumen determinan qué tan eficientemente funciona el software con grandes cantidades proyectadas de datos. También se conoce como prueba de inundación porque la prueba inunda el sistema con datos.

## Problemas comunes observados en pruebas de rendimiento

Durante las pruebas de rendimiento del software, los desarrolladores buscan síntomas y problemas de rendimiento. Los problemas de velocidad (respuestas lentas y tiempos de carga prolongados, por ejemplo) a menudo se observan y abordan. Se pueden observar otros problemas de rendimiento:

- **Cuello de botella**: esto ocurre cuando el flujo de datos se interrumpe o se detiene porque no hay suficiente capacidad para manejar la carga de trabajo.
- **Escalabilidad deficiente**: si el software no puede manejar la cantidad deseada de tareas simultáneas, los resultados podrían retrasarse, los errores podrían aumentar o podría ocurrir otro comportamiento inesperado que afecte:
  - Uso del disco
  - Uso de CPU
  - Fugas de memoria
  - Limitaciones del sistema operativo
  - Mala configuración de red
- **Problemas de configuración del software**: a menudo, la configuración no se establece en un nivel suficiente para manejar la carga de trabajo.
- **Recursos de hardware insuficientes**: las pruebas de rendimiento pueden revelar limitaciones de memoria física o CPU de bajo rendimiento.

## Métricas de rendimiento

Entre las métricas utilizadas en las pruebas de rendimiento, a menudo se utilizan las siguientes:

- **Tiempo de respuesta**: Tiempo total para enviar una solicitud y obtener una respuesta.
- **Tiempo de espera**: También conocida como latencia promedio, esto les dice a los desarrolladores cuánto tiempo se tarda en recibir el primer byte después de que se envía una solicitud.
- **Tiempo medio de carga**: La cantidad promedio de tiempo que lleva entregar cada solicitud es un indicador importante de la calidad desde la perspectiva del usuario.
- **Tiempo de respuesta pico**: Esta es la medida de la mayor cantidad de tiempo que lleva cumplir con una solicitud. Un tiempo de respuesta máximo que es significativamente más largo que el promedio puede indicar una anomalía que creará problemas.
- **Tasa de error**: Este cálculo es un porcentaje de solicitudes que dan como resultado errores en comparación con todas las solicitudes. Estos errores generalmente ocurren cuando la carga excede la capacidad.
- **Usuarios concurrentes**: Esta es la medida de carga más común: cuántos usuarios activos en cualquier momento. También conocido como tamaño de carga.
- **Solicitudes por segundo**: Cuántas solicitudes se manejan.
- **Transacciones aprobadas/fallidas**: Una medida del número total de solicitudes exitosas o fallidas.
- **Rendimiento**: Medido en kilobytes por segundo, el rendimiento muestra la cantidad de ancho de banda utilizado durante la prueba.
- **Utilización de la CPU**: Cuánto tiempo necesita la CPU para procesar las solicitudes.
- **Utilización de la memoria**: Cuánta memoria se necesita para procesar la solicitud.
