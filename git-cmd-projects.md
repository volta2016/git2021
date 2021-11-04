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
