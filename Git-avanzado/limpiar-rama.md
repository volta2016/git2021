# Limpiar rama

Tengo la rama misiones que no es mía, entonces cómo hacemos para hacer limpieza.
Primero tengo que regresar a la rama **main** no tengo la rama de las misiones, pero no importa
porque yo se que todo eso se encuentra en nuestro main de repositorio remoto.
Todo eso ya fue unido mediante el pull request, aquí queda mucho a nuestra discreción de qué hacer.

Podemos hacer el merge de la rama, aunque lo ideal es que realicemos mediante pull request y luego en el main solamente aplicamos un git pull. Para bajar los ultimos cambios que se encuentran en el repositorio remoto.

remote: Enumerating objects: 1, done.
remote: Counting objects: 100% (1/1), done.
remote: Total 1 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (1/1), done.
From https://github.com/volta2016/avengers-tarea
7920595..5d38bdb main -> origin/main
Updating 71c1575..5d38bdb
Fast-forward
misiones.md | 4 ++++
villanos.md | 5 +++++
2 files changed, 9 insertions(+)
create mode 100644 misiones.md
create mode 100644 villanos.md

si yo hago un
**git branch** solo estan las 2 ramas

- main
  rama-misiones
  rama-villanos

con **git branch a**

voy a ver las demás ramas que a mi no me sirven de hecho en repositorio remoto no las tengo.

Comenzamos por la más fácil

**git branch -d rama-misiones**

me dice que no es posible eliminar la rama de misiones porque el remoto ya no contiene ese referencia y me dice que fallo hacer el push a ese repositorio, la rama-misiones ya no esta aqui nosotros la borramos desde github

![ramas-repo](/images/ramas-repo.png)

**git push origin :rama misiones**

este comando lo hubiera removido de manera local y también hubiese actualizado github, pero nosotros lo borramos desde github entonces que aquí este comando no se puede.

Vamos hacer lo mismo pero el nombre de la otra rama

**git push origin :rama-villanos**

To https://github.com/volta2016/avengers-tarea.git

- [deleted] rama-villanos

puede decir un mensaje de error cuando la rama no existe en el remoto tampoco

Existe algo interesante que como ya esas 2 ramas ya no existen en el remoto, si existieran el comando anterior las limpiaría, pero tenemos otro comando muy interesante:

**git remote prune origin**

Esto va revisar las ramas que en el remoto no existen y otras cosas. Va revisarlas pero va actualizar también la referencias

URL: https://github.com/volta2016/avengers-tarea.git

- [pruned] origin/rama-misiones

si aplico un **git branch -a**

- main
  remotes/origin/main

voy a ver que efectivamente ya las otras 2 ramas fueron limpiadas de mis referencias locales.

Cuando una rama ya no tiene razón de existir o trabajar en ella
borremos la, igual existen las ramas históricas para darle seguimiento a bug fixes y seguir manteniendo esa rama, no hay límite pero queda discreción como trabaja el equipo
