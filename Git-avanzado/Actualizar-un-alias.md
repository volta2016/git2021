# Actualizar un Alias

Con solo hacer **git s**
no me dice la rama, pero yo lo puedo agregar en ese comando

si doy un **git status** me dice la ramas y los cambios que tengo

Your branch is up to date with 'origin/master'.

**git status --short**

es la forma corta de como yo tengo el alias

**git status --short -b**

si adicionalmente le agrego -b o -branch

originalmente me dice como se encuentra la rama local y la rama arriba

**git status -sb**

También hay una forma corta de hacer esto con s de short y b de branch.
Presiono enter y es lo mismo

## master...origin/master

**git status -sb** eso es lo que yo quiero que haga cuando presiono un -> git s

vamos a configurarlo para nuestro alias tenga esas opciones:

git config --global -e

vamos a buscar nuestro alias y le vamos adicionar una linea mas

[alias]
s = status --short

- presionamos a para insertar

podemos adicionarle el **--branch**

[alias]
s = status -sb

una vez hecho eso esc -> :wq1 + enter para salir

luego de eso **git s** y tenemos esta información que es bastante util

## master...origin/master

asi no tengo que estar escribiendo git branch para ver en rama estoy
