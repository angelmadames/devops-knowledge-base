---
title : "Pruebas automáticas"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "aseguramiento-de-calidad"
weight: 1003
toc: true
---

## Prueba manual

La prueba manual es un tipo de prueba de software en la que un probador ejecuta manualmente los casos de prueba sin utilizar ninguna herramienta automatizada.

El propósito de las pruebas manuales es identificar errores, problemas y defectos en la aplicación de software. La prueba de software manual es la técnica más primitiva de todos los tipos de prueba y ayuda a encontrar errores críticos en la aplicación de software.

## Prueba automática

La prueba de automatización es una técnica de prueba de software que se realiza utilizando herramientas especiales de software de prueba automatizada para ejecutar un conjunto de casos de prueba. Por el contrario, la prueba manual es realizada por un ser humano sentado frente a una computadora que ejecuta cuidadosamente los pasos de la prueba.

El software de prueba de automatización también puede ingresar datos de prueba en el Sistema bajo prueba, comparar resultados esperados y reales y generar informes de prueba detallados. La automatización de pruebas de software exige inversiones considerables de dinero y recursos.

Los ciclos de desarrollo sucesivos requerirán la ejecución del mismo conjunto de pruebas repetidamente. Con una herramienta de automatización de pruebas, es posible grabar este conjunto de pruebas y reproducirlo según sea necesario. Una vez que el conjunto de pruebas está automatizado, no se requiere intervención humana. Esto mejoró el ROI de la automatización de pruebas. El objetivo de la automatización es reducir la cantidad de casos de prueba que se ejecutarán manualmente y no eliminar por completo las pruebas manuales.

## Automatización de pruebas

La automatización de pruebas es la práctica de revisar y validar automáticamente un producto de software, como una aplicación web, para asegurarse de que cumpla con los estándares de calidad predefinidos para el estilo del código, la funcionalidad (lógica comercial) y la experiencia del usuario.

Las prácticas de prueba típicamente involucran las siguientes etapas:

- Pruebas unitarias: valida unidades individuales de código, como una función, para que funcione como se espera
- Pruebas de integración: garantiza que varias piezas de código puedan funcionar juntas sin consecuencias no deseadas
- Pruebas de extremo a extremo: valida que la aplicación cumpla con las expectativas del usuario
- Pruebas exploratorias: adopta un enfoque no estructurado para revisar numerosas áreas de una aplicación desde la perspectiva del usuario, para descubrir problemas funcionales o visuales.

Los diferentes tipos de pruebas a menudo se visualizan como una pirámide. A medida que asciende en la pirámide, la cantidad de pruebas de cada tipo disminuye y el costo de crear y ejecutar pruebas aumenta.

Históricamente, todas las pruebas dentro de la pirámide se realizaban manualmente. Este fue un proceso lento, costoso y propenso a errores hasta que se crearon herramientas de prueba automatizadas.

Hoy en día, casi todas las pruebas unitarias están completamente automatizadas y la automatización de las pruebas unitarias se considera una mejor práctica. Las pruebas de integración también están automatizadas en gran medida y, si no, generalmente se omiten a favor de pruebas más manuales de extremo a extremo. La ola actual de esfuerzos de automatización de pruebas se centra en gran medida en la automatización de la capa de extremo a extremo de la pirámide de pruebas, lo que reduce la necesidad de pruebas de integración.

Aunque las herramientas de automatización han existido durante más de una década, muchas requieren habilidades de codificación y, a menudo, dan como resultado pruebas frágiles que son extremadamente costosas de solucionar y mantener a escala. Muchos equipos terminan creando sus propios marcos de automatización de pruebas personalizados, lo que dificulta y consume mucho tiempo para incorporar nuevos miembros del equipo debido a la pronunciada curva de aprendizaje. Los marcos personalizados también terminan requiriendo su propio mantenimiento y mejoras para mantenerse al día con la pila de tecnología cambiante. Como resultado, la mayoría de las pruebas de extremo a extremo eran un proceso manual, hasta ahora.

A medida que las organizaciones maduran sus prácticas de DevOps, la necesidad de automatización de pruebas a lo largo del ciclo de vida es importante para desbloquear los beneficios clave de DevOps: la capacidad de construir, probar y enviar más rápido y de manera más confiable, agilizar las respuestas a incidentes y mejorar la colaboración y la comunicación entre equipos. . Ya no es una opción tener una compilación de lanzamiento con el equipo de control de calidad durante varios días antes de que los desarrolladores reciban comentarios y solucionen los problemas identificados. Los equipos de control de calidad deben alinear sus esfuerzos en el ciclo DevOps asegurándose de que los casos de prueba estén automatizados y logren una cobertura de código cercana al 100 %. Los entornos deben estandarizarse y la implementación en sus cuadros de control de calidad debe automatizarse. Las tareas previas a la prueba, las limpiezas, las tareas posteriores a la prueba, etc. deben automatizarse y alinearse con el ciclo de integración continua.

Ahora existen herramientas de código bajo como mabl que permiten incorporar pruebas confiables y automatizadas de extremo a extremo en cada etapa de la canalización de CI/CD, lo que ayuda a detectar problemas mucho antes en el ciclo de vida del desarrollo. Es bien sabido que cuanto antes detecte los problemas con una versión, más rápido y económico será solucionarlos.

### Empezando con la automatización de pruebas

No existe una solución única para todos, pero aquí hay algunas cosas importantes que debe considerar al definir una estrategia de automatización de pruebas para su equipo:

#### Frecuencia de lanzamiento

Cuanto más frecuentes sean los lanzamientos, más deberá invertir en la automatización de pruebas, especialmente en las pruebas de un extremo a otro que deberían ejecutarse en cada implementación. Si no tiene un ciclo de lanzamiento frecuente y le gustaría acelerarlo, puede comenzar agregando más cobertura de prueba unitaria y creando pruebas de humo de interfaz de usuario simples y automatizadas para realizar una verificación rápida de cordura en cada compilación. A continuación, puede invertir gradualmente en la creación de pruebas más automatizadas de un extremo a otro que le ayuden a reducir el tiempo que se tarda en comprobar si hay regresiones en una versión.

#### Disponibilidad de herramientas

Las herramientas modernas de automatización de pruebas mejorarán significativamente la capacidad de su equipo para entregar continuamente software de alta calidad. Al evaluar las herramientas de prueba, tenga en cuenta la facilidad de creación de pruebas, la confiabilidad, la necesidad de mantenimiento y la integración con su pila de CI/CD.

Es igualmente importante comprender la curva de aprendizaje y las habilidades requeridas para una herramienta determinada. Cuanto más fácil sea usar su solución, más rápido podrá aumentar su equipo. Y será más accesible para más personas en su equipo, lo que puede conducir a una mayor cobertura de las pruebas y ayudar a cultivar una cultura de calidad. Una forma efectiva de evaluar las soluciones de prueba es hacer que todo el equipo dedique tiempo a automatizar algunos escenarios de casos de prueba con los principales contendientes en su lista de preseleccionados.

#### Madurez del producto

Si su equipo trabaja en un producto con numerosos clientes existentes y una base de código madura, es probable que ya tenga una cadencia de lanzamiento y prácticas de prueba establecidas. A medida que su equipo avanza hacia la integración continua o la CI/CD completa, es importante incluir la automatización de pruebas como una parte clave de la automatización de canalización. La entrega rápida y la retroalimentación rápida son insostenibles sin la automatización de las pruebas antes y durante todo el desarrollo.

Por otro lado, si su equipo está creando un nuevo producto, es una oportunidad ideal para instrumentar pruebas automatizadas desde el principio. Desde el principio, establezca un objetivo para la cobertura de pruebas unitarias y concéntrese en definir los casos de prueba de extremo a extremo para cada función. Es mejor esperar hasta que una característica esté cerca de su lanzamiento antes de agregar pruebas automatizadas de un extremo a otro para evitar fallas en las pruebas debido a cambios importantes en la interfaz de usuario.

#### Entornos CI/CD y datos de prueba

La creación de pruebas automatizadas es un desafío en sí mismo, pero a menudo es la falta de entornos prístinos con datos de prueba lo que impide que los equipos adopten la automatización de pruebas antes en la canalización de CI/CD. Por lo tanto, es importante tener una discusión en equipo desde el principio sobre la estrategia de prueba y comprometerse a crear la infraestructura de prueba necesaria. Por ejemplo, los desarrolladores deben implementar soporte para cuentas de usuario de prueba y tener la capacidad de cargar un entorno con datos de prueba a través de una API. La creación de infraestructura para el aprovisionamiento temprano de entornos de prueba efímeros acelerará significativamente el ciclo de revisión y comentarios de la versión.

## Beneficios

Adoptar las pruebas automatizadas ayuda a desbloquear los siguientes beneficios de DevOps:

- **Velocidad sin sacrificar la calidad**: obtenga una alta velocidad del producto que haga felices a los desarrolladores y les permita ofrecer más valor a los usuarios, más rápido.
- **Colaboración en equipo mejorada**: la responsabilidad compartida por la calidad permite una mejor colaboración entre los miembros del equipo.
- **Confiabilidad**: mejore la confiabilidad de los lanzamientos al aumentar la cobertura con la automatización de pruebas. Los problemas en la producción deberían ser una ocurrencia rara en lugar de la norma.
- **Escala**: produzca resultados de calidad consistentes con un riesgo reducido al distribuir el desarrollo entre múltiples equipos pequeños que operan de manera autosuficiente.
- **Seguridad**: muévase rápidamente sin comprometer la seguridad y el cumplimiento mediante el aprovechamiento de las políticas de cumplimiento automatizadas, los controles detallados y las técnicas de administración de la configuración.
- **Mayor felicidad del cliente**: la confiabilidad mejorada y las respuestas rápidas a los comentarios de los usuarios aumentan la satisfacción del usuario y conducen a más referencias de productos.
