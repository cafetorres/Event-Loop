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
Cuando se corre git reset B --soft , master (y por lo tanto CABEZA ) ahora apunta a B , pero el índice todavía tiene los cambios de C ; git status mostrará como por etapas. Así que si corremos git commit en este punto, vamos a tener un nuevo commit con los mismos cambios que C.

Si se utiliza "soft" (git reset --soft) para retornar a un punto en específico del proyecto, el mismo lo logra sin disolver el estado actual del proyecto, esto porque no restablece el indice ni la rama de trabajo. Cuando aplicamos este comando todos los archivos pertenecientes a "commits" posteriores a el quedan en "stage" listos para cualquier otra operación que se desee realizar. De forma similar actúa el comando "mixed" (git reset --mixed), la única diferencia con el comando "soft" es que el los cambios no se quedan en "stage". Este es el comando por defecto que usa git cuando no se le asigna una bandera (mixed, soft, hard, etc). De ser necesario retornar completamente a un estado pasado, ignorando todos los "commits" que se encuentren por encima (más nuevos) que este, se utiliza git reset --hard, Este comando particular ignora completamente todos los cambios que hemos realizado ya que restablece el indice y la rama de trabajo al punto donde se encontraban.


Estos tres métodos antes descritos podemos decir que son los "más" populares, ya que a la hora de haber realizado algo realmente errado utilizamos el reset --hard para retornar al estado anterior descartando todo, y cuando realizamos un mal "commit" ya sea porque el mensaje no nos gustó o agregamos muchos archivos en un solo "commit" empleamos reset --soft o reset --mixed.

