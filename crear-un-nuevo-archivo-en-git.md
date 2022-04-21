# Pull request

No es mas que una rama que se desprendio en cierto punto de tiempo
en la rama principal y luego cuando nosotros queremos unir la rama, podemos hacerlo mediante un pull request. La idea del pull request **no es que alguien la integre y punto NO**. La idea es que nos sriva para hacer un análisis previo a un merge. **Por ejemplo yo realice una nueva caracteristica en mi App que la tiene que revisar alguien, ante de unirla al main** Debería haber una persona que tenga el conocimiento
suficiente para decidir estos cambios estas bueno o dar feedback de que mejorar, del código que se quiere integrar, le comento que puede causar un conflicto y que hay que resolverlo o simplemente que NO cumple con el estandar de calidad.

un pull request igual todo lo podemos hacer desde github en la parte superior lo pordemos encontrar

![pull](/images/pull.png)

Pero esta vez en lugar de hacer el commit directo al main, lo voy hacer mediante un nuevo pull request. Este pull request me esta pidiendo el nombre de la rama

![pull](/images/new-pull.png)

entonces aplicamos proponer un nuevo archivo, ¿ por qué ? proponer porque esto puede ser cancelado.

Ahora estamos en el punto de proponer un nuevo pull request.
👀 Me dice a que rama estoy intentando mandar el pull request

![pull](/images/proponer-new-pull-request.png)

mis cambios que tengo dentro del patch historia los quiero dejar caer dentro del main, puede ser que ese no fue el caso y lo puedo poner en otra rama.

- También me dice que es compatible unirlo:
  **Able to merge. These branches can be automatically merged.**

agregamos una nota, luego le damos en crear pull request.

![pull-1](/images/proponer-new-pull-request.png)
