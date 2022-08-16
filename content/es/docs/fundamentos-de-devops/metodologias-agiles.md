---
title : "Metodologías ágiles"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "fundamentos-de-devops"
weight: 203
toc: true
---
<!-- markdownlint-disable MD026 -->

## ¿Qué es ágil?

De forma simple, [Ágil][Agile Methodologies] es un enfoque [iterativo] para la gestión de proyectos y el desarrollo de software que ayuda a los equipos a entregar valor a sus clientes más rápido.

En lugar de realizar un único despliegue a producción, como en la [metodología de cascada], un equipo ágil entrega el trabajo en incrementos pequeños pero consumibles. Los requerimientos, planes de acción y resultados se evalúan continuamente para que los equipos tengan un mecanismo natural para dar respuesta a cambios.

Mientras que el enfoque tradicional de "cascada" hace que una disciplina contribuya al proyecto y luego "lo arroje por encima del muro" al siguiente contribuyente, la metodología ágil requiere equipos colaborativos multifuncionales. La comunicación abierta, la colaboración, la adaptación y la confianza entre los miembros del equipo están en el corazón de Agile. Si bien el líder del proyecto o el propietario del producto generalmente prioriza el trabajo que se entregará, el equipo toma la iniciativa para decidir cómo se realizará el trabajo, autoorganizado en torno a tareas y asignaciones granulares.

Agile no se define por un conjunto de ceremonias o técnicas de desarrollo específicas. Más bien, ágil es un grupo de metodologías que demuestran un compromiso con los ciclos de retroalimentación estrictos y la mejora continua.

## Historia de ágil

Ágil no sería lo que conocemos como ágil de no ser por el [Agile Manifesto] (Manifiesto ágil).

La publicación del manifiesto ágil en 2001 marca su nacimiento. Desde entonces, han surgido muchos marcos ágiles, como [Scrum], [Kanban], [Lean][Lean Agile] y [Extreme Programming (XP)][Extreme Programming]. Cada uno encarna los principios básicos de iteración frecuente, aprendizaje continuo y alta calidad a su manera.

`Scrum` y `XP` son los preferidos por los equipos de desarrollo de software, mientras que `Kanban` es favorito entre los equipos orientados a servicios como TI o recursos humanos.

Hoy en día, muchos equipos ágiles combinan prácticas de algunos marcos diferentes, aderezadas con prácticas exclusivas del equipo. Un ejemplo claro es [Scrumban], un mixto entre Scrum y Kanban.

El mensaje de esto es que, siempre y cuando te bases en los principios del manifiesto ágil, puedes adaptar la metodología que cumpla con las necesidades de tu equipo y organización. Puedes usar un marco existente, una combinación, o uno propio justo a la medida.

## Manifiesto ágil

Antes de entrar en materia con los principios de ágil, no podemos dejar pasar los valores (también mencionados en el manifiesto). Estos valores deben de igual manera siempre tomarse en consideración a la hora de adoptar esta nuevo paradigma de trabajo, puesto no hacerlo puede resultar en una adopción ineficiente de ágil, y como resultado, DevOps.

### Valores

- **Individuos e interacciones** sobre procesos y herramientas
- **Software funcional** sobre documentación completa
- **Colaboración con el cliente** sobre la negociación del contrato
- **Respondiendo al cambio** sobre seguir el plan

### 12 principios de ágil

> **Enlace de interés**: [Principles behind the Agile Manifesto]

1. Nuestra mayor prioridad es satisfacer al cliente a través de la entrega temprana y continua de software valioso.
2. Bienvenido a los requisitos cambiantes, incluso tarde desarrollo. Los procesos ágiles aprovechan el cambio para la ventaja competitiva del cliente.
3. Entregue software que funcione con frecuencia, desde un un par de semanas a un par de meses, con un preferencia a la escala de tiempo más corta.
4. Los empresarios y los desarrolladores deben trabajar juntos diariamente a lo largo del proyecto.
5. Construir proyectos en torno a personas motivadas. Bríndeles el entorno y el apoyo que necesitan, y confiar en ellos para hacer el trabajo.
6. El método más eficiente y eficaz de transmitir información hacia y dentro de un desarrollo El equipo es una conversación cara a cara.
7. El software que funciona es la medida principal del progreso.
8. Los procesos ágiles promueven el desarrollo sostenible. Los patrocinadores, desarrolladores y usuarios deben poder mantener un ritmo constante indefinidamente.
9. Atención continua a la excelencia técnica y un buen diseño mejora la agilidad.
10. Simplicidad: el arte de maximizar la cantidad del trabajo no hecho--es esencial.
11. Las mejores arquitecturas, requisitos y diseños. surgen de equipos autoorganizados.
12. A intervalos regulares, el equipo reflexiona sobre cómo para volverse más efectivo, luego afina y ajusta su comportamiento en consecuencia.

## Scrum

Uno de los *marcos de referencia* más comunes y populares en los cuales se implementa la filosofía ágil es [Scrum].

[Scrum] motiva a los equipos a:

- **aprender** a través de experiencias,
- **autoorganizarse** mientras trabajan en un problema y,
- reflexionar sobre sus *victorias* y *derrotas* para **mejorar continuamente**.

A pesar de que **Scrum** es más utilizado por los equipos de desarrollo de software, se puede utilizar a todo tipo de trabajo en equipo, lo que hace bastante popular. Scrum también describe un conjunto de *reuniones*, *herramientas* y *roles* que funcionan en conjunto para ayudar a los equipos a estructurar y administrar su trabajo de manera óptima.

### Scrum, marco de referencia de ágil

A menudo se piensa que scrum y ágil son lo mismo porque ambos se centran en la **mejora continua**, que es un principio fundamental de ágil.

Sin embargo, scrum es un marco de referencia para llevar a cabo el trabajo y ágil es una mentalidad. Implementar ágil implica la dedicación de todo el equipo en cambiar su forma de pensar acerca de la entrega de valor a los clientes. Scrum es como un paso inicial hacia ello, te permite practicar y enforzar la comunicación y entrega continua.

El marco de scrum es [heurístico]:

- Se basa en el `aprendizaje continuo` y la `rápida adaptación a factores variables`.
- Reconoce que el equipo no sabe todo al comienzo de un proyecto y evolucionará a través de la `experiencia`.
- Ayuda a los equipos a adaptarse naturalmente a las condiciones cambiantes y requerimientos de los usuarios.
- Incluye priorización integrada y ciclos de lanzamiento cortos para que el equipo pueda mejorar constantemente.

Si bien Scrum está estructurado, no es **rígido**. Su ejecución puede adaptarse a las necesidades de cualquier organización.

> **Nota en base a la experiencia**: Hay muchas teorías sobre **cómo deben funcionar** los equipos de scrum para tener **éxito**. Hemos aprendido que la comunicación clara, la transparencia y la dedicación a la mejora continua siempre deben permanecer en el centro de cualquier marco que se utilice.

### Equipo de scrum

Scrum es un marco ágil, así que su base se encuentra personas, no herramientas. En scrum, la unidad fundamental de personas, se le llama `equipo scrum`.

El equipo scrum consta con tres entidades:

- Scrum master (Jefe de scrum)
- Product owner (Propietario del producto)
- Developers (Desarrolladores)

Dentro de un equipo scrum, no hay sub-equipos o jerarquías. Es una unidad cohesiva de profesionales enfocados en un objetivo a la vez, **la meta del producto**.

Otras características relevantes sobre los equipos scrum:

- Son responsables de todas las actividades relacionadas con el producto, desde la colaboración de las partes interesadas, la verificación, el mantenimiento, la operación, la experimentación, la investigación y el desarrollo, y cualquier otra cosa que pueda ser necesaria.
- Son multifuncionales, lo que significa que los miembros tienen todas las habilidades necesarias para crear valor en cada sprint.
- Se autogestionan, lo que significa que deciden internamente quién hace qué, cuándo y cómo.
- Es lo suficientemente pequeño como para seguir siendo ágil y lo suficientemente grande como para completar un trabajo significativo dentro de un Sprint. Si los equipos Scrum se vuelven demasiado grandes, deberían considerar reorganizarse en múltiples equipos Scrum cohesivos, cada uno enfocado en el mismo producto. Por lo tanto, deben compartir el mismo objetivo del producto, cartera de productos y propietario del producto.

> El tamaño recomendado para un equipo scrum es normalmente 10 o menos personas. En general, se ha descubierto que los equipos más pequeños se comunican mejor y son más productivos.

#### Scrum master

El scrum master es responsable de:

- Establecer Scrum como se define en la guía scrum.
- La efectividad del **equipo scrum**.

Para conocer más sobre este rol, se puede consultar la sección [Scrum Master en la Guía Scrum][Scrum master].

#### Product owner

Es responsable de maximizar el valor del producto resultante del trabajo del [equipo scrum][Scrum team]. La forma en que se hace esto puede variar ampliamente entre organizaciones, equipos Scrum e individuos.

El propietario del producto también es responsable de la gestión eficaz del [product backlog][Product backlog]:

- Desarrollar y comunicar explícitamente el Objetivo del Producto;
- Crear y comunicar claramente los elementos del Product Backlog;
- Ordenar elementos de la Lista de Producto; y,
- Asegurar que el Product Backlog sea transparente, visible y comprensible.

Para conocer más sobre este rol, se puede consultar la sección [Product Owner en la Guía Scrum][Scrum master].

#### Desarrolladores

Los [desarrolladores][Developers] son las personas del equipo scrum que se comprometen a crear cualquier aspecto de un **Incremento** utilizable en cada **Sprint**.

Las habilidades específicas que necesitan los [desarrolladores][Developers] suelen ser amplias y variarán según el dominio del trabajo. Sin embargo, los [desarrolladores][Developers] siempre son responsables de:

- Crear un plan para el Sprint, el [Sprint Backlog];
- Inculcar calidad al adherirse a una Definición de Listo;
- Adaptando su plan cada día hacia el [Sprint Goal]; y,
- Responsabilizarse unos a otros como profesionales.

### Artefactos de scrum

Scrum utiliza tres artefactos para ayudar a administrar el trabajo:

> Usaremos las definiciones en inglés puesto es muy poco usual ver su uso en español.

#### Product backlog

Es la lista principal de trabajo a realizar. Es una lista dinámica de funciones, requerimientos, mejoras y correcciones que actúa como entrada para el trabajo pendiente del [Sprint]. En otras palabras es la lista de "cosas por hacer" del equipo. Es mantenida por el propietario del producto ([Product Owner]) así que se encarga de revisar, priorizar y actualizar su contenido. A medida que aprendemos más o cambia el mercado, es posible que los requerimientos ya no sean relevantes o que los problemas se resuelvan de otras maneras.

#### Sprint backlog

Es la lista de elementos, historias de usuarios o correcciones de errores, seleccionados por el equipo de desarrollo para su implementación en el ciclo actual. Antes de cada [Sprint], el equipo elige en qué elementos trabajará para el sprint a partir del [product backlog][Product backlog]. Una acumulación de [Sprint] puede ser flexible y puede evolucionar durante un sprint. Sin embargo, el objetivo fundamental del sprint, lo que el equipo quiere lograr en el sprint actual, no puede verse comprometido.

#### Sprint goal

También conocido como **[Increment][Increment]**. El producto final utilizable de un sprint. Generalmente se muestra el "incremento" durante la demostración de final de sprint, donde el equipo muestra lo que se completó en el sprint.

En ágil hay cabida para las variaciones, incluso dentro de los artefactos. Por eso es importante permanecer abierto a la evolución de la forma en que mantiene incluso estos artefactos.

> **Nota de interés**: El producto que se trabaja t ambién debe ser ágil. Se debe tomar el tiempo necesario para verificar cómo van las cosas, hacer ajustes si es necesario y no forzar algo solo por el bien de la consistencia.

### Eventos de Scrum

> Usaremos las definiciones en inglés puesto es muy poco usual ver su uso en español.

Scrum define varios **eventos** (a veces llamados *ceremonias*) que ocurren dentro de cada **sprint**:

- Refinement
- Sprint planning
- Daily stand-up
- Sprint review
- Sprint retrospective

> Todos los eventos, desde la planificación hasta la retrospectiva, suceden durante el sprint. Una vez que se establece un cierto intervalo de tiempo para un sprint, debe permanecer constante durante todo el período de desarrollo. Esto ayuda al equipo a aprender de experiencias pasadas y aplicar esa información a futuros sprints.

#### Sprint

Primero, definamos `sprint`:

Un **sprint** es el período de tiempo real en el que el equipo Scrum trabaja en conjunto para finalizar un incremento.

Dos semanas es una duración bastante típica para un sprint, aunque algunos equipos encuentran que una semana es más fácil de alcanzar o un mes es más fácil de entregar un incremento valioso. Dave West, de [Scrum.org][Scrum], aconseja que cuanto más complejo sea el trabajo y más incógnitas, más corto debería ser el sprint.

Durante este período, el alcance se puede volver a negociar entre el propietario del producto y el equipo de desarrollo si es necesario.

#### Refinement

El refinamiento es una actividad estrechamente relacionada con la visión del producto, el mercado y el cliente que le gestiona. Por lo tanto, es responsabilidad del [propietario del producto][Product backlog]; es quién refina el [product backlog], utilizando los comentarios de los usuarios y el equipo de desarrollo para ayudar a priorizar y mantener una lista de cosas por hacer apropiadamente documentada.

#### Sprint planning

El trabajo a realizar (alcance) durante el [Sprint](#sprint) actual es planificado durante una reunión donde participa todo el equipo de desarrollo. A este reunión se le denomina **sprint planning**.

La reunión está dirigida por el [scrum master] y es donde el equipo decide el [objetivo del sprint](#sprint-goal). Luego, se agregan historias de uso específicas al sprint desde el **product backlog**. Estas historias siempre se alinean con el objetivo y el equipo Scrum también acuerda que sean factibles de implementar durante el sprint.

Al final de la reunión de planificación, cada miembro del scrum debe tener claro qué se puede entregar en el sprint y cómo se puede entregar el incremento.

#### Stand-up

Es una reunión diaria de corta duración que ocurre a la misma hora (generalmente al principio del día de trabajo) y lugar. Muchos equipos intentan completar la reunión en 15 minutos, pero eso es solo una guía. Esta reunión también se denomina "**daily stand-up**" y se enfatiza que debe ser rápida.

El objetivo del scrum diario es que todos los miembros del equipo estén en sintonía, alineados con el [objetivo del sprint](#sprint-goal) y que elaboren un plan para las próximas `24 horas`.

El stand up es el momento de expresar cualquier inquietud que tenga sobre el cumplimiento del [objetivo del sprint](#sprint-goal) o cualquier bloqueo.

Una forma común de realizar un stand up es que cada miembro del equipo responda tres preguntas en el contexto de lograr el [objetivo del sprint](#sprint-goal):

- **¿Qué hice ayer?**
- **¿Qué planeo hacer hoy?**
- **¿Hay obstáculos?**

> **CUIDADO!** Los "Stand-up" son una arma de doble filo pues en ocasiones simplemente crean ruido innecesario. Si el propósito no es claro, y la reunión ya no es tan corta debido al tamaño del equipo, es posible flexibilizar y adaptarse a las necesidades puntuales del equipo. ¡Nada está escrito en piedra!

#### Sprint review

Al final del sprint, el equipo se reúne en una sesión informal para ver una demostración o inspeccionar el incremento. El equipo de desarrollo muestra los elementos del backlog que ahora están "Terminados" a las partes interesadas y a los compañeros de equipo para recibir comentarios. El propietario del producto puede decidir si libera o no el incremento, aunque en la mayoría de los casos se libera el incremento.

Esta reunión de revisión también es cuando el propietario del producto vuelve a trabajar en la acumulación del producto en función del sprint actual, que puede alimentar la próxima sesión de planificación del sprint. Para un sprint de un mes, considere dividir el tiempo de su revisión de sprint en un máximo de cuatro horas.

#### Sprint retrospective

La retrospectiva es donde el equipo se reúne para documentar y discutir qué funcionó y qué no funcionó en un sprint, un proyecto, personas o relaciones, herramientas o incluso para ciertas ceremonias. La idea es crear un lugar donde el equipo pueda concentrarse en lo que salió bien y lo que debe mejorarse para la próxima vez, y menos en lo que salió mal.

<!-- Referencias -->
[iterativo]: ../../referencias/enlaces#iterativo
[Scrum]: ../../referencias/enlaces#scrum
[Kanban]: ../../referencias/enlaces#kanban
[Lean Agile]: ../../referencias/enlaces#lean-agile
[Extreme Programming]: ../../referencias/enlaces#extreme-programming
[Scrumban]: ../../referencias/enlaces#scrumban
[Agile Manifesto]: ../../referencias/enlaces#agile-manifesto
[Metodología de Cascada]: ../../referencias/enlaces#metodologia-de-cascada
[Principles behind the Agile Manifesto]: ../../referencias/enlaces#principles-behind-the-agile-manifesto
[Scrum team]: ../../referencias/enlaces#scrum-team
[Product owner]: ../../referencias/enlaces#product-owner
[Scrum master]: ../../referencias/enlaces#scrum-master
[Developers]: ../../referencias/enlaces#developers
[Sprint backlog]: ../../referencias/enlaces#sprint-backlog
[Agile Methodologies]: ../../referencias/enlaces#agile-methodologies
[Product backlog]: ../../referencias/enlaces#product-backlog
[Increment]: ../../referencias/enlaces#increment
[Sprint]: ../../referencias/enlaces#sprint
