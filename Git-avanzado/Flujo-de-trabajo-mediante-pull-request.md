# Flujo de trabajo mediante pull request

Hay que hacer incapie de que no debemos trabajar directamente en la rama main, puede que estemos realizando commit y digamos mejor todo esto desechemoslo o pueda que trabajameos en otra característica mas urgente y luego continuamos el trabajo. Por eso es importante que siempre trabajemos en rama, pero como minimo debemos trabajar en ramas independientes esas ramas usualmente reciben el nombre de:

**feature branch**

es decir una rama en cual estamos implementando una nueva característica de la aplicación

**git checkout -b rama-villanos**
Switched to a new branch 'rama-villanos'

aqui nos dice que efectivamente nos movimos a la rama

creo un commit y ya tengo los cambios localmente, pero si voy github yo los cambios no los veo, no veo nisiquiera la rama y en branches solo voy a ver la rama main porque es la unica que tengo

Como subo esta rama por que puede ser que esta es una característica que me esta tomando tiempo hacer y quiero que este respaldada en la nube por si acaso le pasa algio a mi repositorio local. La rama principal siempre se llama main o master. Ahora si yo creo una rama de igual manera yo puedo hacer, push, pull o fetch puedo hacerlo mismo, incluso crear tags en esa rama

## Cómo hago para subirla?

La manera mas facil para evitar memorizarse un comando muy largo, estando en la rama villano vamos hacer un push y me va fallar, me sale este mensaje:

fatal: The current branch rama-villanos has no upstream branch.
To push the current branch and set the remote as upstream, use

    **git push --set-upstream origin rama-villanos**

me dice que rama-villanos no tiene un upstream branch, en mi parte de Github no conoce esa rama, incluso me da el comando para crearla y también que me acepte esos cambios

**git push --set-upstream origin rama-villanos**

lo prefrible es que te tire el error o te memorizas el comando, al copiar y pegar ese comando vemos que tenemos una nueva rama

![--set-upstream](/images/--set-upstream.png)

nos muestra un mensaje que la rama villano tiene nuevos cambios que fueron hace 1 minuto, también nos aconseja compararlo y hacer un pull request

ahora si voy al main con:

**git checkout main**

vamos a ver que el archivo de villano no esta ahí, entonces vamos a github vamos a comparar y hacer un pull request, si no aparece el botón podemos llegar a la pestaña del pull request mi rama-villano la quiero unir con la rama main podemos utlizar markdown para agregar una nota. Creando el pull request los miembros del quipo van a ser notificados.

![merge-pull-rama-villanos](/images/merge-pull-rama-villanos.png)

agregamos unos cambios al archivo villano y damos push y vemos que me automaticamente me sale el nuevo commit con las nuevas modificaciones.

![modificaciones](/images/merge-pull-rama-villanos.png)

seleciono **merge pull request** -> un merge commit

![modificaciones](/images/merge-pull-rama-villanos.png)

acá nos dice que nuestra rama fue perfectamente unida y puedo borrar la rama pero aún no lo voy hacer

puedo borrar la rama directamente desde github, si vuelvo al proyecto voy a ver que solo tengo una rama activa, pero si vuelvo a vs code a mi repo local aún existe la rama, si me muevo al master.

git checkout main

voy a ver que no tengo el archivo de los villanos, eso esta bien. Estando en el main ahora puedo hacer un pull. al hacer un **pull**
me va trear la información de como se encuentra en mi repositorio
y acá estan todos los cambios, perfecto ya no necesito la rama villanos local como la borramos:

**git branch -d rama-villanos**

si la rama tiene cambios que no hemos unidos nos va preguntar git y podemos agregar el forze -f que a la fuerza borra esto, sin importar que hayan commits que no he unido

**git branch -d rama-villanos -f**
