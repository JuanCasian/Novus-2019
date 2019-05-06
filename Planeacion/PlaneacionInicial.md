# Planeación Novus 2019

Mapeo de señales musculares para control de drones a través de Radio Control.

## Resumen
En este proyecto se llevará a cabo el mapeo de las señales músculares del brazo con el fin de poder controlar distintos dispositivos, en este caso un drone. El proyecto se divide en distintas fases:

1. Ensamblaje de los drones
2. Control manual de drones por transmisor externo
3. Recepción de señales EMG para preparar modelo de Machine Learning
4. Pruebas de distintas arquitecturas para procesamiento de señales musculares.
	1. Clasificador de señales musculares
	2. Regresión de potencia
5. Conexión entre transmisor de RC con modelo de ML

## Tiempo de desarrolllo

El proyecto está planeado para desarrollarse en 9 meses, de Agosto 2019 a Mayo 2020. La fecha de inicio oficial es cuando se da el financiamiento para la compra de piezas, pero podemos comenzar con el software antes.

## Iteraciones

A lo largo del proceso se llevarán a cabo iteraciones por lo que los mismos pasos se podrán repetir en varias ocasiones buscando mejorar la calidad final del proyecto.

### Primer Iteración

**(Semana 1 a Semana 12)**

La primer iteración es Quick and Dirty, simplemente nos interesa tener algo funcional. El objetivo de esta iteración es tener un drone siendo controlado por señales músculares. No queremos algo perfecto, simplemente que se pueda elevar y que tal vez se mueva adelante y atrás. Puede ser que no se utilice Machine Learning en esta iteración porque lo que queremos es quitar de una vez toda la dificultad técnica del control del drone: cómo vincular un transmisor digital con receptor del drone, generar software control de motores del drone, poder recibir señales musculares y procesarlas en tiempo real.

### Segunda Iteración

**(Semana 13 a Semana 28)**

En la segunda iteración es cuando vamos a integrar machine learning a nuestro prototipo, para que se puedan mapear otros movimientos al drone, no solo arriba y abajo. Esta iteración es más larga porque mucho tiempo se va a ir en juntar las muestras de señales músculares y encontrar la arquitectura de modelo lo suficientemente compleja como para reconocer los comandos pero que se pueda correr de manera local en una equipo que no tiene tanta potencia. En este iteración el mayor reto va a ser el análisis de los datos de manera continua.

### Tercer Iteración

**(Semana 29 a Semana 36)**

En la tercer iteración se va a buscar mejorar el prototipo en todos los aspectos, buscar que la clasificación de comandos sea lo más eficiente posible y que las respuestas en el drone sean casi inmediatas. Cómo un bonus en caso de que sobre tiempo se buscará poder controlar más de un drone a la vez.

### Cierre de proyecto

Una vez finalizada la última iteración del proyecto, se creará la documentación del proyecto para poder publicarlo. 

## Materiales

Para poder llevar el proyecto hay 3 partes que se tienen que tomar en cuenta:

1. El drone
2. El dispositivo de transmisión
3. La creación del modelo de Machine Learning

Cada una de estas partes tienen distintos materiales los cuales son necesarios. Anexo los materiales para la creación de un solo prototipo y para sacar el costo total del proyecto solo es multiplicarlo por el número de prototipos que vamos a crear (para los alumnos). Los precios en el documento son promedios basados en distintas opciones, incluyo capturas de pantalla de sitios de venta en [carpeta de recursos](/res/).

### Drone

- Frame
	- Precio: $20.00 USD + tax
- Electronic Speed Controller (ESC)
	- Precio: $70.00 USD + tax
	- El precio es de paquete de 4, uno por cada motor en quadcopter
- Motores Brushless
	- Precio: $12.50 USD + tax
	- El precio es por pieza entonces es $48.00 USD en total
- Hélices
	- Precio: $13.25 USD + tax
	- Precio por 10 hélices
- Flight controller
	- Precio: $40.00 USD + tax
- Power distribution board
	- Precio: $19.00 USD + tax
- Battery
	- Precio: $34.00 USD + tax
	- Es bueno tener varias baterías para porque no duran mucho a la hora de volarlos. 
- Control
	- Precio: $65.00 USD - $120.00 USD + tax
	- Aunque vayamos a utilizar un transmisor externo, es bueno tener unos controles manuales para poder correr pruebas

### Transmisor

- Arduino o Raspberry pi
	- Precio: $22.00 USD + tax - $35.00 USD + tax
- Componente transmisor
	- Precio $12 USD + tax

### Creación de modelo de Machine Learning

Para la creación del modelo de machine learning necesitamos recibir las señales músculares, pero aun no estoy seguro de cuál es la mejor manera de hacerlo, por lo que puse todo los que podríamos necesitar según las distintas maneras.

- Google cloud credits
	- Precio: 300.00 USD per month
- Audio Interface (probables)
	- $280.00 USD + tax
- Audio cables (probables)
	- $8.00 USD + tax
	- One cable per channel
- Electrode Cables (probables)
	- $7.00 USD + tax
- Muscle Sensor (probables)
	- $40.00 USD + tax
- Electrodos 
	- $13.00 USD + tax
	- Paquete de 30

## Links

No los he ordenado, lo siento hay links de todo en desorden

- https://shop.openbci.com/products/skintact-f301-pediatric-foam-solid-gel-electrodes-30-pack?utm_medium=cpc&utm_source=googlepla&variant=29467659395&gclid=Cj0KCQjwyoHlBRCNARIsAFjKJ6CmnzCn9ORw_9f7Ad-WWaS1SlT9b87mGDNVMrcE8E-WvufQLtk6GfMaAniuEALw_wcB

- https://www.emrnmedicalsupplies.com/us/medi-trace-200-ecg-electrodes-pack-of-100.html?fee=8&fep=4577&gclid=Cj0KCQjwyoHlBRCNARIsAFjKJ6DO7N68vh6LqrbcBiodOZKfeaqUQH0yo3yxanRyURY9mBkiLE8s5FcaAoMgEALw_wcB

- https://forum.arduino.cc/index.php?topic=515771.0

- https://learn.adafruit.com/getting-started-with-myoware-muscle-sensor

- https://www.adafruit.com/product/2699?gclid=Cj0KCQjwyoHlBRCNARIsAFjKJ6CH8lYRs3XkwWCjHpzN6R2NlUKVBmmA5V4Yd5F6lp87a2wybTZd5twaAgygEALw_wcB

- https://www.amazon.com/AmazonBasics-Male-Female-Microphone-Cable/dp/B01JNLUA5G/ref=sr_1_3?keywords=microphone+cables&qid=1554091508&s=musical-instruments&sr=1-3

- https://shop.openbci.com/products/emg-ecg-snap-electrode-cables?utm_medium=cpc&utm_source=googlepla&variant=32372786958&gclid=Cj0KCQjwyoHlBRCNARIsAFjKJ6D9wU_wD-GMIx-qfUF_yEoWxl0163kWL8iPx7MV18NEZu-n-GGUzBMaAluXEALw_wcB

- https://www.amazon.com/Electrotherapy-Wires-Electrode-Connecting-Machine/dp/B00P66S2MQ/ref=sr_1_4?keywords=electrode+cable&qid=1554091731&s=gateway&sr=8-4

- https://www.instructables.com/id/Muscle-EMG-Sensor-for-a-Microcontroller/

- https://www.banggood.com/1100-Meter-Long-Distance-NRF24L01PALNA-Wireless-Module-With-Antenna-p-1057170.html?p=4N130123074053201807&custlinkid=118333&utm_campaign=23074053&utm_content=3312&cur_warehouse=USA

- https://www.banggood.com/5Pcs-NRF24L01-SI24R1-2_4G-Wireless-Power-Enhanced-Communication-Receiver-Module-p-1059601.html?p=4N130123074053201807&utm_campaign=23074053&utm_content=3312&cur_warehouse=USA

- https://www.amazon.com/MakerFocus-NRF24L01-Transceiver-Antistatic-Compatible/dp/B01IK78PQA/ref=as_li_ss_tl?ie=UTF8&qid=1547396728&sr=8-4&keywords=nrf24l01+pa+lna&linkCode=sl1&tag=howto045-20&linkId=2633b70ca0153dc90317bd6f33b40079&language=en_US

- https://www.amazon.com/Aideepen-Wireless-Transceiver-NRF24L01-Antenna/dp/B01ICU18XC/ref=as_li_ss_tl?ie=UTF8&qid=1533398618&sr=8-8&keywords=NRF24L01&linkCode=sl1&tag=howto045-20&linkId=6a0d99d36f781543f23f967281c11309

- https://www.youtube.com/watch?v=-BDCmwNssiw

- https://howtomechatronics.com/projects/diy-arduino-rc-transmitter/

- http://dronenodes.com/how-to-build-a-drone/

- https://www.youtube.com/watch?v=GFNGUDT_9_c
