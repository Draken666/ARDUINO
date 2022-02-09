## TEMPERATURA LCD


Hemos utilizado lo de la [bola de cristal](https://github.com/Draken666/ARDUINO/blob/main/Bola%20de%20cristal.MD)
Solo utilizemos la base de la bola de cristla para plasmar la temperatura y la humedad que ofrece el KY-015
Conectamos el KY-015   el negativo al grnd
El positivo lo conectemos a los 5 voltios
Y el que queda al pin que le asignamos en el arduino.
Pusimos una temperatura limite de 24 grados, despues asignamos un botton en HIGH, i le asignamos que subiera la temperatura cuando le damos.

C++

#include "DHT.h" 
#include <LiquidCrystal.h>
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);
const int sensor_pin_ky015 = 7;            //pin por donde entra la señal del KY-015
#define DHT1 DHT11 

//declaro variables del programa
float humedad_ky015;                        //aqui almacenamos la humedad leida del ky-015
float temperatura_ky015;                   //aqui almacenamos la temperatura leida del ky-015

DHT dht11(sensor_pin_ky015, DHT11);         //inicializamos el sensor KY-015 y le llamamos dht11

void setup() {
  // put your setup code here, to run once:
  lcd.begin(16,2);
 Serial.begin(9600);                       //Iniciamos la trasmision a 9600 baudios
 dht11.begin ();                           //le indicamos al sensor dht11 que comience a medir
   lcd.print(" ARDUINO  FACIL   ");        //mostramos un mensaje de bienbenida
  lcd.setCursor(0,1);                       //movemos el cursor a 1ª columna y 2ª fila
  lcd.print("   PARA TODOS     ");        //mostramos un mensaje en esa posición
  
  delay(3000);                              //pausamos 3seg para leer los mensajes
  lcd.clear(); 
  pinMode(6,INPUT);
 }
 
void loop() {
  delay(2000);
  // put your main code here, to run repeatedly:

 //Leemos el sensor y almacenamos los valores
  humedad_ky015 = dht11.readHumidity();             //leemos la humedad y almacenamos

   int switchState = digitalRead(6);
 if (switchState == HIGH) {
  temperatura_ky015 ++;
  if (temperatura_ky015 > 60) {
    temperatura_ky015 = dht11.readTemperature();  
  }
 }
 else {
  temperatura_ky015 = dht11.readTemperature();  
 }

      //leemos la temperatura y almacenamos
  //Comprobamos si la lectura a fallado. La instruccion isnan, comprueba si la variable
  //que le pasamos tiene un valor representativo.  
  //Primero al dht11 incluido en la placa ky-015
  if (isnan(humedad_ky015) || isnan(temperatura_ky015)) {
    //Si la lectura es incorrecta
      lcd.setCursor(0,1);    
      lcd.print("Error de lectura    ");  
    Serial.println ("Error de lectura en KY-015");    //mostramos el mensaje de error en el serial
  }

     else {
    //Si la lectura es correcta
        //Si la lectura es correcta
    lcd.setCursor(9,0);                     //movemos el cursor a 10ªcolumna y 1ª fila
    lcd.print ("H=");                       //mostramos el mensaje de humedad con la H
    lcd.print (humedad_ky015,1);            //mostramos el valor de la humedad con un decimal
    lcd.print ('%');                        //mostramos el simbolo de porcentaje
  

    lcd.setCursor (0,1);                    //movemos el cursor a 1ª columna y 2ª fila
    lcd.print("                    ");      //borramos la 2ª fila entera por si ha aparecido el
                                            //mensaje de error
    lcd.setCursor (9,1);                    //movemos de nuevo el cursos a 10ª columna y 2ª fila
    lcd.print ("T=");                       //mostramos el mensaje de temperatura con la T
    lcd.print (temperatura_ky015,1);        //mostramos el valor de la temperatura con un decimal
    lcd.print (char(223));                  //mostramos el caracter º con el valor 223
    lcd.print ('C');                        //mostramos la letra C


    Serial.print("KY-015: ");               //mandamos texto al visor serie
    Serial.print("Humedad = ");             //mandamos texto al visor serie
    Serial.print(humedad_ky015,1);          //mandamos el valor medido de humedad con 1 decimal
    Serial.print(" %\t");                   //mandamos el simbolo % y un tabulador
    Serial.print("Temperatura = ");         //mandamos texto al visor serie
    Serial.print(temperatura_ky015,1);      //mandamos el valor medido de temperatura con 1 decimal
    Serial.println("ºC");                     //mandamos texto al visor serie
  }

}

[ARDUINO FOTOS](https://github.com/Draken666/ARDUINO/blob/main/IMG_20220202_133636.jpg)







