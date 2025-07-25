# Unidad 1

## 🤔 Fase: Reflect

En tu bitácora. Sin mirar tus apuntes, los tutoriales o los sketches previos, responde a las siguientes preguntas con tus propias palabras. El objetivo es el proceso de recordar, no la perfección.
## Actividad 07
### Parte 1: recuperación de conocimiento (Retrieval Practice)

1.Basándote en los ejemplos que vimos de sistemas físicos interactivos al iniciar el curso, describe las tres características que definen a un sistema físico interactivo.

2.Explica el modelo input-process-output de Patrick Hübner usando como ejemplo el sistema que construiste con micro:bit y p5.js en la Actividad 06.

3.¿Cuál fue el input, cuál fue el proceso y cuál fue el output.**

- Según los ejemplos que fuimos  viendo en clase, las tres caracteristicas principales que estos tenian y siempre se repetian eran; primero era leer las entradas ( entorno, ambiente, etc), despues procesarlas y por ultimo el resultado o salida.

  
- El modelo input-process de Patrick Hübner esta dividido en tres: Input, Process y Output. 


__Input__

 
- En el programa que yo hice, el input era los botones del micro:bit ( el a y el B) y el puerto que manda la informacion al computador. 

__Proceso__


- Primero en el programa del micro:bit se lee si se preciosa la tecla a o b, para asi en el p5.js procesar esta tecla.


__Output__

- La salida es el movimiento del circulo que se muestra en la pantalla del computador.

  
4.¿Cuál es la función de la línea uart.write('A') en el código del micro:bit y qué función en p5.js se encarga de “escuchar” ese mensaje?


- La función uart.write('A') manda la tecla A a leerla en el programa de p5.js, y en este programa el serialevent lo lee.


5.¿Cuál es la diferencia fundamental entre el arte/diseño tradicional y el arte/diseño generativo?

- En el arte tradicional cada cosita que se haga es hecha manualmente y cada trazo depende del artista en si, a cambio en el arte generativo se puede crear unas reglas para que un sistema las siga, no depende todo el tiempo del artista.


6.Imagina que quieres que un círculo en p5.js cambie a un color aleatorio cada vez que sacudes el micro:bit. Describe qué tendrías que programar en el micro:bit y qué tendrías que programar en p5.js para lograrlo.

- En el micro:bit tendria que programar el movimiento. En p5.js programaria primero la funcion que detecte la informacion del movimiento del microbit y que cuando este se sacuda cambie el color del circulo que esta en el canva.
  
## Parte 2: reflexión sobre tu proceso (Metacognición)


1.¿Qué fue más desafiante para ti en esta unidad: la parte conceptual (entender qué es un sistema físico interactivo) o la parte técnica (hacer que el micro:bit y p5.js se comunicaran)? ¿Por qué?

- Para mi lo mas desafiante fue entender los inputs, procesos y outputs de cada sistema interactivo, siento que fue complicado de entender la logica que iba detras de cada objeto en el      sistema para saber si eran inputs, procesos o outputs.


2.Describe el momento “¡Aha!” que tuviste cuando lograste que una acción en el micro:bit (presionar un botón, sacudirlo) tuviera un efecto visible en el canvas de p5.js por primera vez. ¿Qué fue lo que entendiste en ese instante?


- Fue cuando usamos el micro:bit por primera vez en clase, que al hundir los botones se cambiaba el color en el canvas. En ese momento entendi la cantidad de posibilidades que habian para crear sistemas interactivos bien interesantes, tambien entendi un poquito mejor lo que el profesor explicaba de las caracteristicas de los sistemas (inputs, procesos y outputs).

3.Al inicio de la unidad te pregunté: “¿Este curso para qué me sirve?”. Después de experimentar y construir tu primer prototipo, ¿Cómo ha cambiado o se ha vuelto más concreta tu respuesta a esa pregunta?


- Siento que ahora este curso me va a ayudar a expandir las posibilidades en las que me gustaria expresar mi creatividad y sentimientos por medio de arte generativa, la verdad me parecio increible las cosas que se podian crear, como las ondas con movimientos y colores que podia hacer.


4.El tutorial de la Actividad 05 te llevó paso a paso. ¿Cómo te sentiste con ese método de aprendizaje? ¿Te dio seguridad o preferirías haberlo intentado por tu cuenta desde el principio?


- Sin la explicación paso al paso del profesor no hubiera entendido nada, la verdad la parte de la programación estaba confusa, no hubiera sabido interpretar las funciones del codigo y entenderlas.

## Actividad 08
**Encuentra un compañero de trabajo.
Intercambien las URLs de sus bitácoras de aprendizaje.
Concéntrate en la Actividad 06: control de movimiento con micro:bit de tu compañero. Lee su código (Python y JavaScript).**


**Tu compañero resolvió el problema de manera diferente a ti, qué hizo diferente, qué aprendiste de su solución?.**
- Mi compañera Andrea Yepes hizo la solución similar a mi, las dos usamos una variable x en el circulo en el eje x, para su movimiento usamos un if que detectaba si la tecla a o b eran presionadas y dependiendo de esto, se le sumaba o restaba a la variable x un valor y se moveria el circulo. 

## Actividad 09

1.**Continuar:** ¿Qué actividad, video o ejemplo de esta unidad te resultó más inspirador o te ayudó más a entender el potencial de los sistemas físicos interactivos?


 - El video de la chica que programo unas maquinas para que pintaran unos lienzos.
 
2.**Dejar de hacer:** ¿Hubo alguna parte que te pareció demasiado abstracta, muy rápida o confusa? ¿Hay algo que crees que podríamos cambiar para que sea más claro?

- La verdad me parecio que el ritmo de la clase es bueno.

3.**Empezar a hacer:** ¿Qué te genera más curiosidad ahora? ¿Te gustaría explorar más sensores del micro:bit (luz, temperatura), crear visualizaciones más complejas en p5.js o ver más ejemplos de proyectos artísticos?


- La verdad me encantaria crear visualizaciones más complejas en p5.js, quede fascinada con la pagina.
  

4.**Balance inspiración vs. técnica:** ¿Cómo sentiste el equilibrio entre ver los videos inspiradores de la Actividad 01 y la parte técnica de conectar las herramientas en las actividades 03-06?


- Lo senti bien, es importante tener una idea de lo que podemos llegar a hacer y luego empezar con la parte practica.


5.Comentario adicional: ¿Hay algo más que quieras compartir sobre tu experiencia en esta unidad introductoria?


- Me parecio muy buena forma de introducir el curso, me ayudo a aclarar mejor como funcionan los sistemas fisicos interactivos.

