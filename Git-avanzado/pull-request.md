# Pull request

![gitclone](/images/nuevos-comit-repofork.png)

## Fetch upstream

Hace un fetch de repositorio del cual realizamos el fork, pero el botón que nos interesa es el de **contribute**.

Le damos a **contribute** y vemos que esta rama está commit adelante del master desde acá comenzamos con el pull request

![gitclone](/images/contribute-ahead.png)

hasta este punto perfectamente podemos seguir

![gitclone](/images/comparingchanging.png)

en este preciso momento aún no está el **pull request** ejecutado
Github no muestra el movimiento que se va hacer en el pull request, vemos la rama que yo apunto con mis cambios hacia la rama que se se encuentra en el repositorio remoto, cada commit es único y tiene su respectivo hash

👀 si aún no ha sido aceptado el pull request y me faltó realizar un cambio todavía puedo realizar commit al rama quequiero actualizarr

![gitclone](/images/third-commit.png)

## Creando pull request

![gitclone](/images/create-pull-request.png)

agregamos el título y marcamos el checkbox. En este punto le va llegar un correo a la persona que creo el repositorio o a todos los colaboradores que pueden hacer la revisión de este pull request

- Nos notifica que no tiene conflictos

![gitclone](/images/no-conflicts.png)

si marcas el botón de
**close pull request** lo cierras el que iniciaste, por algún motivo en que necesites agregar algo mas o simplemente cancelar

## Pull request part 2

ahora nos queda que el dueño del repositorio o alguien que tiene acceso de escritura, pueda aceptar o rechazar el pull request vamos a poder continuar

Este es el usuario que creo la legión del mal, vamos a irnos a la pestaña de pull request

![ventana-pullrequest](/images/ventana-pullrequest.png)

esto significa que es un pull request que esta abierto

![ventana-pullrequest](/images/open-pull.png)

el color morado quiere decir que esta fusionado y el color rojo quiere decir que esta cancelado. En este punto voy revisar como administrador y voy ver que es lo realizo la persona que solicitó el pull request, vamos revisar los pull request:

![lista-pull](/images/lista-pull.png)

borro una línea de código, entonces hay varias cosas que uno puede hacer, entonces puedo hacer comentarios.

![comentarios](/images/comentarios.png)

en teoria el otro usuario ya puede ver los comentarios

![comentarios](/images/comentarios-dev.png)

ya podemos darle a reply, y si vamos al usuario dueños del repositorio podemos marcar que ya se resolvió **resolve conversation**

Llega un punto de tomar la decisión que hacer, como dueño del repo me muestra toda estas opciones, ninguna de esas me cancela el procedimiento todo estos son como positivos para unirlos, ahora lo que podemos hacer es irnos a filechange.

En este punto como dueño del repositorio, puedo ver
review changes

![review-changes](/images/review-changes.png)

podemos aprobarlo o en pocas palabras solicitar cambios

![request changes](/images/request-changes.png)

acá voy a marcar request changes, doy en submit review. Ahora cambia esto y tengo la parte de cambios solicitados

![changes requested](/images/changes-requested.png)

La tarea del dueño del repositorio ya termino. El que hace el pull request se puede dar cuenta que le han solicitado cambios con estos pasos previos.

Entonces esta persona que revisando me esta pidiendo los cambios

![users repo](/images/users-repo.png)

Esto va realizar una lista de toda las personas que hayan revisado mi código que hayan solicitado cambio por no solamente puede ser 1 pueden ser un montón de personas, entonces voy hacer los cambios que me solicitaron.

Lo idea es no hacer un ctrl z si no un git lg para viajar en un punto en específico, vemos que lo borramos lo que nos solicitan en un commmit así que volvemos al commit anterior

![lg-pul](/images/lg-pull.png)

quiero revertir únicamente este archivo lo demas quiero que quede igual tomamos el hash

agregamos el hash y el nombre del archivo

**git checkout 7b118971 miembros.md**

se actualizo un path, entonces vamos hacer un nuevo commit con esa reversión, doy push con un nuevo commit y en teoría ya hice lo que me pidieron, podemos agregar a la persona encargada de revisar el repositorio con un comentario.

La persona que revisa el repositorio tiene una opción más fácil
de revisar los cambios

![cambios](/images/cambios.png)

esto son los últimos cambios, ahora marco Approve

un merge y un squash cualquiera de lo 2 sirve

![create-newcommit](/images/create-newcommit.png)

después confirmamos con un mensaje lo que se está actualizando marcamos

confirm squash and merge

al final cuando este todo ok se marca de color morado

![merge-ok](/images/merge-ok.png)

luego nos notifica por correo cuando esta ok
