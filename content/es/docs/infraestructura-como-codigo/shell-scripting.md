---
title : "Shell scripting"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "infraestructura-como-codigo"
weight: 803
toc: true
---

## Script de shell

Un script de Shell es un programa de computadora diseñado para ser ejecutado por el shell de UNIX/Linux que podría ser uno de los siguientes:

- [The Bourne Shell][Bourne Shell]
- [The C Shell][C Shell]
- [The Korn Shell][Korn Shell]
- [The GNU Bourne-Again Shell][Bourne-Again Shell]

Un shell es un intérprete de línea de comandos y las operaciones típicas realizadas por los scripts de shell incluyen la manipulación de archivos, la ejecución de programas y la impresión de texto.

## Scripts de shell extendidos

Los scripts de shell tienen varias construcciones necesarias que le indican al entorno de shell qué hacer y cuándo hacerlo.

El `shell` es, después de todo, un lenguaje de programación real, completo con variables, estructuras de control, etc. No importa cuán complicado se vuelva un script, sigue siendo solo una lista de comandos ejecutados secuencialmente.

El siguiente script usa el comando "**read**" que toma la entrada del teclado y la asigna como el valor de la variable `PERSONA` y finalmente la imprime en `STDOUT`.

```shell
#!/bin/sh

echo "¿Cuál es tu nombre?"

read PERSONA

echo "¡Hola, $PERSONA!"
```

Aquí hay una muestra de ejecución del script:

```shell
$ ./test.sh
¿Cuál es tu nombre?
Angel Adames
¡Hola, Angel Adames!
```

## Shell

Un Shell le proporciona una interfaz para el sistema [UNIX]. Recopila información de usted y ejecuta programas basados en esa entrada. Cuando un programa termina de ejecutarse, muestra la salida de ese programa.

Shell es un entorno en el que podemos ejecutar nuestros comandos, programas y scripts de shell. Hay diferentes sabores de shell, al igual que hay diferentes sabores de sistemas operativos. Cada tipo de shell tiene su propio conjunto de funciones y comandos reconocidos.

## Shell prompt

El *prompt*, `$`, también denominado `símbolo del sistema`, lo emite el **shell**. Mientras se muestra el prompt, puede escribir un comando.

Shell lee su entrada después de presionar Enter. Determina el comando que desea ejecutar mirando la primera palabra de su entrada. Una palabra es un conjunto ininterrumpido de caracteres. Los espacios y las tabulaciones separan las palabras.

El siguiente es un ejemplo simple del comando `date`, que muestra la fecha y la hora actuales:

> Todos los comandos que se usan en shell están asociados al idioma inglés. Es importante reconocer los principios básicos del idioma para lograr entender con mayor facilidad cómo funcionan estos recursos. Por ejemplo, en el ejercicio siguiente `date` es el inglés para `fecha`.

```shell
$ date
Mon May 16 20:53:36 AST 2022
```

## Tipos de shell

En UNIX, hay dos tipos principales de shells:

- Shell Bourne: si está utilizando un shell de tipo Bourne, el carácter $ es el indicador predeterminado.
- Shell C: si está utilizando un shell tipo C, el carácter % es el indicador predeterminado.

El Bourne Shell tiene las siguientes implementaciones:

- Bourne shell (sh)
- Korn shell (ksh)
- Bourne Again shell (bash)
- POSIX shell (sh)

El shell original de [UNIX] fue escrito a mediados de la década de 1970 por Stephen R. Bourne mientras estaba en AT&T Bell Labs en Nueva Jersey.

Bourne shell fue el primer shell que apareció en los sistemas [UNIX], por lo que se lo conoce como "el shell".

Bourne shell generalmente se instala como /bin/sh en la mayoría de las versiones de [UNIX]. Por esta razón, es el shell elegido para escribir scripts que se pueden usar en diferentes versiones de [UNIX].

En este capítulo, cubriremos la mayoría de los conceptos de Shell que se basan en Borne Shell.

## Scripts

El concepto básico de un script de shell es una lista de comandos, que se enumeran en orden de ejecución. Un buen script de shell tendrá comentarios, precedidos por el signo #, que describen los pasos.

Hay pruebas condicionales, como que el valor A es mayor que el valor B, bucles que nos permiten pasar por grandes cantidades de datos, archivos para leer y almacenar datos y variables para leer y almacenar datos, y el script puede incluir funciones.

Tanto los scripts como las funciones de Shell se interpretan. Esto significa que no están compilados.

<!-- Referencias -->
[UNIX]: ./../referencias/enlaces#unix
[Bourne Shell]: ./../referencias/enlaces#bourne-shell
[C Shell]: ./../referencias/enlaces#c-shell
[Korn Shell]: ./../referencias/enlaces#korn-shell
[Bourne-Again Shell]: ./../referencias/enlaces#bourne-again-shell
