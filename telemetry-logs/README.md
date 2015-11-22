# �C�mo utilizar los archivos .log?

Los archivos .log que encuentras en esta carpeta contienen capturas de datos de telemetr�a de los distintos protocolos. Estos archivos se pueden usar para hacer pruebas con nuestro tracker si no disponemos de la fuente de telemetr�a correspondiente al protocolo que queremos testear.

## �Qu� necesitamos?

* Un adaptador USB-FTDI para conectar la controladora, en el caso de la crius se, o bien tener conectados el ordenador y el amv-open360tracker a trav�s de bluetooth. En el caso de tener un Arduino s�lo necesitamos su cable USB para conectarlo directamente al ordenador.
* En el archivo config.h del firmware del amv-open360tracker debemos definir los baudios a los que vayamos a transmitir, y el protocolo que queremos testear. Por ejemplo:

	`#define LTM`
	
	`#define BAUDS 9600`

* Un programa de comunicaciones serie que permita el env�o de archivos, como por ejemplo [H�rcules](http://new.hwg.cz/files/download/sw/version/hercules_3-2-8.exe).

## �C�mo enviar el archivo?

Los pasos a seguir son:

    1.- Enchufar el cable usb al ordenador, o conectamos los m�dulos bluetooth.
    2.- Suministrar alimentaci�n al tracker.
    3.- Abrir h�rcules.
    4.- Hacer clic en la pesta�a Serial.
    5.- Modificar los par�metros de comunicaci�n:
		Name: 		COM8 (suponiendo que COM8 sea el puerto que se corresponde al adaptador UBS-FTDI / Bluetooth)
		Baud: 		9600 (suponiendo que en el confi.h se ha definido #define BAUD 9600)
		Data size:	8
		Parity: 	none
		Handshake: 	OFF
		Mode: 		Free
    6.- Hacer clic en el bot�n Open.
		Deber�a aparecer en verde "Serial COM8 opened".
	7.- Pulsamar las tecla CTROL + O (letra O, el s�mbolo + no se pulsa)
    8.- Seleccionamos el archivo que quermos enviar.
	9.- Hacer clic en el bot�n Abrir.

Aparecer� una peque�a ventana con el mensaje Sending file, la ruta completa del archivo que se est� enviadno, los bytes enviados, y una barra de progreso.

Cuando termine se puede hacer clic en el bot�n Close para cerrar la conexi�n, o enviar el archivo nuevamente si se desea. 