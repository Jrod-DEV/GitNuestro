**Respuestas práctica 1 Git**

*11) Deshacer el último commit (perdiendo los cambios realizados en el working copy)*
*- ¿Qué comando utilizaste en el paso 11? ¿Por qué?*
Para deshacer el último commit hago un reset: “  git reset --hard HEAD~1 “para perder además los cambios realizados en el working copy.

*12) Rehacer el último commit (el que acabamos de deshacer)*
*- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?*
Usando el comando  git reflog localizo el hash del commit al que quiero ir (deshacer).
Uso este comando porque es la única forma de encontrar el identificador de todos los commits que he realizado, en eta situación, git log no me permite verlo.

Seguidamente hago git reset  --hard 67603cb y vuelvo al commit deseado(el último que había realizado), donde mi .md ya tiene estilo. 

*13) Hacer un merge con ‘master’ (styled absorbe a master)*
*- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?*
No causó ningún conflicto porque el contenido del poema sigue siendo el mismo.
Las lineas de los dos archivos que hacen merge7 son iguales, por lo que no crea conflicto al mergear.

*19) Hacer un merge de “htmlify” en “styled” (styled absorbe a htmlify)*
*- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?*

Si hay conflictos.
Esto se debe a que los caracteres de html que hay en la rama “htmlfiy” alteran el contenido del texto y no es igual al contenido el archivo de la rama “styled”, por lo que tengo que elegir el código con el que me quedo(en este caso me quedo con el contenido de la rama styled), editando los dos archivos y finalizando este problema con un git add para llevarme el archivo al staying area y realizar git commit.

*21) Desde “master”, hacer un merge con “styled”*
*- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?*
No me genera ningún conflitcto.
Porque en un paso anterior ya había realizado merge desde style absorbiendo a la rama master, así que el contenido del archivo no es diferente.


*25) Dibujar el diagrama*
*¿Qué comando o comandos utilizaste en el paso 25?*
Inicialmente utilizo el comando git log --graph, pero añado los atributos --decorate para que me muestre los punteros 
y --pretty=oneline para que me muestre además un resumen en una linea de cada commit.
Desktop/GIT/Practica1_GIT  master ✔                                                                     11m  
▶ git log --graph --decorate --pretty=oneline

*   353d1be59fe13c11f82fbfa7f709ac545c4af356 (HEAD -> master, styled) Merge branch 'htmlify' into styled, resuelvo conflicto y me quedo con el contenido de la rama syled(texto con estilo)
|\  
| * 44191d432f356eda1e9851078d9ce3fd2ca05a86 (htmlify) Transformo el poema a un formato de HTML(de estilo a HTML)
* | 4443aa5e7745854534afb796df5f5aea308e4e16 2º commit, modifico el poema con estilos
|/  
* 4a87cceb050f74bff148cb941276a83bbfa569e0 Primer commit, escribo poema sin estilos.


*26) Hacer un merge “no fast-forward” de “title” en “master” (master absorbe a title)*
*- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?*
Sí podría ser fast forward porque no perdería acceso a ningún commit.

*27) Deshacer el merge (sin perder los cambios del working copy)**- ¿Qué comando o comandos utilizaste en el paso 27? *
Para deshacer el merge sin perder los cambio en el working copy utilizo el comando git reset HEAD~1.

*28) Descartar los cambios*
*- ¿Qué comando o comandos utilizaste en el paso 28?*
Para descartar los cambios en este paso, git me da dos opciones, usar git checkout o git restore. 
Finalmente utilizo git restore.

*29) Eliminar la rama “title”*
*- ¿Qué comando o comandos utilizaste en el paso 29?*
Ejecuto el comando git -D title, ya que al haber deshecho el merge de master con title, esta no fue fusionado. Por esta razón , git me obliga a usar git -D title, para asegurarse de que yo realmente quiero eliminar esta rama.

*30) Rehacer el merge que hemos deshecho*
*- ¿Qué comando o comandos utilizaste en el paso 30?*
En primer lugar utilizo git reflog para buscar el identificador del merge que necesito rehacer.
Acto seguido, necesito hacer un git reset --hard HEAD + el identificador para volver al commit donde se realiza el merge de master absorbiendo title.
Desktop/GIT/Practica1_GIT  master ✔                                                                   1h12m  
▶ git reset --hard d7fb307
HEAD está ahora en d7fb307 Desde la rama title le pongo título al poema


*32) Volver al commit inicial cuando se creó el poema*
*¿Qué comando o comandos usaste en el paso 32?*
Primero uso git log para ver la referencia  del commit inicial.
En segundo lugar utilizo reset HEAD y en este caso ~3 para ir al commit inicial. No utilizo hard para evitar que se modifique mi working copy.
Compruebo mi ubicación con git log, que solo me permite ver este primer commit.

*33) Volver al estado final, cuando pusimos título al poema.*
*- ¿Qué comando o comandos usaste en el punto 33?*
Para volver al estado final, ejecuto git reflog, copio la referencia y hago git reset HEAD@{6} .
Vuelvo a comprobar mi ubicación con git log y estoy en el commit deseado, donde le puse el título al poema.






