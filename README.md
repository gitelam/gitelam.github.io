# Prototipo de Medidor de Temperatura - Potencial en Dispositivos de Salud

## Idea
El prototipo de Medidor de Temperatura tiene como objetivo principal la creación de un esbozo funcional de un dispositivo de seguimiento de la salud personal. Este prototipo se enfoca en la medición de la temperatura corporal, pero su diseño es esquemático y simplificado para fines de demostración y desarrollo temprano. Se contempla su potencial en futuros dispositivos de salud más avanzados.

## Funcionalidad
El prototipo ofrece una funcionalidad básica para la medición de la temperatura corporal y sirve como punto de partida para proyectos más elaborados:

- **Medición de Temperatura:** El prototipo es capaz de realizar mediciones rudimentarias de la temperatura corporal.

- **Interfaz de Consola:** Los valores de temperatura se muestran en la consola de manera simplificada para fines de prueba y desarrollo.

- **Potencial de Escalabilidad:** Aunque actualmente es un esquema básico, el diseño modular del prototipo permite explorar su escalabilidad en futuros desarrollos.

- **Exploración en Dispositivos de Salud:** El prototipo demuestra la viabilidad de la medición de temperatura en dispositivos de salud. Aunque rudimentario, sienta las bases para la incorporación de sensores biométricos en dispositivos médicos más avanzados.

En resumen, este Prototipo de Medidor de Temperatura sirve como una representación temprana y esquemática de un dispositivo de seguimiento de la salud. Su simplicidad es intencional y su verdadero potencial radica en su capacidad de servir como punto de partida para futuros desarrollos en el campo de la salud, donde se podrán explorar funcionalidades más avanzadas y aplicaciones médicas especializadas.

## Código en micropython

Este es el código Python del prototipo. Aunque es simple, demuestra la capacidad de medir la temperatura corporal y mostrar los resultados en la consola.

- **Medición de Temperatura:** El código configura el sensor DS18B20 y realiza mediciones rudimentarias de la temperatura corporal.

- **Interfaz de Consola:** Los valores de temperatura se muestran en la consola de manera simplificada para fines de prueba y desarrollo.

- **Potencial de Escalabilidad:** Aunque actualmente es un esquema básico, el diseño modular del prototipo permite explorar su escalabilidad en futuros desarrollos.

- **Exploración en Dispositivos de Salud:** El prototipo demuestra la viabilidad de la medición de temperatura en dispositivos de salud. Aunque rudimentario, sienta las bases para la incorporación de sensores biométricos en dispositivos médicos más avanzados.

En resumen, este Prototipo de Medidor de Temperatura sirve como una representación temprana y esquemática de un dispositivo de seguimiento de la salud, con el código proporcionado como ejemplo de su funcionalidad básica.

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

while True:
    for rom in roms:
        ds.convert_temp()
        time.sleep_ms(750)
        temp = ds.read_temp(rom)
        print("Temperatura:", temp, "°C")
    time.sleep(5)
