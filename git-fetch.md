# git fetch

- ejercicio
  desde gitHub desde la carpeta liga de la justicia vamos a crear un nuevo
  archivo .md **historia.flash.md**, vamos agregarle un poco de texto sobre
  la historia de flash

luego de esto nos aparece el commit change, no lo voy hacer mediante pull request simplemente lo voy hacer un commit directamente al main branch.

En este caso nos dice que ese archivo **historia.flash.md** debe ser eliminado. Todo estos cambios que se realizaron se hicieron en el repositorio
en la rama principal.

Si yo en mi repositorio local aplicó un git lg voy ver que no tengo ninguno de esos cambios podemos ver el hash de mi repositorio local está ante que los nuevos comit de agregar el archivo y borrarlos.

![historia remote](/images/history-remote.png)

Puede ser que no queramos hacer un pull request porque cuando entremos nos puede hacer un merge o entre un rebase. NO queremos eso, **solo queremos actualizar la referencias locales**. entonces con un **fetch** podemos actualizar la referencias que están en el remoto, entonces para eso podemos usar el comando:

**git fetch**

![historia remote](/images/gitfetch.png)

acá podemos ver el hash que estaba en nuestro repositorio local el último, pasa actualizarse al último del repositorio remoto y ahora es donde va apuntar el main

pero vemos que estamos posicionado en nuestro ultimo commit pero de nuestros últimos cambios a nivel local queremos apuntar el head los los cambios actualizados para eso aplicamos:

**git pull**

![historia remote 2](/images/remote.png)

![git pull](/images/gitpull.png)

![git lg  git pull ](/images/gitpull2.png)

para que el head se encuentre posicionado y actualizado, hay personas que prefieren hacer un **git fetch ante a un git pull** pero eso depende de cada uno.
