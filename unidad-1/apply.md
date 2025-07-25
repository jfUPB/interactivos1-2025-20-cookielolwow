# Unidad 1

## 🛠 Fase: Apply

## Actividad 05 ##

- **Input microbit**: Botón A

- **Output microbit**: Mensaje 
  
- **Proceso:** Si se oprime el boton A se envia el mensaje


- **Input p5.js:** Botón para conectar, informacion del serial

- **Output p5.js**: Cambio visual del botón de Connect to micro:bit" a "Disconnect", el cuadro verde y rojo.

- **Proceso:** Si recibe una "A" se pinta de rojo 

## Actividad 6 ##
### Control de movimiento con micro:bit ###
**Crea un programa en p5.js que muestre un círculo en la pantalla. Utiliza los botones A y B del micro:bit para controlar la posición en x del círculo en el canvas de p5.js.**

- Escribe el enlace a tu programa en el editor de p5.js.
  
   [editor de p5.js](https://editor.p5js.org/cookielolwow/sketches/z1iK2VRAE)
 
- Copia el código de tu programa en la bitácora (recuerda insertarlo usando markdown y el lenguaje javascript).

  ``` js
  let port;
  let connectBtn;
  let connectionInitialized = false;
  let x = 200;

  function setup() {
    createCanvas(400, 400);
    background(220);
    port = createSerial();
    connectBtn = createButton("Connect to micro:bit");
    connectBtn.position(80, 300);
    connectBtn.mousePressed(connectBtnClick);
  }

  function draw() {
    background(220);

    if (port.opened() && !connectionInitialized) {
      port.clear();
      connectionInitialized = true;
    }

    circle(x,200,50);
    
    if (port.availableBytes() > 0) {
      let dataRx = port.read(1);
      if (dataRx == "A") {
      x-=5;
      } else if (dataRx == "B") {
       x+=5;
      }
    }

    if (!port.opened()) {
      connectBtn.html("Connect to micro:bit");
    } else {
      connectBtn.html("Disconnect");
    }
  }

  function connectBtnClick() {
    if (!port.opened()) {
      port.open("MicroPython", 115200);
      connectionInitialized = false;
    } else {
      port.close();
    }
  }
  
  ```
- Copia el código del micro:bit en la bitácora (recuerda insertarlo usando markdown y el lenguaje python).

``` py
from microbit import *

uart.init(baudrate=115200)

while True:

    if button_a.is_pressed():
        uart.write('A')
    elif button_b.is_pressed():
        uart.write('B')

    sleep(100)
 ```



