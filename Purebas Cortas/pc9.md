### Prueba Corta # 9 - (pc9)
### Esteban Ignacio Durán Vargas - 2020388144
### IC - 7602 - 2023 I Semestre
### Fecha de entrega: 30/05/23


#  Respuestas

 1. **Autrum Transfer Protocol (ATP), es un protocolo creado durante los años 90 para el envío de mensaje (este utilizaba el puerto TCP/666), este se volvió muy popular entre las personas jóvenes de la época que tenían acceso a una red, este protocolo era capaz de transportar cualquier carácter visible ASCII, parte de lo emocionante de este protocolo era lograr enviar los mensajes de forma cifrada y el proceso era enteramente manual, lo cual quiere decir que las personas involucradas en la transmisión conocían las llaves para cifrar y descifrar mensajes. ATP se ha puesto de moda en el 2022, el problema es que ATP es un protocolo sumamente débil en términos de seguridad y además usa un puerto poco convencional como lo es TCP/666, con el fin de evaluar sí es posible implementar una versión segura de este protocolo, se le solicita responder las siguientes preguntas:**
	
	**a. ¿Es posible enviar datos que no sean HTTPs sobre el puerto 443? Justifique su respuesta. (10 pts)**

	Si es posible, los puertos no están fijados a un tipo de protocolo en específico. Estos protocolos, como HTTPs, solo han sido adoptados como el predeterminado. Al fin de cuentas lo que se pasa por los puertos son paquetes de datos y la interpretación depende del protocolo que se use. Esto siempre y cuando el emisor y receptor estén de acuerdo por cuál puerto se recibe cuál dato. 


	**b. Suponiendo que creamos el protocolo ATP over SSL (ATPs), describa un subprotocolo para el establecimiento de una conexión SSL. (40 pts)**

	Este subprotcolo sería muy similar al de HTTPs donde se negocian los parámetros para establecer la conexión segura con SSL. Empieza con el cliente iniciando un handshake con la información que ocupa de SSL para la conexión como la versión y el conjunto de cifrado. Este handshake lo responde el cliente  con la misma información y un certificado de SSL que el cliente autentica con los certificados que ya conoce y saber con quién está hablando. El siguiente paso es que el cliente genere una llave simétrica y encripte con la llave pública del cliente y finalmente ambos tendrán la llave simétrica para encriptar los datos que envíe el cliente por el ATP. 




	**c. Si existe el protocolo ATPs, ¿Es posible transportar ATPs sobre HTTPs? Justifique su respuesta. (10 pts)**

	Si es posible mientras que se cumplan ciertas condiciones. La primera sería que tanto el emisor como receptor de los paquetes de datos sean capaces de interpretar los pquetes ATPs mediante HTTPs. En segundo lugar a nivel de HTTPs se deben tomar las consideraciones para hacer ATPs funcionar. Se pueden utilizar el formato de HTTP para encapsular ATP. Esto implica usar flexiblemente los headers de HTTP dependiendo de las acciones de ATP e información que vaya en el payload del paquete. También, debido a que se especifica que sea ATPs debe servir con SSL para su encripción entonces se debería serguir los pasos anteriores de la pregunta anterior para transportarlo por HTTPs siempre y cuando ATPs si esté estructurado para este. 


	**d. Desde un punto de vista de firewalls, ¿Porqué sería muy conveniente usar el puerto TCP/80 en lugar de puerto TCP/666?**

	Porque es común que los firewalls bloqueen la gran mayoría de puertos a excepción de 3 (que incluye el 80). Si se usa el puerto 80 en vez del 666, este brinda la ventaja de que es muy probable que pueda acceder a través de una gran mayoría de firewalls sin tener que ser configurado para permitirlo. 

	

 2. **Explique detalladamente el funcionamiento de RSA. (30 pts)**


Se debe calcular primero dos número primos grandes p y q; n = p X q y z = (p-1) X (q-1); un número primo d con respecto a z; y e tal que e X d = 1 mod z.

Se divide un texto llano P en bloques de tamaño 0 <= P < n. Se agrupa el texto en bloques de k bits (k siendo el entero más grande para 2^k < n). Se calcula C que es = P^e(mod n) que requiere (e,n) que se encuentra en la llave pública. Para desencriptarlo se calcula P = C^d(mod n) que requeire (d,n) en la privada. 