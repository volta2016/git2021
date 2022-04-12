# Github Git remote push pull

tenemos nuestro proyecto con commits con ramas todo listo, llegan un punto donde nosotros
vamos a querer hacer un respaldo de ese repositorio por general en una computadora agena a la nuestra
esto se llama un repositorio remoto. La idea es que nostros estemos en interación con ese servidor remoto
para asegurarnos de que nuestro proyecto esta a salvo. Porque el disco duro de nuestra maquina puede fallar
en cualquier momento.

## Push

Para eso nostros ejecutaremos un comando llamado **push** que es tomar nuestro repositorio o lo últimos
cambios que hemos hecho o los cambios pendientes que no estan en el repositorio y subirlos a ese
servidor

## Push

puede ser que vengan al equipo otras 2 personas nuevas. Esas 2 nuevas personas tiene
que hacer un **pull** para obtener los cambios desde el servidor, es decir yo subo los cambios y otras
2 personas pueden hacer el **pull** para descargarlo. Ahora si una de esa personas hace modificaciones
también va poder realizar un push y yo darme cuenta de los cambios que realizo. Asi podemos trabajar
de forma colaborativa con otras personas

👀 Es importante saber que git no maneja el acceso a repositorio es importante considerar que **git** y
**github** son cosas totalmente diferentes

## Control de acceso

Hosted services

- bitbucket
- Github

## Manejados por nosotros mismos

- Gitosis

## Github

Es una platoforma de desarrolla colaborativo de software. ¿ Por qué ?
github es tan popular

- Repositorios ilimitados
- Páginas HTML y Css JS ilimitadas
- Push, Push, clones ilimitados
- Issues, Wikis, estadísticas ilimitadas

## Agregando un origen remoto

Cuando estamos en nuestro repositorio local y queremos agregar un origen remoto aplicamos el siguiente comando:

git remote add origin seguido del url de donde se encuentra el repositorio

**git remote add origin https://github.com/2022/sass-proyect.hit**

que significa la palabra **add** podemos agregar

**Origin** es un estándar para referirse al origen al origen

![origin](/images/origin.png)

Cuando queremos revisar las fuentes remotas que tenemos en el repositorio ejecutamos:

**git remote -v**

el push siempre va ser del mismo lugar -v\*\*

origin https://github.com/volta2016/ECMASCRIPT.git (fetch)
origin https://github.com/volta2016/ECMASCRIPT.git (push)

si nosotros tenemos 2 o mas tenemos diferentes lineas

![origin](/images/origin-master.png)

## Gitosis

### Qué es ?

[gitosis](https://wiki.archlinux.org/title/gitosis#:~:text=Gitosis%20is%20a%20tool%20which,system%20accounts%20on%20the%20server.)

### Instalación

[gitosis install](https://github.com/res0nat0r/gitosis)

### Guardar su contraseña de GitHub en la máquina WINDOWS

[Guardar usuario y contraseña de GitHub](https://docs.github.com/en/get-started/getting-started-with-git/caching-your-github-credentials-in-git#platform-windows)

### Guardar su contraseña de GitHub en la máquina LINUX

[Guardar usuario y contraseña de GitHub](https://docs.github.com/en/get-started/getting-started-with-git/caching-your-github-credentials-in-git#platform-linux)

### Pull de los últimos cambios en el repositorio de Github

Nosotros podemos editar el readme, hacer cambios desde la web. Si yo voy a mi repositorio local yo no tengo esas modificaciones.

¿ Como puedo hacerlo para obtener esos cambios ?

**git pull**

este comando sirve para traer los datos del origen que esta seteado por defecto.

**git pull origin main**

también funciona para traer los datos. Aunque cuando configuramos por primera vez nuestro repo
el origin lo configuramos por defecto con la rama main

**git remote -v**

podemos ver el pad de donde se encuentra nuestro repositorio

origin https://github.com/volta2016/git2021.git (fetch)
origin https://github.com/volta2016/git2021.git (push)

luego de aplicar el **git pulll** vemos que se aplica un mensaje y nos muestra el Fast-fordward significa que avanzó al último punto mi repositorio local, los cambios no dan conflicto con mi repo que tengo actualmente, si lo cambios dan conflicto entro al modo de problemas manualmente aceptando cambios o desechando cambio, luego debo hacer un commit
de esos inconvenientes.

### Warning - Pulling without reconcile strategy

![wp](/images/warnign-pull.png)

git config pull.rabase - false solo va usar el merge
git config pull.rebase true - cuando vengan los cambios va aplicar un rabase
git config pull.ff only - solo va aplicar esto si puede aplicar un Fast forward

vamos a hacer una nueva configuración global.

**git config --global pull.ff only**

para poder ver que esta configurado

**git config --global -e**

vemos que esta en las tecnicas del pull

esc :q! para cerrar

aplicamos **git pull**

![ff](/images/ff.png)

podemos apreciar que mis cambios locales perfectamente pueden ser
movidos al punto en cual mi repositorio local se encuentra

vamos aprenciar que el head esta apuntando al ultimo commit, tambien aparece el origin main.
Origin es el repositorio remoto, no necesariamente lo vamos tener como origin, simplemente es un estandar pero podemos tener diferentes origenes. Entonces el orgin hace referencia al repositorio de github que tenemos actualmente

## Clonar un repositorio

Para clonar un repositorio simplemente no posicionamos con cd en la carpeta donde queremos
descomprimir nuestro archivo y ejecutamos el siguiente comando:

**git clone https://github.com/volta2016/git2021.git**

esto es mediante HTTPS

## Subir cambios locales a remoto

Tenemos cambio en nuestros archivos luego de esto con el comando:

**git commit -am "name commit"**

este comando va renombrar el útimo commit

![ff](/images/lg.png)

luego de esto con **git push** subimos los cambios.

- Los conflictos se generan cuando modificamos la misma linea en 2 lugares diferentes.

## git Pull Rebase

La estrategia que usualmente se recomienda es el fast forward por que evitamos problemas. Cuando tenemos inconvenientes de actualizar cambios que están es la misma línea, nosotros manualmente le vamos a especificar como queremos que trabaje la parte del **pull**

para eso vamos aplicar el siguiente comando:

**git config pull.rebase true**

esto hace una configuración local a este repositorio, ya vamos a ver para que esto sea la configuración por defecto

ahora vamos a intentar hacer un git pull nuevamente

![conflict](/images/conflict.png)

en este punto yo me encuentro en medio de un rebase

(no branch, rebasing main)
que queremos hacer mantener los cambios que vienen de github o mis cambios. Nosotros
vemos que queremos aceptar

vamos grabar los cambios, git status vamos a ver que aún estoy en git interactivo, agregamos
nuestro commit para actualizar, aplicamos un mensaje descriptivo de nuestro commit

- git commit -m "unificamos lógica cart"

por ejemplo, si damos git status no debe decir que estamos trabajando en un árbol limpio

![conflict](/images/conflict.png)

git rebase continue es lo que yo debo aplicar después de mi commit y nos dice que el
rebase se logró de manera exitosa.

finalmente aplicamos un **git push** y revisamos nuestro repositorio que este nuestro último commit

para configurarlo de manera global en toda la computadora por defecto podemos usar

**git config --global pull.rebase true**

# Errores

siempre que damos un push y si tenemos cambios que se realizaron en gihub desde el
navegador nos va mostrar este error en consola:

![errores-push](/images/errores-push.png)
