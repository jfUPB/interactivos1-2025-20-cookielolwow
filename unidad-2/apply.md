# Unidad 2


## 🛠 Fase: Apply
### Actividad 04
- Construye un diagrama detallado de la máquina de estados, incluyendo estados, eventos, transiciones y acciones.
  <img width="1146" height="713" alt="image" src="https://github.com/user-attachments/assets/b7f8ec9b-f061-4514-a54f-d7b54d447bfc" />

### Actividad 5
```py
from microbit import *
import utime

STATE_CONFIG = 0
STATE_ARMED = 1
STATE_EXPLODED = 2

state = STATE_CONFIG
time_left = 20  
start_time = 0

while True:
    if state == STATE_CONFIG:
        display.show(str(time_left))
        
        if button_a.was_pressed():
            if time_left < 60:
                time_left += 1
        
        if button_b.was_pressed():
            if time_left > 10:
                time_left -= 1

        if accelerometer.was_gesture("shake"):
            state = STATE_ARMED
            start_time = utime.ticks_ms()
            display.show(str(time_left))
    
    elif state == STATE_ARMED:
        current_time = utime.ticks_ms()
        if utime.ticks_diff(current_time, start_time) >= 1000:
            time_left -= 1
            start_time = utime.ticks_ms()
            if time_left > 0:
                display.show(str(time_left))
            else:
                state = STATE_EXPLODED
                display.show(Image.SKULL)
                music.play(music.BOOM)
    
    elif state == STATE_EXPLODED:
        if pin_logo.was_touched():  
            music.stop()
            time_left = 20
            state = STATE_CONFIG
```
          
1. En STATE_CONF	si se presiona a con tiempo en 20 . se muestra 21 y se vuelve a	STATE_CONF.
2. En STATE_CONF	Presionar b	 con tiempo en 20, se muestra 19	y se vuelve STATE_CONF.
3. En STATE_CONF	Presionar button_b con time=10, se mantiene en 10	y se vuelve a STATE_CONF.
4. En	STATE_CONF	si se sacuede (shake) con time en	25	Inicia cuenta regresiva desde 25 a 0 y pasa a	STATE_ARMED.
5	En STATE_ARMED	Pasa 1 segundo	y se le resta a time, de 25	Muestra 24	y sigue en STATE_ARMED hasta que sea 0.
6	En STATE_ARMED time llega a	 0 , muestra calavera ,suena buzzer y pasa a 	STATE_EXPLODED.
7. En	STATE_EXPLODED si se toca touch	se reinicia el tiempo a 20 y apaga sonido. Y vuelve a	STATE_CONF.

