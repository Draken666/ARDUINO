## MORSE 1


![Captura de pantalla de 2021-10-06 12-05-16](https://user-images.githubusercontent.com/90753279/136183115-55c765dd-009f-42ca-9f50-0aa42993b227.png)

Lo que hace el arduino wa compilar y enviar, a la hora de abrir el puerto nos da error, eso es porque no tiene los permisos del ordenador.

Conectamos los cables uno al GND i el otro a los 5v

El circuito en serie es la eletricidad que se le da a un led la trasmite a los demas atraves de conductos de electricidad

Conectamo uno de los cables a la fila donde este la resistencia entonces, el otro cable en la otra fila y en el mismo numero se conecta el boton, con esto podemos encender el led sin que se sobrecaliente.

Hemos conectado dos botones con varios cables la resistencia tiene que estar en el positivo despues un cable mas abajo en el negativo, el led esta conectado en el 17 y 18 el largo en el 17, el led se encendera si le das a los dos botones, si le das solo a uno es como si no llegase el mensaje al led ( se queda a medio camino)



## EL ERROR LO QUE PASO

Lo que paso es que no habian permisos para escribir en el usb, congo una excepcion y se detuvo el programa, y esto sucedio por un tema de permisos de usuarios.

## PRIMEROS CIRCUITOS

Pese a funcionar y dar luz genera dos problemas, el primero se claienta y es incomodo de tocar, el segundo puede fundir el led.

## CIRCUITOS EN SERIE

Si desconectamos una parte todo se apaga, daigual simplemente se desconecta.

CON BOTON

si ponemos el boton en paralelo no funciona, si lo ponemos en serie si funciona, aparte añadimos una resistencia para que no se fund ael led.

##APUNTES ELECTRICIDAD

Voltaje --- Altura    (diferencia de potencial)

La intensidad o el amperaje es la cantidad de agua o rotuladores.

La resistencia el paso del agua o rotuladores, y la intensidad es = al voltaje/resistencia ley de OM

VOLTAJE= intensidad x resistencia

Rsistencia= Vltaje/Intensidad

### POR QUE NECESITAMOS RESISTENCIAS CON LOS LEDS

Tenemos 2 circuitos

1 5V------2 GND

El voltaje de los dos circuitos son 5v

5 VOLTIOS/441=0'0122 Ampereos 11'33 miniampereos

![Captura de pantalla de 2021-10-13 10-58-12](https://user-images.githubusercontent.com/90753279/137101466-bf078db3-99d2-42b9-88e4-a33099f72677.png)

He entrado al arduino y me da un error

![lol](https://user-images.githubusercontent.com/90753279/137111649-c3de9333-392e-4f89-9fec-2daa99c80a1c.png)

Hemos probado el arduino con  la app y no funcioanaba porque no esta configurado, sale un error.

![Captura de pantalla de 2021-10-13 13-39-05](https://user-images.githubusercontent.com/90753279/137125752-c2abf9d5-c47c-4ed2-95e4-b9f28e50a1fe.png)


Hemos escritos nuestros nombres en codigo morse.

La j esta en la segunda raya

La o esta en la cuarta raya

La a hasta el siguiente punto

La n las dos rayas y puntos que quedan

# FALLOS

Bug: Es un error del programa, es decir el programa lo mandas hacer una cosa y hace otra.

GLith: El glitch es un tipo de bug, grafico.

Error: Es una operacion no permitida por el lenguaje de progrmacion que estemos utilizando, esto suele ocurrir en la ejecucion (roomtime), tambien hay errores de compilacion.

EXCEPCION: Son errores controlados desde el propio codigo suelem ser roomtimes.

LAG: e sun retraso en las comunicaciones


# MORSE1

Primero tenemos el arduino id instalado, tenemos un usuario con permisos, se conecta por USB, cargamos el programa, BLINK.ino, entramos al arduino id, le damos a archivo ejemplos 1. Basic, y dentro de alli blink

Si no hay puerto, herraminetas, puerto y lo seleccionas, se soluciona esperando un min aprox sin tocar nada.

Opciones para enlazarlo:

1.Buscarlo por internet
2.Subirlo en otro
3.Enlazar en primeras pruebas.md

Hicimos que los leds, tubiesen delay es decir que havia un retraso de x sgundos que pongamos.
  
Cambabamos el numero de arriba que tenai que se el mismo que el de abajo del todo y los del medio el que estaba abajo del primero tenia que ser mas grande que el siguiente.

1 SENTENCIA: digital write, high=1 low=0 
2 DELAY: por defecto viene 1000 lo podemos cambiar
3 DIGITAL WRITE( led, builtin, low) 
4 DELAY (1000)

delay: 1000= 1 seg  0'05 seg= 50 no lo podremos ver con nuestros ojos como parpadea.

Hicimos un pulso largo y uno corto


## SEGUNDA PRUEBA 

Vamos a programar desde un software no desdee un hardware como hicimos el otro dia, vamos a ello

Para poner un boton necesitamos una resistencia de 10.000 (OMNIOS)

Estas son las que tienen el cuerpo veix y una linea naranja

SI el boton lo pulsamos pasa a low, si lo cambaimos de sitio el boton a uno x especifico ara lo contrario estara high. 

Hay que tenr en cuneta la polaridad del led. La pata mas corta va hacia el ground y la larga hacia el voltage

Da igual si la resistencia va detras o delante del led, conectaremos dos leds uno al pin 4 y el otro al pin 5
