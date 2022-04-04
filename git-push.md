# git push

Estos son los comandos básicos que usamos a la hora de crear nuestro
repositorio y hacer nuestro primer commit.

![origin](/images/create-newrepo.png)

**git push -u origin main**

el -u quiere decir que este va ser el repositorio por defecto.

- agregar el **origin** es muy importante a la hora de conectarnos con nuestro repositorio

- Si es primera vez que que vas hacer push github te va pedir autorizar
  el acceso

- luego de aplicar la lista de comando para crear el nuevo repositorio vamos apreciar esto en consola:

![push](/images/comandos-push.png)

**git push** podemos este comando de ahora en adelante para actualizar directamente nuestra nuestra rama principal

si recargamos nuestro repositorio en github deberíamos ver todos
las carpetas y archivos que añadimos a nuestro repositorio.

En este caso ¿ por qué ? hay 32 commit y está creado hace 4 años, esto es porque estamos tomando la sección de código cuando se creó por primera vez. Podemos ver el autor de cada commit con la fecha

- 👀 al momento de dar el comando **git add** debe tomar en cuenta que tiene otro origen remoto y otra carpeta .git

por eso es recomendable aplicar el comando de

**git rm --cached 09-heroes**

![git-rm](/images/git-rm.png)

# Push de los tag en nuestro repositorio

**git tag**

con este comandopuedo ver los tags las versiones

v0.1.0
v1.0.0
v2.0.0

nada esto se ecuentra actualmente en le repositorio de github, yo tengo que manualmente
subirlos. Lo mejor es subirlos todos al mismo tiempo el comando es el siguiente

**git push --tags**

Esto va revisar nuestros tags y los va comparar con nuetro origen remoto

si damos click en el zip nostros descargamos unicamente el contenido de ese repositorio

![git-rm](/images/tags.png)

acá simplemente descargue como estaba el proyecto en ese punto, no es lo mismo clonar
que a descargarlo de esta maneracuando clonamos el respositorio también clonamos la
Historia de git. Esta decarga es, como estaban los archivos en ese preciso momento en el tiempo.

- Podemos ir al Hash de commit no va llevar un punto unificado, podemos ver igual las lineas que se agregaron. En split podemos ver como estaba ante el archivo y como quedo después

- Podemos tocar el signo de mas y añadir ciertos comentarios con : podemos agregar emojis
  a los comentarios

## Releases

Por defecto en este preciso momento lo releases y los tags en este preciso momento son iguales cual es la diferencia entre un tag y release tag. Es que un tag es un punto donde van poder descargar las personas de github

![git-rm](/images/versiones.png)

vamos hacer click en la versión

![git-rm](/images/edit-releases-tag.png)

luego de agregar el comentario el markdown le damos a publish releases

![git-rm](/images/publish.png)

aparte crea un url especifico
