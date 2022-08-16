---
title : "Despliegue continuo"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "entrega-continua"
weight: 703
toc: true
---

## Definición

Es posible que en varias fuentes los términos de despliegue continuo y entrega continua se interpongan, y no existe una diferencia clara de en qué consisten. Sin embargo, para mejor segregación de procesos, es ideal separar el proceso de entrega del despliegue.

El despliegue continuo, en el contexto que ya definimos, es el lo siguiente a la entrega continua, con la sutil diferencia de que en lugar de desplegar la aplicación manualmente, se configura para que se despliegue automáticamente. No se requiere intervención humana (a excepción quizás de ejecutar el evento que inicializa el proceso automático).

## Despliegue en demanda

La capacidad de desplegar en demanda es una competencia crítica, ya que permite a las empresas responder a las oportunidades del mercado con funcionalidades o soluciones de mayor valor en los plazos de entrega sostenibles más breves y a un ritmo que permite a los clientes absorber la nueva funcionalidad.

Esta competencia es particularmente importante cuando estamos frente a una organización cuyas operaciones se realizan en un mercado altamente competitivo y cambiente; el tiempo de respuesta de las iteraciones del ciclo de vida de desarrollo de software son sumamente importantes.

## Despliegue vs. lanzamiento

Algo importante a notar aquí es que el despliegue no necesariamente implica "el lanzamiento" para el usuario final, ya que se pueden utilizar estrategias de despliegue modernas para controlar cómo se habilitan las nuevas funcionalidades a los usuarios.

Por ejemplo, digamos que se desarrolló una nueva funcionalidad para una aplicación web. Pero, no queremos que todos los usuarios la tengan disponible de un solo golpe, sino ir progresivamente habilitándola para obtener retroalimentación de ese segmento de usuarios específico antes de hacer el lanzamiento en masas. En ese sentido, el despliegue se realizó exitosamente y de manera automática, pero el lanzamiento a los usuarios se hizo progresivamente.

De igual manera, pueden existir muchas necesidades y comportamientos que pueden adaptarse a las necesidades de cualquier organización; y justamente de todo esto se trata el despliegue continuo.
