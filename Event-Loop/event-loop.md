Event Loop en Node js
==============================
----
## Computo en la Nube
#### Carlos fernando Torres Luna
##### cf.torresluna@gmail.com 

---

![alt text][logo]
[logo]: http://www.tutorialspoint.com/nodejs/images/event_loop.jpg "Event Loop"

Node proporciona el Event Loop como una construcción del lenguaje, no sólo como una biblioteca. Con el bucle de eventos node empieza y no termina hasta la última devolución de llamada a realizar.

Por el bucle de eventos y la naturaleza misma de JavaScript y node, hay una gran cantidad de devoluciones de llamada que se ocupan de E / S que tienen que ver con las devoluciones de llamada e iniciar desde otras E / S. Aquí es donde las desviaciones del lado del cliente JavaScript del navegador verdaderamente desvían del lado de nodo de servidor de JavaScript. Con estos estilos de desarrollo, es importante tener en cuenta las pautas que nos ayudan a utilizar con eficacia JavaScript en el servidor. El ciclo de eventos es clave para entender todo este flujo.

El ciclo de eventos Node.js se ejecuta bajo un solo hilo, esto significa que el código de la aplicación que escribes se evalúa en un solo hilo. Nodejs sí utiliza muchos hilos debajo través libuv, pero usted nunca tendrá que lidiar con aquellos con al escribir código nodejs.

Cada llamada que implica la llamada de E / S requiere que se registre una devolución de llamada. Esta llamada también devuelve inmediatamente, esto le permite hacer múltiples operaciones de IO en paralelo sin necesidad de utilizar las discusiones en el código de aplicación. Tan pronto como se haya completado una operación de E / S es de devolución de llamada será empujado en el bucle de eventos. Se ejecutará tan pronto como todos los demás servicios repetidos que, cuando empujó en el bucle de eventos antes de que se ejecuten.

##### Limitaciones

Debido al ciclo de eventos, el nodo no tiene que iniciar un nuevo hilo para cada conexión TCP entrante. Esto permite que el nodo al servicio cientos de miles solicitan al mismo tiempo, siempre y cuando usted no está calculando los primeros 1000 números primos para cada solicitud.

Esto también significa que es importante no hacer operaciones intensivas de la CPU, ya que estos mantendrán un bloqueo en el bucle de eventos y prevenir otros caminos asíncronos de ejecución de continuar. También es importante no utilizar el sync variante de todos los métodos de E / S, ya que estos mantener un bloqueo en el bucle de eventos también.


