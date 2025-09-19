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

  - El framing usa un byte específico que muestra el inicio de un paquete. Después se leen los bytes correspondientes a un paquete. Si el primer byte no es  0xAA, se sigue buscando hasta encontrar el byte de sincronización, garantizando que el receptor esté alineado con los paquetes
