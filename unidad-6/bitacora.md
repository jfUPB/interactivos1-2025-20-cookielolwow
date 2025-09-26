
# Evidencias de la unidad 6
## Actividad 01
**Preparación del entorno y primer contacto**


¿Qué ocurrió en la terminal cuando ejecutaste npm install? ¿Cuál crees que es su propósito?


<img width="252" height="112" alt="image" src="https://github.com/user-attachments/assets/30834544-44bd-4011-98ee-2a430ba4024f" />


 - Creo que su proposito era descargal algún archivo.
   
¿Qué mensaje específico apareció en la terminal después de ejecutar npm start? ¿Qué indica este mensaje?


  <img width="1026" height="78" alt="image" src="https://github.com/user-attachments/assets/517e381d-d624-4be4-81f2-9916ea7e4b5d" />

- Este mensaje indica que se está ejecutando el script definido como start en el archivo package.json. En este caso, ese script está configurado para correr el archivo server.js usando Node.js.

  
Describe lo que ves inicialmente en page1 y page2 en tu navegador.

- Inicialmente veia un mesnaje que decia algo como esperando la conexion de la otra ventana. Luego ya cuando las dos estaban abiertas en cada pagina habia un circulo rojo conectado por una linea desde el centro al circulo de la otra pagina.

  
¿Qué mensajes aparecieron en la terminal del servidor cuando abriste page1 y page2?


<img width="471" height="47" alt="image" src="https://github.com/user-attachments/assets/9038f0b3-41c1-46ad-ae72-9e0a89b4aa71" />


Describe qué sucede en ambas páginas del navegador cuando mueves una de las ventanas. ¿Cambia algo visualmente? ¿Qué mensajes aparecen (si los hay) en la consola del navegador (usualmente accesible con F12 -> Pestaña Consola) y en la terminal del servidor?

- En ambas paginas los circulos como que se conectan y cuando se mueven la pestañas se ajustan los ejes de los circulos como persiguiendose.

  <img width="900" height="277" alt="image" src="https://github.com/user-attachments/assets/0ddfc88e-cece-4bcd-852e-71561ed789c1" />

## Actividad 02
**🪼🫧 Reporta en tu bitácora**


Piensa en cómo te conectas a Internet en casa o en la Universidad. ¿Usas Wi-Fi? ¿Un cable de red? Eso es simplemente tu “rampa de acceso” a la gran red de carreteras. ¿Qué pasaría si esa rampa se corta? Anota tus ideas.

- La verdad nunca he buscado o entendido del todo como nos conectamos al internet, a pesar de estar la mayoria del tiempo conectada a el. Uso wifi y cable de red,y siento que si la rampa de acceso se corta simplemente no se va a poder usar.


>Indagación:
>
>Internet es una enorme y extensa colección de redes que se conectan entre sí.
>De hecho, podría decirse que la palabra "Internet" proviene de las términos interconectadas y redes en inglés.
>Ya que los ordenadores se conectan entre sí dentro de las redes y estas redes también se conectan entre sí,un ordenador puede comunicarse con otro ordenador de una red lejana gracias a Internet.Esto permite intercambiar rápidamente información entre ordenadores de todo el mundo
>Los ordenadores se conectan entre sí y a Internet mediante cables, ondas de radio y otros tipos de infraestructura de red.Todos los datos que se envían por Internet se traducen en pulsos de luz o electricidad,también conocidos como "bits", que luego interpreta el ordenador receptor. Los cables y ondas de radio dirigen estos bits a la velocidad de la luz.Cuantos más bits puedan pasar por cables al mismo tiempo, más rápido funcionará Internet.


**🪼🫧 Reporta en tu bitácora**


¿Puedes identificar otros ejemplos de relaciones Cliente-Servidor en tu vida diaria (no necesariamente digitales)? Por ejemplo, al pedir comida en un restaurante. ¿Quién es el cliente y quién el servidor? ¿Qué se pide y qué se entrega?

- Al pedir comida en el restaurante, el cliente pues es el cliente del restaurante y el servidor podria ser el mesero o el restaurante en general ya que este es el que funcionalmente te da las cosas¿?. Se pide un platillo y se entrega el platillo pedido.
- Otro ejemplo es una biblioteca ( y sus trabajadores ) como servidor y el cliente como un lector. Se pide un libre y se busca si el libro esta disponible para entregarlo despúes.

**🪼🫧 Reporta en tu bitácora**


Toma la URL de tu sitio web favorito. Intenta identificar el protocolo, el nombre de dominio y la ruta (si la hay). ¿Qué crees que pasa si solo escribes el nombre de dominio (ej. www.google.com) sin una ruta específica? ¿Qué “página por defecto” crees que te envía el servidor?

- la url que escogí es https://www.newgrounds.com/portal/view/778607. El protocolo es `http://`, el nombre del dominio es `www.newgrounds.com` y la ruta específica es `/portal/view/778607`.
- Seguramente al poner solamente `www.newgrounds.com` me lleve a la pagina de inicio.

**🪼🫧 Reporta en tu bitácora**

Compara HTTP con los protocolos seriales que usaste.

¿Qué similitudes encuentras?

- Los tres son protocolos de de comunicación.
- Envían datos.
- Usan texto.
  
¿Qué diferencias clave ves?

- Que tan complejo son los mensajes.
- Ascii y framing tenian comunicación directa entre los dispositivos. HTTP es comunicación cliente-servidor
- El formato y estructura. Mientras el de ASCII y framing eran basiquitos, HTTP es muy detallado.
- ASCII y framin solo enviaban datos para sensores, texto, etc, y HTTP solicita y entraga varios ttipos de recursos como paginas, imagenes, etc.

  
¿Por qué crees que HTTP necesita ser más complejo que un simple envío de bytes como hacías con el micro:bit?

- HTTP necesita ser mas complejo ya que tiene que tiene que identificar el cliente, lo que se pide, responder correctamente con el pedido y adémas, mantener la seguridad y el control.

**🪼🫧 Reporta en tu bitácora**

Piensa en una página web simple, como un formulario de login.


¿Qué parte crees que es HTML (ej. los campos de texto, el botón)?

- La parte HTML son los textos que salen pidiendo la información, los botones para confirmar la información.

  
¿Qué parte es CSS (ej. el color del botón, el tipo de letra)?

- La parte de CSS es la fuente que esten usando los textos, los colores que vemos en la pagina, la posición de cada cosa en la pantalla, el tamaño de las cosas.
  
¿Qué parte es JavaScript (ej. la comprobación de si escribiste algo antes de enviar, el mensaje de “contraseña incorrecta” que aparece sin recargar la página)?

- El JavaScript  verifica si los campos están llenos antes de enviarlos. También es el que muestra mensajes de error como “contraseña incorrecta” sin tener que recargar toda la página. Muestra animaciones que reaccionen a los clicks, botones, etc.

**🪼🫧 Reporta en tu bitácora**


Compara el bucle draw() de p5.js con este modelo de “esperar a que algo pase y reaccionar”.

| Modelo de ejecución con `draw()` en p5.js               | Modelo basado en eventos en JavaScript                     |
|----------------------------------------------------------|-------------------------------------------------------------|
| Hay un bucle que se ejecuta 60 veces por segundo         | El navegador espera a que ocurra un evento en vez de un bucle constante |
| Se controla lo que sucede en cada fotograma              | Se definen funciones que solo se ejecutan cuando ocurre un evento específico |
| Útil para animaciones, juegos o simulaciones visuales    | El navegador gestiona mejor lo que ocurre y mantiene la página más liviana |

¿Qué ventajas crees que tiene el modelo basado en eventos para una interfaz de usuario web?

- Se actualiza la pagina solo cuando es necesario.
- Al no estar en constante ejecución es mejor el rendimiento.
- Hay mas interacción humana con la pagina. Al basarse en clics y desplazamientos es mas natural usarlo.

  
¿Sería eficiente tener un bucle draw() redibujando toda la página 60 veces por segundo si nada ha cambiado?

- No, es ineficiente porque redibujar la pagina todo el tiempo alteraria bastante el rendimiento. Además de que sirve cambiar algo cada segundo si nadie lo ha movido.

**🪼🫧 Reporta en tu bitácora**

¿Por qué crees que podría ser útil usar JavaScript tanto en el cliente (navegador) como en el servidor? ¿Se te ocurre alguna ventaja para los desarrolladores?

Permite usar el mismo lenguaje en todos lados. Y un desarrollador que ya tenga experiencia en Javascript podra aprender a usar node.js más facilmente sin tener que ver otro lenguaje de programación desde 0.

**🪼🫧 Reporta en tu bitácora**


Resume con tus propias palabras la diferencia fundamental entre una comunicación HTTP tradicional y una comunicación usando WebSockets/Socket.IO. ¿En qué tipo de aplicaciones has visto o podrías imaginar que se usa esta comunicación en tiempo real?  

-  La diferencia entre la comunicación HTTP tradicional y la comunicación usando Websockets nace de que que con HTTP la comunicación no es fluida, cada qeu se hace una petición el servidor responde una sola vez, y si se quiere mas información se tiene que volver a pedir. En cambio, con Websockets la comunicación es como una llamada telefónica continua, ambos lados se mandan mensajes en tiempo real sin necesidad de estar pidiendo información todo el tiempo.

-  Los Websockets los podemos ver en los chats como en whatsapp, en juegos multijugador, en trabaos colaborativos como los documentos en google docs.


## Actividad 03

Detén el servidor si está corriendo.


Cambia la primera ruta de /page1 a /pagina_uno.


Inicia el servidor.


Intenta acceder a http://localhost:3000/page1. ¿Funciona?

- nop
  <img width="326" height="117" alt="image" src="https://github.com/user-attachments/assets/72a81f82-ccfd-4410-ade5-e1af6d66798e" />


Ahora intenta acceder a http://localhost:3000/pagina_uno. ¿Funciona?

-  sip

<img width="549" height="624" alt="image" src="https://github.com/user-attachments/assets/632bda7d-8f55-46ef-b7f9-d11e0aaa114e" />


¿Qué te dice esto sobre cómo el servidor asocia URLs con respuestas? Restaura el código.

La ruta pagina_uno no esta definida, por lo cual la función no la va a encontrar por ningun lado.
