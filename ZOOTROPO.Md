
## Puente H

Cuando queremos cambiar la orientacion del molino, tendremos que poner el puente h: 

Puente h: son un tipo de componente conocido como un circuito integrado.

Los CI son componentes que contienen circuitos grandes en un paquete de tamaño reducido

Ayudan a simplificar circuitos mas complejos al colocarlos  en un componente facil de remplazar

![Captura de pantalla de 2022-01-19 12-17-21](https://user-images.githubusercontent.com/90753279/150120244-a1f5120e-0231-43ee-a563-2f555fb7a72a.png)


#CON UN CI

puedes acceder a una clavijas que salen por los lados, tienen numero de clavija, y no todas se utilizan para x circuito, cada clavija tiene una funcion

Al mirar el CI la parte que tiene hoyuelo que es la parte de arriba, pudes identificar el numeros de las clavijas al contar desde la parte superior de la izquierda siguiendo con una linea U

## DATA SHEET

[Pagina de salida] https://store.arduino.cc/products/arduino-starter-kit-multi-language

Informacion de data sheet¡https://www.arduino.cc/documents/datasheets/H-bridge_motor_driver.PDF                                


## EL CODIGO

Crear constantes para los pins de salida y de entrada.

const int controlPin1 = 2;
const int controlPin2 = 3;
const int enablePin = 9;
const int directionSwitchPin = 4;
const int onOffSwitchStateSwitchPin = 5;
const int potPin = A0;

Utilizar variables para guardar los valores de las variables de entrada. Se utilizan para detectar el cambio de estado de ambos pulsadores, comparado el estado dentro de un ciclo con el siguiente ciclo, igual a lo que se hizo en el proyecto del reloj de arena digital. De esta forma, además de almacenar el estado actual, será necesario guardar el estado anterior de cada pulsador.

int onOffSwitchState = 0;
int previousOnOffSwitchState = 0;
int directionSwitchState = 0;
int previousDirectionSwitchState = 0;

La variable motorDirection guarda la dirección de giro del motor, y la variable motorEnabled es la que indica si el motor está girando o no.

int motorEnabled = 0;
int motorSpeed = 0;
int motorDirection = 1;

Dentro del bloque del setup(), configurar la dirección de cada pin de entrada y salida.

void setup() 
{
  pinMode(directionSwitchPin, INPUT);
  pinMode(onOffSwitchStateSwitchPin, INPUT);
  pinMode(controlPin1, OUTPUT);
  pinMode(controlPin2, OUTPUT);
  pinMode(enablePin, OUTPUT);

Poner la variable enablePin en estado LOW (bajo) para comenzar, de esta manera el motor no girará.

  digitalWrite(enablePin, LOW);
}

En la función loop(), leer el estado del pulsador de arranque o encendido para guardar su estado dentro de la variable onOffSwitchState.

void loop() 
{
  onOffSwitchState = digitalRead(onOffSwitchStateSwitchPin);
  delay(1);
  directionSwitchState = digitalRead(directionSwitchPin);
  motorSpeed = analogRead(potPin) / 4;

Si existe una diferencia entre el estado actual del pulsador de arranque con respecto a como estaba en el ciclo anterior, y el pulsador se encuentra en estos momentos en HIGH, se pone la variable motorEnabled en el estado contrario al que se encuentra actualmente, si esta en “1” se pone en “0” y viceversa.
Se leen los valores de las posiciones de los pulsadores y del potenciómetro. Se almacenan estos valores en sus respectivas variables.

  if (onOffSwitchState != previousOnOffSwitchState) 
  {
    if (onOffSwitchState == HIGH) 
    {
      motorEnabled = !motorEnabled;
    }
  }

Verificar si el valor de la variable del pulsador de dirección es actualmente el mismo que en el ciclo anterior. Si es diferente, cambiar la variable de dirección del motor. Solo existen dos formas de que el motor pueda girar, así que esta variable alternará entre dos estados para hacer que el motor gire en un sentido o en el sentido contrario. La forma de lograr esto es utilizando el operador de inversión: motorDirection = !motorDirection.

  if (directionSwitchState != previousDirectionSwitchState)
  {
    if (directionSwitchState == HIGH) 
    {
      motorDirection = !motorDirection;
    }
  }




