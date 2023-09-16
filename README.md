# Prototipo de Medidor de Temperatura - Potencial en Dispositivos de Salud

## Idea
El prototipo de Medidor de Temperatura tiene como objetivo principal la creación de un esbozo funcional de un dispositivo de seguimiento de la salud personal. Este prototipo se enfoca en la medición de la temperatura corporal, pero su diseño es esquemático y simplificado para fines de demostración y desarrollo temprano. Se contempla su potencial en futuros dispositivos de salud más avanzados.

# Explicación del Código - Prototipo de Medidor de Temperatura

## Resumen
Este código en Python es parte de un prototipo de medidor de temperatura diseñado para demostrar la funcionalidad básica de medición de temperatura corporal utilizando un sensor DS18B20 y una Raspberry Pi Pico W. El prototipo muestra los valores de temperatura en la consola en tiempo real.

## Componentes Clave
El código hace uso de las siguientes bibliotecas y componentes clave:

- `machine`: Esta biblioteca proporciona acceso a los pines GPIO y permite la configuración de la Raspberry Pi Pico.

- `onewire` y `ds18x20`: Estas bibliotecas se utilizan para comunicarse con el sensor de temperatura DS18B20 a través del protocolo OneWire. `ds18x20` facilita la lectura de datos del sensor.

# Relaciones entre Elementos - Prototipo de Medidor de Temperatura

## Componentes Clave

El prototipo de medidor de temperatura utiliza varios componentes clave que trabajan juntos para medir y mostrar la temperatura. Estos componentes incluyen:

- **Raspberry Pi Pico W:** Es la plataforma de desarrollo utilizada para controlar y comunicarse con el sensor DS18B20 y procesar los datos de temperatura.

- **Sensor de Temperatura DS18B20:** Este sensor se encarga de medir la temperatura corporal. Se comunica con la Raspberry Pi Pico W a través del protocolo OneWire.

- **Bibliotecas Python:** El código Python utiliza las bibliotecas `machine`, `onewire`, y `ds18x20` para interactuar con el hardware y obtener datos del sensor.

## Relaciones y Flujo de Datos

El flujo de datos y las relaciones entre los componentes son los siguientes:

1. **Configuración Inicial:** La Raspberry Pi Pico W se configura para utilizar un pin GPIO específico (`sensor_pin`) para conectar el sensor DS18B20. También se establece una conexión a través del protocolo OneWire.

2. **Escaneo de Dispositivos:** El código escanea el bus OneWire en busca de dispositivos DS18B20 conectados y almacena sus direcciones en `roms`.

3. **Medición de Temperatura:** El bucle principal del código inicia la medición de temperatura para cada dispositivo DS18B20 detectado en `roms`. Esto implica la conversión de temperatura y la lectura de datos.

4. **Muestra de Datos en Consola:** Los valores de temperatura medidos se muestran en la consola de la Raspberry Pi Pico W en tiempo real.

5. **Repetición Continua:** El bucle principal se ejecuta de manera continua, lo que permite una monitorización constante de la temperatura corporal. El código realiza mediciones periódicas y muestra los resultados en la consola.

## Potencial de Escalabilidad

Aunque este prototipo es esquemático y rudimentario, sienta las bases para futuros desarrollos y aplicaciones en dispositivos de salud más avanzados. Su diseño modular permite la incorporación de sensores adicionales y la expansión de las funcionalidades para aplicaciones médicas especializadas.

