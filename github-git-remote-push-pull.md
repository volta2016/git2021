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
