
# Evidencias de la unidad 5

## ACTIVIDAD 1 ##

Describe cómo se están comunicando el micro:bit y el sketch de p5.js. ¿Qué datos envía el micro:bit?

Se comunican por puerto serial utilizando el uart.

- El micro:bit usa uart.write(data) para enviar una línea de texto con datos separados por comas. Envia data = "{},{},{},{}\n".format(xValue, yValue, aState, bState)


- El sketch en p5.js usa la biblioteca p5.webserial.js para abrir el puerto serial, leer los datos y procesarlos en JavaScript.

¿Cómo es la estructura del protocolo ASCII usado?

- xValue,yValue,aState,bState\n

Muestra y explica la parte del código de p5.js donde lee los datos del micro:bit y los transforma en coordenadas de la pantalla.
```js
if (port.availableBytes() > 0) {
  let data = port.readUntil("\n");
  if (data) {
    data = data.trim();
    let values = data.split(",");
    if (values.length == 4) {
      microBitX = int(values[0]) + windowWidth / 2;
      microBitY = int(values[1]) + windowHeight / 2;
      microBitAState = values[2].toLowerCase() === "true";
      microBitBState = values[3].toLowerCase() === "true";
      updateButtonStates(microBitAState, microBitBState);
    } else {
      print("No se están recibiendo 4 datos del micro:bit");
    }
  }
}

```
- Se lee una línea hasta \n y se separa por comas con .split(","). Luego, los valores se convierten a sus respectivos tipos: xValue y yValue se transforman en coordenadas (microBitX, microBitY) centradas en la pantalla, y aState y bState se convierten en valores booleanos. Finalmente, se llama a updateButtonStates() para detectar eventos de los botones.


¿Cómo se generan los eventos A pressed y B released que se generan en p5.js a partir de los datos que envía el micro:bit?

 ```js
function updateButtonStates(newAState, newBState) {
  if (newAState === true && prevmicroBitAState === false) {
    // Botón A acaba de ser presionado
    lineModuleSize = random(50, 160);
    clickPosX = microBitX;
    clickPosY = microBitY;
    print("A pressed");
  }

  if (newBState === false && prevmicroBitBState === true) {
    // Botón B acaba de ser soltado
    c = color(random(255), random(255), random(255), random(80, 100));
    print("B released");
  }

  prevmicroBitAState = newAState;
  prevmicroBitBState = newBState;
}

```
- A pressed: Detecta cuando aState pasa de false a true.

- B released: Detecta cuando bState pasa de true a false.
  
Capturas de pantalla de los algunos dibujos que hayas hecho con el sketch.
<img width="984" height="913" alt="20250912_143048" src="https://github.com/user-attachments/assets/4e20f4a1-4648-4b5b-bb8c-d9d59f73bf37" />
<img width="984" height="913" alt="20250912_150448" src="https://github.com/user-attachments/assets/9f5d9f10-076a-49d3-8a69-4baba82e91cc" />

## ACTIVIDAD 2 ##

*Captura el resultado del experimento anterior.* ¿Por qué se ve este resultado?

- Al visualizar los mensajes binarios en texto (ASCII) se ve ilegible. Esto ocurre porque los datos en binario no representan letras ni numeros.
<img width="1001" height="263" alt="image" src="https://github.com/user-attachments/assets/f38316a0-bc5f-4651-839a-6c2488c77cab" />



*Captura el resultado del experimento anterior.* Lo que ves ¿Cómo está relacionado con esta línea de código?
- Cuando ponemos la visualización a todo hex se pueden ver los 8 bytes que se estan enviando. 2h: xValue y yValue → 2 * 2 bytes = 4 bytes. 2B: aState y bState → 2 * 1 byte = 2 bytes. Esto son 6 bytes y al incluir n\ se añaden dos bytes más.

¿Qué ventajas y desventajas ves en usar un formato binario en lugar de texto en ASCII?
- La ventajas del formato binario son : Ocupa menos espacio, se transmiten menos datos por mensaje y no hay necesidad de analizar ni convertir a texto.
- las desventajas del formato binario: No es tan legible.

*Captura el resultado del experimento.* ¿Cuántos bytes se están enviando por mensaje? ¿Cómo se relaciona esto con el formato '>2h2B'? ¿Qué significa cada uno de los bytes que se envían?
- Se envian 6 bytes por mensaje
- Cada byte o grupo de bytes representa uno de los datos que el micro:bit está enviando.
<img width="889" height="222" alt="image" src="https://github.com/user-attachments/assets/86ee9a76-472c-42c8-a9b1-65ec93ea425e" />

*Recuerda de la unidad anterior que es posible enviar números positivos y negativos para los valores de xValue y yValue.* ¿Cómo se verían esos números en el formato '>2h2B'?

- los números negativos se representan en complemento a dos, una forma estándar de codificación en la que el primer bit indica el signo del número.Un número positivo como 100 se guarda como 00000000 01100100 (en binario).
Un número negativo como -100 se guarda como 11111111 10011100.
Ambos ocupan 2 bytes, pero el primer bit (el más a la izquierda) indica si es positivo (0) o negativo (1).

*Captura el resultado del experimento.* ¿Qué diferencias ves entre los datos en ASCII y en binario? ¿Qué ventajas y desventajas ves en usar un formato binario en lugar de texto en ASCII? ¿Qué ventajas y desventajas ves en usar un formato ASCII en lugar de binario?

- El mensaje en binario no se entendía nada si lo veía como texto… eran como símbolos raros o letras que no tenían sentido. Después, aparecía la palabra "ASCII:" y ahí sí se veía clarito algo como 132,-45,1,0, que son los valores del acelerómetro y los botones.



    Luego cambié la vista en el programa a "hexadecimal" y ahí pude ver mejor el mensaje binario: eran seis bytes. Me acordé que en el código decía '>2h2B', y eso significa que se están enviando dos números grandes (los del acelerómetro) y dos pequeños (los de los botones). Cada uno ocupa un espacio fijo en bytes, y por eso el mensaje binario es más chiquito.



    Entonces, me di cuenta de las diferencias:
El formato binario es más corto y rápido, pero no se entiende fácil si lo mirás así nomás. En cambio, el ASCII es mucho más claro para leer, pero ocupa más espacio y puede ser más lento si se mandan muchos datos.



    Para mí, el ASCII te ayuda más porque podés leer todo.
<img width="872" height="89" alt="image" src="https://github.com/user-attachments/assets/d75e0167-1701-4041-8616-46fd6c8db58f" />

  ## ACTIVIDAD 3 ##
Explica por qué en la unidad anterior teníamos que enviar la información delimitada y además marcada con un salto de línea y ahora no es necesario.

- Antes habia que indicarle al programa que el texto debia pasar a la siguiente línea porque el tamaño del paquete no era fijo, además permiten que las lineas de texto sean comprensibles para los humanos. Ahora no es necesario porque el tamaño del paquete es fijo y no necesita un delimitador.

¿Qué ves en la consola? ¿Por qué crees que se produce este error?
- Cuando se envían datos a través de una comunicación serial, los bytes pueden llegar en fragmentos arbitrarios y sin respetar los límites de los paquetes. Cosa que produce una desincronización en la lectura de datos.
``` js 
microBitX: 5121 microBitY: -19456 microBitAState: false microBitBState: false 
 
microBitX: -22016 microBitY: 5121 microBitAState: false microBitBState: false 
 
microBitX: 197 microBitY: -22016 microBitAState: false microBitBState: true 
 
B released 
microBitX: -18432 microBitY: 205 microBitAState: false microBitBState: false 
 
microBitX: 3073 microBitY: -18432 microBitAState: false microBitBState: false 
 
microBitX: -22016 microBitY: 4097 microBitAState: false microBitBState: false 
 
microBitX: 201 microBitY: -22016 microBitAState: false microBitBState: true 
 
B released 
microBitX: -19456 microBitY: 197 microBitAState: false microBitBState: false 
```
¿Qué cambios tienen los programas y ¿Qué puedes observar en la consola del editor de p5.js?

- Con el framing (header + checksum) lo que pasa en la consola es mucho más claro. Ahora el micro:bit envía 8 bytes: primero el header [0xAA], después los 6 datos, y al final el checksum. Ahora en la consola se ven sincronizados los datos con las variable del micro:bit.

## ACTIVIDAD 4 ##
**Codigo a modificar**
```js
var x = 0;
var y = 0;
var stepSize = 5.0;

let fontSize = 10; 
let fontSizeMax = 72;
let fontSizeMin = 3;
var font = 'Georgia';
var letters = 'All the world\'s a stage, and all the men and women merely players. They have their exits and their entrances.';

var angleDistortion = 0.0;

var counter = 0;
let microBitX = 0;
let microBitY = 0;
let microBitAState = false;
let microBitBState = false;
let prevmicroBitAState = false;
let prevmicroBitBState = false;
let c;

//*********************************
// Código para soportar el serial
let port;
let connectBtn;
let microBitConnected = false;
//*********************************

const STATES = {
  WAIT_MICROBIT_CONNECTION: "WAITMICROBIT_CONNECTION",
  RUNNING: "RUNNING",
};

let appState = STATES.WAIT_MICROBIT_CONNECTION;

function setup() {
  createCanvas(displayWidth, displayHeight);
  background(255);
  cursor(CROSS);

  x = mouseX;
  y = mouseY;

  textFont(font);
  textAlign(LEFT);
  fill(0);
  c = color(1, 1, 1, 1);
  port = createSerial();
  connectBtn = createButton("Connect to micro:bit");
  connectBtn.position(0, 0);
  connectBtn.mousePressed(connectBtnClick);
}

function connectBtnClick() {
  if (!port.opened()) {
    port.open("MicroPython", 115200);
    connectionInitialized = false;
  } else {
    port.close();
  }
}

function updateButtonStates(newAState, newBState) {
  if (newAState === true && prevmicroBitAState === false) {
    x = microBitX;
    y = microBitY;
    print("A pressed: start drawing at", x, y);
  }

   if (newBState === true && prevmicroBitBState === false) {
    // Aquí guardamos la captura
    saveCanvas('microbit_screenshot_' + Date.now(), 'png');
    print("B pressed: screenshot taken!");
  }

  prevmicroBitAState = newAState;
  prevmicroBitBState = newBState;
}


function draw() {
  
  
  if (!port.opened()) 
  {
    connectBtn.html("Connect to micro:bit");
    microBitConnected = false;
  } else {
    microBitConnected = true;
    connectBtn.html("Disconnect");
  }

      if (port.availableBytes() > 0) {
      let data = port.readUntil("\n");
      if (data) {
        data = data.trim();
        let values = data.split(",");
        if (values.length == 4) {
          microBitX = int(values[0]) + windowWidth / 2;
          microBitY = int(values[1]) + windowHeight / 2;
          microBitAState = values[2].toLowerCase() === "true";
          microBitBState = values[3].toLowerCase() === "true";
          updateButtonStates(microBitAState, microBitBState);
        } else {
          print("No se están recibiendo 4 datos del micro:bit");
        }
      }
    }
  
  
  switch (appState) 
  {
 case STATES.WAIT_MICROBIT_CONNECTION:
      if (microBitConnected === true) {
        // Preparo todo para el estado en el próximo frame
        print("Microbit ready to draw");
        strokeWeight(0.75);
        c = color(1, 1, 1);
        noCursor();
        appState = STATES.RUNNING;
      }

      break;
     

    case STATES.RUNNING:
            print(`Estado RUNNING: A:${microBitAState}, B:${microBitBState}, X:${microBitX}, Y:${microBitY}, Pos dibujo: (${x},${y}), FontSize: ${fontSize}`);
      if (microBitAState === true) {
  let d = dist(x, y, microBitX, microBitY);
  
 
  let targetFontSize = map(d, 0, 50, fontSizeMin, fontSizeMax);
  
  
  fontSize = lerp(fontSize, targetFontSize, 0.1);
  
  textSize(fontSize);
  let newLetter = letters.charAt(counter);
  stepSize = textWidth(newLetter);

  if (d > stepSize) {
    var angle = atan2(microBitY - y, microBitX - x);

    push();
    translate(x, y);
    rotate(angle + random(angleDistortion));
    fill(c);
    text(newLetter, 0, 0);
    pop();

    counter++;
    if (counter >= letters.length) counter = 0;

    x = x + cos(angle) * stepSize;
    y = y + sin(angle) * stepSize;
  }


}

      break;
  }
  
}

function mousePressed() {
  x = mouseX;
  y = mouseY;
}

function keyReleased() {
  if (key == 's' || key == 'S') saveCanvas(gd.timestamp(), 'png');
  if (keyCode == DELETE || keyCode == BACKSPACE) background(255);
}

function keyPressed() {
  // angleDistortion ctrls arrowkeys up/down
  if (keyCode == UP_ARROW) angleDistortion += 0.1;
  if (keyCode == DOWN_ARROW) angleDistortion -= 0.1;
}

```

**Codigo modificado**

```js
var x = 0;
var y = 0;
var stepSize = 5.0;

let fontSize = 10; 
let fontSizeMax = 72;
let fontSizeMin = 3;
var font = 'Georgia';
var letters = 'All the world\'s a stage, and all the men and women merely players. They have their exits and their entrances.';

var angleDistortion = 0.0;
var counter = 0;

let microBitX = 0;
let microBitY = 0;
let microBitAState = false;
let microBitBState = false;
let prevmicroBitAState = false;
let prevmicroBitBState = false;

let c;



let port;
let connectBtn;
let microBitConnected = false;
let serialBuffer = []; // buffer para los bytes recibidos


const STATES = {
  WAIT_MICROBIT_CONNECTION: "WAIT_MICROBIT_CONNECTION",
  RUNNING: "RUNNING",
};
let appState = STATES.WAIT_MICROBIT_CONNECTION;

function setup() {
  createCanvas(displayWidth, displayHeight);
  background(255);
  cursor(CROSS);

  x = mouseX;
  y = mouseY;

  textFont(font);
  textAlign(LEFT);
  fill(0);
  c = color(1, 1, 1, 1);

  port = createSerial();
  connectBtn = createButton("Connect to micro:bit");
  connectBtn.position(0, 0);
  connectBtn.mousePressed(connectBtnClick);
}

function connectBtnClick() {
  if (!port.opened()) {
    port.open("MicroPython", 115200);
  } else {
    port.close();
  }
}

function updateButtonStates(newAState, newBState) {
  if (newAState === true && prevmicroBitAState === false) {
    x = microBitX;
    y = microBitY;
    print("A pressed: start drawing at", x, y);
  }

  if (newBState === true && prevmicroBitBState === false) {
    saveCanvas('microbit_screenshot_' + Date.now(), 'png');
    print("B pressed: screenshot taken!");
  }

  prevmicroBitAState = newAState;
  prevmicroBitBState = newBState;
}


function readSerialData() {
  let available = port.availableBytes();
  if (available > 0) {
    let newData = port.readBytes(available);
    serialBuffer = serialBuffer.concat(newData);
  }

  while (serialBuffer.length >= 8) {
    if (serialBuffer[0] !== 0xaa) {
      serialBuffer.shift(); // descarta hasta el header
      continue;
    }

    if (serialBuffer.length < 8) break;

    let packet = serialBuffer.slice(0, 8);
    serialBuffer.splice(0, 8);

    let dataBytes = packet.slice(1, 7);
    let receivedChecksum = packet[7];
    let computedChecksum = dataBytes.reduce((acc, val) => acc + val, 0) % 256;

    if (computedChecksum !== receivedChecksum) {
      console.log("Checksum error in packet");
      continue;
    }

    let buffer = new Uint8Array(dataBytes).buffer;
    let view = new DataView(buffer);

    microBitX = view.getInt16(0) + windowWidth / 2;
    microBitY = view.getInt16(2) + windowHeight / 2;
    microBitAState = view.getUint8(4) === 1;
    microBitBState = view.getUint8(5) === 1;

    updateButtonStates(microBitAState, microBitBState);
  }
}

function draw() {
  if (!port.opened()) {
    connectBtn.html("Connect to micro:bit");
    microBitConnected = false;
  } else {
    microBitConnected = true;
    connectBtn.html("Disconnect");
  }

  switch (appState) {
    case STATES.WAIT_MICROBIT_CONNECTION:
      if (microBitConnected === true) {
        print("Microbit ready to draw");
        strokeWeight(0.75);
        c = color(1, 1, 1);
        noCursor();
        port.clear();
        prevmicroBitAState = false;
        prevmicroBitBState = false;
        appState = STATES.RUNNING;
      }
      break;
    case STATES.RUNNING:
      if (microBitConnected === false) {
        print("Waiting microbit connection");
        cursor();
        appState = STATES.WAIT_MICROBIT_CONNECTION;
        break;
      }

     
      readSerialData();

      // Dibujar letras si A está presionado
      if (microBitAState === true) {
        let d = dist(x, y, microBitX, microBitY);
        let targetFontSize = map(d, 0, 50, fontSizeMin, fontSizeMax);
        fontSize = lerp(fontSize, targetFontSize, 0.1);

        textSize(fontSize);
        let newLetter = letters.charAt(counter);
        stepSize = textWidth(newLetter);

        if (d > stepSize) {
          var angle = atan2(microBitY - y, microBitX - x);
          push();
          translate(x, y);
          rotate(angle + random(angleDistortion));
          fill(c);
          text(newLetter, 0, 0);
          pop();

          counter++;
          if (counter >= letters.length) counter = 0;

          x = x + cos(angle) * stepSize;
          y = y + sin(angle) * stepSize;
        }
      }
      break;
  }
}

function mousePressed() {
  x = mouseX;
  y = mouseY;
}

function keyReleased() {
  if (key == 's' || key == 'S') saveCanvas('screenshot_' + Date.now(), 'png');
  if (keyCode == DELETE || keyCode == BACKSPACE) background(255);
}

function keyPressed() {
  if (keyCode == UP_ARROW) angleDistortion += 0.1;
  if (keyCode == DOWN_ARROW) angleDistortion -= 0.1;
}
```

Empecé el ejercicio siguiendo exactamente el instructivo de la Unidad 5 y siguiendo paso a paso lo que el profe iba mostrando en esta unidad.


En esta parte de la unidad hice varias pruebas para comprobar que realmente entendí lo del framing y los paquetes binarios. Primero comparé cómo se comportaba la aplicación cuando usaba el envío en texto con comas, frente al nuevo envío en binario con header y checksum. Me di cuenta de que con el método en texto a veces se colaban lecturas incompletas, lo que hacía que el dibujo saltara o aparecieran mensajes de error. En cambio, al implementar los paquetes binarios con 0xAA y el checksum, la transmisión se sincronizó mejor.
<img width="543" height="89" alt="image" src="https://github.com/user-attachments/assets/501f2ce5-0fe8-4576-93df-c0975f2d8674" />


Para probarlo,  corri la aplicación y miré la consola de p5.js. Cuando los paquetes llegaban bien, veía valores  de microBitX, microBitY y los estados de A y B. Pero cuando movía el micro:bit muy rápido o lo desconectaba y reconectaba, a veces aparecía el mensaje “Checksum error in packet”. Eso me sirvió como evidencia de que el programa realmente estaba descartando basura y no se usaban datos dañados en el dibujo.
<img width="458" height="105" alt="image" src="https://github.com/user-attachments/assets/4d5a5dfb-820d-4fcf-91bd-542fd7c4c293" />


Algo que notamos en el codigo es que los valores que se leen son decimales cuando se supone que lo estamos convirtiendo a enteros. Lo que sucede es que en la parte en la que estamos recibiendo los datos de x y y se realiza una división por 2. Esto convierte los numeros a float.<img width="429" height="54" alt="image" src="https://github.com/user-attachments/assets/71148875-a3f9-4eed-a5a4-627c4ce88de7" />



## AUTOEVALUACIÓN ##

| CRITERIOS | NOTA | JUSTIFICACIÓN|
|----------|----------|----------|
| 1. Profundidad de la Indagación  | 5   | A la par que iba leyendo la guia y resolviendo las preguntas iba profundizando en los temas y buscando por aparte cosas para aclarar mas los temas.  |
| 2. Calidad de la Experimentación | 5   | Iba probando paso a paso los codigos para ir entendiendo lentamente lo que estaba ocurriendo mientras aplicaba lo nuevo del sistema binario. |
| 3. Análisis y Reflexión | 4.4   | La bitácora conecta claramente la evidencia (capturas de la terminal, logs de la consola, depurador) con la explicación teórica.|
| 4. Apropiación y Articulación de Conceptos | 4.4  | La bitácora demuestra una comprensión clara y correcta de cada componente del protocolo.    |
| TOTAL| 4.7| :)   |
