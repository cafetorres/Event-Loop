Apache vs NGINX
==============================
----
## Computo en la Nube
#### Carlos fernando Torres Luna
##### cf.torresluna@gmail.com 

---

### Apache HTTP Server 

Es el servidor web más usado en el mundo, pero como pasa en muchos casos, lo más usado no es siempre lo mejor, solo lo que se conoce más. Apache tiene muchas características positivas, pero su gran deficiencia es el rendimiento, cosa que es sumamente importante en las aplicaciones de hoy en día. 

Apache crea hilos y sub-hilos para manejar conexiones adicionales. El administrador puede configurar el servidor para controlar el número máximo de hilos permitidos. Esta configuración varía dependiendo de la memoria disponible en la máquina. 

Demasiados procesos en memoria hace que el rendimiento se vea gravemente disminuido. 

Además, cuando el máximo de hilos es alcanzado, Apache restringe conexiones adicionales. Igualmente puede ser configurado para ejecutarse en modo multi-proceso de pre-bifurcada o worker (MPM). De cualquier manera sé que crean nuevos procesos por cada usuarios adicional que se conecte. 

El factor limitante en Apache es la memoria y el potencial de hilos-muertos que se contengan en la memoria. Si se detiene un hilo, el usuario espera a que la página web aparezca, hasta que el proceso se libere, para que puede enviar la página nuevamente. Si un proceso se estanca, no sabe cómo reiniciar, quedando así atrapados.

### NGINX

NGINX es un servidor web HTTP de código abierto que incluye servicios de correo electrónico con acceso al Internet Message Protocol (IMAP) y al servidor Post Office Protocol (POP). Además, NGINX está listo para ser utilizado como un proxy inverso. En este modo, se utiliza para equilibrar la carga entre los servidores back-end, como también para ser utilizado como caché en un servidor back-end lento.

Su arquitectura, es diferente al modelo tradicional, de crear una instancia por cada request. NGINX procesa decenas de miles de conexiones simultáneas en un proceso compacto y con varios núcleos de CPU. 

Además se compone de módulos que se incluyen en tiempo de compilación. Eso significa que el usuario descarga el código fuente y selecciona qué módulos quiere utilizar, haciendo más liviano que la competencia. Hay módulos para la conexión a clones de aplicaciones, balanceo de carga, servidor proxy, y otros. No hay módulo para PHP, ya que Nginx puede interpretar código PHP en sí mismo.
