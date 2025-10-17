
# Evidencias de la unidad 7


## Actividad 01

**🧐🧪✍️ Reporta en tu bitácora**


1. ¿Qué URL de Dev Tunnels obtuviste? ¿Por qué crees que necesitamos usar esta URL en lugar de http://localhost:3000 o la IP local de tu computador para que el celular se conecte?


    - La URL que obtuve fue:
  https://fm4m11mt-3000.use2.devtunnels.ms/

    Necesitamos usar esa en lugar de http://localhost:3000 o la IP local porque el celular no puede conectarse al localhost del computador.

2. Describe brevemente qué hace npm install y npm start.
    - npm install descarga e instala todas las dependencias que necesita el proyecto para funcionar, según lo que esté listado en el archivo package.json.

    - npm start ejecuta el proyecto, normalmente iniciando el servidor o la aplicación principal que está configurada en el mismo archivo package.json.

    
3. ¿Qué mensajes observaste en la terminal del servidor al conectar el cliente de escritorio y el cliente móvil? ¿Eran diferentes los mensajes o identificadores?
    - Cuando se conectó el cliente de escritorio y luego el móvil, el servidor mostró un mensaje “New client connected” para cada uno, pero con identificadores distintos, porque cada cliente tiene su propio socket ID.

   <img width="643" height="214" alt="image" src="https://github.com/user-attachments/assets/be7dc86b-d31f-4a9a-9e14-c4e1e0cb4904" />

4. Describe el comportamiento observado: ¿Funcionó la interacción? ¿Hubo algún retraso (latencia)?
   
    - Sí, la interacción funcionó bien. Cuando movía el dedo en el celular, las visuales en el escritorio reaccionaban casi al instante, así que se notaba que la conexión entre ambos estaba activa.
    - Solo se notaba una ligera latencia, pero poquito, qn sabe si fue mi pc pq es una porqueria  :) . 
## Actividad 02
**🧐🧪✍️ Reporta en tu bitácora**


Explica con tus propias palabras: ¿Por qué es necesario Dev Tunnels en este escenario y cómo funciona conceptualmente?
    - Dev Tunnels es necesario porque el servidor está corriendo en localhost:3000, y esa dirección solo sirve dentro de mi propio computador. Si intento abrirla desde el celular, no conecta, porque para el celular “localhost” sería él mismo, no mi PC.

Describe la función de touchMoved() y por qué se usa la variable threshold en el cliente móvil.
    - touchMoved() se activa cada vez que toco la pantalla y muevo el dedo.
Ahí se toman las coordenadas del toque y se mandan al servidor con Socket.IO, que luego las envía al escritorio para que las visuales reaccionen.

    - El threshold sirve para que no se manden demasiados mensajes si el dedo apenas se mueve o tiembla un poco. Solo cuando hay un cambio más grande, se envía la info, así no se satura la conexión.

Compara brevemente Dev Tunnels con simplemente usar la IP local. ¿Cuáles son las ventajas y desventajas de cada uno?
| Método          | Ventajas                                              | Desventajas                                                        |
| --------------- | ----------------------------------------------------- | ------------------------------------------------------------------ |
| **IP local**    | Sirve si el compu y el celular están en la misma red. | No funciona si el celular usa datos o está en otra red.            |
| **Dev Tunnels** | Funciona desde cualquier lugar y usa HTTPS seguro.    | Puede tener un poquito más de retraso o depender más del internet. |


Coloca en tu bitácora capturas de pantalla del sistema completo funcionando. Esto lo puedes hacer abriendo tanto el mobile como el desktop en tu computador y tomando una captura de pantalla de todos los involucrados (celular, computador y terminal).
<img width="871" height="439.5" alt="Captura de pantalla 2025-10-15 190628" src="https://github.com/user-attachments/assets/4335d236-33ed-46b1-8e65-afd2ccee7bb3" />
<img width="585" height="1266" alt="image" src="https://github.com/user-attachments/assets/11957e6d-1655-4dc3-8558-4184241f11ca" />


## Actividad 03

1. ¿Cuál es la función principal de express.static(‘public’) en este servidor? ¿Cómo se compara con el uso de app.get(‘/ruta’, …) del servidor de la Unidad 6?
  - Esa línea le dice al servidor que todo lo que esté dentro de la carpeta public se pueda abrir directamente desde el navegador.
2. Explica detalladamente el flujo de un mensaje táctil: ¿Qué evento lo envía desde el móvil? ¿Qué evento lo recibe el servidor? ¿Qué hace el servidor con él? ¿Qué evento lo envía el servidor al escritorio? ¿Por qué se usa socket.broadcast.emit en lugar de io.emit o socket.emit en este caso?


  -  En el celular, cuando muevo el dedo sobre la pantalla, se activa touchMoved(). Esa función crea un objeto con las coordenadas del toque y lo envía al servidor con:
```js
socket.emit('message', { type: 'touch', x: mouseX, y: mouseY });
```

  -  El servidor escucha ese evento con:
```js
socket.on('message', (message) => { ... })
```

  -  Ahí recibe el mensaje del celuco. Luego el servidor usa
```js
socket.broadcast.emit('message', message);
```

  -  para reenviarlo a todos los demás clientes conectados, excepto al que lo envió (en este caso, el escritorio).

  -  Se usa socket.broadcast.emit y no io.emit porque no quiero que el móvil se reenvíe su propio mensaje, solo que lo reciba el escritorio.

 
Si conectaras dos computadores de escritorio y un móvil a este servidor, y movieras el dedo en el móvil, ¿Quién recibiría el mensaje retransmitido por el servidor? ¿Por qué?
  - Si tengo dos compus con el cliente de escritorio y un celular, cuando muevo el dedo en el celular, los dos escritorios recibirían el mensaje, porque el servidor lo retransmite a todos los clientes conectados, menos al que lo envió.

    
¿Qué información útil te proporcionan los mensajes console.log en el servidor durante la ejecución?

  - Los console.log sirven para ver lo que está pasando en tiempo real.
## Actividad 04

## APPLY

Q RETO TAN HORRIBLEEEKJDFNWKDNFPWEHFWEFJEWFJBW


ME ESTA PASANDO ESTO:


<img width="345" height="333" alt="image" src="https://github.com/user-attachments/assets/1b1be96c-942a-4860-91da-9b8445a9390b" />


Me inspire en:


<img height="229px" src="https://media2.giphy.com/media/v1.Y2lkPWZjZGU1NDk1Y3lvN2puOGdwYmQ5eXN6Zjd3M3N1eDc3cWxsYW5mMHI5MHYwdjBwMyZlcD12MV9naWZzX3NlYXJjaCZjdD1n/W8krmZSDxPIfm/giphy.gif" width="400px" itemtype="http://schema.skype.com/Giphy" key="gif_0">


quiero hacer la simulacion de un mini rave con gatos saltando asi bien hallowen, com si fuera una fiesta de hallowen, con muchas flashing lights asi bien loko. Y que los gatos desaparecieran cuando las luces se apagaran para simular una habitacion.


Usando de base el proyecto que estabamos trabajando en clase.  En el sketch del compu puse el código para que los gatos saltaran al ritmo de la canción. Como el tema tiene 162 BPM, eso da como 2.7 saltos por segundo, así que usé eso para sincronizar el movimiento. Cada gato es una imagen PNG que se mueve para arriba y abajo al ritmo.


Y por el lado del móvil, hice que aparecieran unos controles para cambiar los colores de las luces o apagarlas. Cuando las luces se apagan, los gatos se dejan de ver, como si el lugar quedara oscuro. Cuando las prendes, vuelve toda la locura de colores.



<img width="1910" height="891" alt="image" src="https://github.com/user-attachments/assets/768e1539-7a60-413e-87df-5c333ebbbe91" />




dea fue probar todo junto: el audio, los saltos, las luces, y que todo respondiera bien entre el celular y el escritorio. Cuando por fin lo vi funcionando con la canción y los gatos brincando, fue una locura total

**INDEX DESKTOP**
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Cat Rave Desktop</title>

  <script src="https://cdn.jsdelivr.net/npm/p5@1.11.0/lib/p5.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/p5@1.11.0/lib/addons/p5.sound.min.js"></script>
  <script src="https://cdn.socket.io/4.7.5/socket.io.min.js"></script>
  <script src="sketch.js" defer></script>

  <style>
    body {
      margin: 0;
      overflow: hidden;
      background-color: black;
    }
  </style>
</head>
<body></body>
</html>

```
**SKETCH DESKTOP**
```js
let cats = [];
let fft, song;
let audioStarted = false;

let socket;
let lightsOn = true;
let colorShift = 0;
let bpm = 162;
let beatInterval;
let lastBeat = 0;
let jumpScale = 0;
let catImages = [];

function preload() {
  soundFormats('mp3', 'ogg');
  song = loadSound('SceneHalloween.mp3');

 
  for (let i = 1; i <= 5; i++) {
    catImages.push(loadImage(`cat${i}.png`));
  }
}

function setup() {
  createCanvas(windowWidth, windowHeight);
  imageMode(CENTER);
  fft = new p5.FFT();


  for (let i = 0; i < 50; i++) {
    cats.push(new Cat(random(width), random(height - 100), random(catImages)));
  }

  beatInterval = (60 / bpm) * 1000;

  socket = io();
  socket.on("connect", () => console.log("Conectado al servidor"));


  socket.on("message", (data) => {
    if (data.type === "lightControl") {
      lightsOn = data.state;
    } else if (data.type === "colorShift") {
      colorShift = random(255);
    }
  });
}

function draw() {

  if (lightsOn) {
    let r = sin(frameCount * 0.1) * 127 + 128;
    let g = sin(frameCount * 0.15 + colorShift) * 127 + 128;
    let b = sin(frameCount * 0.2 + colorShift * 2) * 127 + 128;
    background(r, g, b);
  } else {
    background(0);
  }

  if (!audioStarted) {
    drawStartScreen();
    return;
  }

  let spectrum = fft.analyze();
  let bass = fft.getEnergy('bass');

 
  if (millis() - lastBeat > beatInterval) {
    jumpScale = map(bass, 0, 255, 0.5, 1.3);
    for (let c of cats) c.jump();
    lastBeat = millis();
  }

 
  if (lightsOn) {
    for (let c of cats) {
      c.update();
      c.display(jumpScale);
    }
  }
}

function drawStartScreen() {
  background(0);
  fill(255);
  textAlign(CENTER, CENTER);
  textSize(32);
  text(" TOCA PARA EMPEZAR EL RAVE DE GATOS ", width / 2, height / 2);
}

function mousePressed() {
  if (!audioStarted) {
    userStartAudio();
    song.loop();
    audioStarted = true;
  }
}

class Cat {
  constructor(x, y, img) {
    this.x = x;
    this.y = y;
    this.baseY = y;
    this.img = img;
    this.velY = 0;
    this.isJumping = false;
    this.size = random(100, 180);
  }

  jump() {
    if (!this.isJumping) {
      this.velY = -random(8, 14);
      this.isJumping = true;
    }
  }

  update() {
    if (this.isJumping) {
      this.y += this.velY;
      this.velY += 0.9; 
      if (this.y >= this.baseY) {
        this.y = this.baseY;
        this.isJumping = false;
      }
    }
  }

  display(scaleFactor) {
    push();
    translate(this.x, this.y);
    scale(scaleFactor);
    image(this.img, 0, 0, this.size, this.size);
    pop();
  }
}

```
**INDEX MOBILE**
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Cat Rave Controller</title>


  <script src="https://cdn.jsdelivr.net/npm/p5@1.11.0/lib/p5.min.js"></script>
  <script src="https://cdn.socket.io/4.7.5/socket.io.min.js"></script>
  <script src="sketch.js" defer></script>

  <style>
    body {
      margin: 0;
      overflow: hidden;
      background-color: black;
      color: white;
      font-family: sans-serif;
      text-align: center;
    }
  </style>
</head>
<body></body>
</html>

```

**SKETCH MOBILE**
```js
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Cat Rave Controller</title>


  <script src="https://cdn.jsdelivr.net/npm/p5@1.11.0/lib/p5.min.js"></script>
  <script src="https://cdn.socket.io/4.7.5/socket.io.min.js"></script>
  <script src="sketch.js" defer></script>

  <style>
    body {
      margin: 0;
      overflow: hidden;
      background-color: black;
      color: white;
      font-family: sans-serif;
      text-align: center;
    }
  </style>
</head>
<body></body>
</html>

```
AUTOEVALUACIÓN 🪼🫧
Nota propuesta: 4.0

Justificación general

Considero que mi desempeño en esta unidad merece la nota máxima porque realicé TODAS las actividades propuestas.


Actividad 02

Hice todo :)

Evidencias: textos de reflexión.

Actividad 03

- Defensa de la nota:

    - Hice todo :)

Actividad 04
- no lo hice 


Actividad 05

- Defensa de la nota:


    - Hice una aplicación super cool de gatos lokos.


    - Expliqué los pasos que implemente.


    - Documenté todos los archivos

