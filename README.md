**TUTORIAL PARA SIMULAR RASPBERRY PI 2 MODELO B EN MULTISIM**

**RASPBERRY PI 2 MODELO B**

La Raspberry Pi es una computadora de bajo costo y con un tamaño compacto, del porte de una tarjeta de crédito, puede ser conectada a un monitor de computador o un TV, y usarse con un mouse y teclado estándar. Es un pequeño computador que correo un sistema operativo Linux capaz de permitirle a las personas de todas las edades explorar la computación y aprender a programar lenguajes como Scratch y Python. Es capaz de hacer la mayoría de las tareas típicas de un computador de escritorio, desde navegar en internet, reproducir videos en alta resolución, manipular documentos de ofimática, hasta reproducir juegos.

Raspberry Pi 2 B es un equipo completo en una pequeña placa de circuito, compuesto por un procesador ARMv7, 4 puertos USB, conexión HDMI, Ethernet y mucho más. Gracias a su procesador ARMv7 soporta el rango completo de distribuciones ARM GNU/Linux (Raspbian, XBMC, Snappy Ubuntu Core) y Microsoft Windows 10.  Soporta herramientas de software libre como KOffice, Python, GNU IceCat, etc. Permite un uso flexible en: Juegos, Multimedia, Trabajo, Educación, Proyectos, etc.

**Características**

•	Microprocesador: Broadcom BCM2836 de 900 MHz ARM quad core Cortex-A7 de cuatro núcleos
GPU: VideoCore IV de doble núcleo con soporte de Open GL ES 2.0, hardware acelerado OpenVG hasta 1080p30 H.264

•	RAM: 1GB SDRAM LPDDR2

•	Almacenamiento: tarjeta MicroSD para el Sistema Operativo

•	Vídeo:

HDMI 1.3 y 1.4 tamaño estándar a 1080p con soporte CEC para control desde el mando del televisor
Salida de vídeo compuesto (PAL/NTSC) tipo jack de de 3,5 mm 4 polos

•	Audio:

Audio digital por salida HDMI

Salida de audio estéreo compartida con la salida de vídeo compuesto

•	Red: Ethernet RJ45 10/100 BaseT

•	USB: 4 x USB 2.0

•	Otros:

Conector MPI CSI-2 de 15 vías para cámara de vídeo HD Raspberry Pi

Conector de interfaz serie de display de 15 vías

GPIO: 40 x pin conector macho

•	Sistemas Operativos disponibles para Raspberry Pi más:

Snappy Ubuntu Core versión alfa

Windows 10 aún en desarrollo

•	Alimentación: +5 V a 2 A a través de conector hembra microUSB

•	Tamaño: 86 x 56 x 20 mm

**ESPICIFICACIONES HADWARE RASPBERRY PI 2 MODELO B**

![](https://github.com/EvelinHidalgo/RASPBERRY-PI/blob/master/img/img1.jpg)

**1.microUSB:** Es el sistema de alimentación de la Raspberry, con un cargador dé móvil microUSB común podemos darle corriente. Es recomendable que sea de al menos 2A para un funcionamiento estable.

**2.GPIO:** Estos puertos son una de las cosas que diferencia a la Raspberry de un PC clásico. Mediante estas entradas y salidas de propósito general podremos hacer que nuestra Rasp interactue con el exterior abriendo y cerrando contactos, encendiendo LEDs, conociendo el estado de un interruptor, etc. Seguro que algunos Nergizos ya os habréis dado cuenta de por donde van los tiros. Son un total de 40 puertos de los cuales 26 se pueden usar como entradas/salidas.

**3.USB:** La versión 2 B cuenta con 4 puertos USB para lo que lo necesitemos, en mi caso los he usado para un adaptador WIFI y un teclado/ratón inalámbrico, quedando dos libres para discos duros externos, memorias USB, etc…

**4.microSD:** En la cara trasera de la Raspberry debemos insertar una tarjeta microSD donde se guardará el sistema operativo. Nuestros archivos también podemos guardarlos aquí o en una memoria USB (o disco duro) externos. Es recomendable una microSD de al menos 4GB y clase 10.

**5.HDMI:** A través de un cable HDMI podemos conectar la Raspberry a la TV u otro monitor para poder interactuar con ella, aunque realmente no es 100% necesario ya que, como veremos más adelante, podemos acceder a ella en remoto desde otro PC, smartphone, etc.

**6.Audio 3,5mm:** Por si queremos conectar unos cascos, altavoces u otro tipo de dispositivo de audio.

7.Ethernet: Para dotar a la Raspberry de conexión a internet podemos usar este puerto o un USB WIFI como he hecho yo.

**8.Display DSI:** Existen pequeñas pantallas táctiles con conector de este tipo que podemos acoplar a la Raspberry y hacernos una pseudo-tablet.

**DIAGRAMA PINES RASPBERRY PI**

![](https://github.com/EvelinHidalgo/RASPBERRY-PI/blob/master/img/img2.png)

Pines GPIO para Raspberry Pi 2 Modelo B

•	Amarillo (2): Alimentación a 3.3V.

•	Rojo (2): Alimentación a 5V.

•	Naranja (26): Entradas / salidas de propósito general. Pueden configurarse como entradas o salidas. Ten presente que el nivel alto es de 3.3V y no son tolerantes a tensiones de 5V.

•	Gris (2): Reservados.

•	Negro (8): Conexión a GND o masa.

•	Azul (2): Comunicación mediante el protocolo I2C para comunicarse con periféricos que siguen este protocolo.

•	Verde (2): Destinados a conexión para UART para puerto serie convencional.

•	Morado (5): Comunicación mediante el protocolo SPI para comunicarse con periféricos que siguen este protocolo.

Es importante saber que todos los pines son de tipo "unbuffered", es decir, no disponen de buffers de protección y puedes dañar la placa con un mal uso.

Existen 2 formas de numerar los pines de la Raspberry Pi, en modo GPIO o en modo BCM.

En el modo GPIO, los pines se numeran de forma física por el lugar que ocupan en la placa (representados por el color gris) viene siendo igual para todas las versiones (se comienza a contar desde arriba a la izquierda y finalizamos abajo a la derecha).
En el modo BCM, los pines se numeran por la correspondencia en el chip Broadcom (que es la CPU de la Raspberry Pi).

**NOMENCLATURA GPIO Y BCM**

![](https://github.com/EvelinHidalgo/RASPBERRY-PI/blob/master/img/img3.png)

Los pines de la Raspberry Pi 2 modelo B no dispone de ningún convertidor de analógico a digital. Esto quiere decir que para medir valores de sensores analógicos necesita utilizar un convertidor externo o un Arduino en la mayoría de los casos.

**PROTECCIÓN DE GPIO**

Cuando se utilizan los pines de GPIO para interfaz con hardware de cualquier tipo hay que poner mucho cuidado para no dañar la propia Raspberry Pi. Es muy importante comprobar los niveles de tensión y la corriente solicitada. Los pines de GPIO pueden generar y consumir tensiones compatibles con los circuitos de 3.3V (no son tolerantes a 5V) y pueden sacar hasta 16 mA. Eso es suficiente para iluminar un LED.
Sin embargo hay que tener presente que la corriente que sale de esos pines proviene de la fuente de alimentación de 3.3V y esta fuente está diseñada para una carga pico de unos 3 mA por cada pin de GPIO. Es decir, aunque el SoC de Broadcom permita drenar hasta 16 mA por cada pin la fuente no podrá dar más de unos 78 mA en total (51 mA en los modelos originales). 

**MULTISIM 14.0**

Multisim™ es un software estándar en industria para diseño de circuitos y simulación SPICE para electrónica de potencia, analógica y digital en la educación y la investigación.
El software Multisim™ integra simulación SPICE estándar en la industria con un entorno esquemático interactivo para visualizar y analizar al instante el comportamiento de los circuitos electrónicos. Su interfaz intuitiva ayuda a los profesores a reforzar la teoría de circuitos y a mejorar la retención de la teoría en todo el plan de estudios de ingeniería. Al añadir simulación potente de circuitos y análisis al flujo de diseño, Multisim™ ayuda a los investigadores y diseñadores a reducir las iteraciones de prototipos de tarjeta de circuito impreso (PCB) y a ahorrar los costos del desarrollo.

**MANUAL DE USUARIO**

1.Ingresar al programa Multisim.

![](https://github.com/EvelinHidalgo/RASPBERRY-PI/blob/master/img/img4.jpg)

2.En la parte izquierda de la ventana. Click en NEW.
![](https://github.com/EvelinHidalgo/RASPBERRY-PI/blob/master/img/img5.png)

3.Se abrirá una ventana. Click en CREATE y se abrirá una nueva ventana donde se podrá diseñar la Raspberry Pi.
![](https://github.com/EvelinHidalgo/RASPBERRY-PI/blob/master/img/img6.png)
![](https://github.com/EvelinHidalgo/RASPBERRY-PI/blob/master/img/img7.png)

4.Seleccionar el atajo CRTL + W se abrirá una nueva ventana para seleccionar los componentes de la Rapberry Pi. Se empezará con las entradas USB: 4 x USB 2.0.Click en Connectors-USB-1734035-1. Click en Ok.
![](https://github.com/EvelinHidalgo/RASPBERRY-PI/blob/master/img/img8.png)

5.Seleccionar el atajo CRTL + W se abrirá una nueva ventana para seleccionar los componentes de la Rapberry Pi. Red: Ethernet RJ45 10/100 BaseT.Click en Connectors-Ethernet_Telecom-5558067-1. Click en Ok. 
![](https://github.com/EvelinHidalgo/RASPBERRY-PI/blob/master/img/img9.png)

6. Seleccionar el atajo CRTL + W se abrirá una nueva ventana para seleccionar los componentes de la Rapberry Pi. Salida de audio estéreo compartida con la salida de vídeo compuesto.Click en Connectors-AUDIO_VIDEO -SJ1-3515N. Click en Ok. 
![](https://github.com/EvelinHidalgo/RASPBERRY-PI/blob/master/img/img10.png)

7. Seleccionar el atajo CRTL + W se abrirá una nueva ventana para seleccionar los componentes de la Rapberry Pi. HDMI 1.3 y 1.4 tamaño estándar a 1080p con soporte CEC .Click en Connectors-DSUB-182-015-113R431. Click en Ok.
![](https://github.com/EvelinHidalgo/RASPBERRY-PI/blob/master/img/img11.png)

8.Seleccionar el atajo CRTL + W se abrirá una nueva ventana para seleccionar los componentes de la Rapberry Pi. Red: Ethernet RJ45 10/100 BaseT.Click en Connectors-Ethernet_Telecom-PhonePlug2. Click en Ok. 
![](https://github.com/EvelinHidalgo/RASPBERRY-PI/blob/master/img/img12.png)

9.Seleccionar el atajo CRTL + W se abrirá una nueva ventana para seleccionar los componentes de la Rapberry Pi.Display DSI & CSI.Click en Connectors-HEADERS_TEST -HDR2X17. Click en Ok. 
![](https://github.com/EvelinHidalgo/RASPBERRY-PI/blob/master/img/img13.png)

10. Seleccionar el atajo CRTL + W se abrirá una nueva ventana para seleccionar los componentes de la Rapberry Pi. GPIO: 40 x pin conector macho.Click en Connectors-MFR_CUSTOM-EVAL-SDP-CB1Z. Click en Ok. 
![](https://github.com/EvelinHidalgo/RASPBERRY-PI/blob/master/img/img14.png)

11. Seleccionar el atajo CRTL + W se abrirá una nueva ventana para seleccionar los componentes de la Rapberry Pi. Microprocesador: Broadcom BCM2836 de 900 MHz ARM quad core Cortex-A7.Click en Msc Digital-MICROPROCESSORS-Z84C10-DIP(40). Click en Ok. 
![](https://github.com/EvelinHidalgo/RASPBERRY-PI/blob/master/img/img15.png)

12.Finalmente se obtiene el diseño de la Raspberry Pi modelo B.
![](https://github.com/EvelinHidalgo/RASPBERRY-PI/blob/master/img/img16.png)
![](https://github.com/EvelinHidalgo/RASPBERRY-PI/blob/master/img/img17.jpg)
**BIBLIOGRAFÍA**

[1]Rodríguez,E.(2018).De cero a maker todo lo necesario para empezar con Raspberry Pi.Recuperado de: https://www.xataka.com/makers/cero-maker-todo-necesario-para-empezar-raspberry-pi

[2]Ergo Sum.(2020).Control de GPIO con Python en Raspberry Pi.Recuperado de: https://www.programoergosum.com/cursos-online/raspberry-pi/238-control-de-gpio-con-python-en-raspberry-pi/que-es-gpio
