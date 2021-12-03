# tags - Etiquetas

Son una referencia a un commit específico en el tiempo
Puedes colocar el nombre que sea a la etiquetas tales como: nombre, numeros etc.

por ejemplo:

version4.0.0-alpha.6

Para crear un tag hay varias formas:

- Se pueden poner con nombre
- Se pueden poner versiones semánticas

### Con nombre:

**git tag nametag**

por ejemplo:

**git tag superrelease**

**git tag**

Si aplico este comando voy a ver todos los git tag que tengo

**git tag -d nametag**

Comando para eliminar un tag en epecífico

### Con versiones semánticas:

**git tag -a v1.0.0 -m "Version 1.0.0 lista"**

Con este comando creamos un versión semántica, -a se refiere a annotated, -m es para escribir el mensaje.

**git tag -a v0.1.0 004c496 -m "Version Alpha de nuestra App"**

Agregar un tag a un commit en específico en el tiempo. Acá aplicamos el hash para hacer la referencia al commit

**git show v0.1.0**

Con este comando voy a ver toda la información respectiva a la creación de ese tag

Agregar el tag nos ayuda mucho con el tema de versionamiento de la app

V1: versión mayor
0: segundo numero cuando añade cierta funcionalidad a la aplicación, librería o paquete lo que están creando
0: este último significa algún tipo de bug fix -> correcciones de errores

**git tag -a v0.1.0 004c496 -m "Version Alpha de nuestra App"**

Agrega un tag a una versión de un commit antiguo
