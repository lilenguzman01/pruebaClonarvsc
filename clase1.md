Aquí tienes el contenido de las diapositivas en formato de texto, extraído de las fuentes proporcionadas:

---

**Arquitectura y Conectividad**
**Telecomunicaciones**
**TECNICATURA SUPERIOR EN**
**MÓDULO I: Protocolos de Comunicaciones**

ISPC / Tecnicatura Superior en Telecomunicaciones
Protocolos de Comunicación

**¿Qué son los protocolos IoT y en qué consisten?**

*   Las plataformas de IoT proporcionan múltiples beneficios a las empresas del entorno industrial, desde el impulso de la automatización y la productividad hasta la generación de nuevos modelos de gestión. Sin embargo, sin protocolos de red, estos sistemas no podrían funcionar.
*   En el ámbito de la informática y las telecomunicaciones, los protocolos IoT son un **conjunto de normas y reglas que permiten a dos entidades entenderse e intercambiar información**, facilitando la comunicación Machine2Machine (M2M).
*   En otras palabras, los protocolos IoT son para la comunicación entre máquinas lo que los idiomas, los gestos o el lenguaje corporal son para la comunicación entre humanos. Así que, al igual que dos humanos necesitan hablar el mismo idioma para entenderse, los dispositivos deben utilizar los mismos protocolos IoT para intercambiar información.

ISPC / Tecnicatura Superior en Telecomunicaciones
Protocolos de Comunicación

Para su funcionamiento, los protocolos de datos emergentes utilizados en las redes IoT tienen varias capas:

*   **Aplicación**: la interfaz entre el usuario y el dispositivo.
*   **Red**: potencia la comunicación entre el router y cada uno de los dispositivos conectados a la red.
*   **Transporte**: facilita la comunicación de datos entre los distintos niveles y garantiza su seguridad.
*   **Física**: la red de comunicación física entre dispositivos.
*   **Enlace de datos**: se encarga de transportar los datos en el sistema y de detectar y corregir los problemas.

ISPC / Tecnicatura Superior en Telecomunicaciones
Protocolos de Comunicación
**¿Por qué son necesarios los protocolos IoT?**

*   Permiten la comunicación entre un gran número y variedad de dispositivos simultáneamente. Deben transportar mensajes entre dispositivos con diferentes requisitos (sensores y actuadores, pero también dispositivos de procesamiento y almacenamiento de datos), todo ello de forma eficiente.
*   Evitan el acoplamiento entre dispositivos para que, idealmente, no haya dependencia entre ellos.
*   Facilitan la **escalabilidad**, ya que permiten añadir o eliminar dispositivos del entorno del IoT sin que ello afecte al despliegue general.
*   Garantizan la **seguridad** de las comunicaciones en entornos vulnerables como el IoT industrial, pero la ciberseguridad también debe abordarse a nivel de dispositivo.
*   Proporcionan un **fácil acceso** a los dispositivos, haya o no problemas de latencia o cortafuegos, entre otros obstáculos.

ISPC / Tecnicatura Superior en Telecomunicaciones
Protocolos de Comunicación
**Tipos de protocolos IoT y cuáles son los más comunes**

*   Debido a la variedad de dispositivos IoT existentes, han surgido diferentes protocolos IoT para gestionar la comunicación en diferentes contextos.
*   El tipo de protocolo viene determinado por los dispositivos a conectar, la función que realizan y la distancia que deben recorrer los datos para ser transmitidos. En cualquier caso, los protocolos de comunicación del IoT se dividen en dos tipos:

1) Protocolos de Acceso a la red
2) Protocolos de Transmisión

ISPC / Tecnicatura Superior en Telecomunicaciones
Protocolos de Comunicación

1) **Protocolos de acceso a la red**: es la capa inferior, que permite la conexión entre dos máquinas. Volviendo a la analogía con la comunicación humana, los protocolos de acceso a la red son el vehículo de comunicación elegido (comunicación oral, escrita, gestual...). Aquí es donde entran las redes Wifi, Ethernet, 3G, 5G....

2) **Protocolos de transmisión**: se utilizan para codificar la información que enviamos a través de las redes mencionadas. Siguiendo la comparación con la forma en que nos comunicamos los humanos, en este caso los protocolos de transmisión serían el lenguaje específico elegido para transmitir la información. Dentro de estos protocolos IoT destacan dos familias:

a) Protocolos informáticos, que se utilizan para transmitir información a Internet o a otros dispositivos IoT.
b) Protocolos OT (Industrial) para la comunicación con equipos industriales.

ISPC / Tecnicatura Superior en Telecomunicaciones
Protocolos de Comunicación

No existe una estandarización a la hora de elegir entre los diferentes protocolos del IoT. Sin embargo, hay algunas pautas comunes que se siguen: A la hora de comunicar los dispositivos IoT con Internet, los protocolos más comunes son **MQTT, CoAP y HTTP**. Son muy flexibles, ya que están diseñados para transmitir cualquier tipo de información. Además de los conocidos protocolos HTTP, destacan aquí los siguientes protocolos:

*   **MQTT** (transporte de telemetría MQ). Sigue un modelo de **publicación-suscripción** que permite la comunicación entre un gran número de dispositivos. Para su funcionamiento, un servidor central llamado **broker** se encarga de recibir los mensajes de los dispositivos emisores y distribuirlos entre los receptores. Además, los mensajes se organizan jerárquicamente por etiquetas.
*   **CoAP** (Constrained Application Protocol) está destinado a la comunicación entre dispositivos de **bajo consumo** y utiliza el modelo **REST** de HTTP, junto con otros requisitos como la multidifusión, el soporte de UDP y una baja sobrecarga.

ISPC / Tecnicatura Superior en Telecomunicaciones
Protocolos de Comunicación

En los despliegues de comunicación industrial y de IoT industrial se utilizan protocolos muy **enfocados a las operaciones** y no tanto al envío de información. Es decir, son protocolos orientados a que un dispositivo controlador (un PLC) se comunique con otra máquina que ejecuta órdenes.

En este caso, el protocolo más común es **Modbus**. Sin embargo, existen protocolos IoT muy específicos para sectores industriales concretos, como el **IEC102** y el **IEC104** para contadores eléctricos o el **MBUS** para contadores de agua.

ISPC / Tecnicatura Superior en Telecomunicaciones
Protocolos de Comunicación

En resumen, a la hora de elegir los protocolos de IoT más adecuados para un despliegue concreto, es crucial determinar primero las **necesidades del sistema concreto** que se va a utilizar, y luego ajustar los protocolos elegidos.

¡Muchas gracias!

---
