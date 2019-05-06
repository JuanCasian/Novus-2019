# Planeación Novus 2019

Mapeo de señales musculares para control de drones.

## Resumen

En este proyecto se creará un sistema completo para el control de drones a través de señales músculares, utiilizando inteligencia artificial por medio de modelos de *Aprendizaje Automatizado* (Machine Learning). El proyecto se divide en 2 semestres de trabajo, durante el primero se trabaja en la recopilación de señales y el ensamblaje del drone en sí, buscando hacerlo semi-autónomo. En el segundo semestre se implementan distintos modelos de Machine Learning para mapear las señales músuclares y se integra al sistema de control del drone, para poder controlar a tiempo real un drone semi-autónomo. Se esperan poder mapear 6 comandos de movimiento del drone: arriba, abajo, derecha, izquierda, frente y atrás. Además de un comando pasivo con el cual el drone solo se mantendrá en su posición.

---

## Desarrollo

El proyecto será desarrollado en 3 partes:

- Bioingenieriá
  - Recopilación de Señales músculares
- Ciencias computacionales
  - Creación de modelo de aprendizaje automatizado para reconocimiento de comandos.
- Integración de drone
  - Creación de sistema para control de drone

El plan de trabajo está diseñado para que la primero se lleve a cabo la parte de *bioingeniería* y en el siguiente semestre la de *ciencias computaciones*, pero la parte de *integración de drone* va a correrse paralelos a estos dos para poder integrar el proyecto completo a finales del semestre Enero-Mayo 2020.

---

### Bioingeniería 

Las señales musculares que recopilamos por medio de electrodos tienden a diferir entre persona y persona, es por esto que es de suma importancia tener una base de datos lo suficientemente robusta para poder hacer un mapeo universal y que nuestro dispositivo pueda ser utilizado por cualquiera. 

#### Detalles del Sección

- Tiempo de desarrollo:
  - Semestre Agosto-Diciembre 2019
- Clase en la que se impartirá:
  - Biointrstrumentación - BI3011
- Cómo se impartirá:
  - Se impartirá como una práctica de laboratorio
- Numero de alumnos:
  - 31 Alumnos

#### Hardware Utilizado

- Ganglion Board (4 - canales)
  - Es un dispositivo especialmente diseñado para obtener señales músculares de 4 músculos diferentes. Es la pieza más importante de esta sección.
- Ganglion Dongle
  - Ya que el dispositivo Ganglion se comunica por Bluetooth con otros dispositivos, se utiliza este dongle para poder recibir las señales en computadoras.
- EMG Snap Electrode cables
  - Latiguillos para conectar el Ganglion con los electrodos de gel.
- EMG Gel Electrodes
  - Electrodos adhesivos desechables para poder obtener señales músculares.

#### Que se espera obtener

Al final de esta sección del proyecto se espera como resultado una base de datos de aproximadamente 6500 muestras. Esto se logrará pidiéndole a los alumnos que repitan cada comando  30 veces, ya que vamos a utilizar 7 comandosy esto se repetirá por 31 alumnos tendremos suficientes muestras al final de la práctica. 

--- 

### Ciencias Computacionales

Una vez obtendas suficientes señales musculares por cada comando se creará un modelo de Machine Learning que pueda clasificar estas señales en los distintos comandos, para esto se utilizarán distintos métodos de Machine Learning como Deep Learning, SVMs, etc.

#### Detalles de la Sección

- Tiempo de desarrollo:
  - Aun por confirmar
- Clase en la que se impartirá:
  - Aun por confimar
- Cómo se impartirá:
  - Se impartiría como un proyecto para alumnos de maestría en ciencias computacionales
- Numero de alumnos:
  - 3 ~ 8 alumnos

#### Gastos

En este caso no hay uso de hardware adicional pero sí habrá gastos para trabajar con una plataforma de cloud computing.

- Google Cloud Platform Credits
  - Se utilizará esta plataforma para entrenar los modelos de inteligencia artificial. Además creemos que le da fuerza al proyecto poder decir que utilizaremos tecnologías actuales.
  
#### Qué se espera obtener

Al final de la sección se espera obtener un programa que sea capaz de recibir señales músculares en tiempo real para después clasificarlas y poder obtener a qué comando se refiere. En otras palabras el software recibe como input las señales musculares y tiene como output el comando.

---

### Integración de Drone

Esta sección del proyecto se va a encargar de que una vez que el modelo de inteligencia esté terminado simplemente se integre al drone y este ya pueda entender qué es lo que debe hacer. Para poder lograr esto se tiene que crear un drone semi-autónomo, ya que lo único que obtendrá el drone va a ser comandos sobre cómo cambiar su ubicación actual. Es por esto que todo el control de los motores debe estar automatizado y el drone debe de ser capaz de ubicarse en el espacio para poder navegar. 

#### Detalles de la sección

- Tiempo de desarrollo:
  - Agosto 2019 - Marzo 2020
- No se impartirá en ninguna clase
- El drone tiene que pasar por 4 fases para poder llegar a lo que esperamos
  1. Drone normal controlado por radio frecuencia - (Septiembre 2019 - Octubre 2019)
     - Ademas de se ensambla el drone esto es necesario para poder comprobar que todos los componentes son funcionales, que el diseño del drone es el correcto para poder volar estable.
  2. Drone semi-autónomo controlado por Raspberry Pi (Octubre 2019 - Noviembre 2019)
     - En esta fase el drone debe de poder se controlado por una Raspberry Pi que se conectará a una computadora por medio de wifi. No tendremos mucho rango de vuelo pero podremos corroborar de que el drone puede volar con puros comandos.
     - En esta fase también se crea el software que correrá en el drone para poder ser controlado por puros comandos.
  3. Drone semi-autónomo controlado por radio frecuencia (Noviembre 2019 - Enero 2020)
     - En esta fase se crea la manera de comunicar 2 Raspberry Pi por medio de radio frecuencia. Esto incrementeará el rango de comunicación para poder volar como cualquier otro drone pero siendo controlado por teclas.
     - Esta fase es un poco complicada porque se necesita "hackear" la manera en la que los radio transmisores y receptores funcionan. En nuestro caso vamos a transmitir señales que no van a ser análogas, por lo que utilizaremos los canales de Tx/Rx (transmisión/recepción) para crear una especie de switch, de esta manera en el drone se podrá entender a qué comando se refiere.
  4. Drone controlado por señales músculares (Enero 2020 - Marzo 2020)
     - Este es el paso final del proyecto dónde se integra todo el sistema para poder utilizarlo.
- Además del trabajo con el drone se tienen que generar otros 2 programas para poder integrar la parte de las señales músculares.
	- El primero es un programa que se conecte con el Ganglion y pueda obtener el output continuo del dispositivo para poder utilizarlo en los modelos de machine learning. (Septiembre 2019 - Octubre 2019)
	- El segundo es de la lógica con la que se controlará el drone según el comando que se obtenga del clasificador. Se tienen que probar distintas lógicas para que el vuelo del drone sea lo más común posible. (Enero 2020 - Marzo 2020)

#### Hardware

- Hélices
- Electronic Speed Controllers
- Motores
- Batería
- Control Transmisor
  - Este solo es necesario para la pimer fase del drone
- Raspberry Pi
  - Se utilizan 2, una montada en el drone para recibir los comandos y actualizar las coordenadas y otra en el dispositivo de reconocimiento de señales musculares para hacer la clasificación.
- Transmisor y Receptor de radio frecuencia
- Pixhawk 4
  - Es un flight controller que ya tienen todos los sensores necesarios para poder controlar el drone de una manera semi-autónoma, además de que se le puede cargar un firmware que es utilizado para vuelo autónomo

### Qué se espera obtener

Una vez terminada esta sección se llegaría casi al final del proyecto, ya que tendríamos un prototypo funcional al cual se le pude cargar distintos clasificadores. Lo que seguría sería iterar en el diseño para buscar mejorarlo funcional o estéticamente.

---

**Nota final:** Los precios de todo el hardware se encuentran en el excel

