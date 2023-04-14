# Apuntes - 31/04/23
### Esteban Ignacio Durán Vargas
### 2020388144
### IC - 7602 - 2023 I Semestre



# Enrutamiento jerárquico

El enrutamiento jerárquico se tiene asignaciones de porciones (rangos) de ips de forma geográfica (continentes), las cuales se asignan a los países y con este se pueden saber si un servicio al que se va a acceder está dentro de un continente en específico. Se sabe que queda en este continente, no se sabe cómo calcular la ruta más óptima. De esto se encarga la tabla de routeo que hace la misma computadora para saber dónde enviar el tráfico. Con esta se envía al cloud provider, el cual identifica a dónde se envía el paquete y, con un servicio de routing, este nuevo destino calcula a dónde tiene que enviarlo a continuación. 

Cuando se llega al backbone, se toman rutas que están basadas en la jerarquía de ips, por qué router enviar la información. Los routers de una región no saben cómo se organizan los de otras. Al que se le entregan los paquetes para salir del router se le llama **default gateway**.


# Congestión

La congestión es la presencia de muchos paquetes en la red que causa que los dispositivos de red gasten recursos haciendo análisis de dónde enviar paquetes y llena el buffer. Cuando una estación se queda esperando un ACK por mucho tiempo en una red congestionada, empieza a volver a mandar los paquetes que podría estar dentro del buffer. Esto provoca routers lentos, retrasos y perdidas de paquetes hasta que colapsa la red. El router trata de solucionarlo de las siguientes maneras:

- Descartar paquetes que causa que los dispositivos de red generen timeouts y empiezan a reenviar información.
- Redirecciona tráfico.
- Agrega recursos dinámicamente (posible por medio de cloud).


Hay 2 diferencias:
- **Control de Congestión**: Muchos clientes están en el mismo router y generan mucho tráfico hasta que el router colapse. Existen delays y pérdida de paquetes. Afecta a todos los clientes.
- **Control de flujo**: Se da entre un emisor de paquetes y un receptor de paquetes. No afecta a todos los clientes.


Para lidiar con congestión se tienen las siguientes soluciones:

- **Aprovisionamiento**: Se dedican más recursos. Nunca se sabe cuántos recursos se van a necesitar para nunca tener congestión. **Overprovisioning: No existe forma de darle solución a un problema de red comprando Hardware porque al final ese hardware nunca será suficiente.**
- **Traffic-aware routing**: Se recibe feedback de los routers para saber qué pasa en la red. Se busca mandar paquetes por otros lados para conseguir una notificación explícita para saber si existe congestión e indicarle a los emisores de paquetes que se detengan hasta que baje la congestión.  
- **Control de admisión**: Si un router está llegando a sus límites, no acepta a clientes nuevos. 
- Desprendimiento de carga: Los clientes se quedan esperando un ACK y si nunca lo recibe es porque hay congestión y mejor espera para que baje la congestión. Se busca que el cliente con más tráfico en el buffer sea el cliente que pare (mayor probabilidad de que sea descartado).
- **Ingeniería de tráfico**: Hacer un análisis para identificar si va a ver congestión y cómo evitarlo.
- **Random Early detection**: Asumir que va a haber congestión cuando se dan ciertos patrones de uso en los routers.



