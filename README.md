# SCADA — Estación Meteorológica 🌡️

Interfaz SCADA desarrollada en Python con **Flet** y **MQTT** para monitorear en tiempo real los datos de temperatura y humedad publicados por un sensor **MXChip AZ3166 (HTS221)**.

---

## Descripción

La aplicación se conecta a un broker MQTT y muestra los valores de temperatura y humedad actualizados en tiempo real. También permite controlar el LED RGB del dispositivo de forma remota desde la interfaz.

---

## Tecnologías utilizadas

- **Python 3**
- **Flet** — framework de UI
- **Paho MQTT** — cliente MQTT para Python

---

## Requisitos

- Python 3.10 o superior
- Broker MQTT activo y accesible en la red
- MXChip AZ3166 publicando datos en los topics correspondientes

Instalación de dependencias:

```bash
pip install flet paho-mqtt
```

---

## Configuración

En la parte superior del archivo `mqtt.py` se encuentran los parámetros de conexión:

```python
BROKER = "10.0.14.196"
PUERTO = 1883
```

Modificar `BROKER` con la IP del broker MQTT de la red local.

---

## Topics MQTT

| Topic | Descripción |
|---|---|
| `estacion2/temperatura` | Valor de temperatura en °C |
| `estacion2/humedad` | Valor de humedad en % |
| `estacion2/led` | Control del LED RGB del dispositivo |

---

## Funcionalidades

- Visualización en tiempo real de temperatura y humedad
- Historial de los últimos 4 mensajes recibidos
- Control del LED RGB del MXChip mediante botones: 🔴 Rojo, 🟢 Verde, 🔵 Azul, ⬛ Apagar
- Indicador de estado de conexión al broker

---

## Ejecución

```bash
python mqtt.py
```

---

## Autor

Proyecto desarrollado para la materia de IoT / SCADA.
