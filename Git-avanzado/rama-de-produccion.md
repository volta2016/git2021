# Rama de producción

Suponemos que tenemos nuestro línea de tiempo, o super aplicación que es lo que nosotros estamos desarrollando. Nosotros vamos a ir avanzando a la versión 2.0, pero sucede que en un determinado tiempo se crea la rama versión 1.1.0 en la cual estoy trabajando en cierta actualizaciones que eventualmente no fueron incluidas en la versión master, pero son necesarias por que llega un cliente. La verdad es que no voy pagar la versión 2, necesito que sigamos trabajando en la versión 1 y se queda de esa manera es una forma de trabajar también.

Que sucede en la vida real, si cobras o cuando hacemos cambios muy dramáticos de las versiones

versiones-ramas

![versiones-ramas](/images/versiones-ramas.png)

## Esto sucede cuando:

- Cuando le damos soporte prologando a una versión en particular o cuando nos pagan para darle mantenimiento a esa versión

- Arreglos en caliente y urgentes

- Cuando nosotros subimos a producción algo, pero constantemente tenemos que estar dando soporte y arreglos cada vez que hay un nuevo despliegue de la aplicación

Esto ayuda mucho a que podamos analizar o el equipo de soporte pueda darnos un feedback de lo que esta pasando para que después podamos aplicar las correcciones.

Cuando un cliente va necesitar un periodo prolongado de soporte a una versión vieja o bien cuando necesitamos darle soporte a una versión de la App nosotros seguimos avanzando. Un ejemplo cuando sale un versión nueva de una librería o framework que usamos, posiblemente todavía le van querer dar soporte a versiones anteriores y nosotros podemos hacer actualizaciones de a lo mismo. Esa es como una dimensión alterna de nuestra App que eventualmente no v terminar uniéndose o puede ser que si. Puede que muerda en cierto punto y hasta aquí llegamos

Hay una forma de hacer esto y otra para mantener la referencia en caso de algo extra.

git branch

\*main

no trabajamos nunca directamente en el main

vamos a crear una rama

**git checkout -b ramakit**

# Villanos

- Dr. Doom
- Red Skull
- Capitan América

en villanos.md actualizamos este archivo, doy commit a los cambios.

Una vez tengo los cambios voy hacer un git push y nos dice que realicemos el upstream origin de la ramas usando el siguiente comando

es mejor hacerlo así nos tira error y no memorizando este comando complejo. esto pasa cuando creamos ramas locales que no están en el remoto

**git push --set-upstream origin rama-kit**

regreso a mi repositorio en github y veo que tengo al rama-kit.
Aquí yo puedo darle soporte especifico por que el cliente ya no quiere versiones mayores no va pagar nada y quiero seguir manteniendo esto. Nada me impide a mi mantener esta rama de manera perpetua la puedo dejar.

Acá podemos ver como trabaja react, así manejan las ramas

![react](/images/react.png)

nada nos obliga a tener que borrar esa rama lo podemos dejar así y eventualmente esté mensajes nos va dejar de molestar.

Eso está bien pero a parte de crearse esa rama vamos a crearnos un tag

**git tag**

v0.0.1

**git tag -a v1.0.0 -m "Kit v1.0.0 - stable"**

subamos estos tag a github

**git push --tags**

Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 318 bytes | 318.00 KiB/s, done.
Total 3 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
remote:
remote: Create a pull request for 'rama-kit' on GitHub by visiting:
remote: https://github.com/volta2016/avengers-tarea/pull/new/rama-kit
remote:
To https://github.com/volta2016/avengers-tarea.git

- [new branch] rama-kit -> rama-kit
  Branch 'rama-kit' set up to track remote branch 'rama-kit' from 'origin'.
  ❯ git tag
  ❯ git tag -a v1.0.0 -m "Kit v1.0.0 - stable"
  ❯ git push --tags
  Enumerating objects: 1, done.
  Counting objects: 100% (1/1), done.
  Writing objects: 100% (1/1), 168 bytes | 168.00 KiB/s, done.
  Total 1 (delta 0), reused 0 (delta 0)
  To https://github.com/volta2016/avengers-tarea.git
- [new tag] v1.0.0 -> v1.0.0

Notemos algo interesante vamos a ver que ese tags yo lo cree en la rama Kit

- 0926ee8 - (40 minutes ago) [git] Capitan america goes mad - volta2016 (HEAD -> rama-kit, tag: v1.0.0, origin/rama-kit)

es un tag creado específicamente en un rama

![releases](/images/releases.png)

publicamos el releases, Esto es importante que nosotros lo hagamos por que, por qué? porque pudiera ser que alguien accidentalmente borro la rama de producción.

Es importante por que si el día de mañana, esta la rama kit y alguien accidentalmente llego y la borro y todavía acá tiene el botón de restore y la recargamos vamos a ver que ya no tenemos eso, pero era importante para nosotros mantener esa rama era la que estábamos trabajando con algún cliente y esa rama era importante y alguien la borro quien diablo borro la rama y podemos ver que todo esto queda en historial, pero a pesar de que la rama no fue unida **el releases tag se mantiene, todavía puedo irme a la rama, tengo los cambios e irme a versión 1.0.0 y veo el archivo el que fue creado.**

La ventaja de hacerlo así, es que no importa si la rama fue eliminada por accidente el tag perdura y si borramos el tag también lo podemos recuperar por que eliminamos el hash y también lo podemos ver en el
**git reflog**

Pero lo importante es que nosotros podemos tener de esta manera un tag que apunta específicamente como se encontraba el repositorio en esa rama especifica.

Entonces en ese punto podemos reconstruir la rama de diferentes manera:

git s

## rama-kit...origin/rama-kit

estoy trabajando localmente en la rama

git push
Total 0 (delta 0), reused 0 (delta 0)
remote:
remote: Create a pull request for 'rama-kit' on GitHub by visiting:
remote: https://github.com/volta2016/avengers-tarea/pull/new/rama-kit
remote:
To https://github.com/volta2016/avengers-tarea.git

- [new branch] rama-kit -> rama-kit

se sube la rama recargo y aqui esta rama nuevamente

![push-rama](/images/push-rama.png)

## Vamos a ver un caso extremo

git s
git checkout main

ya estoy en la rama main y digamos que yo ya se que eso se unió, ya no necesito mi rama kit mantenerla.

git branch -d rama-kit
warning: deleting branch 'rama-kit' that has been merged to
'refs/remotes/origin/rama-kit', but not yet merged to HEAD.
Deleted branch rama-kit (was 0926ee8).

la borramos y cliente nos dice que necesita esa rama porque hay que implementar una nueva característica, no la tenemos ni local, ni en el remoto

**git branch -a**

- main
  remotes/origin/main
  remotes/origin/rama-kit

aquí está por ahí va las cuestion

**git remote prune origin**

solo para asegurarme de que se limpio

**git branch -a**

ya no tengo la rama dejo de existir que hacemos

## Como la volvemos a crear si no tengo la rama
