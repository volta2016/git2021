# Crear alias

Para esto podemos añadir ciertos comandos o ciertas banderas como por ejemplo

**git status --short**

Me muestra el consola un resumen muy condensado de la información que yo realmente quiero
saber cuando aplico un git status:
M index.html

El archivo index.html fue modificado muestra solo información mas precisa.

## Hay un camino corto de hacer esto - Es creando nuestros propios alias

Los alias no son mas que comandos de git bastante largo que son resumidos como
una forma corta.

## ¿Cómo creo mi propio alias?

Después del punto agregamos como queremos a llamar a nuestro alias, seguido de la
acción de comando que queremos que ejecute entre comillas.

**git config --global alias.s "status --short"**

luego puedo ir a ver las configuración global para ver si se agrego correctamente con el
siguiente comando:

**git config --global -e**

## Log Info sobre ramas

Podemos aplicar una forma corta resumida del comando **git log** muestra el hash
y commit, el comando es el siguiente:

**git log --oneline**

lo que muestra la consola
b82670c [git] styles add
3092c84 [git] folder uploads add .gitkeep
