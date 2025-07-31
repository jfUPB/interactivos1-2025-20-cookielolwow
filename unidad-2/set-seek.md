# Unidad 2

## 🔎 Fase: Set + Seek

### Actividad 01

**1. Describe detalladamente cómo funciona este ejemplo.**


Este código hace que dos píxeles en la pantalla del micro:bit parpadeen, cada uno con un ritmo diferente. Uno cambia cada segundo (1000 milisegundos) y el otro cada medio segundo (500 milisegundos).
Para lograr esto, se usa una máquina de estados, que básicamente es una forma de organizar el comportamiento del programa dependiendo de en qué "etapa" esté.

**2. ¿Cuáles son los estados en el programa?**
- "Init": Es el estado inicial, donde se muestra el píxel y se guarda el momento en el que comenzó.

- "WaitTimeout": Es el estado donde el programa espera a que pase cierto tiempo para volver a cambiar el estado del píxel (de apagado a prendido, o al revés).

**3. ¿Cuáles son los eventos/inputs en el programa?**
- El paso del tiempo. No hay botones ni sensores que se usen.

**4. ¿Cuáles son las acciones en el programa?**
- Mostrar el píxel en la pantalla.

- Guardar el tiempo actual.

- Cambiar el valor del píxel entre 0 y 9 (apagado y prendido).

- Volver a mostrar el nuevo estado del píxel.

### Actividad 02
``` py
from microbit import *
import utime

class Semaforo:
    def __init__(self):
        self.state = "Rojo"
        self.startTime = utime.ticks_ms()
        self.interval = 2000 

    def update(self):
        currentTime = utime.ticks_ms()

        # Transiciones de estado
        if self.state == "Rojo":
            display.clear()
            display.set_pixel(2, 0, 9)  
            self.interval = 3000  
            if utime.ticks_diff(currentTime, self.startTime) > self.interval:
                self.state = "Verde"
                self.startTime = currentTime

        elif self.state == "Verde":
            display.clear()
            display.set_pixel(2, 2, 9) 
            self.interval = 3000  # duración del verde
            if utime.ticks_diff(currentTime, self.startTime) > self.interval:
                self.state = "Amarillo"
                self.startTime = currentTime

        elif self.state == "Amarillo":
            display.clear()
            display.set_pixel(2, 4, 9) 
            self.interval = 1000  # duración del amarillo
            if utime.ticks_diff(currentTime, self.startTime) > self.interval:
                self.state = "Rojo"
                self.startTime = currentTime


semaforo = Semaforo()


while True:
    semaforo.update()

```

**Estados**
- "Rojo": se enciende el LED de arriba.

- "Verde": se enciende el LED del centro.

- "Amarillo": se enciende el LED de abajo.

**Inputs**
- El paso del tiempo. Se mide cuánto tiempo ha pasado desde que entramos a un estado, y si ya pasó el tiempo definido, cambiamos al siguiente estado.

**Acciones**
- Limpiar la pantalla (display.clear()).

- Encender el LED de cada color.

- Actualizar el tiempo de inicio cuando se cambia de estado.




