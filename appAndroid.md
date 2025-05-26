# Sistema de Control de Emergencia para Concentración de Gas

![Dashboard de la Aplicación](enlace_imagen_dashboard.jpg)

## Descripción del Sistema
Sistema IoT que combina un **ESP32**, un **sensor MQ2** y una **aplicación Android** para monitorear y controlar la concentración de gas en entornos de riesgo. Permite activar ventiladores de emergencia de forma manual cuando se detectan niveles peligrosos (medidos en PPM - Partes Por Millón).

---

## Componentes Clave
| Componente              | Función                                                                 |
|-------------------------|-------------------------------------------------------------------------|
| **Sensor MQ2**          | Mide concentración de gases inflamables (metano, propano) y envía datos en PPM al ESP32. |
| **ESP32**               | - Publica datos al broker MQTT.<br>- Recibe comandos ON/OFF para controlar ventiladores. |
| **App Android (IoT MQTT Panel)** | - Muestra gráficos en tiempo real.<br>- Incluye botones de acción manual. |

---

## Funcionamiento Técnico

### Flujo de Datos
1. **Publicación de Datos**  
   - El ESP32 publica lecturas del sensor MQ2 en el tópico:  
     ``` 
     wokwi/gas_concentration  
     ```  
   - Formato del mensaje:  
     ```json
     {
       "ppm": 3313,
       "timestamp": "15:34:51"
     }
     ```

2. **Recepción en la App**  
   - La aplicación se suscribe al tópico `wokwi/gas_concentration` y muestra los datos en un gráfico temporal con:  
     - **Eje X**: Marcas de tiempo (ej: `15:34:34` a `15:34:50`).  
     - **Eje Y**: Valores de PPM (rango típico: 1,500 a 4,000).  

3. **Control Manual de Ventiladores**  
   | Botón      | Acción                                  | Tópico MQTT                | Comando |
   |------------|----------------------------------------|----------------------------|---------|
   | 🔴 **ENCENDER** | Activa ventiladores al 100% de capacidad | `wokwi/fan_control`        | `ON`    |
   | 🟢 **APAGAR**  | Detención inmediata (emergencia)        | `wokwi/fan_control`        | `OFF`   |

---

## Dashboard de la Aplicación

### Capturas de Pantalla

**Figura 1: Gráfico de Concentración en Tiempo Real**  
![Gráfico de PPM](enlace_imagen_grafico.jpg)  
- Visualiza tendencias históricas (últimos 10 valores).  
- Línea roja: Umbral crítico (2,000 PPM).  

**Figura 2: Panel de Control Manual**  
![Botones de Acción](enlace_imagen_botones.jpg)  
- Diseño intuitivo con botones grandes para operación rápida.  
- Confirmación visual al enviar comandos (ej: notificación *"Ventiladores activados"*).  

---

## Configuración MQTT
| Parámetro          | Detalle                               |
|--------------------|---------------------------------------|
| **Broker**         | Mosquitto, HiveMQ Cloud o AWS IoT Core|
| **Protocolo**      | TCP/IP (puerto 1883)                  |
| **Seguridad**      | Autenticación por usuario/contraseña |

---

## Instalación
1. **Programación del ESP32**  
   ```cpp
   #include <PubSubClient.h>
   #include <WiFi.h>
   
   // Configura WiFi
   const char* ssid = "TU_SSID";
   const char* password = "TU_CONTRASEÑA";
   
   // Configura MQTT
   WiFiClient espClient;
   PubSubClient client(espClient);
   client.setServer("mqtt.broker.com", 1883);
