Para montar el circuito de este proyecto necesitamos los siguientes componentes:

– 1 Led rojo.

– 1 Resistencia de 220Ω.

– 1 Resistencia de 1MΩ.

– Una lámina de material conductor. Por ejemplo, un trozo de papel de aluminio.

Una vez tenemos los componentes necesarios, debemos seguir los pasos siguientes:

1 – Conectamos el ánodo del led al pin 12 del Arduino y cátodo a tierra mediante la resistencia de 220Ω.

2 – A continuación, conectamos los pines 2 y 4 a la protoboard.

3 – Seguidamente, unimos ambos pines mediante la resistencia de 1MΩ.

4 – Ahora cogemos un cable que tenga un mínimo de entre 8 y 10cm de longitud y lo unimos al mismo punto de la protoboard en donde hemos conectado el pin 2. Al otro lado del cable no conectaremos nada, lo dejamos al aire, ya que será donde coloquemos el sensor táctil.

5 – Para finalizar, tengamos en cuenta que no es necesario conectar la alimentación de 5V a la protoboard, ya que el pin digital 4 proporcionará la corriente necesaria al sensor.

Terminado de montar el circuito, deberíamos de tener algo parecido al mostrado en la siguiente figura.

![imagen](https://user-images.githubusercontent.com/90753279/153162556-a6b0fb2f-b34c-4fbf-8fde-9d5869c94ba0.png)

  ## CODIGO
  
  CapacitiveSensor.h>
CapacitiveSensor capSensor = CapacitiveSensor(4,2);

int threshold = 1000;
const int ledPin = 12;

void setup() {

    Serial.begin(9600);
    pinMode(ledPin, OUTPUT);

}//Fin de la funcion setup.

void loop() {

    long sensorValue = capSensor.capacitiveSensor(30);
    Serial.println(sensorValue);

        if(sensorValue > threshold) {
        digitalWrite(ledPin, HIGH);
    }
    else {
        digitalWrite(ledPin, LOW);
    }

        delay(10);

}//Fin de la funcion loop.
