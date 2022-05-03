# Fork clone colaboraciones

Pensemos que tenemos nuestro propio repositorio en github, luego tenemos problemas en nuestra computadora y queremos volver a configurar el repositorio. Simplemente hacemos un git clone y se acabó el problema, tenemos todo el repositorio clonado en nuestra máquina y podemos comenzar a trabajar. Cuando ya estamos listos con los cambios podemos hacer un git push. Aunque el repositorio no es de nosotros pero nos agregan como colaboradores, igual podemos hacer todas las acciones como si ese repositorio fuera de nosotros

![githubflow](/images/repo1.png)

tenemos el caso de un repositorio publico pero nosotros no somos colaboradores. En el repositorio local de nuestra maquina nosotros vamos a poder hacer commits locales, crear ramas todo como si nosotros fuéramos dueños de ese repositorio, pero va hacer imposible hacer push a gihub. Nuestros cambios no lo vamos poder subir a ese repositorio original

![githubflow](/images/repo2.png)

¿ Pero cómo podemos colaborar ?

acá entra el concepto de lo que es un **Fork** que es tomar el repositorio original y clonarlo a un lugar donde nosotros tenemos total acceso a ese repositorio, vamos a tener total acceso a ese repositorio

![githubflow](/images/fork.png)

pero que pasa cuando hacemos la modificaciones a nuestro repositorio y queremos enseñarlas a los dueños del repositorio de google:

- agreguen esta característica
- aquí corregi errores

acá entra el concepto de lo que es el **pull request** piensa que el fork es como una rama adicional que la gente de google maps no tiene ni la menor idea de lo que nosotros estamos haciendo, pero sigue siendo una rama la cual fue unida de regreso al repositorio padre en este caso sería google maps, con la rama nosotros podemos hacer todas la modificaciones que nosotros queramos.
Cuando estemos listo con nuestros cambios para decir a la gente de google por favor revisen ahí entraría el pull request a las personas que tiene total acceso al repositorio de google, ahí ellos van poder revisarlo, avn poder aceptarlo o rechazarlo y si ellos lo aceptan todos su cambios van a ser parte de una rama ala que ellos escojan en ese repositorio, nosotros haríamos una contribución a la librerías de google
