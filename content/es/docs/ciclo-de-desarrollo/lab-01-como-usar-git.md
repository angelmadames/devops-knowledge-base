---
title : "Lab 3.1: Cómo usar git"
description: ""
lead: ""
date: 2022-08-14T08:48:45+00:00
lastmod: 2022-08-14T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "ciclo-de-desarrollo"
weight: 405
toc: true
---

## Requerimientos

- Capacidad de lectura del idioma inglés.
- Registrarse en GitHub.
- [Instalación y configuración de git][git installation].

## Paso 1: Crear un repositorio local de git

Al crear un nuevo proyecto en su máquina local usando [git], primero creará un nuevo [repositorio][Repository] (o, a menudo, `repo`, para abreviar).

Para usar git usaremos la terminal. Asumiremos que ya tienes un conocimiento básico del uso del terminal gracias al [Laboratorio 2.2], si aún no lo has tomado, este puede ser un buen momento.

Para comenzar, abra una terminal y muévase a donde desea colocar el proyecto en su máquina local usando el comando `cd`. Por ejemplo, si tiene una carpeta de "`projects`" en su escritorio, haría algo como:

```shell
cd ~/projects
mkdir myproject
cd myproject
```

Para inicializar un repositorio git en la raíz de la carpeta, ejecute el comando `git init`:

```shell
$ git init
Initialized empty Git repository in ~/projects/myproject/.git
```

## Paso 2: Agregar un nuevo archivo al repositorio

Continúe y agregue un nuevo archivo al proyecto usando cualquier editor de texto que desee o ejecutando el comando `touch`.

```shell
# Solo crea y guarda un archivo en blanco llamado 'newfile.txt'
touch newfile.txt
```

Una vez que haya agregado o modificado archivos en la carpeta que contiene el repositorio de git, git notará que el archivo existe dentro del repositorio pero no rastreará el archivo a menos que se lo indique explícitamente. Git solo guarda/administra los cambios en los archivos que rastrea, por lo que necesitaremos enviar un comando para confirmar que sí, queremos que git rastree nuestro nuevo archivo.

Después de crear el nuevo archivo, puede usar el comando de estado de git para ver qué archivos sabe que existen.

```shell
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
    newfile.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

Básicamente, lo que git nos dice es que: "Oye, notamos que creaste un nuevo archivo llamado **newfile.txt**, pero a menos que uses el comando '`git add`', no haremos nada con el".

## Paso 3: Crear un `commit`

¡Es hora de crear tu primer commit!

Ejecute el comando `git add newfile.txt` seguido de `git commit -m "<un mensaje para el describir el commit>"` reemplazando entre comillas un mensaje para este nuevo cambio.

```shell
git add newfile.txt
git commit -m "Agregando mi primer archivo"
```

Luego, con el comando `git status` podemos validar que nuestro nuevo archivo se encuentra rastreado por git como un nuevo archivo.

```shell
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
    new file:   newfile.txt
```

El mensaje al final del commit debe ser algo relacionado con lo que contiene el commit: tal vez sea una característica nueva, tal vez sea una corrección de errores, tal vez solo esté arreglando un error tipográfico. No es una buena idea colocar un mensaje como "asdfadsf" o "prueba" o similar.

Las commits viven para siempre en un repositorio (técnicamente, puede eliminarlas si realmente lo necesita, pero es complicado), por lo que si deja una explicación clara de sus cambios, puede ser extremadamente útil para los futuros programadores (¡quizás para el tu futuro!) que están tratando de averiguar por qué se hizo algún cambio años después.

## Paso 4: Crea una nueva rama

Ahora que ha realizado una nueva commit, intentemos algo un poco más avanzado.

Digamos que desea crear una función nueva, pero le preocupa realizar cambios en el proyecto principal mientras desarrolla la función. Aquí es donde entran las [ramas de git][git branches].

Las ramas le permiten avanzar y retroceder entre los 'estados' de un proyecto. Los documentos oficiales de git describen las ramas de esta manera: "Una rama en Git es simplemente un puntero móvil liviano a una de estas confirmaciones". Por ejemplo, si desea agregar una nueva página a su sitio web, puede crear una nueva rama solo para esa página. sin afectar la parte principal del proyecto. Una vez que haya terminado con la página, puede [merge][git merge] (combinar) los cambios de su rama en la rama principal. Cuando crea una nueva rama, Git realiza un seguimiento de la commit de la que se 'ramificó' su rama, por lo que conoce el historial detrás de todos los archivos.

Supongamos que está en la rama principal y desea crear una nueva rama para desarrollar su página web. Esto es lo que hará: Ejecute `git checkout -b <nombre de mi rama>`. Este comando creará automáticamente una nueva rama y luego lo 'revisará', lo que significa que git lo moverá a esa rama, fuera de la rama principal.

Después de ejecutar el comando anterior, puede usar el comando `git branch` para confirmar que se creó su rama:

```shell
$ git branch
  main
* my-new-branch
```

El nombre de la rama con el *asterisco* al lado indica en qué rama te encuentras en ese momento.

## Paso 5: Crear un nnuevo repositorio en GitHub

Si solo desea almacenar de su código localmente, no necesita usar [GitHub]. Pero si desea trabajar con un equipo, como es lo más común, puede usar GitHub para modificar el código del proyecto de forma colaborativa. A parte de que siempre tendrá una copia de seguridad.

Para crear un nuevo repositorio en GitHub, inicie sesión y vaya a la página de inicio de GitHub. Puede encontrar la opción "**New repository**" debajo del signo "`+`" junto a su foto de perfil, en la esquina superior derecha de la barra de navegación:

![C1-M03-L301-001](images/C1-M03-L301-001.png)

Después de hacer clic en el botón, GitHub le pedirá que asigne un nombre a su repositorio y proporcione una breve descripción:

![C1-M03-L301-002](images/C1-M03-L301-002.png)

Cuando haya terminado de completar la información, presione el botón '**Create repository**' para crear el nuevo repositorio.

GitHub le preguntará si desea crear un nuevo repositorio desde cero o si desea agregar un repositorio que haya creado localmente. En este caso, dado que ya hemos creado un nuevo repositorio localmente, queremos enviarlo a GitHub:

```shell
$ git remote add origin git@github.com:angelmadames/curso-devops.git
$ git push -u origin main

[...]

To git@github.com:angelmadames/curso-devops.git
 * [new branch]      main -> main
Branch main set up to track remote branch main from origin.
```

> :information_source: Deseará cambiar la URL en la primera línea de comando a lo que GitHub le indica en esa sección, ya que su nombre de usuario de GitHub y el nombre del repositorio serán diferentes.

## Paso 6: `push` una rama a GitHub

Ahora enviaremos el commit en su rama a su nuevo repositorio de GitHub. Esto permite que otras personas vean los cambios que ha realizado. Si el propietario del repositorio los aprueba, los cambios se pueden fusionar en la rama principal.

Para enviar cambios a una nueva rama en GitHub, deberá ejecutar `git push origin <nombre-de-la-rama>`. GitHub creará automáticamente la rama para usted en el repositorio remoto:

```shell
$ git push origin my-new-branch
[...]
remote: Create a pull request for 'my-new-branch' on GitHub by visiting:
remote:      https://github.com/angelmadames/curso-devops/pull/new/my-new-branch
To github.com:angelmadames/curso-devops.git
 * [new branch]      my-new-branch -> my-new-branch
```

Quizás se pregunte qué significa esa palabra "`origin`" en el comando anterior. Lo que sucede es que cuando clona un repositorio remoto en su máquina local, git crea un *alias* para usted. En casi todos los casos, este alias se denomina "`origin`". Es esencialmente una abreviatura de la URL del repositorio remoto. Entonces, para enviar sus cambios al repositorio remoto, podría haber usado el comando: `git push git@github.com:git/git.git <nombre-de-la-rama>` o `git push origin <nombre-de-la-rama>`

> Si es la primera vez que usa GitHub localmente, es posible que le solicite que inicie sesión con su nombre de usuario y contraseña de GitHub.

Si actualiza la página de GitHub, verá una nota que dice que una rama con el nombre que acaba de insertar en el repositorio. También puede hacer clic en el enlace '**Branches**' para ver la rama en la lista.

![C1-M03-L301-003](images/C1-M03-L301-003.png)

Ahora haga clic en el azúl verde en la captura de pantalla de arriba que dice "**Compare & pull request**". ¡Vamos a abrir un **Pull Request**!

## Paso 7: Crear un `Pull Request` (PR)

Un `pull request` (o PR) es una forma de alertar a los propietarios de un repositorio que desea realizar algunos cambios en su código. Les permite revisar el código y asegurarse de que se vea bien antes de colocar los cambios en la rama principal.

Así es como se ve la vista de un PR antes de crearlo:

![C1-M03-L301-004](images/C1-M03-L301-004.png)

Y así es como se ve una vez que haya enviado el PR:

![C1-M03-L301-005](images/C1-M03-L301-005.png)

Es posible que veas un gran botón azul en la parte inferior que dice "**Merge pull request**". Hacer clic aquí significa que fusionará sus cambios en la rama principal.

A veces, será copropietario o el único propietario de un repositorio, en cuyo caso es posible que no necesite crear un `PR` para fusionar sus cambios. Sin embargo, sigue siendo una buena idea crear uno para que pueda mantener un historial más completo de sus actualizaciones y para asegurarse de que siempre crea una nueva rama cuando realiza cambios.

## Paso 8: `merge` un PR

Continúe y haga clic en el botón azul "**Merge pull request**". Esto fusionará sus cambios en la rama principal.

![C1-M03-L301-006](images/C1-M03-L301-006.png)

Cuando haya terminado, le recomiendo que elimine su rama (demasiadas ramas pueden volverse un caos), así que presione el botón "**Delete branch**" también.

Puede verificar que sus commits se fusionaron haciendo clic en el enlace "**Commits**" en la primera página de su nuevo repositorio.

![C1-M03-L301-007](images/C1-M03-L301-007.png)

Esto le mostrará una lista de todas los commits en esa rama. Puede ver el que acabo de `merge` en la parte superior.

![C1-M03-L301-008](images/C1-M03-L301-008.png)

También puede ver el código `hash` del commit en el lado derecho. Un código `hash` es un identificador único para ese commit específico. Es útil para hacer referencia a commits específicos y al deshacer cambios (use el comando `git revert <código-hash>`).

## Paso 9: `pull` cambios en GitHub de vuelta a su local

En este momento, el repositorio en GitHub se ve un poco diferente al que tiene en su máquina local. Por ejemplo, el commit que realizó en su rama y fusionó en la rama principal no existe en la rama principal en su máquina local.

Para obtener los cambios más recientes que usted u otros hayan combinado en GitHub, use el comando maestro `git pull origin` (cuando trabaje en la rama principal). En la mayoría de los casos, esto se puede acortar a "`git pull`".

```shell
$ git checkout main
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

$ git pull
[...]
From github.com:angelmadames/curso-devops
   0964021..86636e0  main       -> origin/main
Updating 0964021..86636e0
Fast-forward
 newfile.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 newfile.txt
```

Esto le muestra todos los archivos que han cambiado y cómo han cambiado.

Ahora podemos usar el comando `git log` nuevamente para ver todos los commits nuevos.

![C1-M03-L301-009](images/C1-M03-L301-009.png)

---

Has realizado correctamente una `PR` y fusionado tu código con la rama principal.
¡Felicidades! :partying_face:

<!-- Referencias -->
[Repository]: ../../referencias/enlaces#repository
[git]: ../../referencias/enlaces#git
[git installation]: ../../referencias/enlaces#git-installation
[git branches]: ../../referencias/enlaces#git-branch
[git merge]: ../../referencias/enlaces#git-merging
[GitHub]: ../../referencias/enlaces#github
