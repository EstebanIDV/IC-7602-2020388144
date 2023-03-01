# Prueba Corta # 1 - (PC1)
### Esteban Ignacio Durán Vargas
### 2020388144
###  Tecnológico de Costa Rica - Escuela de Ingeniería en Computación Redes
### IC - 7602 - 2023 I Semestre
### Fecha de entrega: 28/02/23 antes de las 11:59 pm



#  Respuestas

 1. **Explique de forma concisa, ¿En que consiste el modelo OSI?**

	El modelo OSI corresponde a un modelo de estandarización internacional de sistemas de comunicación. Este modelo se divide en 7 capas (algunas siendo aplicación, red, física, datalink, etc.) cada una dividida según la función que se requiera y el tipo de información que se quiera transmitir con esta para cumplir con el proceso de comunicación. 


 2. **¿En que consiste el concepto de encapsulamiento de datos en redes? Explique detalladamente**

	El concepto de encapsulamiento de datos se refiere al proceso de comunicación usado entre capas del modelo OSI. Para este proceso, una capa superior construirá un paquete con su payload con los datos del mensaje a construir, al igual que el header y trailer con la información necesaria para esta capa. Luego, la siguiente capa tomará este paquete y lo encapsulará dentro su propio payload, y añadirá la información del header y trailer que le corresponde (para la de transporte son los protocolos de transporte y puertos, la de red tiene las ips, y así con los demás). Una vez se llega a la última capa y se hace la última encapsulación, se transmiten los datos y al llegar al destino, esta empieza a desencapsular. Lo que significa que saca el payload del paquete que llegó, que es el paquete de la capa superior; para que luego el paquete de la capa superior desencapsule su payload y la pase a la superior, y este se repite hasta que la capa de aplicación pueda mostrar el mensaje que se quería transmitir. 
	

 3. **¿Cuál es el funcionamiento de un modem en la red telefónica pública conmutada?**
	
Dentro de las computadoras podemos encontrar fácilmente señales digitales de 1s y 0s. Pero estas no pueden ser transmitidas en otros medios físicos como lo sería la red telefónica conmutada porque su señal cambiaría y perdería el sentido una vez llegara a su destino, destruyendo el mensaje. Es por esto que  requiere de una conversión de los datos digitales a analógicos (ondas de voltajes) para transmitirlos sobre un sistema de red. Para esto se utiliza el dispositivo módem que realiza esta conversión para convertirlo y transmitirlo (**MOD**ulator); y este al llega a su destino entra por el mismo dispositivo para invertir el proceso (**DEM**odulator).

 4. **Explique, ¿En que consiste la multiplexión por frecuencia?**

La multiplexión por frecuencia consiste en dividir por medio de filtros el espectro de frecuencias de modo que cada señal tenga una banda de frecuencia propia. Cada uno de estos canales tiene  una banda de frecuencia que encuentran una al lado de la otra. Para evitar el ruido que esto provocaría, entre cada una existe una banda pequeña de separación. De esta manera se multiplexan varias señales dentro del mismo ancho de banda. 
