# Unidad 3

## 🔎 Fase: Set + Seek
<img width="1433" height="732" alt="image" src="https://github.com/user-attachments/assets/10d47279-4239-4a01-ab9c-ab3caf7abb9e" />

# Vectores de prueba

| Estado inicial | Evento disparador | Acciones | Estado final |
|----------------|-------------------|----------|--------------|
| CONFIG         | A                 | count = min(count+1, 60), display.show(count) | CONFIG |
| CONFIG         | B                 | count = max(count-1, 10), display.show(count) | CONFIG |
| CONFIG         | S (shake)         | startTime = utime.ticks_ms(), state = 'ARMED' | ARMED |
| CONFIG         | — (sin evento)    | Ninguna acción | CONFIG |
| ARMED          | 1 segundo transcurrido | count--, display.show(count) | ARMED |
| ARMED          | count == 0        | display.show(Image.SKULL) | EXPLODED |
| ARMED          | A (input clave)   | key[keyindex] = 'A', keyindex++ | ARMED |
| ARMED          | B (input clave)   | key[keyindex] = 'B', keyindex++ | ARMED |
| ARMED          | Secuencia correcta (A,B,A) | Reinicia count=20, display.show(count), keyindex=0 | CONFIG |
| ARMED          | Secuencia incorrecta | keyindex=0 | ARMED |
| EXPLODED       | T (logo touch)    | Reinicia count=20, display.show(count), state='CONFIG' | CONFIG |
| EXPLODED       | — (sin evento)    | Ninguna acción | EXPLODED |

