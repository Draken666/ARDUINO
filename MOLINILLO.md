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

}//Fin de la funcion setup.
void loop() {
    switchState = digitalRead(switchPin);

   if (switchState == HIGH) {
        digitalWrite(motorPin, HIGH);

   }
    else {
        digitalWrite(motorPin, LOW);
    }
