# Recuperando una rama en produccion

Primero vemos la versión de nuestro tag

**git tag**

luego aplicamos la versión que queremos recuperar.

**git checkout v1.0.0**

Note: checking out 'v1.0.0'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

git checkout -b <new-branch-name>

HEAD is now at 0926ee8 [git] Capitan america goes mad

Me dice que estamos en un detached HEAD eso esta bien.

Si hago un git lg el head esta apuntando a este tag y esto en teoria esta bien por que este es el tag como yo lo quería que se mantuviera. En este preciso instante en repositorio local
si aplico un

**git s**

## HEAD (no branch)

me dice no branch, es decir me encuentro en un punto especial ubicado literalmente en ese tag

**git checkout -b rama-kit**

creamos esa nueva rama

**git lg**

- 0926ee8 - (3 hours ago) [git] Capitan america goes mad - volta2016 (HEAD -> rama-kit, tag: v1.0.0)

vemos que me encuentro en la rama kit la cual apunta a la version
v1.0.0

En este punto yo puedo hacer un

**git push**

**git push --set-upstream origin rama-kit**

regreso al navegador web recargo, ya tengo la rama kit puedo volver a entrar voy a parte de villano y debria estar Capitan America

si quiero seguir trabajando en el main

**git checkout main**

perfecto ya apagamos el incendio

## Vamos hacer esto pero desde github

pero para eso vamos a borrar la rama, si yo quiero actualizar que también borre la rama de manera local, también quiero que se borre la rama aya arriba

**git push origin :rama-kit**

con este comando ya no existe la rama en el repositorio remoto de github.

Pasa esto y por emergencia deben recuperar esa rama para nuevamente existen los tags.

Muy importante los tags -> los tags marcan un commit no importa en la rama que se encuentren y lo apunta de manera unica

Los tags marcan un commit no importa en la rama que se ecuentren y lo apunta de manera unica y podemos ver que entre a esa versión.
Asi es como estaba el repositorio hay que crearse una rama basado en
eso la versión

![v1](/images/v1.png)

Entonces creo la rama desde github, crear una rama a partir de la versión

![create-branch-v1](/images/create-branch-v1.png)

regreso al código principal y nuevamente tengo la rama-kit como yo la deje y aquí no ha pasado absolutamente nada

si borramos la rama el tag del repositorio, tenemos que aplicar el comando

**git reflog**

y tenemos que buscar el respectivo punto del tiempo del cual queremos construir
