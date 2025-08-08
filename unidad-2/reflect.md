# Unidad 2


## 🤔 Fase: Reflect
## Actividad 06

**Parte 1: recuperación de conocimiento (Retrieval Practice)**

1. Describe con tus palabras qué es una máquina de estados. ¿Cuáles son sus cuatro componentes fundamentales que has utilizado en esta unidad?


   - Representa un sistema que puede estar en uno de varios estados programados, siendo posible cambiar de estado en respuesta a eventos o entradas.

   
2. Explica por qué la técnica de máquina de estados es tan útil para gestionar la “concurrencia” (atender un temporizador y botones “al mismo tiempo”) en un dispositivo con un solo hilo de ejecución como el micro:bit. ¿Qué problema soluciona en comparación con usar funciones como sleep()?

    - Es una técnica util ya que permite organizar de forma estructurada el sistema y permite visualizarlo. Ademas, en diferencia al sleep, no se va a supender el programa por un tiempo determinado y se puede programar estos cambios de estado sin necesidad de suspenderlo.
  
      
3. Imagina que tienes que añadir una nueva funcionalidad a la bomba temporizada: si se agita (shake) el micro:bit mientras la cuenta regresiva está activa, el tiempo se reduce a la mitad. ¿Cómo modificarías tu diagrama de máquina de estados para incluir este nuevo evento y acción?

    - Crearia un estado nuevo que se derive de ARMED, a este estado se ingresaria despues de sacudir el micro:bit y como evento se restaria la mitad del tiempo.

4. Explica qué es un “vector de prueba” y por qué es una herramienta crucial para verificar que una máquina de estados funciona como se espera.

   -  Un "vector de prueba" es el que testea que las accioones y eventos funcionen de manera adecuada.

**Parte 2: reflexión sobre tu proceso (Metacognición)**

1. ¿Qué parte del diseño de la bomba temporizada te resultó más desafiante: crear el diagrama de estados (Actividad 04) o traducir ese diagrama a código MicroPython (Actividad 05)? ¿Por qué?


    - Para mi el diagrama de estados fue el más desafiante, ya que para poder realizarlo tenia que aclarar mucho mas los conceptos trabajados en clase.

2. Describe un error o “bug” que encontraste al implementar tu programa. ¿Cómo te ayudó pensar en términos de estados, eventos y transiciones a identificar y solucionar el problema?

    - Pensar en terminos de estados, eventos y transiciones me ayudo a ir programando de manera más organizada y un poco mas sencilla de realizar.

3. El problema de la bomba era complejo. ¿Qué estrategia usaste para abordarlo? ¿Comenzaste con una versión simple y añadiste funcionalidades poco a poco?

     - Inicialmente en el diagrama añadi los estados que tenian la bomba y fui añadiendo los eventos, acciones, etc poco a poco.

4. Ahora que entiendes el patrón de máquina de estados, ¿En qué otro tipo de proyecto o sistema de entretenimiento digital crees que podrías aplicarlo?


     - En la gran mayoria de de proyectos de videojuegos. El patrón de maquina de estados puede ayudar a añadir funcionalidades poco a poco a las diferentes mecanicas que estemos realizando dentro de los juegos.

## Actividad 07
1. Encuentra a un compañero de trabajo.
2. Intercambien las URLs de sus bitácoras de aprendizaje.
3. Revisa con atención las entradas de tu compañero para las Actividades 04 (diagrama de la bomba) y 05 (código y pruebas).
4. Analiza de manera crítica el diseño y la implementación de tu compañero y deja un comentario de retroalimentación específico y constructivo.

    - Para mi pudo intentar verificar que implementación sea coherente con los objetivos del ejercicio.

5. Conversa con tu compañero sobre su diseño y código, y discutan sus comentarios.

    - Lo hicimos realmente similares, los dos tuvimos problemas a la hora de entender la logica detras del diagrama y como realizarlo.

## Actividad 08
1. **Continuar:** ¿Qué actividad, explicación o ejemplo de esta unidad te ayudó más a entender el poder de las máquinas de estados? ¿Qué elemento consideras que es indispensable y debería mantener?

    -  El ejemplo de las caritas me ayudo a conocer por primera vez las maquinas de estados, pero para entenderlo a mucha mas profundidad, el ejercicio de la bomba fue el que termino por hacerlo. Considero que es indispensable matener los ejemplos practicos para entender mejor los conceptos.

2. **Dejar de hacer:** ¿Hubo algún paso o actividad que te pareció confuso, innecesariamente complicado o que aportó poco a tu aprendizaje? ¿Qué cambiarías o eliminarías?

    - Realizar los diagramas fue confunso, pero eso fue porque a mi se me dificultó entenderlo. 


3. **Empezar a hacer:** ¿Qué te habría ayudado a entender mejor?

    - Poner más atención.

4. **Ritmo y dificultad:** En una escala del 1 (muy fácil) al 5 (muy difícil), ¿Cómo calificarías la dificultad de pasar del análisis de un programa (Actividad 03) al diseño desde cero de uno complejo (Actividad 04 y 05)? ¿Por qué?

   - 4, porque ya la lógica se cambia y realizarlo desde 0 ya es un reto gigante.

5. **Comentario adicional:** ¿Hay algo más que te gustaría compartir sobre tu proceso de aprendizaje en esta unidad? ¿Algún momento de frustración o de “¡Aha!” que quieras destacar?

   - La verdad, mi momento ¡Aha! fue cuando logre entender el diagrama.
