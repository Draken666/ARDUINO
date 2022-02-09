## CODIGO
```

const int greenLEDin = 9;
const int redLEDin = 11;
const int blueLEDin = 10;

const int redSensorPin = A0;
const int greenSensorPin = A1;
const int blueSensorPin = A2;

// aadimos variableds para los valores de entrada de sensores y para los valores de salida
int redValue = 0;
int greenValue = 0;
int blueValue = 0;

int redSensorValue = 0;
int greenSensorValue = 0;
int blueSensorValue = 0;

// Empieza la comunicacin en serie en 9600 bps
void setup() {
  Serial.begin(9600);

  pinMode(greenLEDin, OUTPUT);
  pinMode(redLEDin, OUTPUT);
  pinMode(blueLEDin, OUTPUT);

}

//lee los valores de los sensores en A0, A1 y A2 con analogRead y aolmacena los valores en las variables apropiadas
void loop() {
  redSensorValue = analogRead(redSensorPin);
  delay(5);
  greenSensorValue = analogRead(greenSensorPin);
  delay(5);
  blueSensorValue = analogRead(blueSensorPin);

//imprime los valores de los sensores en una sola lnea
  Serial.print("Raw Sensor Values /t Red: ");
  Serial.print(redSensorValue);
  Serial.print("/t Green: ");
  Serial.print(greenSensorValue);
  Serial.print("/t Blue: ");
  Serial.print(blueSensorValue);

//cambiamos el brillo del LED
  redValue = redSensorValue/4;
  greenValue = greenSensorValue/4;
  blueValue = blueSensorValue/4;

// imprimimos los nuevos valores
  Serial.print("Mapped Sensor Values /t Red: ");
  Serial.print(redValue);
  Serial.print("/t Green: ");
  Serial.print(greenValue);
  Serial.print("/t Blue: ");
  Serial.print(blueValue);

  analogWrite(redLEDin, redValue);
  analogWrite(greenLEDin, greenValue);
  analogWrite(blueLEDin, blueValue);

}
