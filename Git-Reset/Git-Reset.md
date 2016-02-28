Git Reset
==============================
----
## Computo en la Nube
#### Carlos fernando Torres Luna
##### cf.torresluna@gmail.com 

---
![alt text][logo]
[logo]: http://i.stack.imgur.com/qRAte.jpg "git-reset"

#### Git Reset --mixed
Al hacer git reset --mixed B . Master y head punto A a B, pero esta vez el índice también se modifica para que coincida B . Si corremos git commit en este punto, no pasará nada ya que el índice coincide cin head . Todavía tenemos los cambios en el directorio de trabajo, pero ya no están en el índice, git status muestra los archivos como no preparados. Se tienen que agragar con git add y luego hacer el commit.
+
+
#### Git Reset --soft
Cuando se corre git reset B --soft , master (y por lo tanto CABEZA ) ahora apunta a B , pero el índice todavía tiene los cambios de C ; git status mostrará como por etapas. Así que si corremos git commit en este punto, vamos a tener un nuevo commit con los mismos cambios que C .

