# Ramas, uniones, conflictos y tags

Una rama en git no es mas que línea en el tiempo de commits, una nueva rama
es una línea en tiempo totalmente a parte.

## Merge - Uniones

aplicamos merge cuando queremos unir una rama con otra
hay 3 posibles escenarios que pueden suceder de un merge:

### Fast-fostward

Se dispara cuando git detecta que no hay ningún cambio en la rama principal y los cambios
se pueden integrar de forma transparente cada uno de los commits formara parte de la rama principal.
Cada uno de los commits formara parte de la rama principal como si nunca las hubiéramos separado, esa
característica se puede desactivar si no la queremos.

### Uniones automáticas

Git detecta que en la rama principal hubo algún cambio que en la rama secundaria desconocen, pero cuando nostros
intentamos hacer el merge git dice:

- No se modificaron lineas iguales no hay conflictos lo puedo unir de forma automática, git lo hace sin ningún problema, marcando
  que en este momento ambas ramas se unieron

### Unión manual

Acá git no puede resolver esto de forma automática por ejemplo:
tenemos la rama 1 y rama 2:
En la rama 2 nosotros hicimos alguna modificaciones que también afectan las mismas lineas los mismos archivos en la rama
que nosotros queremos unir los cambios.

Cuando git quiere aplicar estos cambios nos va a decir que no se puede y va entrar en un modo de conflicto:

- Git nos va pedir resolverlo de forma manual y una vez resolvemos ese conflicto Git crea un commit nuevo que se conoce como el
  **merge commit**

luego ya podemos ir trabajando son ningún problema.
