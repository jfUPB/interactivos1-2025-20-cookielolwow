**1. Tabla comparativa: Protocolo ASCII vs Protocolo Binario**

| Aspecto             | Protocolo ASCII                                                                            | Protocolo Binario                                                     | Justificación con ejemplos concretos                                                                |
| ------------------- | ------------------------------------------------------------------------------------------ | --------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| **Eficiencia**      | cada dato se codifica en caracteres ASCII.                    | Alta, los datos se envían en formato binario compacto.                | En la aplicación, el ASCII usa 2 caracteres para un número, mientras que el binario usa 1 byte.     |
| **Velocidad**       | Más lenta debido a mayor cantidad de datos enviados. | Más rápida, menor cantidad de datos y menos procesamiento.            | El binario reduce el tiempo de transmisión en la aplicación, mejorando la respuesta en tiempo real. |
| **Facilidad**       | Más fácil de entender (texto legible).                                           | Más difícil porque los datos no son legibles directamente. | ASCII facilita ver datos en consola, binario requiere herramientas o código para interpretar.       |
| **Uso de recursos** | Más uso de memoria por la mayor cantidad de bytes.                        | Menor uso de ancho de banda y memoria.                                | El buffer para ASCII se llena más rápido, mientras que el binario permite buffers más pequeños.     |


**2. ¿Por qué fue necesario introducir framing en el protocolo binario?**
  - En  binario no hay un delimitador para separar un paquete de otro cosa que causa que los datos se puedan confundir entre ellos. El Framing permite identificar dónde comienza y termina cada paquete de datos, asegurando que la aplicación pueda estarr sincronizada.

**3. ¿Cómo funciona el framing?**

  - El framing usa un byte específico que muestra el inicio de un paquete. Después se leen los bytes correspondientes a un paquete. Si el primer byte no es  0xAA, se sigue buscando hasta encontrar el byte de sincronización, asegurando que el receptor esté alineado con los paquetes.

**4. ¿Qué es un carácter de sincronización?**
  - Es un byte  que señala el inicio de un paquete en un protocolo de comunicación. Sirve para sincronizar el receptor y evitar interpretar datos erróneos.

**5. ¿Qué es el checksum y para qué sirve?**

  - El checksum es un valor calculado a partir de los datos transmitidos que permite verificar que los datos del paquete sean correctos. Si el checksum no coincide con el enviado, se sabra que hay un error en la transmisión.

**6. En la función readSerialData() en p5.js:**

- ¿Qué hace la función concat? ¿Por qué?
  - "Concatena" el nuevo array newData al final del array serialBuffer, acumulando todos los datos recibidos hasta el momento para procesarlos en conjunto.
- ¿Por qué el bucle solo recorre el buffer si tiene 8 o más bytes
  - Porque cada paquete  tiene un tamaño  de 8 bytes. Solo cuando hay al menos 8 bytes en el buffer tiene sentido intentar procesar un paquete completo.
- ¿Qué significa 0xAA?
  - Representa el carácter de sincronización. En decimal es 170.
- ¿Qué hacen shift() y continue?
  -Se usan para descartar datos basura y mantener la sincronización con el inicio de los paquetes.
  - shift() elimina el primer elemento del array (desplaza el buffer hacia adelante).
  - continue salta a la siguiente iteración del bucle, evitando procesar el byte actual porque no corresponde al inicio de un paquete.
- ¿Qué hace la instrucción break si hay menos de 8 bytes?
  -Sale del bucle porque no hay datos suficientes para formar un paquete y espera más datos para procesar.
- Diferencia entre slice y splice. ¿Por qué se usa splice justo después de slice?
  - Se usan juntos para extraer el paquete y luego eliminarlo del buffer.
- ¿Cómo funciona la función reduce?
  - Suma todos los valores de dataBytes,y luego calcula el checksum.
- ¿Por qué se compara el checksum enviado con el calculado? ¿Para qué sirve esto?
  - Para validar la sincronización del paquete. Si no son el mismo, significa que hubo errores en la transmisión.
- ¿Qué hace la instrucción continue en este contexto?
  - Ignora el paquete con error y pasa a procesar el siguiente paquete.
- ¿Qué es un DataView? ¿Para qué se usa?
  - DataView es un objeto de JavaScript que permite leer y escribir datos binarios en buffers.
- ¿Por qué es necesario hacer estas conversiones y no simplemente tomar los datos tal cual?
  - Porque sin esta conversión no se puede trabajar con los valores numéricos correctos ni con los estados.
