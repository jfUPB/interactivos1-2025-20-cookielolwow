# Unidad 3
## 🛠 Fase: Apply

Enlace del codigo: https://editor.p5js.org/cookielolwow/full/z1iK2VRAE

**Codigo p5.js**
```js
let port;
let connectBtn;
let connectionInitialized = false;
let validChars = "ABST";

let Bombevent;
let bomb;

function setup() {
  createCanvas(400, 400);
  textAlign(CENTER, CENTER);
  textSize(24);


  port = createSerial();
  connectBtn = createButton("Connect to micro:bit");
  connectBtn.position(120, 350);
  connectBtn.mousePressed(connectBtnClick);

 
  Bombevent = new BombEvent();
  bomb = new BombTask();
}

function draw() {
  background(220);


  if (port.opened() && !connectionInitialized) {
    port.clear();
    port.on("data", serialRead);
    connectionInitialized = true;
  }


  bomb.update();


  bomb.draw();


  if (!port.opened()) {
    connectBtn.html("Connect to micro:bit");
  } else {
    connectBtn.html("Disconnect");
  }
}



class BombEvent {
  constructor() {
    this.value = "";
  }
  write(v) {
    this.value = v;
  }
  read() {
    return this.value;
  }
  clear() {
    this.value = "";
  }
}



class BombTask {
  constructor() {
    this.PASSWORD = ["A", "B", "A"];
    this.key = [];
    this.keyindex = 0;

    this.count = 20;
    this.startTime = millis();
    this.state = "CONFIG";
  }

  update() {
    let e = Bombevent.read();

    if (this.state === "CONFIG") {
      if (e === "A") {
        this.count = min(this.count + 1, 60);
        Bombevent.clear();
      }
      if (e === "B") {
        this.count = max(this.count - 1, 10);
        Bombevent.clear();
      }
      if (e === "S") {
        this.startTime = millis();
        this.state = "ARMED";
        Bombevent.clear();
      }
    }

    else if (this.state === "ARMED") {
      if (millis() - this.startTime > 1000) {
        this.startTime = millis();
        this.count -= 1;
        if (this.count <= 0) {
          this.state = "EXPLODED";
        }
      }

      if (e === "A" || e === "B") {
        this.key[this.keyindex] = e;
        this.keyindex++;
        Bombevent.clear();
      }

      if (this.keyindex === this.PASSWORD.length) {
        let passOk = true;
        for (let i = 0; i < this.PASSWORD.length; i++) {
          if (this.key[i] !== this.PASSWORD[i]) {
            passOk = false;
          }
        }
        if (passOk) {
          this.count = 20;
          this.keyindex = 0;
          this.state = "CONFIG";
        } else {
          this.keyindex = 0;
        }
      }
    }

    else if (this.state === "EXPLODED") {
      if (e === "T") {
        this.count = 20;
        this.startTime = millis();
        this.state = "CONFIG";
        Bombevent.clear();
      }
    }
  }

  draw() {
    fill(0);
    if (this.state === "CONFIG") {
      text("CONFIG", width/2, height/2 - 50);
      text("Tiempo: " + this.count, width/2, height/2);
    } else if (this.state === "ARMED") {
      text("ARMED", width/2, height/2 - 50);
      text("Tiempo: " + this.count, width/2, height/2);
    } else if (this.state === "EXPLODED") {
      fill("red");
      text(" EXPLODED ", width/2, height/2);
    }
  }
}


function keyPressed() {
  let keyValue = key.toUpperCase();
  if (validChars.includes(keyValue)) {
    Bombevent.write(keyValue);
    port.write(keyValue); 
  }
}

function serialRead() {
  let val = port.read();
  if (val && validChars.includes(val)) {
    Bombevent.write(val);
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

**Codigo Micro:Bit**
```py
from microbit import *
import utime

uart.init(baudrate=115200)

while True:
    if button_a.was_pressed():
        uart.write("A")
    if button_b.was_pressed():
        uart.write("B")
    if accelerometer.was_gesture("shake"):
        uart.write("S")
    if pin_logo.is_touched():
        uart.write("T")
    
    utime.sleep_ms(100)

```
