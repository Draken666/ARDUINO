## MOLINILLO

Induccion:

Energia: potencia > tiempo

E= P x T

P= I V

Potencia= Intensidad = voltaje

I= V/R

Intensidad= voltaje / resistencia

codigo:
```c++

 const int switchPin = 2;
const int motorPin = 9;
int switchState = 0;
void setup() {

   pinMode(motorPin, OUTPUT);
    pinMode(switchPin, INPUT);

}
void loop() {
    switchState = digitalRead(switchPin);

   if (switchState == HIGH) {
        digitalWrite(motorPin, HIGH);

   }
    else {
        digitalWrite(motorPin, LOW);
    }

```


Este proyecto trata de conseguir que el Arduino haga girar un molinillo de colores con un motor.
Para crear este circuito necesité un transistor mosfet, una resistencia de 10 kiloohmios, un diado 1N4007, un motor, una batería de 9 V, un interruptor y un broche de presión de la batería.

Por un par de razones, controlar motores con un Arduino es mas complicado que controlar unos leds. En primer lugar, los motores necesitan más corriente del que pueden suministrar las clavijas de salida de Arduino.

Y, en segundo lugar, los motores pueden generar su propia corriente atrevas de un proceso llamado inducción, que puede dañar tu circuito si no tomas precauciones.
La interfaz fue un poco difícil y entraña de crear, ya que el motor no solo era alimentado por la placa de Arduino, sino que necesita una batería de 9V adicional para poder funcionar.


Cuando queremos cambiar la orientacion del molino, tendremos que poner el puente h: 

Puente h: son un tipo de componente conocido como un circuito integrado.

Los CI son componentes que contienen circuitos grandes en un paquete de tamaño reducido

Ayudan a simplificar circuitos mas complejos al colocarlos  en un componente facil de remplazar
