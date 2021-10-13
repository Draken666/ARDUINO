Hemos probado el arduino con  la app y no funcioanaba porque no esta configurado, sale un error.

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



