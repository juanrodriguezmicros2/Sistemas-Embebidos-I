import network, time
from machine import Pin
from umqtt.simple import MQTTClient

# ====== CONFIGURA AQUÍ ======
WIFI_SSID = "Hosman"
WIFI_PASS = "20212005117"

MQTT_HOST = "d0c0e7fb911342d49fd0d1cd7643a840.s1.eu.hivemq.cloud"  # host de tu cluster
MQTT_PORT = 8883
MQTT_USER = "raspiberry"
MQTT_PASS = "raspiberry1A"

TOPIC_CMD    = b"demo/led/cmd"     # donde publicarás ON/OFF
TOPIC_STATUS = b"demo/led/status"  # la Pico responde su estado

# ====== LED (integrado) ======
led = Pin("LED", Pin.OUT)

def wifi_connect():
    wlan = network.WLAN(network.STA_IF)
    wlan.active(True)
    if not wlan.isconnected():
        wlan.connect(WIFI_SSID, WIFI_PASS)
        for _ in range(30):
            if wlan.isconnected():
                break
            time.sleep(0.5)
    if not wlan.isconnected():
        raise RuntimeError("No se pudo conectar al WiFi")
    print("WiFi OK:", wlan.ifconfig())
    return wlan

def on_msg(topic, msg):
    m = msg.strip().upper()
    print("MQTT RX:", topic, m)
    if m in (b"ON", b"1", b"TRUE"):
        led.on()
        try:
            client.publish(TOPIC_STATUS, b"ON")
        except: 
            pass
    elif m in (b"OFF", b"0", b"FALSE"):
        led.off()
        try:
            client.publish(TOPIC_STATUS, b"OFF")
        except:
            pass

# ====== Arranque ======
wifi_connect()

# NOTA: HiveMQ Cloud requiere TLS + SNI
client = MQTTClient(
    client_id="pico-led",
    server=MQTT_HOST,
    port=MQTT_PORT,
    user=MQTT_USER,
    password=MQTT_PASS,
    ssl=True,
    ssl_params={"server_hostname": MQTT_HOST}  # importante para SNI
)

client.set_callback(on_msg)
client.connect()
print("MQTT conectado")

client.subscribe(TOPIC_CMD)
# Anuncia estado inicial
try:
    client.publish(TOPIC_STATUS, b"READY")
except:
    pass

print("Esperando mensajes en", TOPIC_CMD.decode())

while True:
    # Espera bloqueante a un mensaje; si prefieres loop no bloqueante, usa client.check_msg()
    client.wait_msg()

