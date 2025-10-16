
# Evidencias de la unidad 7


## Actividad 01

**🧐🧪✍️ Reporta en tu bitácora**


1. ¿Qué URL de Dev Tunnels obtuviste? ¿Por qué crees que necesitamos usar esta URL en lugar de http://localhost:3000 o la IP local de tu computador para que el celular se conecte?


    - La URL que obtuve fue:
  https://fm4m11mt-3000.use2.devtunnels.ms/

    Necesitamos usar esa en lugar de http://localhost:3000 o la IP local porque el celular no puede conectarse al localhost del computador.

2. Describe brevemente qué hace npm install y npm start.
    - npm install descarga e instala todas las dependencias que necesita el proyecto para funcionar, según lo que esté listado en el archivo package.json.

    - npm start ejecuta el proyecto, normalmente iniciando el servidor o la aplicación principal que está configurada en el mismo archivo package.json.

    
3. ¿Qué mensajes observaste en la terminal del servidor al conectar el cliente de escritorio y el cliente móvil? ¿Eran diferentes los mensajes o identificadores?
    - Cuando se conectó el cliente de escritorio y luego el móvil, el servidor mostró un mensaje “New client connected” para cada uno, pero con identificadores distintos, porque cada cliente tiene su propio socket ID.

   <img width="643" height="214" alt="image" src="https://github.com/user-attachments/assets/be7dc86b-d31f-4a9a-9e14-c4e1e0cb4904" />

4. Describe el comportamiento observado: ¿Funcionó la interacción? ¿Hubo algún retraso (latencia)?
   
    - Sí, la interacción funcionó bien. Cuando movía el dedo en el celular, las visuales en el escritorio reaccionaban casi al instante, así que se notaba que la conexión entre ambos estaba activa.
    - Solo se notaba una ligera latencia, pero poquito, qn sabe si fue mi pc pq es una porqueria  :) . 
## Actividad 02
**🧐🧪✍️ Reporta en tu bitácora**


Explica con tus propias palabras: ¿Por qué es necesario Dev Tunnels en este escenario y cómo funciona conceptualmente?
    - Dev Tunnels es necesario porque el servidor está corriendo en localhost:3000, y esa dirección solo sirve dentro de mi propio computador. Si intento abrirla desde el celular, no conecta, porque para el celular “localhost” sería él mismo, no mi PC.

Describe la función de touchMoved() y por qué se usa la variable threshold en el cliente móvil.
    - touchMoved() se activa cada vez que toco la pantalla y muevo el dedo.
Ahí se toman las coordenadas del toque y se mandan al servidor con Socket.IO, que luego las envía al escritorio para que las visuales reaccionen.

    - El threshold sirve para que no se manden demasiados mensajes si el dedo apenas se mueve o tiembla un poco. Solo cuando hay un cambio más grande, se envía la info, así no se satura la conexión.

Compara brevemente Dev Tunnels con simplemente usar la IP local. ¿Cuáles son las ventajas y desventajas de cada uno?
| Método          | Ventajas                                              | Desventajas                                                        |
| --------------- | ----------------------------------------------------- | ------------------------------------------------------------------ |
| **IP local**    | Sirve si el compu y el celular están en la misma red. | No funciona si el celular usa datos o está en otra red.            |
| **Dev Tunnels** | Funciona desde cualquier lugar y usa HTTPS seguro.    | Puede tener un poquito más de retraso o depender más del internet. |


Coloca en tu bitácora capturas de pantalla del sistema completo funcionando. Esto lo puedes hacer abriendo tanto el mobile como el desktop en tu computador y tomando una captura de pantalla de todos los involucrados (celular, computador y terminal).
<img width="871" height="439.5" alt="Captura de pantalla 2025-10-15 190628" src="https://github.com/user-attachments/assets/4335d236-33ed-46b1-8e65-afd2ccee7bb3" />
<img width="585" height="1266" alt="image" src="https://github.com/user-attachments/assets/11957e6d-1655-4dc3-8558-4184241f11ca" />


## Actividad 03

1. ¿Cuál es la función principal de express.static(‘public’) en este servidor? ¿Cómo se compara con el uso de app.get(‘/ruta’, …) del servidor de la Unidad 6?
  - Esa línea le dice al servidor que todo lo que esté dentro de la carpeta public se pueda abrir directamente desde el navegador.
2. Explica detalladamente el flujo de un mensaje táctil: ¿Qué evento lo envía desde el móvil? ¿Qué evento lo recibe el servidor? ¿Qué hace el servidor con él? ¿Qué evento lo envía el servidor al escritorio? ¿Por qué se usa socket.broadcast.emit en lugar de io.emit o socket.emit en este caso?


  -  En el celular, cuando muevo el dedo sobre la pantalla, se activa touchMoved(). Esa función crea un objeto con las coordenadas del toque y lo envía al servidor con:
```js
socket.emit('message', { type: 'touch', x: mouseX, y: mouseY });
```

  -  El servidor escucha ese evento con:
```js
socket.on('message', (message) => { ... })
```

  -  Ahí recibe el mensaje del celuco. Luego el servidor usa
```js
socket.broadcast.emit('message', message);
```

  -  para reenviarlo a todos los demás clientes conectados, excepto al que lo envió (en este caso, el escritorio).

  -  Se usa socket.broadcast.emit y no io.emit porque no quiero que el móvil se reenvíe su propio mensaje, solo que lo reciba el escritorio.

 
Si conectaras dos computadores de escritorio y un móvil a este servidor, y movieras el dedo en el móvil, ¿Quién recibiría el mensaje retransmitido por el servidor? ¿Por qué?
  - Si tengo dos compus con el cliente de escritorio y un celular, cuando muevo el dedo en el celular, los dos escritorios recibirían el mensaje, porque el servidor lo retransmite a todos los clientes conectados, menos al que lo envió.

    
¿Qué información útil te proporcionan los mensajes console.log en el servidor durante la ejecución?

  - Los console.log sirven para ver lo que está pasando en tiempo real.
## Actividad 04

## APPLY

Q RETO TAN HORRIBLEEEKJDFNWKDNFPWEHFWEFJEWFJBW


ME ESTA PASANDO ESTO:


<img width="345" height="333" alt="image" src="https://github.com/user-attachments/assets/1b1be96c-942a-4860-91da-9b8445a9390b" />
