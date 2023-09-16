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

## Configuración Inicial
Antes de iniciar la medición de temperatura, se realiza la configuración inicial:

```python
import machine
import onewire, ds18x20
import time

# Configura el pin GPIO donde está conectado el sensor
sensor_pin = machine.Pin(4)

# Configura el bus OneWire
ow = onewire.OneWire(sensor_pin)
ds = ds18x20.DS18X20(ow)

# Escanea los dispositivos DS18B20 conectados al bus
roms = ds.scan()
