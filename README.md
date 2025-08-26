# 🚗🤖 Carro recolector y clasificador de basura con Raspberry Pi Pico W

## 📌 Descripción del proyecto
Este proyecto consiste en el diseño, construcción y programación de un vehículo de dos ruedas, controlado mediante una **Raspberry Pi Pico W **, que incorpora un **brazo robótico** y una **cámara**.  
El objetivo principal es que el carro pueda desplazarse de manera controlada en forma remota o automatica, identificar objetos considerados, recogerlos mediante el brazo y clasificarlos, contribuyendo así a soluciones tecnológicas como por ejemplo para el cuidado del medio ambiente.  

El sistema busca ser **escalable**. de manera en la cual se pudiese añadir varios de estos carros uno tras otro, ideal para aplicaciones en robótica educativa, prototipado rápido y proyectos de sostenibilidad.  

---

## 🛠️ Materiales requeridos

| Componente | Cantidad | Descripción | Precio | Link | Imagen |
|------------|----------|-------------|-------------|-------------|-------------|
| Raspberry Pi Pico W | 1 | Microcontrolador principal con conectividad Wi-Fi | $38.080 | https://www.sigmaelectronica.net/producto/rpi-pico-2w/ | ![Raspberry pi pico 2w](https://www.sigmaelectronica.net/wp-content/uploads/2025/03/prorpipcio2w-600x450.jpg)|
| Ultrasonido HCSR04|1|Detección de colisiones|$6.900|https://www.zamux.co/sensor-de-ultrasonido-hcsr04|![HCSR04](https://cdnx.jumpseller.com/zamux-electronica/image/55453874/thumb/1438/1438?1729551806)
| Motor DC | 2 | Sistema de tracción principal | $8.925 c/u| https://www.sigmaelectronica.net/producto/sig1750/| ![Motoreductor](https://www.sigmaelectronica.net/wp-content/uploads/2024/11/2-1.jpg)]|
| Driver L298N o puente H | 1 | Controlador de motores DC | $11.800 |https://www.zamux.co/driver-l298-controlador-para-motor-puente-h-inversor-de-giro| ![Puente H L298N](https://cdnx.jumpseller.com/zamux-electronica/image/16745863/thumb/719/719?1657992116)|
| Cámara ESP 32 CAM | 1 | Captura de imágenes para identificación | $38.900 | https://www.zamux.co/modulo-esp32-cam-con-wifi-y-bluetooth| ![ESP32 CAM](https://cdnx.jumpseller.com/zamux-electronica/image/16843143/thumb/719/719?1651276074)|
| Chasis de acrílico o impreso en 3D | 1 | Estructura principal del carro| $7.000 | NA | ![Acrilico](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTbL3TcwoNNor2YLQ3r48g-ve7KfK9M7p7PVA&s)|
| Batería recargable 9V  con cargador| 1 | Fuente de alimentación para los motores | $45.000 | https://www.zamux.co/pila-9v-recargable-con-cargador | ![Bateria 9v y cargador](https://cdnx.jumpseller.com/zamux-electronica/image/60550119/thumb/1438/1438?1740508492)|
| Bateria 3.7V litio | 1 | Energizar el microcontrolador | $25.900| https://www.zamux.co/bateria-recargable-litio-37v-500ma| ![Bateria 3.7V](https://cdnx.jumpseller.com/zamux-electronica/image/18230914/thumb/1438/1438?1647282323)|
| Cargador bateria de litio | 1 | Carga la bateria de litio | $3.500 | https://www.zamux.co/cargador-bateria-litio-tp4056 | ![Cargador bateria de litio](https://cdnx.jumpseller.com/zamux-electronica/image/18484821/thumb/1438/1438?1650413993) |
| Cables jumper y conectores | Varios | Conexión de componentes | $10.000 | NA| ![CABLES VARIOS](https://cdnx.jumpseller.com/zamux-electronica/image/18048014/thumb/1438/1438?1648666296)|
| Protoboard o PCB | 1 | Organización de conexiones | $5.500 |https://www.zamux.co/baquela-virgen-15cm-x-15cm | ![BAQUELA](https://cdnx.jumpseller.com/zamux-electronica/image/18230700/thumb/1438/1438?1647280451)|
| Tornillería y soportes | Varios | Ensamblaje mecánico | $5.000 | NA |  ![TORNILLOS](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQiAsTJZEKFKl2wzAwiwxeOVswvTRXM_0yd7A&s)|
| Servomotores SG90 / MG996R | 3-4 | Para articulaciones del brazo robótico | $15.000 c/u|https://www.zamux.co/servomotor-sg90-15kg-180-grados| ![Sg90](https://cdnx.jumpseller.com/zamux-electronica/image/18094447/thumb/1438/1438?1658248522)|
|Rueda loca|1|Soporte a la estructura|$7.600|https://www.zamux.co/rueda-loca-metalica-con-esfera|![Rueda loca](https://cdnx.jumpseller.com/zamux-electronica/image/18145885/thumb/1438/1438?1650298372)
| Brazo robótico MEARM | 1 | Brazo para levantar y manipular objetos |NA|NA|![MEARM](https://shop.mearm.com/cdn/shop/files/NewImage14.png?v=1676447812&width=1500)|
|iMAN DE NEODIMIO|2|Añadir otro carro al sistema|$2.000|https://www.zamux.co/iman-neodimio-redondo-1-cm|![iman](https://cdnx.jumpseller.com/zamux-electronica/image/51462622/thumb/1438/1438?1722976229)|
|Giroscopio|1|Control de posiccion espacial|$8.900|https://www.zamux.co/sensor-acelerometro-y-giroscopio-mpu6050|![MPU6050](https://cdnx.jumpseller.com/zamux-electronica/image/17612297/thumb/1438/1438?1651879739)|

---
**🔢 Total estimado (sin incluir el brazo MEARM):**  
👉 **$296.930 COP**

> 📌 *Nota:* El costo final puede variar dependiendo del precio del brazo robótico MEARM, que no se incluyó en la suma por no estar disponible su valor. Además, los precios corresponden a una estimación en línea y pueden cambiar según el proveedor y demas adecauciones para la puesta en marcha del proyecto.
> 
---

## 🎯 Finalidades del proyecto
- **Automatización de recolección y seleccion de basura**: ofrecer una solución tecnológica para la limpieza de espacios pequeños.  
- **Aplicación educativa**: fomentar el aprendizaje de robótica, control de motores, visión por computadora y uso de microcontroladores.  
- **Desarrollo sostenible**: integrar tecnologías accesibles para proyectos orientados al cuidado ambiental.  
- **Escalabilidad**: servir como base para futuros desarrollos en robótica móvil y autónoma.  
- **Conectividad**: aprovechar la Raspberry Pi Pico W  para control remoto vía Wi-Fi o integración con aplicaciones móviles/PC.  

---

## 🚀 Próximos pasos
- Integrar el brazo robótico y su control por servomotores.
- Ajuste de desplazamiento del vehiculo y colisiones.
- Añadir procesamiento de imagen para detección de objetos con la cámara.
- Puesta en marcha de seleccion de objetos y mapeo espacial.

---
