```cpp
/*
 * Método: manejarComandoMQTT
 * Descripción: Función de retorno (callback) que se ejecuta al recibir un mensaje MQTT.
 *              Procesa el mensaje recibido, aplica filtros para garantizar su integridad,
 *              y ejecuta acciones en el ESP32 según el comando recibido (ON/OFF).
 * 
 * @param topic   Tópico MQTT donde se recibió el mensaje.
 * @param payload Contenido del mensaje (bytes crudos).
 * @param length  Longitud del payload en bytes.
 */
void manejarComandoMQTT(char* topic, byte* payload, unsigned int length) {
  // -------------------------------
  // Procesamiento del mensaje
  // -------------------------------
  
  // 1. Convertir el payload a String y filtrar caracteres no imprimibles
  String message = "";
  for (int i = 0; i < length; i++) {
    if (isPrintable(payload[i])) {  // Descarta caracteres especiales/control (ej: NULL, \n)
      message += (char)payload[i];   // Construye el mensaje carácter por carácter
    }
  }
  
  // 2. Limpieza del mensaje: elimina espacios/tabuladores al inicio y final
  message.trim();  

  // -------------------------------
  // Lógica de control del ventilador
  // -------------------------------
  
  if (message == "OFF") {
    // Comando OFF: Desactiva el ventilador
    digitalWrite(motorVentilador, LOW);  // LOW = Apagar (asume configuración activa en HIGH)
    Serial.println("Ventilador APAGADO");
    
  } else if (message == "ON") {
    // Comando ON: Activa el ventilador
    digitalWrite(motorVentilador, HIGH); // HIGH = Encender 
    Serial.println("Ventilador ENCENDIDO");
    
  }
  
  // Nota: 'motorVentilador' debe ser un pin GPIO configurado como salida en setup()
  // y corresponder al pin físico donde está conectado el ventilador/relé.
}
```
