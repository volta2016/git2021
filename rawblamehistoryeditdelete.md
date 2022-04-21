## raw

Será el archivo en crudo, vamos a ver como se el archivo en txt pero en la web, podemos copiar ese url.

# blame

Sirve para ver ciertas acciones de las personas, blame va decir que cambios a sufrido desde su creación, es muy util para saber quien realizo ciertos cambios, vamos a ver la foto de perfil de la persona. En la historia podemos ver como se han
movidos los cambios especialmente la fecha. Si muestra el perfil hay que tener en cuenta que diga verificado.

Tambien puedo viajar en el tiempo en esa posición es específico.

![edit file](/images/blame.png)

prestemos mucha antención que tiene el icono de su rama, vamos a notar que tenemos el main, pero nos movimos fisicamente a ese commit, en teoria cada commit que realizamos se puede considerar como una rama

# edit

editamos el el archivo el github

# delete

eliminamos el archivo, para eliminar un archivo debo confirmar con un commit

![edit file](/images/state-pull.png)

En este preciso momento nostros podemos generar un debate sobre el commit,
podemos destruir y cerrar el pull request con el suguiente boton:

❌ close with comment

también podemos hacer un squash o un rebase con un merge

#1 el numeral es para identicar al pull request

- merge commit -> es nuevo commit en el cual se hace esa adición
- squash and merge -> es lo mismo cuando hacemos el rebase interactivo y le especificamos la opción del squash, siginifica que voy tomar estos cambios y los voy a funcionar con el último commit realizado, en pocas palabras es como si no se
  creara un commit independiente par el que realiza el commit.

- Vamos a probar la primera opción -> confirmar merge

![merge-pull](/images/merge-pull.png)

Cuando terminamos de hacer un merge de un pull request significa que la rama en teoría ya no tiene ninguna utlidad, todavía puedo estar trabajando con esa rama.
pero este caso ya se unio la rama no tiene sentido la podemos eliminar directamente desde git y si la borramos por equivocación la podemos restaurar.

![succes](/images/success.png)

la historia no la tengo se ha creado en github o realizo el cambio otra persona
como lo obtengo con **git pull** se trae los cambios, podemos ver los cambios
indentificando #1
