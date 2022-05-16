# Feature branch

Voy crear desde github un rama que se llame rama-misiones

![crear-rama-desde-main](/images/crear-rama-desde-main.png)

como la rama no existe github me dice crear una rama-misiones que sale a partir del main, que es exactamente lo que necesito, si no necesitamos que se separe del main tendríamos que estar parado en la rama respectiva, vamos que la rama fue creada y nos encontramos en la rama misiones.

acá la podemos observar

![crear-rama-desde-main](/images/crear-rama-desde-main.png)

en la rama misiones yo voy a venir y me voy crear un nuevo archivo

![rama-misiones](/images/rama-misiones.png)

vamos a crear un archivo que se va llamar misiones.md
podemos dejarle el mensaje del commit que se creó el archivo de misiones.

Ahora me pregunta si quiero comparar y hacer un pull request - comparar. Por ahora lo vamos dejar así y regresamos a nuestro main.
Al regresar al main el mensaje del pull request eventualmente se va quitar. Vamos a ver que no tenemos el archivo de misiones, si me voy a la **rama-misiones** Pues si lo tengo, pero en main no.

Esto pasaría si un nuevo compañero está trabajando en una nueva rama. Vamos a nuestro repo local vamos hacer un git pull

**git pull**
remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 1), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (4/4), done.
From https://github.com/volta2016/avengers-tarea
71c1575..7920595 main -> origin/main

- [new branch] rama-misiones -> origin/rama-misiones
  Already up to date.

No debería traer nada pero si se trajo la rama de misiones, eso no sucede siempre, por defecto actualmente si lo hace, pero no siempre sucede esto. En este caso no era que sucediera. pero puede ser que cuando hacemos el git pull no hace referencia de la rama misiones.

Para hacer es debemos aplicar:

**git pull --all**

trae la rama de mi compañero de trabajo

al hacer git branch localmente estamos viendo solo nuestra ramas o las ramas en las cuales hemos participado, pero yo se que localmente tengo la rama de otra persona

Esto es para no generar conflicto si alguien trabaja en otra rama es algo del día a día

para ver todas esas ramas que están tanto locales como remoto
aplicó:

**git branch --all**

main

- rama-villanos
  remotes/origin/main
  remotes/origin/rama-misiones
  remotes/origin/rama-villanos

como lo hago para pasarme a esa rama.

**git checkout rama-misiones**

Branch 'rama-misiones' set up to track remote branch 'rama-misiones' from 'origin'.
Switched to a new branch 'rama-misiones'

me dice que ahora le va hacer track a la rama-misiones rama remota desde el origin

si escribo

**git branch**

tengo la rama-misiones y es mas miro ahora ya literalmente las misiones. En este punto estamos exactamente igual parado en punto donde el compañero dijo hey revisen mi código. lo cual es bastante útil. Digamos que el compañero por alguna emergencia se tiene que ir usualmente le vamos a decir que tiene que hacer sus cambios, porque si no vamos a entrar a modo conflicto, por literalmente estamos trabajando sobre la misma rama. Entonces vamos a revisar el código y el finalmente va tener que hacer un git pull del los cambios de esa rama.

Le faltaron unos cambios y los vamos agregar

# Misiones

- Investigar los planes del Dr. Doom
- Capturar a Red Skull

grabamos los cambios en este punto yo realice cambios en su rama y todavía no la estoy unciendo a ningún lugar simplemente modificaciones y voy hacer el commit

git add .
git commit -m "[git] misiones actualizadas"
git push

acá me dice si rama misiones tiene cambios y si quiero hacer un pull

![pull-misiones](/images/pull-misiones.png)

en la rama misiones tengo los cambios que recien di push
y vamos a iniciar un pull request y notamos que github no esta notificando, el primer botón es la forma más fácil, pero lo podemos hacer manualmente con el segundo botón y nos pregunta donde lo deseamos unir a qué rama. Luego vamos hacer merge para aceptar los cambios lo confirmamos

![all-checks](/images/all-checks.png)

![all-checks](/images/confirm-merge.png)

![delete-rama-misiones](/images/delete-rama-misiones.png)

borramos la rama misiones desde el remoto, regresamos a la raíz y vemos que no la tenemos pero si regresamos al repo local, incluso los cambios

![delete-rama-misiones](/images/delete-rama-misiones.png)

**git branch**

vamo a ver que tengo la rama misiones

main

- rama-misiones
  rama-villanos

  main

- rama-misiones
  rama-villanos
  remotes/origin/main
  remotes/origin/rama-misiones
  remotes/origin/rama-villanos

  vemos que dejamos varia basura en el workflow
