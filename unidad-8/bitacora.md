
# Evidencias de la unidad 8

## Seek: Investigación 🔎
### Actividad 01

**🐡🪸 Reporta en tu bitácora**

1. Documenta los referentes visuales que te inspiren.
<img width="225" height="225" alt="image" src="https://github.com/user-attachments/assets/f3e14949-b0ba-406b-9e58-5b9bd9eb6711" />

<img width="220" height="210" alt="image" src="https://github.com/user-attachments/assets/e850c671-b7c2-4c98-a2be-798bfa50207b" />
<img width="228" height="221" alt="image" src="https://github.com/user-attachments/assets/ce3b3c56-9e05-467c-ab0c-e3ee2a50e481" />
<img width="800" height="450" alt="image" src="https://github.com/user-attachments/assets/d2be2b5d-b724-4860-beed-f547ae8c90aa" />

- La canción que voy a usar es [Scene halloween](https://youtu.be/unDEgaQFgs8?si=OTH_nJTRK2Ychvoq)
2. Define el concepto de las visuales que quieres crear.
- Continuando con la tematica del Rave de gatos, voy a crear 4 salas mas de animales en fiesta. Una sala de perros, otra de peces , otra de hamsters Y una combinada.
3. Explica cómo el móvil y el micro:bit controlarán las visuales.
- En el celular se podran manejar las luces de la fiesta ayeee. Y desde el microbit con a y b podras cambiar entre salas.
4. Haz un bocetos de todas las interfaces del sistema.

- La idea es que asi se vean las salas nuevas.

  
  <img width="962" height="584" alt="Sin título" src="https://github.com/user-attachments/assets/a300b142-4c9c-49c5-9df5-2ccdf76f023a" />
- Algo asi se ve el celular

  
  <img width="326" height="530" alt="image" src="https://github.com/user-attachments/assets/5f38acfd-6706-4ea1-86d8-a85b7c97f8a8" />

5. Haz un diagrama que explique cómo se comunicarán los diferentes componentes del sistema.
- Me niego a hacer diagramas 

## Apply: Aplicación 🛠
### Actividad 02

**🐡🪸 Reporta en tu bitácora**

**RESULTADOOOOO**

1. 
![Vídeo sin título ‐ Hecho con Clipchamp](https://github.com/user-attachments/assets/49172829-0cf0-46cc-8bfa-c0083590a3e1)


Empecé armando el rave con varias salas: gatos, perros, peces, hámsters y una combinada. La idea era que se pudiera cambiar de sala con las teclas A y B o desde el micro:bit. Monté toda la estructura en p5.js con el audio, el FFT y los animales saltando al ritmo, pero cuando lo corrí la pantalla se quedaba negra y no mostraba nada.

Me puse a revisar todo y al final resultó que el error era una bobada: una imagen estaba mal nombrada. Tenía escrito hamster3.jpg y es con png en el código. Por eso el preload nunca terminaba y no llegaba a setup(). Lo corregí y todo empezó a cargar normal.

Después ajusté la parte del audio para que empezara con un clic (por el bloqueo del navegador) y revisé que los animales saltaran con el beat. También probé la conexión del micro:bit con el servidor y funcionó: cuando mandaba el mensaje del botón B cambiaba de sala.


2. Incluye todos los códigos:
**servidor**
```js
const { SerialPort } = require('serialport');
const { ReadlineParser } = require('@serialport/parser-readline');


const portMicrobit = new SerialPort({ path: 'COM4', baudRate: 115200 });
const parser = portMicrobit.pipe(new ReadlineParser({ delimiter: '\n' }));

parser.on('data', (data) => {
    const button = data.trim();
    console.log("Micro:bit envió:", button);

    if (button === 'A') {
        io.emit('message', { type: 'microbitButton', button: 'A' });
    }
    if (button === 'B') {
        io.emit('message', { type: 'microbitButton', button: 'B' });
    }
});

const express = require('express');
const http = require('http');
const socketIO = require('socket.io');

const app = express();
const server = http.createServer(app); 
const io = socketIO(server); 
const port = 3000;

app.use(express.static('public'));

io.on('connection', (socket) => {
    console.log('New client connected');
    socket.on('message', (message) => {
        console.log('Received message =>', message);
        socket.broadcast.emit('message', message);
    });

    socket.on('disconnect', () => {
        console.log('Client disconnected');
    });
});

server.listen(port, () => {
    console.log(`Server is listening on http://localhost:${port}`);
});
```

**cliente móvil**
```js
let socket;
let lightsOn = true;

function setup() {
  createCanvas(windowWidth, windowHeight);
  socket = io();
  socket.on("connect", () => console.log("Celular conectado"));
}

function draw() {
  background(lightsOn ? color(255, 100, 200) : color(20, 0, 40));
  fill(255);
  textAlign(CENTER, CENTER);
  textSize(22);
  
  if (lightsOn) {
    text(" TAP para CAMBIAR luces", width / 2, height / 2 - 20);
    text(" MANTÉN presionado para APAGAR", width / 2, height / 2 + 20);
  } else {
    text(" TAP para ENCENDER el RAVE", width / 2, height / 2);
  }
}

function touchStarted() {
  if (socket && socket.connected) {
    if (lightsOn) {
      socket.emit("message", { type: "colorShift" });
    } else {
      socket.emit("message", { type: "lightControl", state: true });
      lightsOn = true;
    }
  }
  return false;
}

function touchEnded() {
  if (socket && socket.connected) {
    socket.emit("message", { type: "lightControl", state: false });
    lightsOn = false;
  }
  return false;
}

```

 
**cliente de escritorio** 
 ```js
let animals = [];
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
let dogImages = [];
let fishImages = [];
let hamsterImages = [];
let mixedImages = [];

let currentRoom = 0; 

function preload() {
  soundFormats('mp3', 'ogg');
  song = loadSound('SceneHalloween.mp3', () => {
    console.log("🎵 Canción cargada");
  });

  
  function safeLoadImage(path) {
    try {
      return loadImage(path);
    } catch {
      console.warn("No se encontró:", path);
      return createGraphics(100, 100); 
    }
  }

  for (let i = 1; i <= 5; i++) {
    catImages.push(safeLoadImage(`cat${i}.png`));
    dogImages.push(safeLoadImage(`dog${i}.png`));
    fishImages.push(safeLoadImage(`fish${i}.png`));
    hamsterImages.push(safeLoadImage(`hamster${i}.png`));
  }

  mixedImages = [...catImages, ...dogImages, ...fishImages, ...hamsterImages];
}

function setup() {
  createCanvas(windowWidth, windowHeight);
  imageMode(CENTER);
  fft = new p5.FFT();
  createRoom();

  beatInterval = (60 / bpm) * 1000;

  socket = io();
  socket.on("connect", () => console.log("💻 Desktop conectado al servidor"));

  socket.on("message", (data) => {
    if (data.type === "lightControl") {
      lightsOn = data.state;
    } else if (data.type === "colorShift") {
      colorShift = random(255);
    } else if (data.type === "microbitButton") {
      if (data.button === "B") nextRoom();
      if (data.button === "A") previousRoom();
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
    for (let a of animals) a.jump();
    lastBeat = millis();
  }

  if (lightsOn) {
    for (let a of animals) {
      a.update();
      a.display(jumpScale);
    }
  }

  drawRoomName();
}

function drawStartScreen() {
  background(0);
  fill(255);
  textAlign(CENTER, CENTER);
  textSize(32);
  text(" TOCA PARA EMPEZAR EL RAVE ", width / 2, height / 2);
}

function mousePressed() {
  if (!audioStarted) {
    userStartAudio();
    song.loop();
    audioStarted = true;
  }
}

function keyPressed() {
  if (key === 'b' || key === 'B') nextRoom();
  if (key === 'a' || key === 'A') previousRoom();
}

function nextRoom() {
  currentRoom = (currentRoom + 1) % 5;
  createRoom();
}

function previousRoom() {
  currentRoom = (currentRoom - 1 + 5) % 5;
  createRoom();
}

function createRoom() {
  animals = [];
  let imgs;

  switch (currentRoom) {
    case 0: imgs = catImages; break;
    case 1: imgs = dogImages; break;
    case 2: imgs = fishImages; break;
    case 3: imgs = hamsterImages; break;
    case 4: imgs = mixedImages; break;
  }

  for (let i = 0; i < 50; i++) {
    animals.push(new Animal(random(width), random(height - 100), random(imgs)));
  }
}

function drawRoomName() {
  fill(255);
  textSize(20);
  textAlign(RIGHT, TOP);
  let names = [
    "SALA DE GATOS ",
    "SALA DE PERROS ",
    "SALA DE PECES ",
    "SALA DE HÁMSTERS ",
    "SALA COMBINADA "
  ];
  text(names[currentRoom], width - 20, 20);
}

class Animal {
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
**micro:bit.**

```
from microbit import *
import bluetooth
import uart

uart.init(baudrate=115200)

while True:
    if button_a.was_pressed():
        uart.write("A\n")
    if button_b.was_pressed():
        uart.write("B\n")
    sleep(100)

```







