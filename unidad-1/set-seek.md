# Unidad 1

## 🔎 Fase: Set + Seek
 ## Actividad 01

 
 ### ¿Qué es un sistema físico interactivo?

 
Un sistema fisico interactivo es un sistema que combina elementos físicos con la capacidad de interactuar con usuarios o con otros sistemas de manera dinámica. Es una combinación de elementos que podemos manejar. tocar, etc.Ademas la programación del sistema le permite percibir, procesar y actuar sobre el mundo físico.


 
### ¿Cómo podrías aplicar lo que has visto en tu perfil profesional?


En la ingenieria de diseño de entretenimiento digital podemos aplicar los sistemas fisicos en la creacion de experiencias interactivas y inmersivas. Estos sistemas permiten combinar sensores, y software para que los usuarios no solo vean o escuchen, sino también interactúen físicamente con los elementos del entorno. Por ejemplo en los conciertos pueden utilizar sistemas físicos interactivos para transformar el espectáculo en una experiencia llena de diferentes sensaciones. Sensores de movimiento, cámaras y micrófonos pueden captar la energía del público y traducirla en efectos visuales, como luces que cambian de color e intensidad según los aplausos o el ritmo de la música.



## Actividad 02


### ¿Qué es el diseño/arte generativo?
Se refiere a cualquier practica artistica en la que se usa un sistema que introduce unas reglas añadidas y autonomia en la creación.
Esto significa que al activar el sistema, este contribuya a una obra (de diseño y de arte) o de como resultado la obra terminada.


### ¿Cómo podrías aplicar lo que has visto en tu perfil profesional?
En la Ingeniería en Diseño de Entretenimiento Digital, este enfoque puede aplicarse, por ejemplo, en la creación de escenarios generados en videojuegos, efectos visuales , o composiciones musicales. También es útil para diseñar personajes, texturas o animaciones que cambien con base en parámetros previamente programados.

## Actividad 03


identifica los inputs, outputs y el proceso. 

 **◦ inputs**
◦ Puerto microUSB del microbit

◦ Serial del computador

◦ Botón A del micro:bit

◦ Botón B del micro:bit

◦ Movimiento (sacudir el micro:bit)


**◦ Outputs**

◦ **Microbit:** Puerto microUSB

◦**computador**: Serial, Cable, Boton "Send love" y Pantalla
 

**◦ Procesos**

◦ **El micro:bit** detecta entradas (botones y gestos) y envía un carácter por UART (comunicación serial).

◦ **p5.js**recibe esos caracteres y actualiza la interfaz gráfica.

◦ Si desde p5.js se envía 'h', el micro:bit interpreta ese dato y cambia la imagen en su display.


## Actividad 04

### Crea tu propio programa en p5.js. En tu bitácora:
1. Escribe el enlace a tu programa en el editor de p5.js.
[Ver sketch en p5.js](https://editor.p5js.org/cookielolwow/sketches/ZAhreH82H)


2. Copia el código de tu programa en la bitácora 
```
 let t = 0;

function setup() {
  createCanvas(800, 400);
  background(0);
  colorMode(HSB, 360, 100, 100);
  strokeWeight(2);
}

function draw() {
  let hue = (t * 2) % 360;
  stroke(hue, 100, 100);


  for (let x = 0; x < width; x += 5) {
    let y = height / 2 + sin((x + t) * 0.05) * 100;
    point(x, y);
  }

  t += 1;
}
```

3. Muestra una captura de pantalla del resultado de tu programa.
<p align="center">
  <img src="https://github.com/user-attachments/assets/1351b375-8831-4638-af30-f612a7b33136" alt="mySketch (1)">
</p>
