## CODIGO


#include <Servo.h>
Servo myServo;
int const potPin = A0;
int potVal;
int angle;
void setup() {

    myServo.attach(9);

    Serial.begin(9600);
}
void loop() {

    potVal = analogRead(potPin);
    Serial.print("potVal: ");
    Serial.print(potVal);
angle = map(potVal, 0, 1023, 0, 179);
Serial.print(", angle: ");
Serial.println(angle);
    myServo.write(angle);
    delay(15);
}


En este circuito se usa un servomotor para hacer un calibrador mecánico para indicar de qué humor estás ese día.
Se necesitan los siguientes componentes: potenciometros, servomotor, brazo motor y dos condensadores
La interfaz no fue muy difícil de montar ya que no llevaba gran número de componentes ni de cables.
Este código fue muy fácil de crear ya que era muy corto y no era difícil de comprender.
En este proyecto no tuve ningún problema, solo que aun no comprendí para que servia bien.

