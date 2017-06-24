# Fichero readme del repositorio PracticaGit

Este fichero contiene las preguntas y respuestas especificadas en la practica.

**Pregunta 1:**

¿Qué comando utilizaste en el paso 11?,¿Por qué?:

**Respuesta 1:**

`$ git reset --hard HEAD~1`

Permite eliminar el ultimo *commit*, añadiendo el parametro *--hard* los cambios en el **Working Copy** tambien se pierden.

**Pregunta 2:**

¿Qué comando o comandos utilizaste en el paso 12?, ¿Por qué?:

**Respuesta 2:** 

`$ git reflog`

`$ git reset --hard <id_commit>`

`git reflog` lista todos los **commits** por los que hemos ido pasando en el repositorio y el orden en el que se ha hecho, se puede encontrar el *id* del **commit** que hemos eliminado y a través de `git reset` con el parametro *--hard* y este *id*, recuperarlo. 

**Pregunta 3:**

El `merge`del paso 13, ¿Causó algún conflicto?, ¿Por qué?:

**Respuesta 3:**

No, ya que en este caso la rama *styled* que absorbe a la rama *master* se encuentra por delante formando una lista y por lo tanto se puede decir que *styled* ya ha absorbido a *master* antes del `merge`, *master* ya forma parte de *styled*, de ahi que **git** muestre el mensaje **Already up-to-date** . 

**Pregunta 4:**

El `merge` del paso 19, ¿Causó algún conflicto?, ¿Por qué?:

**Respuesta 4:**

En este caso SI, al querer absorber la rama *htmlyfi* por parte de *styled* git se da cuenta que se ha modificado el mismo fichero, en las mismas lineas en las dos ramas y es necesario corregirlo.   

**Pregunta 5:**

El `merge` del paso 21, ¿Causó algún conflicto?, ¿Por qué?:

**Respuesta 5:**

No se han presentado conflictos, se ha realizado un `merge` de tipo **Fast Forward** ya que las ramas que intervienen en el `merge` forman una lista de manera que ha sido suficiente con que el puntero *master* se desplazase hasta el **commit** al que apunta el puntero de la rama *styled*.

**Pregunta 6:**

¿Que comando o comandos utilizaste en el paso 25?:

**Respuesta 6:**

Se ha utilizado un único comando pero acompañado de varios parametros:

`$ git log --graph --decorate --pretty=oneline`

Hubiera sido posible también definir un *alias* para evitar tener que utilizar tal cantidad de parametros, basta con definirlo en la configuración de *git* de la siguiente forma:

`git config alias.<nombre_alias> "comando_completo_a_ejecutar"`

**Pregunta 7:**

El `merge`del paso 26, ¿Podría ser **Fast Forward**?, ¿Por qué?:

**Respuesta 7:**

Si podría serlo, ya que en este punto, *master* se encuentra un commit por debajo de *tittle* y forman una lista continua por lo que sería posible realizar el `merge` desplazando el puntero de *master* hasta el lugar donde se encuentra el puntero de *tittle*.

**Pregunta 8:**

¿Qué comando o comandos utilizaste en el paso 27?:

**Respuesta 8:**

Para deshacer el `merge` que acabamos de hacer, lo que implica deshacer el útlimo *commit* que se ha creado al hacer el `merge --no-ff'` no fast forward pero sin perder los cambios (manteniendo el titulo), utilizamos el comando `reset` que hemos utilizado en otras ocasiones pero esta vez sin el parámetro `--hard` para así poder conservar los cambios:
 
`$ git reset HEAD~1`

**Pregunta 9:**

¿Qué comando o comandos utilizaste en el paso 28?:

**Respuesta 9:**

Para descartar los cambios del *Working Copy* utilizamos el comando `checkout`:

`$ git checkout -- git-nuestro.md`

**Pregunta 10:**

¿Qué comando o comandos utilizaste en el paso 29?:

**Respuesta 10:**

Para eliminar la rama *tittle* utilizamos el comando:

`$git branch -D title`

**Pregunta 11:**

¿Qué comando o comandos utilizaste en el paso 30?:

**Respuesta 11:**

Utilizamos `reflog` para acceder al listado de todos los *commits* que se han ido realizando, seleccionamos el *id* del que corresponde al `merge` del paso 26 y ejecutamos el comando `reset`como se muestra a continuación:

`$git reflog`

`$ git reset --hard b27cbe2`

Se puede ver que se ha realizado de forma correcta puesto que git nos muestra:

**Merge branch 'title' con la rama master**, que es el mensaje que aparecia cuando se ha realizado el `merge` no fast forward.

**Pregunta 12:**

¿Qué comando o comandos utilizaste en el paso 32?:

**Respuesta 12:**

Para volver al *commit* inicial, sin perder los cambios (el enunciado dice volver al **commit inicial**, no al **estado inicial**), utilizamos `git reflog` para acceder al listado de los *commits* por los que hemos ido pasando, seleccionamos el *id* que corresponde al *commit* inicial, que ademas aparece marcado en el reflog como *(initial)* y ejecutamos el comando `git checkout`, tambien podríamos haber utilizado el comando `git log` para localizar el *id* del *commit* inicial:

`$git reflog`

`$ git checkout 75ee313`

**Pregunta 13:**

¿Qué comando o comandos utilizaste en el paso 33?:

**Respuesta 13:**

Utilizamos `reflog` para acceder al listado de todos los *commits* que se han ido realizando, seleccionamos el *id* del que corresponde al `merge` del paso 26 y ejecutamos el comando `reset`como se muestra a continuación junto con el parámetro `--hard`:

`$git reflog`

`$ git reset --hard 1b7ac1c`
 
 