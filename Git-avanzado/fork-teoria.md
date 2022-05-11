# Actualizando nuestro Fork - Teoría

Cuando tenemos un compañero pero no confiamos en el como para darle acceso a todo el repositorio le decimos que realice un fork.

Tenemos nuestro repositorio central en github que en este caso lo vamos a llamar upstream, llega batman y el hace un fork del repositorio completo, el esta trabajando ahí de forma aislada. Luego llega superman y hace un fork del mismo proyecto en este punto del tiempo ambos repositorios se ven iguales. ninguno de los 2 ha hecho cambios, batman y superman hacen un clon a su repositorio local, ambos hacen cambios locales, hacen push a si respectivos repositorios en github, luego para que estos repositorios actualicen el upstream en este caso el repositorio central ellos tienen que hacer pull request,

Cómo podemos actualizar nuestro fork ? como podemos saber los cambios que realizo superman y tenerlo en nuestro repositorio, para poder realizar trabajos, porque puede ser que superman haga cosas que nosotros ocupamos en nuestro repositorio

![upstream](/images/upstream.png)

tanto batman como superman deberían hacer un pull del upstream, posteriormente ellos pueden hacer cambios locales, hacer push a sus respectivos repositorios y luego hacer una solicitud de un pull request para que estos cambios sean aceptados en el upstream (repositorio central)

Cómo podemos hacer eso si nosotros ya tenemos un remoto en nuestro git local ?

simplemente tenemos que agregar un nuevo remoto y luego tenemos que hacer un fetch o un pull para actualizar nuestro repositorio local,
luego puedo hacer un push y un pull request otra vez

![upstream](/images/add-upstream.png)

## Actualizar nuestro fork Práctica

![upstream](/images/1-upstream.png)

Actualmente en la rama principal en el dueño del repositorio, nos dice que nuestro repositorio local está atrás por 1 commit.

Upstream nos dice que está un commit adelante quiere decir el repositorio original, entonces tenemos 2 opciones comprarlo o hacer el merge.

![upstream](/images/lineas-cambios.png)

Vamos a compararlo vamos la líneas de código donde muestra los cambios y me pregunta si quiero hacer un pull request de esos cambios.

![upstream](/images/createpull.png)

simplemente compare y ahora voy hacer el **fetch and merge**

ahora me dice que de manera exitosa se hizo el fetch y se unió todo desde el upstream que sería Klerith master.

![upstream](/images/fetched-and-merge.png)

El upstream es el repositorio del cual yo hice el fork, entonces veo que hay commit que no tengo actualizados como ejemplo que realizo el merge de tal persona.
Yo no tengo esa información local o historial de commit de que fue hecho el merge, pero como lo tengo en mi repositorio que realice el fork, puedo realizar un:

**git pull**

aplicamos **git lg** y deberíamos ver el historial actualizado, incluso podemos ver la separación de la ramas y todo esta bien.

## ahora lo vamos hacer todo a través de la consola

Vamos agregar unos cambios en repositorio original el upstream, vamos hacer un commit directamente al master 👀 todo esto es directamente desde github.

El mismo procedimiento del compare y el fetch and merge ahora lo quiero hacer a traves de la consola.

**Para hacer eso yo necesito la referencia del repositorio oficial, del repositorio del cual yo hice el fork, obviamente tengo que tener acceso de lectura o que sea del un repositorio publico o tener acceso de lectura para por lo menos hacer esto.**

Copio todo el url HTTPS de code, regreso a la terminal aplico lo siguiente en la terminal

**git remote -v**
origin https://github.com/volta2016/legion-del-mal.git (fetch)
origin https://github.com/volta2016/legion-del-mal.git (push)

Aquí estoy obteniendo mi origin, usualmente si es un repositorio donde solamente yo voy traer información, es conocido como upstream.

Entonces vamos añadir un nuevo repositorio remoto

**git remote add upstream path**

**git remote add upstream https://github.com/Klerith/legion-del-mal.git**

siempre al final va el path al cual donde quiero que este asociado ese upstream voy presionar enter. Si no aparece un error es es buena señal, ahora vamos ver que tenemos el origin y el upstream
que aunque diga push y fetch sabemos que no podemos hacer push a ese repositorio, porque no tenemos acceso de escritura hacia el y tenemos acceso de lectura

origin https://github.com/volta2016/legion-del-mal.git (fetch)
origin https://github.com/volta2016/legion-del-mal.git (push)
upstream https://github.com/Klerith/legion-del-mal.git (fetch)
upstream https://github.com/Klerith/legion-del-mal.git (push)

ahora ya podemos el fetch si nosotros queremos ver los cambios o podemos hacer el pull para trear toda la información

**git pull upstream master**

![current](/images/current.png)

luego aplicamos un commit y el

git rebase --continue

ahora todo esta perfecto ahora solo subamos los cambios
