---
title : "Entrega continua (CD)"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "entrega-continua"
weight: 702
toc: true
---

La entrega continua es la capacidad de introducir cambios de todo tipo (incluidas nuevas funciones, cambios de configuración, correcciones de errores y experimentos) en producción o en manos de los usuarios, de forma segura, rápida y sostenible.

Nuestro objetivo es hacer que los despliegues, ya sea de un sistema distribuido a gran escala, un entorno de producción complejo, un sistema integrado o una aplicación, sean asuntos rutinarios y predecibles que se puedan realizar bajo demanda.

Logramos todo esto asegurándonos de que nuestro código esté siempre en un estado desplegable, incluso frente a equipos de miles de desarrolladores que realizan cambios a diario. De este modo, eliminamos por completo las fases de integración, prueba y endurecimiento que tradicionalmente seguían al "desarrollo completo", así como las congelaciones de código.

## ¿Por qué entrega continua?

A primera instancia, se asume que si quieres desplegar software con más frecuencia, debemos aceptar niveles bajos de estabilidad y confiabilidad. Sin embargo, [varias investigaciones y recolección de datos demuestran lo contrario][1]. Realizar entrega continua (o despliegues frecuentes) resulta, de manera proporcional, en mayor estabilidad de los sistemas manejados debido a que los errores se capturan de igual manera en mayor frecuencia de forma temprana.

## Beneficios

Las prácticas en el corazón de la entrega continua nos ayudan a lograr varios beneficios importantes:

- **Lanzamientos de bajo riesgo**. El objetivo principal de la entrega continua es hacer que los despliegues de software sean eventos sencillos y de bajo riesgo que se puedan realizar en cualquier momento y bajo demanda.
- **Tiempo de comercialización más rápido**. Al automatizar los procesos de compilación y despliegue, aprovisionamiento del entorno y pruebas de regresión, el equipo puede llevar nuevos cambios al ambiente producción de manera segura y escalable de manera más rápida.
- **Mejor calidad**. Teniendo herramientas automatizadas que descubren regresiones en cuestión de minutos, los equipos tienen la libertad de centrar su esfuerzo en la investigación de usuarios y actividades de prueba de nivel superior, como pruebas exploratorias, pruebas de usabilidad y pruebas de rendimiento y seguridad.
- **Costos mas bajos**. Cualquier producto o servicio de software exitoso evolucionará significativamente a lo largo de su vida. Al invertir en la automatización de compilación, prueba, despliegue y entorno, reducimos sustancialmente el costo de realizar y entregar cambios incrementales en el software al eliminar muchos de los costos fijos asociados con el proceso de lanzamiento.
- **Mejores productos**. La entrega continua hace que sea económico trabajar en lotes pequeños. Esto significa que podemos obtener comentarios de los usuarios a lo largo del ciclo de vida de entrega en función del software en funcionamiento.
- **Equipos más felices**. Se ha demostrado que la entrega continua hace que los lanzamientos sean menos dolorosos y reduce el agotamiento del equipo. Además, cuando lanzamos con más frecuencia, los equipos de entrega de software pueden interactuar más activamente con los usuarios, aprender qué ideas funcionan y cuáles no, y ver de primera mano los resultados del trabajo que han realizado. Al eliminar las actividades dolorosas de bajo valor asociadas con la entrega de software, podemos centrarnos en lo que más nos importa: deleitar continuamente a nuestros usuarios.

Si esto suena demasiado bueno para ser verdad, ten en cuenta: **la entrega continua no es magia**. Se trata de mejorar continua y diariamente: la disciplina constante de buscar un mayor rendimiento siguiendo la heurística "si duele, hazlo con más frecuencia y saca adelante el dolor".

## Obstáculos

- **Preferencias de los clientes**: algunos clientes no desean actualizaciones continuas de sus sistemas. Esto es especialmente cierto en las etapas críticas de sus operaciones.
- **Restricciones de industria**: en algunos industrias, como las telecomunicaciones y la medicina, las regulaciones requieren pruebas exhaustivas antes de que se permita que las nuevas versiones entren en la fase de operaciones.
- **Falta de automatización de pruebas**: la falta de automatización de pruebas conduce a una falta de confianza del desarrollador y puede impedir el uso de la entrega continua.
- **Diferencias en los entornos**: los diferentes entornos utilizados en el desarrollo, las pruebas y la producción pueden dar lugar a que problemas no detectados pasen al entorno de producción.
- **Pruebas que necesitan un oráculo humano**: no todos los atributos de calidad se pueden verificar con la automatización. Estos atributos requieren humanos en el circuito, lo que ralentiza la tubería de entrega.

<!-- Referencias -->
[1]: https://continuousdelivery.com/evidence-case-studies/#research
