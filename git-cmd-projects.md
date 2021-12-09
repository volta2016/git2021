## El primer cmd que vamos utilizar ppsicionados en la raiz de nuestro proyecto es:

**git init**

Este comando inicializa mi repositorio

**git status**

Nos va a dar información, sobre los commit, sobre la rama en la que estamos posicionados.

También tenemos un mensaje de que a estos archivos no se le esta dando seguimiento:

Untracked files:
(use "git add <file>..." to include in what will be committed)

    01-bases/
    cmd-git-config.md
    git-cmd-projects.md

**git add .**

Podemos añadir todos los archivos que no estan trackeados o sincronizados con nuestro repositorio.

Podemos ver como todos los archivos están listos para que se tome una fotografía.

**git reset nameFile**

Ese archivo que nombramos ya no es parte del stage, lo saca del stage.

**git commit -m "nombre primer commit"**

Sirve para tener un registro un historial de nuestros cambios del repositorio, con en registro podemos viajar en tiempo y ver que como
era nuestro proyecto en ese punto.

Si aplicamos este comando podemos ver que que el arbol dtrabajo esta limpio.

Lo importante que ahora tenemos esa fotografía o registro que es el commit.

**git log**

Podemos ve el status o resumen de nuetros commit.

## Branch

**git branch -- master main**

cambia el nombre de la rama

**git checkout -- .**

Re-construye el proyecto a como estaba en el ultimo commit.
Re-construye Los directorios borrados.

**git config --global init.defaultBranch main**

Configura a nivel global por defecto que el nombre de la rama sea de main.
Vamos a notar con esto que automaticamente vamos estar trabajando en la rama main al aplicar el
comando **git branch**

# añadir file: puesta en escena y commits

**git add .**

Con este comando digo a todos los archivos preparalos para una fotografía.
Podemos notar que esta añadiendo los archivos los añade
al stage se agrega al lado del file la letra A.
**Quiere decir de que esta añadido al stage**

**git reset README.md**
Con este comando le estamos diciendo que regresa a su estado anterior de Untracked que lo saque del
stage. Podemos notar el contenido sigue igual dentro del archivo.

**git commit -am "Readme actualizado"**

Nos evitamos hacer los 2 pasos de:
git add .  
git commit -m "commit"

- git commit -am con este comando lo aplicamos los 2 comando en 1 solo.
- Este comando funciona solamente si ya le estamos dando seguimiento al archivo.
- Si esta Untracked posiblemente no lo va añadir.

# Log Repositorio

**git log"**

Podemos ver el historial de nuestros commit
El hash es el identificador único de commit

**git lg"**

Configuramos nuestro alias con el log --all --decorate --oneline --graph
pero con un resumen mas detallado con fechas

# Diferentes formas de agregar commit al escenario

**git add index.html main.html"**

Agrega 2 archivos para la parte principal de mi web o 2 archivos que quiera dejar en mi stage.
Si luego doy git status puedo ver que estos 2 archivos están en el stage con color verde.

**git add \*.html"**

Este comando agregando el \* agrega todos los archivos con extension .html a mi proyecto.

**git add js/\*.js"**

Agrega todos los archivos con extension .js pero que están dentro de un directorio.

(use "git reset HEAD <file>..." to unstage)

    new file:   js/bootstrap.min.js
    new file:   js/jquery.min.js
    new file:   js/main.js
    new file:   js/popper.js

podemos ver que añade todos los archivos del directorio que especificamos dentro de nuestro proyecto.

**Git no le da seguimiento a las carpetas almenos que le agregamos un archivo dentro**

# Diferentes formas de agregar commit al escenario

.gitkeep - Es un archivo que pesa 0 bytes nos serive para decirle a git que agregue una carpeta al repositorio
pero sin ningún archivo que hemos agregado al stage.

para añadir el archivo .gitkeep debemos aplicar el siguiente comando.

**git add uploads/.gitkeep**

**git add css/**

toma todo lo que se encuentra en sus directorios y sub-directorios que se encuentran dentro de la carpeta css
y lo sube al stage.

# Cambios en los archivos

**git diff**

Puedes ver los cambios anteriores y actuales el archivo

Puede ser que al inicio esta sintaxis no es tan sencilla.
Me muestra el lugar donde cambio.

diff --git a/install/instalaciones.md b/install/instalaciones.md
index 87c8a79..8d29750 100644
--- a/install/instalaciones.md
+++ b/install/instalaciones.md
@@ -3,5 +3,5 @@
Seguir estos pasos:

```
-npm install
+yarn install
```

El problema de git diff: es muy difícil de leer

**git diff --staged**

Para ver lo que esta en el stage

## source control

Si veo el **source control** puedo ver los cambios igual pero de una forma visual mas amigable
podemos ver como esta quedando el archivo final.

## Actualizar mensaje de commit

Hay veces donde damos enter a nuestro commit por equivocación esto podemos solucionarlo, si aplicamos
git log podemos ver que esta ese último commit por error.

Como lo arreglo:
Hay varias formas comencemos con la mas sencilla:

**git commit --amend -m "nuevo mensaje"**

Podemos escribir nuestro nuevo mensaje en las comillas, podemos comprobar esto con git log,

- Recordemos que esto commit se aplica para el ultimo mensaje agregado.

Que pasa si olvidamos de agregar algunos cambios a nuestro ultimo commit que deben de ser parte de
de ese último commit, simplemente agregamos la data adicional y guardamos los cambios. Pero nos damos
cuenta que este cambio tiene que ser parte del último pero actualmente esta separado. Hay varias formas
de resolver este inconveniente

**git reset --soft HEAD^**

**Mantendrá sus archivos y revertirá automáticamente cualquier cambio**

Estan estas otras posibilidades
--soft --hard --mix

Hay que tener cuidado porque el reset hard si elimina los cambios.

Analizando nuestro comando **git reset --soft HEAD^**

- HEAD está apuntando al último commit -> si estoy en la rama main quiere decir que este
  es el último commit que se encuentra en la rama main
- En teoría pueden colocar le HASH del commit y para no tener que memorizar el HASH aplicamos el HEAD
  con este singo ^ me mueve al commit antes de HEAD
- Aplicamos git status y vemos que tenemos modificaciones en el archivo que estaba en el stage
- Aplicamos git log y vemos que ya no aparece el último commit si no el anterior a ese, estoy en ese punto anterior

Si vemos la consola notaremos esto:

- Hubo modificaciones
- Esta untracked fuera del stage

- Ahora en teoría podríamos nosotros hacer el nuevo commit y actualizar los cambios del commit

- Si aplicamos un git log nuevamente ya tenemos los cambios

## Preparando un repositorio para viajes en el tiempo

**git commit --amend**

Con este comando podemos entrar en este modo de editor, en cual podemos hacer cambios

- Acá podemos ver lo que incluye la fecha vemos información realmente importante
- Si quiero cambiar el texto puedo ir cambiar con la tecla "a"
- Ahora puedo borrar Agregar el nuevo mensaje

Para salir escribe lo siguiente:

:wq!

**git reset --mixed 272c082**

Es el comando **git reset --** predeterminado y mantiene todos los archivos iguales pero descarta los cambios. Esta es la opción más flexible, pero a pesar del nombre, no modifica archivos.

En teoría este comando tampoco es destructivo, pero saca todo del stage y los cambios quedan listo para que podamos volver añadir y es muy parecido al soft. Luego del comando git reset --mixed luego vamos poner el numero del hash respectivo.

Nuestros files o folder podemos notar que están untracked. Git ya no le esta dando seguimiento a esos archivos, pero los directorios y todos los cambios siguen ahí

**git reset --hard 272c082**

Este comando sería entre comillas es destructivo va dejar todo el repositorio como estaba en ese punto.
Va destruir completamente todos los cambios y eliminarlos del directorio local. Solo use esto si sabe lo que está haciendo

También podemos ver que el head se va moviendo para atrás:

commit 08b5720ca3dfd2adf57414fb07d0be8c7f8b5c8e (HEAD -> master)

**git reflog**

Para restablecer, necesitará una referencia a la confirmación a la que desea volver. Puedes conseguirlo corriendo reflog:

- Muestra las referencia de todo lo que ha sucedido en orden cronológico:

ejemplo:

b3f91e5 (HEAD -> master) HEAD@{0}: reset: moving to b3f91e5 //actualmente posicionado útlimo paso
0d80b53 HEAD@{1}: reset: moving to HEAD^
08b5720 HEAD@{2}: reset: moving to 08b5720
272c082 HEAD@{3}: reset: moving to 272c082
272c082 HEAD@{4}: reset: moving to 272c082
b3f91e5 (HEAD -> master) HEAD@{5}: commit: [git] heroes.md: Robin y Linterna verde

- Aquí vamos observar varios punteros en en el head

- Acá tenemos el hash del commit que nos interesa regresar a ese punto por ejemplo nos regresar a un commit en especial de hace
  2 semanas.

  **git reset --hard 272c082**

- Aplicamos el comando donde queremos regresar. Ahora se debería reconstruir todo mi proyecto.

## Resumen:

**git reset —soft** - me muevo a una posición con todos los cambios respectivos (sacamos del stage)

**git reset --mixed** - me muevo a un punto y deja todo untracked, todos los cambios siguen ahí incluso los de mas adelante en el tiempo, no tenemos los commit sub siguientes

**git reset --hard** - Esto restablece todo y no mantienen los cambios, el head se va moviendo hacia atrás y apunta al último commit

## Cambiar el nombre y eliminar archivos mediante git

Tener en cuenta que lo del rename es un movimiento lo que realmente hace

**git mv destruir-machine.md salvar-machine.md**

ejemeplo: git mv oldFolderName newFilename or oldFileName newFilename

en teoría estoy moviendo de una posición a otra y le estoy cambiando el nombre de paso

si aplicamos **git status** tenemos la información:
renamed: desrtuir-machine.md -> salvar-machine.md

de la manera corta con **git s** podemos ver:

R desrtuir-machine.md -> salvar-machine.md
M ../git-cmd-projects.md

vemos que los cambios estan en el stage con **git status**

(use "git reset HEAD <file>..." to unstage)

    renamed:    desrtuir-machine.md -> salvar-machine.md

agrego el commit y vemos que nuestro cambios apuntan al HEAD main

me voy dando cuenta y mejor digo sabes que este archivo mejor lo voy tener que mejor eliminar

## Para eliminar un archivo de git

**git rm namefile**

aún esta en statge pero si aplicamos el comando:

**git commit -m "commit"**

al hacer esto ya quedo como borrado ese archivo

## Cambiar el nombre y eliminar archivos fuera de git

vamos a cambiar el nombre desde vs code superman.historia.md por superman.md

Podría ser que se pierda toda la historia de contenido de nuestro archivo original.

**git status**

D historia/superman.historia.md
M ../git-cmd-projects.md

tenemos D delete esto es peligroso, por el contenido de ese archivo y registros de historia, acá en este punto es como
si eliminamos el archivo y creamos un punto nuevo, git lo interpreta como eso.

Es muy peligroso cambiar el nombre de forma manual.
aplicamos un **git add .** y **git status**

R historia/superman.historia.md -> historia/superman.md
acá nos aparece una R acá todo lo del archivo orginal antes de cambiar el nombre va ser conservado.
La R no es que se elimino simplemente le cambiamos el commit.

vamos aplicar un **git reset --hard hash**

notamos que git recordo el nombre del archivo original y que antes se llamaba superman.historia.md

- La diferencia es que cuando uno elimina manual no esta en el stage, debemos añadirlo al stage
  **git add .**
  **git commit -m "commit"**

- Podemos ver que cambia el color de la letra D cuando esta en el stage
