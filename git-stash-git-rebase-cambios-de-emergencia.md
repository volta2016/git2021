# Git stash

Me sale lo siguiente me dice que se salvo el directorio es decir todo los archivos que se le estaba dando seguimiento a git inclusive otros que ni siquiera git les da seguimiento pero graba todo por mi.

**git stash**

Saved working directory and index state WIP on master: 5440fe5 Resolviendo conflictos
Me dice que se salvo el directorio incluso todos los archivos incluso otros que git no le ha dado seguimiento, pero graba
todo mi working directory y lo indexo.

## WIP:

esto es working in progress en la rama master, luego pone un has o identificador que nos va servir como referencia.

damos git status y nos dice que estamos trabajando en un arbol limpio.

Esto ayudaria a que en este momento cualquier cosa que haya hecho ante del ultimo commit esta alamacenado en algún lugar
especial llamado el stash

**git stash list**

Puedo ver la referencias del stash voy a ver lo siguiente:

stash@{0}: WIP on master: 5440fe5 Resolviendo conflictos

aca vemos que tenemos 0 (que es la primera posición) pero podemos tener mas -> lo mas recomendable es tener solo un stash, lo stash igual pueden causar conflictos.

Agrego modificación en un archivo lo añado a al stage pero voy ver que paso con el stage

Notemos que creamos un stash y que tenemos ese identificador con WIP, esto asimila lo que es un stash resolviendo conflicto ahí esta la info que nosotros teniamos

![wip](images/wip.png)

Pero ya es momento de recuperar nuestro trabajo y hace las modificaciones en las misiones

Obviamente readme no choca con las misiones entonces perfectamente podemos recuperar nuestro trabajo muy fácilmente entonces si nosotros queremos tomar el ultimo stash

Aplicamos el siguiente cmd: esto va tomar el ultimo stash lo va dejar como lo tenia nuestro working directory, lo va dejar como estaba y va mantener los cambios que nosotros hicimos anteriormente

**git stash pop**

Trae los cambios y también borra ese stash.

- tomo el ultimo stash el que esta con el 0 lo vuelve a colocar y lo elimina

git stash pop
On branch master
Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git checkout -- <file>..." to discard changes in working directory)

    modified:   misiones.md

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (07dead7a1fe882d9b9db20c9542aafd72fed46c5)

Apareció que hay un archivo modificado de misiones.md y también dice que hizo el Drop boto el ese stash en la posición 0 si tienes 1 2 34 todo se correcciones hacia arriba el nuevo stash 0 va ser el que ante era el 1

- 56c0252 - (18 minutes ago) readme update - volta2016 (HEAD -> master)
- 5440fe5 - (4 years, 6 months ago) Resolviendo conflictos - Strider (tag: v1.0.0)
  |\
  | \* 52c9666 - (4 years, 6 months ago) Modificamos las misiones - Strider
- | b936625 - (4 years, 6 months ago) Actualizamos las misiones MASTER - Strider
  |/
- a4a9834 - (4 years, 6 months ago) Merge branch 'rama-villano' - Strider
  |\
  | \* b3e02bc - (4 years, 6 months ago) Agregamos a doomsday - Strider
- | 4c24baa - (4 years, 6 months ago) Borre a los heroes que no son de DC - Strider
  |/
- ad66a33 - (4 years, 6 months ago) Agregamos al flash reverso - Strider
- df6ed62 - (4 years, 6 months ago) Agregando villanos - Strider
- 62c8a10 - (4 years, 6 months ago) Agregando el gitignore - Strider
- ac0d374 - (4 years, 6 months ago) Borramos la historia de batman - Strider
- b4c748c - (4 years, 6 months ago) Cambiamos el nombre de la historia de superman - Strider
- d877f01 - (4 years, 6 months ago) Borrando archivo salvar mundo - Strider
- c9ee153 - (4 years, 6 months ago) Renombrando archivo a salvar-mundo - Strider
- fa3cd3a - (4 years, 6 months ago) Creando el archivo destruir el mundo - Strider
- 4e809d4 - (4 years, 6 months ago) Agregamos a Linterna verde y a Robin - Strider
- 345d7de - (4 years, 6 months ago) Editamos el readme.md - Strider (tag: v0.1.0)
- 860c6c2 - (4 years, 6 months ago) Agregamos las historias de los heroes - Strider

# Conflictos con el stash

resumen de lo aprendido:

- qué es el stash ? -> Es un lugar donde puedo almacenar toda información de manera temporal y luego recuperarla

Si te piden cambios pero eso aún no esta listo lo mejor es almacenarlo en el stash, para hacer lo que es urgente.

1- grabas el stash
2- luego lo sacas con el pop

es algo que usualmente vamos a tener que hacer.

podemos ver que nos trae los cambios al archivo, luego listamos esos cambios con git commit -am
si yo doy un git lg, ya no tenemos la referencia aquí, esto fue un auto emerge. Git Resuelve el conflicto por mi

# Stash avanzado

**git stash clear**

Este comando borra todo los stash

**git stash apply apply stash@{2}**

Puedo viajar a un punto especifico en el stash, el que creo me lo posiciona con el número 0 es algo incomodo
como ordena pero de igual forma lo puedo eliminar.

**git stash drop**

Podemos borrar el stash en la primera posición

**git stash drop stash@{1}**

Borra un stash con un numero específico

**git stash show stash@{1}**

Con este comando puedo ver información de un stash en particular

**git stash save "Agregamos new file"**

Es te comando es es muy recomendado porque queda guardado con el mensaje que aplique, así es mas fácil de
reconocer si es que necesitas eliminar o realizar cambios

**git stash list --stat**

Obtengo mas información detalla de cada uno de los stash

**recordar que si ya no necesitamos trabajar con los stash limpiemos con:**

**git stash clear**

## git rebase

Lo primero es saber en que rama me encuentro parado

- main
  rama-dev

si yo quiero hacer un rabese tengo que estar en la rama en cual quiero que se muevan los cambios.

git rebase lo que va hacer es tomar el punto de separación de la rama y tomar los 2 commit **los va a poner en otro lugar aparte**,
Luego va tomar los últimos 2 commit y los va poner > antes de hacer la separación de la rama quiere decir que bajan de nivel en tiempo
esos 2 últimos commit

cuando terminde de unir la rama-dev al main vamos a ver que dice Fast-fostward
estos commit están literalmente paralelos

- 158ba9e - (4 years, 6 months ago) Se agrego a la liga: Volcán Negro - Strider (HEAD -> master)
- 300c014 - (4 years, 6 months ago) Misiones nuevas agregadas - Strider
  | _ 8e755a3 - (4 years, 6 months ago) Actualizamos dos misiones completadas al momento - Strider (rama-misiones-completadas)
  | _ cc55aaf - (4 years, 6 months ago) Agregamos el archivo de las misiones completadas - Strider
  |/
- acea380 - (4 years, 6 months ago) Actualización de las misiones - Strider
- 31efae8 - (4 years, 6 months ago) Retomando el trabajo que guarde en el stash - Strider

los commir de de rama-dev van al final y los del inicio retroceden

**git rebase master**

Nos muestra esto en consola:

First, rewinding head to replay your work on top of it...
Applying: Agregamos el archivo de las misiones completadas
Applying: Actualizamos dos misiones completadas al momento

quiere decir que sube al top nuestro commit de la rama secundaria, pero ahora nuestro commit de nuestras ramas misiones
completadas contiene la información del master, ahora si yo decido unir la rama-dev con la rama master o main, hacer un
Fast-fostward, porque la rama de misiones completada va tener todos cambios del master

Fast-forward
misiones-completadas.md | 4 ++++
1 file changed, 4 insertions(+)
create mode 100644 misiones-completadas.md

como ya no vamos a ocupar mas la rama vamos a eliminarla

**git branch -d rama-misiones-completadas**

Es este es el **rebase normal** que ayuda actualizar el punto inicial de la mi rama

## git rebase - squash

si yo necesito unificar estos commit puedo hacerlo de las siguiente manera

- e127324 - (6 minutes ago) Actualizamos misiones completadas - volta2016 (HEAD -> master)
- fb24aa3 - (4 years, 6 months ago) Actualizamos dos misiones completadas al momento - Strider

- **i**: Le digo que sea interactivo, esto ayuda a que sea así fácil de trabajar cuando hay muchos cambios
- Luego de esto necesito especificar cuantos comandos quiero > desde que commit quiero empezar hacer rebase

> es importante tener en cuenta que a la hora de usar el rebase interactivo es mejor usarlo si ese cambios están aún en equipo, pero si aplicaste push
> eso quedo así ya es parte de las historia.
> Otra persona pudo haberlo descargado y podemos haber generado
> conflictos de manera innecesaria entonces alguien va tener que resolver

- **el rebase**: la correciones de nombre, de separaciones o de uniones que vamos a ver \*\*hay que aplicarlo solamente si solo si no han salido de nuestra computadora, entonces ahí si funcionan super bien

- **HEAD**: Es la referencia al último commit, podemos igual poner un hash
- Si nosotros queremos los últimos 4 commit podemos poner este cararter "~"
  luego pasamos la cantidad 4 commit antes del HEAD

git rebase -i HEAD~4

**squash**

- Es tomar 2 cosas que se funcionen y trabajen en conjunto
- El squash va ver el commit anterior y los va unir

para salir esc :wq! + enter

luego nos muestra un pantalla con las opciones del nuevo mensaje de commit

- pick be699cf Agregamos el archivo de las misiones completadas
- pick fb24aa3 Actualizamos dos misiones completadas al momento
- pick e127324 Actualizamos misiones completadas
- s a9f5cc3 Actualizamos misiones completadas 2

Rebase 158ba9e..a9f5cc3 onto 158ba9e (4 commands)

**Commands:**

- p, pick <commit> = use commit
- r, reword <commit> = use commit, but edit the commit message
- e, edit <commit> = use commit, but stop for amending
- s, squash <commit> = use commit, but meld into previous commit
- f, fixup <commit> = like "squash", but discard this commit's log message
- x, exec <command> = run command (the rest of the line) using shell
- b, break = stop here (continue rebase later with 'git rebase --continue')
- d, drop <commit> = remove commit
- l, label <label> = label current HEAD with a name
- t, reset <label> = reset HEAD to a label
- m, merge [-C <commit> | -c <commit>] <label> [# <oneline>]
- . create a merge commit using the original merge commit's
- . message (or the oneline, if no original merge commit was
- . specified). Use -c <commit> to reword the commit message.

These lines can be re-ordered; they are executed from top to bottom.
-- INSERT --

1. Podemos escribir squash o poner simplemente el shortcut que es un s
2. si agregamos una s en pick e127324 fusiona al commit superior

para salir esc :wq! + enter

luego em sale una pantalla similar que sale cuando hacemos un commit sin especificar un mensaje:

This is a combination of 2 commits.
This is the 1st commit message:

Actualizamos misiones completadas

This is the commit message #2:

Actualizamos misiones completadas 2

Please enter the commit message for your changes. Lines starting
with '#' will be ignored, and an empty message aborts the commit.

Date: Tue Dec 28 18:20:46 2021 -0300

interactive rebase in progress; onto 158ba9e Last commands done (4 commands done):
pick e127324 Actualizamos misiones completadas
squash a9f5cc3 Actualizamos misiones completadas 2
No commands remaining.
You are currently rebasing branch 'master' on '158ba9e'.

Changes to be committed:
modified: misiones-completadas.md
modified: misiones.md

Lo mejor es dejar el primer mensaje o también puedes editarlo

# Rebase reword

Digamos que quiero actualizar 2 commit el mensaje aplico esl siguiente comando
para tomar los últimos 4 commit

pick: quiere decir que simplemente lo selecciono para que sea parte del procedimiento del rebase interactivo pero el
pick en teoria lo va dejar así como esta

presionamos "a" para poder editar dentro de la pantalla de editor pero no es la manera correcta
