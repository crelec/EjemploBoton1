# EjemploBoton1 Leer un Boton simple sin eliminación de rebotes.


## Introducción

Este Programa muestra el problema de los rebotes en entradas mecánicas tipo botón. 
El ejemplo usa el botón propio de la tarjeta Núcleo 401RE (PB_13) el cual es normalmente abierto y tiene un rebote bajo ya que posee un circuito hardware RC diseñado para tal fin. 
Si usamos otro Pin del micro en este caso uso el pin PB_3 se puede observa con facilidad el problema en mención.

![Captura de pantalla de 2022-11-07 05-36-53](https://user-images.githubusercontent.com/111470363/200290289-428feb4c-c8a3-45c1-a075-4c801955fed3.png)

## Montaje
La tarjeta recibe señales de voltaje a través del pin configurado como entrada para ser interpretado como una señal lógica de voltaje, donde se leerá como nivel alto cuando supere un umbral de voltaje y será un nivel bajo cuando esté por debajo de este umbral. Para esto se debe colocar una resistencia de protección con el fin de disminuir la corriente que recibe el pin de entrada. 

![image](https://user-images.githubusercontent.com/59096507/209982771-40c9073c-a43b-4e59-9252-ad75f84fa816.png)

## Pull up y Pull Down

Son circuitos predispuestos de una manera determinada en la tarjeta que simplifica el montaje del botón. Estos se configuran en el código del proyecto para luego implementarse de una forma según la configuración seleccionada.


### Resistencia pull down

En esta configuración nos aseguramos que se obtiene una señal LOW en estado de reposo, y al momento de pulsar el botón se obtiene una señal HIGH.
Para configurar este modo se escribe dentro de la función main la siguiente linea de codigo ``myBoton.mode(PullDown);``

La implementación en protoboard es la siguiente:

![image](https://user-images.githubusercontent.com/59096507/206871599-f5ded0c2-865a-4b1c-8f4f-ecb3e33be7a1.png)

### Resistencia pull up

En esta configuración nos aseguramos que se obtiene una señal HIGH en estado de reposo, y al momento de pulsar el botón se obtiene una señal LOW.
Para configurar este modo se escribe dentro de la función main la siguiente linea de codigo ``myBoton.mode(PullUp);``

La implementación en protoboard es la siguiente:

![image](https://user-images.githubusercontent.com/59096507/206871614-ff6adae1-b6de-4954-a24c-57bcf4f1d319.png)
