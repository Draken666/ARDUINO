## VILLANCICO


Lo que hemos intentado hacer es un villancico, a partir de un altavoz.Depende de la nota que se interpreta a partir de numeros.
Tambien hay una frequencia y un delay, esto hace que cada numero/nota tenga un espacio de tiempo
*si ponemos un -1 esa nota no sonara

CODIGO ARDUINO !(https://github.com/Draken666/ARDUINO/blob/main/CODIGO%20VILLANCICO)!

Aun no hemos hecho ningun villancico, no hemos montado la placa de arduino, en nuestro codigo aun falta poner las notas para hacer una melodia, depende de la frequencia en este caso 667, es decir lo que dura la nota, se multiplicara,

261.63, 293.66, 329.63, 349.23, 392, 440, 466.16, 523.25, 587.33, 587.33, 659.25,698.46, 783.99, 880, 932.33, 1046.50 estos son algunos tipos de frequencia. 

Lo que hicimos fue tomar el codigo de kill switch y agregar primero el pin del altavoz que en este caso sera el pin 8.

Luego pusimos las frecuncias de las notas que las sacamos del Fab Academy de David Prieto y añadimos la nota de la negra que es 667.

luego hicimos un void tocarNota que es donde vamos añadir las notas que queremos tocar en nuestra melodia.

Y tambien hicimos un void tocarMelodia que funciona para que tocarNota sepa que nota tocar y cuanto tiene que durar.

Depende que villancico escojamos seran otras notas.

por ejemplo el 25 de diciembre 

![imagen](https://user-images.githubusercontent.com/90753279/146927649-32a714f0-3d97-45d4-b5fe-971b54b0cb24.png)

![Codigo 25 de diciembre](https://github.com/Draken666/ARDUINO/blob/main/aaaaperro.ino)

Ahora tenemos que traducir esto para nuestro arduino segun la frecuencia de notas que tenmos en el const int freqs[] siendo la primera el numero 0.

Este seria el numeor de cada nota

0 do  1 re  2 mi

3 fa  4 sol 5 la

6 si  16 sol sostenido

 el 25 de dicimbre se usa el sol sostenido la cual en nuestras notas no esta asi que la añadi de ultima y seria el numero 16.

 en el void tocar melodia vamos ayadir todas las notas con tocarNota(Numero de nota,duracion de nota)

Necesito saber el tiempo de cada nota vamos a usar la melodia aqui podemos ver cuando duraria cada una:

![imagen](https://user-images.githubusercontent.com/90753279/146928801-e948bd46-e10e-46bf-92ea-cf8171de37cd.png)












