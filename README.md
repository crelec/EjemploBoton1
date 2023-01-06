# EjemploBoton1 Leer un Boton simple sin eliminación de rebotes.


## Introducción

Este Programa muestra el problema de los rebotes en entradas mecánicas tipo botón. 
El ejemplo usa el botón propio de la tarjeta Núcleo 401RE (PC_13) el cual es normalmente abierto y tiene un rebote bajo ya que posee un circuito hardware RC diseñado para tal fin. 
Si usamos otro Pin del micro en este caso uso el pin PB_3 se puede observa con facilidad el problema en mención.

![Captura de pantalla de 2022-11-07 05-36-53](https://user-images.githubusercontent.com/111470363/200290289-428feb4c-c8a3-45c1-a075-4c801955fed3.png)

## Montaje
La tarjeta recibe señales de voltaje a través del pin configurado como entrada para ser interpretado como una señal lógica de voltaje, donde se leerá como nivel alto cuando supere un umbral de voltaje y será un nivel bajo cuando esté por debajo de este umbral. Para esto se debe colocar una resistencia de protección con el fin de disminuir la corriente que recibe el pin de entrada. 

![EjemploBoton1_bb](https://user-images.githubusercontent.com/59096507/211000822-6625bb88-d202-4f35-b7b4-c8472e1ea26c.svg)

## Pull up y Pull Down

Son circuitos predispuestos de una manera determinada en la tarjeta que simplifica el montaje del botón. Estos se configuran en el código del proyecto para luego implementarse de una forma según la configuración seleccionada.


### Resistencia pull down

En esta configuración nos aseguramos que se obtiene una señal LOW en estado de reposo, y al momento de pulsar el botón se obtiene una señal HIGH.
Para configurar este modo se escribe dentro de la función main la siguiente linea de codigo ``myBoton.mode(PullDown);``

La implementación en protoboard es la siguiente:

![PullDown_bb](https://user-images.githubusercontent.com/59096507/211000924-5d83032e-aded-4e65-85f2-ec7403a1aa1b.svg)

### Resistencia pull up

En esta configuración nos aseguramos que se obtiene una señal HIGH en estado de reposo, y al momento de pulsar el botón se obtiene una señal LOW.
Para configurar este modo se escribe dentro de la función main la siguiente linea de codigo ``myBoton.mode(PullUp);``

La implementación en protoboard es la siguiente:

![PullUp_bb](https://user-images.githubusercontent.com/59096507/211001047-2ac93e4b-d794-4a53-9be3-e2af188acdf1.svg)

