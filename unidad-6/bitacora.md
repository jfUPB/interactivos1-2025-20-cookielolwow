
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
**🪼🫧 Experimenta**

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

- Me dice que el asocia la url con el nombre definido para saber que usar.


**🪼🫧 Experimenta**

Asegúrate de que el servidor esté corriendo (npm start).



Abre http://localhost:3000/page1 en una pestaña. Observa la terminal del servidor. ¿Qué mensaje ves? Anota el ID.
```
A user connected - ID: F46MyBNghJ9zPR1BAAAB

```


Abre http://localhost:3000/page2 en OTRA pestaña. Observa la terminal. ¿Qué mensaje ves? ¿El ID es diferente?
```
A user connected - ID: QH6C85lZmpgZ8D6kAAAD

```
Cierra la pestaña de page1. Observa la terminal. ¿Qué mensaje ves? ¿Coincide el ID con el que anotaste?
```
User disconnected - ID: F46MyBNghJ9zPR1BAAAB
```
- Si coincide.
  
Cierra la pestaña de page2. Observa la terminal.
```
User disconnected - ID: QH6C85lZmpgZ8D6kAAAD
```
- Si coincide.

**🪼🫧 Experimenta**

Inicia el servidor y abre page1 y page2.


Mueve la ventana de page1. Observa la terminal del servidor. ¿Qué evento se registra (win1update o win2update)? ¿Qué datos (Data:) ves?
```
Received win1update from ID: F46MyBNghJ9zPR1BAAAB Data: { x: 179, y: 192, width: 989, height: 944 }
```

Mueve la ventana de page2. Observa la terminal. ¿Qué evento se registra ahora? ¿Qué datos ves?
```
Received win2update from ID: QH6C85lZmpgZ8D6kAAAD Data: { x: 543, y: 179, width: 989, height: 944 }
```

Experimento clave: cambia socket.broadcast.emit(‘getdata’, page1); por socket.emit(‘getdata’, page1); (quitando broadcast). Reinicia el servidor, abre ambas páginas. Mueve page1. ¿Se actualiza la visualización en page2? ¿Por qué sí o por qué no? (Pista: ¿A quién le envía el mensaje socket.emit?). Restaura el código a broadcast.emit.

- Al cambiar el código la page 1 al moverla deja de sincronizarce con la otra y al mover la page 2 vuelve a la "normalidad" pero no sincronizado del todo. El mensaje de socket. emit se manda el mensaje a si mismo y el broadcast.emi se lo manda a todos los clientes menos al que esta mandando el mensaje.
  
**🪼🫧 Experimenta**

Detén el servidor.

Cambia const port = 3000; a const port = 3001;.

Inicia el servidor. ¿Qué mensaje ves en la consola? ¿En qué puerto dice que está escuchando?

Intenta abrir http://localhost:3000/page1. ¿Funciona?

- nop
  
Intenta abrir http://localhost:3001/page1. ¿Funciona?

- sip

¿Qué aprendiste sobre la variable port y la función listen? Restaura el puerto a 3000.

- La variable de port indica donde esta el servidor y la función listen lo inicializa en ese puerto especifico.


## Actividad 04
**Explorando los clientes (p5.js + Socket.IO)**

Ahora nos enfocaremos en cómo uno de los clientes, page2.js, interactúa con el servidor y visualiza la información. El código de page1.js es muy similar, así que entender uno te ayudará a entender el otro.

**🪼🫧 Experimenta**

Abre page2.html en tu navegador (con el servidor corriendo).


Abre la consola de desarrollador (F12).


Detén el servidor Node.js (Ctrl+C).


Refresca la página page2.html. Observa la consola del navegador. ¿Ves algún error relacionado con la conexión? ¿Qué indica?


<img width="553" height="176" alt="image" src="https://github.com/user-attachments/assets/7004437c-bada-41dd-95df-c94548047507" />

Vuelve a iniciar el servidor y refresca la página. ¿Desaparecen los errores?

- si

**🪼🫧 Experimenta**


Comenta la línea socket.emit(‘win2update’, currentPageData, socket.id); dentro del listener connect.


Reinicia el servidor y refresca page1.html y page2.html.


Mueve la ventana de page2 un poco para que envíe una actualización.


¿Qué pasó? ¿Por qué?

<img width="1029" height="325" alt="image" src="https://github.com/user-attachments/assets/01bf9b7f-336d-4202-b6d9-258a1d31053d" />

 - Al comentar esa linea se corto la comunicación.

   
**🪼🫧 Experimenta**


Asegúrate de tener este console.log en page2.js.


Abre ambas páginas.


Mueve la ventana de page1. Observa la consola del navegador de page2. ¿Qué datos muestra?


<img width="394" height="306" alt="image" src="https://github.com/user-attachments/assets/f801f140-d5cc-4b89-8b80-1613b139b4d0" />


Mueve la ventana de page2. Observa la consola de page1. ¿Qué pasa? ¿Por qué?


<img width="440" height="258" alt="image" src="https://github.com/user-attachments/assets/3bd214d5-5ab3-4025-8e17-66108c8df50a" />


Basicamente significa que la aplicación esta sincronizando los datos entre las dos pestañas. Cada que se mueve una de las pestañas se envía por socket.io  y luego aparece en consola como Received valid remote data.


**🪼🫧 Experimenta**


Observa checkWindowPosition() en page2.js y modifica el código del if para comprobar si el código dentreo de este se ejecuta.


Mueve cada ventana y observa las consolas.


¿Qué puedes concluir y por qué?
Concluyó que el sistema está diseñado para detectar y transmitir solo cuando hay cambios reales, lo cual evita que se envíen datos innecesarios.

**🪼🫧 Experimenta**

(¡Sé creativo!)


Cambia el background(220) para que dependa de la distancia entre las ventanas. Puedes calcular la magnitud del resultingVector usando let distancia = resultingVector.mag(); y luego usa map() para convertir esa distancia a un valor de gris o color. background(map(distancia, 0, 1000, 255, 0)); (ajusta el rango 0-1000 según sea necesario).


Inventa otra modificación creativa.


<img width="664" height="531" alt="image" src="https://github.com/user-attachments/assets/d309edab-bd09-42f7-a2bc-65462d66dbab" />


## Actividad 05
### Apply
**🪼🫧 En tu bitácora**

Explica tu idea y realiza algunos bocetos.
- Mi idea para esta actividad es que se simulen unas olas que se mueven como el mar, y que cuando yo separe las dos pestañas, aparezca una especie de “cascada” toda bacana en el hueco entre ambas. La gracia es que las olas viajan normalmente de un lado a otro, pero si hay un espacio, ps cae agua justo en la mitad, así como si se rompiera el océano. Quería que se sintiera como un océano  entre dos ventanas, pero que como tenia que ser interactivo hice que si separabas las olas ps pasara lo de la cascada. 

  
 Lo primero que pensé fue cómo se vería. Me lo imaginé algo así:

 <img width="962" height="470" alt="image" src="https://github.com/user-attachments/assets/246c2666-6ba6-47bf-a9df-e8203130a710" />

 
  Para hacerlo me mie encima. Primero tenía que armar todo el tema del servidor con socket.io, porque obviamente si quería que las ventanas hablaran entre sí, necesitaba esa comunicación en tiempo real. ásicamente el server es el que manda la información  clave: la posición de las ventanas, si están pegadas o no, y la variable noiseOffset que hace que las olas se muevan con ruido Perlin y no se vean todas robóticas.


  Luego me puse con las ventanas. Cada una dibuja sus olas como normales, pero con la condición de que si hay un espacio en la mitad, entonces cambie el comportamiento y se active la cascada.


  Ya de ahi me re perdi pq como se hacia la detección de que las pestañas estaban separadas. Al inicio no tenía ni idea, hasta que caí en cuenta de que podía usar las coordenadas de cada ventana: screenX y width. O sea, si la ventana 1 termina antes     de donde empieza la 2, significa que hay un gap. O sea super cool 10/10.

  Después venía lo de la cascada.  La cascada la hice con particulitas azules, cada partícula es como una gotica de agua que se genera justo en el borde de la ola y empieza a caer con gravedad. Tienen una vida finita y ps van regenrandose, asi se mantiene el efecto de caida.


  La parte que más me enredó fue la sincronización de las olas entre las dos pestañas. Si no lo hacía, cada ventana iba a mostrar olas distintas y las olas estarian a niveles de altura diferente. La solución fue que el servidor mandara el syncUpdate con el noiseOffset cada frame. Eso asegura que las dos ventanas estén siempre dibujando la misma ola, y cuando las pego parecen un solo mar gigante y las ventanas van agarraditas para que en ningun momento las olas esten desniveladas.
  
 Y quedo asi de cool 🤪

 
  <img width="952" height="604" alt="image" src="https://github.com/user-attachments/assets/9cf1f4be-8f68-42d1-97bd-7c42a9a15061" />

Incluye todos los códigos (servidor y clientes) en tu bitácora.


page1.html
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ventana Oceánica 1</title>
    <script src="https://cdn.jsdelivr.net/npm/p5@1.11.0/lib/p5.min.js"></script>
    <script src="https://cdn.socket.io/4.7.5/socket.io.min.js"></script>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            background-color: #003264; /* Fondo azul oscuro del océano */
        }
    </style>
</head>
<body>
    <script defer src="page1.js"></script>
</body>
</html>
```

page2.html
```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ventana Oceánica 2</title>
    <script src="https://cdn.jsdelivr.net/npm/p5@1.11.0/lib/p5.min.js"></script>
    <script src="https://cdn.socket.io/4.7.5/socket.io.min.js"></script>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            background-color: #003264; /* Fondo azul oscuro del océano */
        }
    </style>
</head>

<body>
    <script defer src="page2.js"></script>
</body>
</html>
```

page1.js
```js
let currentPageData = {
    x: window.screenX,
    y: window.screenY,
    width: window.innerWidth,
    height: window.innerHeight
}

let remotePageData = { x: 0, y: 0, width: 100, height: 100 };
let socket;
let isConnected = false;
let hasRemoteData = false;
let isFullySynced = false;
let noiseOffset = 0; 
let oceanLevelY = 0; 
let particles = [];
const PARTICLE_COUNT = 50;

function setup() {
    createCanvas(windowWidth, windowHeight);
    frameRate(60);
    socket = io();
    
    for (let i = 0; i < PARTICLE_COUNT; i++) {
        particles.push(new Particle());
    }

    socket.on('connect', () => {
        isConnected = true;
        socket.emit('win1update', currentPageData);
        setTimeout(() => {
            socket.emit('requestSync');
        }, 500);
    });

    socket.on('getdata', (response) => {
        if (response && response.data && isValidRemoteData(response.data)) {
            remotePageData = response.data;
            hasRemoteData = true;
            socket.emit('confirmSync');
        }
    });

    socket.on('fullySynced', (synced) => {
        isFullySynced = synced;
    });

    socket.on('peerDisconnected', () => {
        hasRemoteData = false;
        isFullySynced = false;
    });

    socket.on('disconnect', () => {
        isConnected = false;
        hasRemoteData = false;
        isFullySynced = false;
    });

    socket.on('syncUpdate', (data) => {
        if (data.noiseOffset !== undefined) noiseOffset = data.noiseOffset;
        if (data.oceanLevelY !== undefined) oceanLevelY = data.oceanLevelY;
    });
}

function isValidRemoteData(data) {
    return data && 
           typeof data.x === 'number' && 
           typeof data.y === 'number' && 
           typeof data.width === 'number' && data.width > 0 &&
           typeof data.height === 'number' && data.height > 0;
}

function checkWindowPosition() {
    // Lectura de nuevas posiciones/tamaños
    const newX = window.screenX;
    const newY = window.screenY;
    const newW = window.innerWidth;
    const newH = window.innerHeight;

    // Verificar si ha habido cambios antes de actualizar y emitir
    if (newX !== currentPageData.x || newY !== currentPageData.y || 
        newW !== currentPageData.width || newH !== currentPageData.height) {

        currentPageData.x = newX;
        currentPageData.y = newY;
        currentPageData.width = newW;
        currentPageData.height = newH;
        
        socket.emit('win1update', currentPageData); 
    }
}


function draw() {
    background(0, 50, 100); 
    
    if (!isConnected || !hasRemoteData || !isFullySynced || oceanLevelY === 0) {
        showStatus(
            !isConnected ? 'Conectando al servidor...' : 
            !hasRemoteData ? 'Esperando conexión de la otra ventana...' : 
            oceanLevelY === 0 ? 'Obteniendo nivel del océano...' :
            'Sincronizando datos...', 
            color(255, 165, 0)
        );
        return;
    }

    checkWindowPosition(); 

    // **CORRECCIÓN CLAVE:** Usar window.screenY para la lectura más inmediata de la posición.
    const waveY = oceanLevelY - window.screenY; 

    // Configuración de la ola
    const waveHeight = 80;
    const resolution = 15; 
    const noiseScale = 0.005; 
    
    noStroke();
    fill(0, 150, 200, 200); 

    beginShape();
    vertex(0, height);
    
    let isGapDetected = false;
    let gapSide = null; 

    // Detección de grieta (horizontal)
    if (currentPageData.x + currentPageData.width < remotePageData.x) { 
        isGapDetected = true;
        gapSide = 'right';
    } else if (remotePageData.x + remotePageData.width < currentPageData.x) { 
        isGapDetected = true;
        gapSide = 'left';
    }
    
    // Dibujar la ola
    for (let i = 0; i <= resolution; i++) {
        let x = map(i, 0, resolution, 0, width);
        let noiseVal = noise((currentPageData.x + x) * noiseScale, noiseOffset);
        let y = waveY + map(noiseVal, 0, 1, -waveHeight / 2, waveHeight / 2);

        // Aplanar el borde para la cascada
        if (isGapDetected) {
            if (gapSide === 'right' && x > width * 0.9) { 
                 y = lerp(y, waveY, (x - width * 0.9) / (width * 0.1));
            } else if (gapSide === 'left' && x < width * 0.1) { 
                y = lerp(y, waveY, (width * 0.1 - x) / (width * 0.1));
            }
        }

        vertex(x, y);
    }
    
    vertex(width, height);
    endShape(CLOSE);
    
    // --- Lógica de la Cascada (solo si hay GAP) ---
    if (isGapDetected) {
        push();
        if (gapSide === 'right') {
            translate(width, waveY); 
        } else {
            translate(0, waveY); 
        }

        for (let p of particles) {
            p.update();
            p.show();
        }
        pop();
    }
}

class Particle {
    constructor() {
        this.reset();
    }

    reset() {
        this.x = random(-5, 5); 
        this.y = random(0); 
        this.z = random(0, 20); 
        this.vy = random(1, 4); 
        this.life = 255;
    }

    update() {
        this.y += this.vy;
        this.life -= 5;
        if (this.life < 0) {
            this.reset();
        }
    }

    show() {
        let size = map(this.z, 0, 20, 2, 8);
        let alpha = map(this.life, 0, 255, 0, 200);
        fill(100, 200, 255, alpha); 
        ellipse(this.x, this.y, size, size);
    }
}


function showStatus(message, statusColor) {
    textSize(24);
    textAlign(CENTER, CENTER);
    noStroke();
    fill(0, 0, 0, 180);
    rectMode(CENTER);
    let textW = textWidth(message) + 40;
    let textH = 40;
    rect(width / 2, height / 2, textW, textH, 10);
    fill(statusColor);
    text(message, width / 2, height / 2);
}

function windowResized() {
    resizeCanvas(windowWidth, windowHeight);
    checkWindowPosition(); 
}
```

page2.js
```js
let currentPageData = {
    x: window.screenX,
    y: window.screenY,
    width: window.innerWidth,
    height: window.innerHeight

}

let remotePageData = { x: 0, y: 0, width: 100, height: 100 };
let socket;
let isConnected = false;
let hasRemoteData = false;
let isFullySynced = false;
let noiseOffset = 0; 
let oceanLevelY = 0; 
let particles = [];
const PARTICLE_COUNT = 50;

function setup() {
    createCanvas(windowWidth, windowHeight);
    frameRate(60);
    socket = io();
    
    for (let i = 0; i < PARTICLE_COUNT; i++) {
        particles.push(new Particle());
    }

    socket.on('connect', () => {
        isConnected = true;
        socket.emit('win2update', currentPageData);
        setTimeout(() => {
            socket.emit('requestSync');
        }, 500);
    });

    socket.on('getdata', (response) => {
        if (response && response.data && isValidRemoteData(response.data)) {
            remotePageData = response.data;
            hasRemoteData = true;
            socket.emit('confirmSync');
        }
    });

    socket.on('fullySynced', (synced) => {
        isFullySynced = synced;
    });

    socket.on('peerDisconnected', () => {
        hasRemoteData = false;
        isFullySynced = false;
    });

    socket.on('disconnect', () => {
        isConnected = false;
        hasRemoteData = false;
        isFullySynced = false;
    });

    socket.on('syncUpdate', (data) => {
        if (data.noiseOffset !== undefined) noiseOffset = data.noiseOffset;
        if (data.oceanLevelY !== undefined) oceanLevelY = data.oceanLevelY;
    });
}

function isValidRemoteData(data) {
    return data && 
           typeof data.x === 'number' && 
           typeof data.y === 'number' && 
           typeof data.width === 'number' && data.width > 0 &&
           typeof data.height === 'number' && data.height > 0;
}

function checkWindowPosition() {
    // Lectura de nuevas posiciones/tamaños
    const newX = window.screenX;
    const newY = window.screenY;
    const newW = window.innerWidth;
    const newH = window.innerHeight;

    // Verificar si ha habido cambios antes de actualizar y emitir
    if (newX !== currentPageData.x || newY !== currentPageData.y || 
        newW !== currentPageData.width || newH !== currentPageData.height) {

        currentPageData.x = newX;
        currentPageData.y = newY;
        currentPageData.width = newW;
        currentPageData.height = newH;
        
        socket.emit('win2update', currentPageData); 
    }
}


function draw() {
    background(0, 50, 100); 
    
    if (!isConnected || !hasRemoteData || !isFullySynced || oceanLevelY === 0) {
        showStatus(
            !isConnected ? 'Conectando al servidor...' : 
            !hasRemoteData ? 'Esperando conexión de la otra ventana...' : 
            oceanLevelY === 0 ? 'Obteniendo nivel del océano...' :
            'Sincronizando datos...', 
            color(255, 165, 0)
        );
        return;
    }

    checkWindowPosition(); 
    
    // **CORRECCIÓN CLAVE:** Usar window.screenY para la lectura más inmediata de la posición.
    const waveY = oceanLevelY - window.screenY; 

    // Configuración de la ola
    const waveHeight = 80;
    const resolution = 15; 
    const noiseScale = 0.005; 
    
    noStroke();
    fill(0, 150, 200, 200); 

    beginShape();
    vertex(0, height);
    
    let isGapDetected = false;
    let gapSide = null; 

    // Detección de grieta (horizontal)
    if (currentPageData.x + currentPageData.width < remotePageData.x) { 
        isGapDetected = true;
        gapSide = 'right';
    } else if (remotePageData.x + remotePageData.width < currentPageData.x) { 
        isGapDetected = true;
        gapSide = 'left';
    }
    
    // Dibujar la ola
    for (let i = 0; i <= resolution; i++) {
        let x = map(i, 0, resolution, 0, width);
        let noiseVal = noise((currentPageData.x + x) * noiseScale, noiseOffset);
        let y = waveY + map(noiseVal, 0, 1, -waveHeight / 2, waveHeight / 2);

        // Aplanar el borde para la cascada
        if (isGapDetected) {
            if (gapSide === 'right' && x > width * 0.9) { 
                 y = lerp(y, waveY, (x - width * 0.9) / (width * 0.1));
            } else if (gapSide === 'left' && x < width * 0.1) { 
                y = lerp(y, waveY, (width * 0.1 - x) / (width * 0.1));
            }
        }

        vertex(x, y);
    }
    
    vertex(width, height);
    endShape(CLOSE);
    
    // --- Lógica de la Cascada (solo si hay GAP) ---
    if (isGapDetected) {
        push();
        if (gapSide === 'right') {
            translate(width, waveY); 
        } else {
            translate(0, waveY); 
        }

        for (let p of particles) {
            p.update();
            p.show();
        }
        pop();
    }
}

class Particle {
    constructor() {
        this.reset();
    }

    reset() {
        this.x = random(-5, 5); 
        this.y = random(0); 
        this.z = random(0, 20); 
        this.vy = random(1, 4); 
        this.life = 255;
    }

    update() {
        this.y += this.vy;
        this.life -= 5;
        if (this.life < 0) {
            this.reset();
        }
    }

    show() {
        let size = map(this.z, 0, 20, 2, 8);
        let alpha = map(this.life, 0, 255, 0, 200);
        fill(100, 200, 255, alpha); 
        ellipse(this.x, this.y, size, size);
    }
}


function showStatus(message, statusColor) {
    textSize(24);
    textAlign(CENTER, CENTER);
    noStroke();
    fill(0, 0, 0, 180);
    rectMode(CENTER);
    let textW = textWidth(message) + 40;
    let textH = 40;
    rect(width / 2, height / 2, textW, textH, 10);
    fill(statusColor);
    text(message, width / 2, height / 2);
}

function windowResized() {
    resizeCanvas(windowWidth, windowHeight);
    checkWindowPosition(); 
}
```

server.js
```js
const express = require('express');
const http = require('http');
const socketIO = require('socket.io');
const path = require('path');
const app = express();
const server = http.createServer(app); 
const io = socketIO(server); 
const port = 3000;

let page1 = { x: 0, y: 0, width: 100, height: 100 };
let page2 = { x: 0, y: 0, width: 100, height: 100 };
let connectedClients = new Map();
let syncedClients = new Set();
let noiseOffset = 0; // Para sincronizar la animación de olas
const OCEAN_LEVEL_Y = 500; // Nuevo: Nivel Y absoluto del agua en la pantalla (Ej. 500px desde el tope)

app.use(express.static(path.join(__dirname, 'views')));

app.get('/page1', (req, res) => {
    res.sendFile(path.join(__dirname, 'views', 'page1.html'));
});

app.get('/page2', (req, res) => {
    res.sendFile(path.join(__dirname, 'views', 'page2.html'));
});

// Bucle para actualizar la variable de tiempo de las olas
setInterval(() => {
    noiseOffset += 0.005; // Velocidad de la ola
    // Enviar la hora de la ola y el nivel del océano
    io.emit('syncUpdate', { 
        noiseOffset: noiseOffset,
        oceanLevelY: OCEAN_LEVEL_Y
    });
}, 1000 / 60); // 60 FPS

io.on('connection', (socket) => {
    console.log('A user connected - ID:', socket.id);
    connectedClients.set(socket.id, { page: null, synced: false });
    
    socket.on('disconnect', () => {
        console.log('User disconnected - ID:', socket.id);
        connectedClients.delete(socket.id);
        syncedClients.delete(socket.id);
        socket.broadcast.emit('peerDisconnected');
        checkAndNotifySyncStatus(); 
    });

    socket.on('win1update', (window1) => {
        if (isValidWindowData(window1)) {
            page1 = window1;
            connectedClients.set(socket.id, { page: 'page1', synced: connectedClients.get(socket.id)?.synced || false });
            socket.broadcast.emit('getdata', { data: page1, from: 'page1' });
            checkAndNotifySyncStatus();
        }
    });

    socket.on('win2update', (window2) => {
        if (isValidWindowData(window2)) {
            page2 = window2;
            connectedClients.set(socket.id, { page: 'page2', synced: connectedClients.get(socket.id)?.synced || false });
            socket.broadcast.emit('getdata', { data: page2, from: 'page2' });
            checkAndNotifySyncStatus();
        }
    });

    socket.on('requestSync', () => {
        const clientInfo = connectedClients.get(socket.id);
        if (clientInfo?.page === 'page1') {
            socket.emit('getdata', { data: page2, from: 'page2' });
        } else if (clientInfo?.page === 'page2') {
            socket.emit('getdata', { data: page1, from: 'page1' });
        }
        // Enviar datos de sincronización
        socket.emit('syncUpdate', { 
            noiseOffset: noiseOffset,
            oceanLevelY: OCEAN_LEVEL_Y
        });
    });

    socket.on('confirmSync', () => {
        syncedClients.add(socket.id);
        const clientInfo = connectedClients.get(socket.id);
        if (clientInfo) {
            connectedClients.set(socket.id, { ...clientInfo, synced: true });
        }
        checkAndNotifySyncStatus();
    });    
});

function isValidWindowData(data) {
    return data && 
           typeof data.x === 'number' && 
           typeof data.y === 'number' && 
           typeof data.width === 'number' && data.width > 0 &&
           typeof data.height === 'number' && data.height > 0;
}

function checkAndNotifySyncStatus() {
    const page1Clients = Array.from(connectedClients.entries()).filter(([, info]) => info.page === 'page1');
    const page2Clients = Array.from(connectedClients.entries()).filter(([, info]) => info.page === 'page2');
    
    const bothPagesConnected = page1Clients.length > 0 && page2Clients.length > 0;
    const allClientsSynced = Array.from(connectedClients.keys()).every(id => syncedClients.has(id));
    const hasMinimumClients = connectedClients.size >= 2;

    const fullySynced = bothPagesConnected && allClientsSynced && hasMinimumClients;
    io.emit('fullySynced', fullySynced);
}

server.listen(port, () => {
    console.log(`Server is listening on http://localhost:${port}`);
});
```
## AUTOEVALUACIÓN 🪼🫧


**Nota propuesta:** 5.0

**Justificación general**

Considero que mi desempeño en esta unidad merece la nota máxima porque realicé TODAS las actividades propuestas, documenté paso a paso cada proceso con evidencias en la bitácora, respondí las preguntas de reflexión con ejemplos propios, realicé modificaciones creativas al código y logré aplicar los conceptos vistos (cliente-servidor, HTTP, Socket.IO, p5.js, etc.) en un proyecto funcional.

**Actividad 01**

 **Defensa de la nota:**

Ejecuté los comandos npm install y npm start, dejando en la bitácora lo que iba pasando en la terminal y para qué servía cada cosa. Después expliqué qué mostraban las páginas page1 y page2 al abrirlas y registré los mensajes que aparecían tanto en la terminal del servidor como en el navegador. También analicé cómo se sincronizaban los círculos cuando movía las ventanas.

**Evidencias:** capturas de terminal, descripciones de comportamiento visual y análisis de los resultados bien bacanos :) .


**Actividad 02**

 **Defensa de la nota:**
Reflexioné sobre varios temas y hasta encontré ejemplos de cliente-servidor en la vida diaria. Analicé la URL de un sitio web explicando sus componentes y comparé HTTP con protocolos seriales antiguos, viendo similitudes y diferencias. También identifiqué las partes de un formulario desde HTML, CSS y JavaScript, y comparé el bucle draw() con el modelo basado en eventos. Además, pensé en las ventajas de usar JavaScript tanto en cliente como en servidor y expliqué la diferencia entre el HTTP tradicional y los WebSockets.

  
**Evidencias:** textos de reflexión, ejemplos propios, comparaciones bien bacanas :) .



**Actividad 03** 

 **Defensa de la nota:**

Modifiqué las rutas en el servidor (por ejemplo de /page1 a /pagina_uno) para ver cómo se asociaban las URLs con las respuestas. También probé la conexión de distintos usuarios y revisé los IDs que aparecían en la terminal, además de mirar qué pasaba cuando alguien se desconectaba. Experimenté con socket.emit y socket.broadcast.emit, entendiendo bien la diferencia entre ambos, y hasta cambié el puerto para comprobar que todo siguiera funcionando
  
**Evidencias:** capturas de terminal, registro de IDs, descripciones del resultado de cada prueba bien bacanos :) .



**Actividad 04** 

 **Defensa de la nota:**
 
Verifiqué los errores que aparecían en consola cuando el servidor se detenía y también fui probando a comentar líneas de código para entender mejor cómo se estaba dando la comunicación. Usé varios console.log para revisar qué datos se estaban enviando entre pestañas y me puse a analizar la función checkWindowPosition(), donde entendí que se optimiza porque solo detecta los cambios reales. Además, hice mis propias modificaciones creativas al código, como cambiar el background() según la distancia entre ventanas y meterle una idea mía para darle un toque más personal.
  
**Evidencias:** pruebas en consola, modificaciones de código documentadas y reflexión sobre el diseño eficiente bien bacana :) .

**Actividad 05**

 **Defensa de la nota:**

- Hice una aplicación super cool de olas interactiva.
- Hice el bocetico y los pasos que implemente.
- Documenté todos los archivos (server, page1, page2, scripts JS).

**Evidencias:** código completo del proyecto, explicación de la idea, bocetos y pruebas visuales.





