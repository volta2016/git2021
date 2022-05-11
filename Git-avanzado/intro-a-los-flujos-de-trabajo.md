# Introducción a los flujos de trabajo

Tenemos el repositorio central (upstream) donde otros compañeros de trabajo, tenían que hacer un fork, tenia que descargar localmente, hacer modificaciones subirlas a sus respectivos repositorios en github, para después mandarla al repositorio central. Esto no es malo para cuando tenemos compañeros que queremos que trabajen de esta manera aislados del equipo.

Pero esto para otro equipo sería muy lento y engorroso

## el problema de trabajar con un solo repositorio

si diferentes compañeros agregan constantes commit a la misma rama esto va generar conflictos con los compañeros de trabajo, no es que no se puede trabajar de esta manera pero hay formas de trabajar con este tipo de repositorios

![1-repo](/images/1-repo.png)

veamos que el punto morado es el último commit hecho en el master, lugue cada uno del equipo de trabajo crea una rama independiente en la cual ellos solamente están trabajando esa rama se conoce como el
**feature branch** una rama en la cual estoy trabajando nuevas características que posteriormente van ser incluidas al master.

Ahora para revisar las ramas de otros compañeros simplemente tenemos que hacer:

![ramas](/images/ramas.png)

git fetch
git branch -a -> para revisar todas las rama que se encuentran en el repo
git checkout rama-capitan -> para pasarnos a la rama de otra persona

cualquier compañero puede hacer el push para que nuestro repositorio este actualizado

![ramas](/images/2-repo.png)

para eso podemos hacer algo muy similar a esto

git checkout master -> nos pasamos a la rama master
git merge rama-capitan -> es la rama que yo quiero unir al master
git push -> para actualizar el repositorio en github

## también podemos utilizar esa misma forma pero usando los pull request, de esa manera el equipo se entera y puede discutir los cambios ante de unirlos al master

en lugar de pasarme al master y hacer un push al master podemos hacer:

![ramas](/images/3-repo.png)

git push origin rama-silver -> la rama silver es el trabajo que estoy realizando de la persona en pantalla, al hacer esto yo voy subir toda la rama con estos cambios y una vez en github yo puedo hacer un **pull request** para que mi equipo de trabajo se entere de los cambios y de esta forma podemos revisarlo entre todos ante de unirlo al master
