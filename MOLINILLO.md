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
