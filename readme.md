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

`reflog` lista todos los **commits** que se han realizado en el repositorio, se puede encontrar el *id* del **commit** que hemos eliminado y a través de `reset` con el parametro *--hard* y este *id*, recuperarlo. 

**Pregunta 3:**

El `merge`del paso 13, ¿Causó algún conflicto?, ¿Por qué?:

**Respuesta 3:**

No, ya que en este caso la rama *styled* que absorbe a la rama *master* se encuentra por delante formando una lista y por lo tanto se puede decir que *styled* ya ha absorbido a *master* antes del `merge`. 

**Pregunta 4:**

El `merge`del paso 19, ¿Causó algún conflicto?, ¿Por qué?:

**Respuesta 4:**

En este caso SI, al querer absorber la rama *htmlyfi* por parte de *styled* git se da cuenta que se ha modificado el fichero en las dos ramas y es necesario corregirlo.   

**Pregunta 5:**

El `merge`del paso 21, ¿Causó algún conflicto?, ¿Por qué?:

**Respuesta 5:**

No se han presentado conflictos, se ha realizazo un `merge` de tipo **Fast Forward** de manera que el puntero *master* se ha desplazado hasta el ultimo **commit** de la rama *styled*.

**Pregunta 6:**

¿Que comando o comandos utilizaste en el paso 25?:

**Respuesta 6:**

Se ha utilizado un único comando pero acompañado de varios parametros:

`$ git log --graph --decorate --pretty=oneline`

**Pregunta 7:**

El `merge`del paso 26, ¿Podría ser **Fast Forward**?, ¿Por qué?:

**Respuesta 7:**

Si podría serlo, ya que en este punto, *master* se encuentra un commit por debajo de *tittle* y forman una lista continua por lo que sería posible realizar el `merge` desplazando el puntero de *master* hasta el lugar donde se encuentra el puntero de *tittle*.

**Pregunta 8:**

¿Qué comando o comandos utilizaste en el paso 27?:

**Respuesta 8:**

Para deshacer el `merge` sin perder los cambios, utilizamos el comando `reset` que hemos utilizado en otras ocasiones pero esta vez sin el parámetro `--hard` para así poder conservar los cambios:
 
`$ git reset HEAD~1`

**Pregunta 9:**

¿Qué comando o comandos utilizaste en el paso 28?:

**Respuesta 9:**

Para descartar los cambiso del *Working Copy* utilizamos de nuevo el comando `checkout`:

`$ git checkout -- git-nuestro.md`

**Pregunta 10:**

¿Qué comando o comandos utilizaste en el paso 29?:

**Respuesta 10:**

Para eliminar la rama *tittle* utilizamos el comando:

`$git branch -D tittle`

**Pregunta 11:**

¿Qué comando o comandos utilizaste en el paso 30?:

**Respuesta 11:**

Utilizamos `reflog` para acceder al listado de todos los *commits* que se han ido realizando, seleccionamos el *id* del que corresponde al `merge` del paso 26 y ejecutamos el comando `reset`como se muestra a continuación:

`$git reflog`

`$ git reset --hard c4110b9`

**Pregunta 12:**

¿Qué comando o comandos utilizaste en el paso 32?:

**Respuesta 12:**

El proceso es igual que en el punto anterior, `reflog` para acceder al listado de todos los *commits* que se han ido realizando, seleccionamos el *id* del que corresponde al *commit* inicial, que ademas aparece marcado en el reflog como *(initial)* y ejecutamos el comando `reset`como se muestra a continuación:

`$git reflog`

`$ git reset --hard 9ba19ad`

**Pregunta 13:**

¿Qué comando o comandos utilizaste en el paso 33?:

**Respuesta 13:**

Volvemos a utilizar los mismos comandos de nuevo, `reflog` para localizar el *commit* y `reset` para volver a el:

`$git reflog`

`$ git reset --hard af14344`
 
 