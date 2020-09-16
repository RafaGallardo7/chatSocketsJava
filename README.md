"# chatSocketsJava" 

Como Hacer un Chat con Sockets en Java en Netbeans

En este nuevo post mostraremos como hacer un chat mediante el uso de Sockets en Java en el ambiente de programacion Netbeans. Los Sockets sirven para comunicar procesos de diferentes maquinas de una red.

Haremos un servidor y un cliente utilizando Sockets.

Del lado del Servidor se tiene un bucle infinito que espera conexiones de clientes. Cuando un cliente se conecta el servidor acepta la conexion y genera dos threads: uno para enviar datos y el otro para recibirlos.

Del lado del Cliente se tiene que esperar un Servidor para poder conectarse, cuando se conecta al servidor se generan dos threads, al igual que en el Servidor uno para enviar y otro para recibir los datos.

Los threads que se generan del lado del servidor y del cliente son los mismos.
La clase principal del Servidor es identica a la clase principal del cliente; la unica diferencia esta en el main, el servidor espera conexiones del cliente y el cliente busca servidor para conectarse.

Para nuestro ejemplo utilizaremos localhost para poder correr el programa en nuestra propia maquina.

Es importante tener en cuenta que puerto se va a utilizar para poder abrirlo con anterioridad, en nuestro caso abriremos el puerto 11111.

Se debe conocer que las asignaciones a los puertos comprendidos entre los valores (0 - 1023) estan determinados por la IANA (Internet Assigned Numbers Authority). y no se los puede utilizar de otro manera.

Se puede utilizar los puertos comprendidos entre los valores (1024 - 65535). 

Nuestro programa cuenta con dos paquetes, uno para el servidor y otro para el cliente; los mismo que contiene threads identicos para envio y recepcion de datos.

Empezaremos describiendo las clases del lado del servidor:

Clase PrincipalChat:
Esta clase implementa la interfaz grafica para poder mostrar los mensajes entrantes y un JTextField para poder enviarlos. La interfaz contiene un menu para poder salir del programa.
En el main se puede ver que se espera conexiones de clientes.

Clase ThreadEnvia:
En esta clase establecemos nuestro canal de salida tipo ObjectOutputStream, el cual nos sirve para escribir el mensaje, enviarlo y mostrarlo en pantalla mediante el metodo enviarDatos().
Ademas declaramos la variable conexion tipo Socket, la cual se encarga de establecer el flujo de datos entre  cliente y servidor.

Clase ThreadRecibe:
En esta clase establecemos nuestro canal de entrada tipo ObjectInputStream, el cual se encarga de recibir los mensajes enviados por el cliente o servidor.
Aqui se procesa los mensajes recibidos y luego son mostrados en pantalla.
Es importante aclarar que se debe cerrar el canal de entrada de datos y el Socket de conexion una vez finalizado el flujo de datos.

En el paquete Cliente encontramos:

Clase PrincipalChat:
Esta clase implementa la interfaz grafica para poder mostrar los mensajes entrantes y un JTextField para poder enviarlos. La interfaz contiene un menu para poder salir del programa.
Esta clase busca servidores para poder conectarse.

Las clases descritas en el paquete Cliente: ThreadRecibe y ThreadEnvia son exactamente las mismas que se describieron en el paquete Servidor.


https://aflrovvs.blogspot.com/2012/07/como-hacer-un-chat-con-sockets-en-java.html

