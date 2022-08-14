---
title : "Mejores prácticas"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "integracion-continua"
weight: 604
toc: true
---

## Hacer commit temprano, hacer commit frecuente

Es mucho más fácil solucionar problemas pequeños que problemas grandes.

Una de las mayores ventajas de la integración continua es que el código se integra en un repositorio compartido frente a otros cambios que ocurren al mismo tiempo. Si un equipo de desarrollo realiza cambios de código temprano y con frecuencia, los errores son más fáciles de identificar porque hay menos código para clasificar.

Al probar en lotes pequeños, se mejora la calidad del código y los equipos pueden iterar de manera más efectiva.

## Leer la documentación

Puede ser útil hacer referencia a la documentación en `README` o en otros formatos accesibles. Aliente a los miembros del equipo a leer primero la documentación, marcar enlaces, crear preguntas frecuentes e incorporar estos recursos en la incorporación de nuevos miembros del equipo.

## Optimizar las etapas del pipeline

Los pipelines de CI contienen **jobs** (*trabajos*) y **stages** (*etapas*): los jobs son las actividades que suceden dentro de un stage particular y, una vez que pasan todos los jobs, el código pasa a la siguiente stage.

Las stages son una manera fácil de organizar jobs similares.

## Promover compilaciones rápidas y simples

Nada ralentiza un pipeline como la complejidad. Mantener las compilaciones rápidas es siempre buena idea, y la mejor manera de hacerlo es mantener las cosas lo más simples posible.

Cada minuto que se quita de los tiempos de compilación es un minuto que cada desarrollador ahorra cada vez que se compromete. Dado que CI exige confirmaciones frecuentes, este tiempo puede sumar.

## Utilice los errores para mejorar los procesos

**La mejora es un proceso.** Cuando los equipos cambian su respuesta a las fallas, se crea un cambio cultural para la mejora continua. En lugar de preguntar quién causó la falla, pregunte qué causó la falla. Esto significa pasar de una cultura de culpa a una cultura de aprendizaje.

Si los equipos realizan *commits* frecuentes, se vuelve mucho más fácil identificar problemas y resolverlos. Si hay patrones en las compilaciones fallidas, observe las causas subyacentes.

## El entorno de prueba debe reflejar el de producción

Cuando los entornos de prueba y producción coinciden, significa que los desarrolladores pueden confiar en los resultados y desplegar con confianza.

## En resumen, usar el proceso de CI

En última instancia, el mejor sistema de integración continua es el que realmente usa. Encuentre el CI adecuado para sus necesidades y luego incorpore estas mejores prácticas para aprovechar al máximo su nuevo flujo de trabajo de CI.
