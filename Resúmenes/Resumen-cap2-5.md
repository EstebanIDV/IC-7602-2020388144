

# Resumen 1 (R1) - IC7602
### Esteban Ignacio Durán Vargas
### 2020388144
### IC - 7602 - 2023 II Semestre
### 24/02/23

#  Red Telefónica Pública Conmutada
Cuando hay distancias considerable, muchas computadoras o los cables para una LAN deben pasar por vía pública o zona restringida, los diseñadores de redes dependen de instalaciones de telecomunicaciones existentes, como **PSTN** (Red Telefónica Pública Conmutada). Estas originalmente transmitían voces humanas y tenía capacidades muy limitadas para comunicación de computadoras. Sus cables pueden transmitir 56 kbps (un cable entre computadoras transmite 10^9 bps).  Esto ha cambiado con la introducción de fibra óptica y tecnología digital. 

## Estructura del sistema telefónico

Inicialmente (1876) se ocupaban enlazar n alambres entre teléfonos para comunicarse con n propietarios de teléfonos. Esto cubrió ciudades en cables. La Bell Telephone Company (1878) colocó un alambre para cada propietario,  el cual llamaba la atención de un operador que conectaba manualmente al receptor de la llamada. Luego, las llamadas a larga distancia (conectando oficinas de conmutación) mostraron que no era práctico. Estas eran las 3 partes del sistema telefónico: oficinas de conmutación, cables y las conexiones entre oficinas. 

Luego, AT&T (1984) organizó el sistema como una jerarquía. Cada teléfono tenía dos alambres de cobre que van a la oficina central local a menos de 10 km. La conexión de estos cables y las oficinas era el **circuito local.** Si ambos suscriptores tenían el mismo circuito local, se hacía una conexión eléctrica intacta directa entre los dos circuitos locales. Si no están en la misma, cada oficina central tiene varias líneas a otros centros cercanos llamados **oficinas interurbanas**, y estas líneas (**troncales de conexión interurbana**) pueden establecer conexión dentro de la oficina interurbana. Si los que están en llamada tienen una oficina interurbana en común, se establece una trayectoria de un nivel más alto de la jerarquía. Las centrales interurbanas, primarias, seccionales y regionales se comunican con **troncales interurbanas** de gran ancho de banda.  A continuación se muestra cómo enrutar una conexión de media distancia:

![](https://cdn.discordapp.com/attachments/462125259382849546/1077484336854601808/image.png)


Actualmente hay varios medios de transmisión. Los circuitos locales son pares trenados, previamente siendo cables no aislados espaciados a 25 cm en los postes telefónicos. En las oficinas de conmutación se usan cables coaxiales, microondas y fibra óptica.

En el pasado, toda transmisión era analógica, transmitida con voltaje eléctrico. Actualmente todas las troncales y conmutadores son digitales (fibra óptica, electrónica digital y computadoras) debido a que es simple solo distinguir correctamente un 0 de un 1; lo que da **confiabilidad** a la transmisión digital, además de ser económico y sencillo.

Los tres componentes principales:

 1. Circuitos locales. (Cruciales pero débiles; par trenzado)
 2. Troncales. (Largo alcance y unen llamadas por multiplexión; fibras ópticas digitales)
 3. Oficinas de conmutación.

## La política de teléfonos

En 1970, EEUU dividió AT&T par acabar el monopolio de telecomunicación en AT&T Long Lines y **BOCs** (Compañías Operativas de Bell). Esto se describió en **MFJ** (Juicio Final Modificado). Trajo mayor competencia, mejor servicio y menores precios; pero los servicios locales se elevaron de precio cuando los subsidios a llamadas a larga distancia se eliminaron y el servicio local pasó a a ser autosuficiente.

EEUU se dividió en **LATAs** (160 Áreas de Acceso y Transporte Local) del tamaño de áreas locales. Tenían **LECs** (Portadora de Intercambio Local) que tenía un monopolio de servicios dentro de LATA. El tráfico interLATA lo manejaba una **IXC** (Portadora Entre Centrales) como Sprint o WorldCom. Manejaban llamadas originadas en una LATA mediante una oficina de conmutación llamada **POP** (Punto de Presencia). Estas no ofrecían servicio telefónico local y las LECs no podían ofrecer servicio interLATA. LECs y IXCs se empezaron a fusionar con operadores de celulares cuando la televisión pasó a ser bidireccional y los celulares se volvieron más baratos. El Congreso (1995) se permitió a las compañías de televisión, telefónicas locales, celulares y de larga distancia negociar juntos y ofrecer paquetes integrados; y que así pudieran competir. BOCs se volvieron IXCs y operadores de televisión competían con LECs por servicio telefónico. También se quitó la restricción donde un cliente puede cambiar compañía sin cambiar de número.

## El circuito local: módems, ADSL e inalámbrico




![](https://cdn.discordapp.com/attachments/462125259382849546/1077492636656603156/image.png)

En la imagen anterior se pueden ver los circuitos locales, troncales, oficinas interurbanas y centrales, con el equipo para conmutar llamadas y hasta 10000 circuitos locales.

Los circuitos locales de conexión entre dos alambres, que parte de la oficina central de una compañía telefónica a los clientes, utiliza señal analógica y con costos elevados de conversión a digital. Esto último es porque primero se convierten los datos a analógicos para transmitir por el circuito local, el modem lo convierte en la oficina central y se transmite por las troncales. Se convierte de nuevo en el nuevo modem al llegar al destino. Así los ISP pueden manejar tantas conexiones como modems tengan (hasta que aparecieron los modems de 56 kbps).

La señalización analógica consiste en la variación del voltaje con el tiempo para representar el flujo de información. La señal recibida no es la misma transmitida. Las líneas de transmisión tienen 3 problemas:

 1. **Atenuación**: perdida de energía conforme la señal se propaga hacia su destino. Esta depende de la frecuencia, como si fueran componentes de Fourier de diferente medida. 
 2. **Distorsión**: Los componentes de Fourier se propagan a diferente velocidad por cable.
 3. **Ruido**: La energía no deseada de fuentes distintas al transmisor. Provocada por movimiento al azar de electrones en un cable que causa el ruido térmico. La diafonía se debe al acoplamiento inductivo de dos cables cercanos. Hay ruidos de impulso, por picos en la energía y puede eliminar bits (solo digital).

## Módems

Es indeseable tener un rango amplio de frecuencias por los problemas anteriores. Las ondas cuadradas tienen un espectro amplio entonces tienen mucha atenuación y distorsión por retardo. Entonces la señalización de banda base (Corriente Continua) sea inadecuada.
Corriente Alterna resuelve problemas de CC. Se introduce un rango de 1000 a 2000 HZ (**portadora de onda senoidal**) cuya amplitud, frecuencia o fase se modulan para transmitir información.

En la **modulación de amplitud** se usan dos niveles para 0 y 1. En **modulación de frecuencia** (por desplazamiento de frecuecia) se usan dos tonos. En **modulación de fase** la onda se desplaza de 0 a 180 grados a intervalos espaciados de manera uniforme. Es mejor utilizar desplazamientos de 45, 135, 225 o 315 para 2 bits por información.

![](https://cdn.discordapp.com/attachments/462125259382849546/1077499683179614238/image.png)

En la imagen anterior se muestra que en señal binaria (a) hay 2 amplitudes (1 y 0), en modulación de amplitud hay 2 frecuencias y en modulación de frecuencia está presente o ausente el desplazamiento de fase en cada límite de bit.

Un **modem** (modulador-demodulador) acepta un flujo de bits como entrada y produce una portadora modulada mediante 1+ de estos métodos. El modem se conecta entre una computadora (digital) y el sistema telefónico (analógico).

Para alcanzar velocidades se incrementa la velocidad de muestreo pero no a más de 6000 Hz.  La mayoría de módems muestrea a 2400 veces por segundo. Esto se mide en **baudios**. Un **símbolo** por baudio. 0 voltios para un 0 lógico y 1 para 1 lógico, entonces la tasa de bits es 2400 bps. Para 0, 1, 2, 3 los símbolos son de 2 bits y puede transmitir  24000 símbolos con una tasa de 4800 bps (Conocida como **QPSK** o Codificación por Desplazamiento de Fase en Cuadratura).

Se definen los siguientes conceptos:

 - **Ancho de banda**: Propiedad física del medio que es el rango de frecuencias que atraviesa al medio con atenuación mínima; se mide en hertzios (HZ).
 - **Tasa de baudios**: Muestras por segundo que se realizan; cada muestra envía una porción de información. Mismo que la **tasa de símbolo**, como QPSK.
 - **Tasa de bits** : Cantidad de información que se envía por el canal, igual a símbolos por segundo por la cantidad de bits por símbolo.

	![](https://cdn.discordapp.com/attachments/462125259382849546/1078057535040401520/image.png)

En los diagramas de la imagen anterior se identifican diagramas de constelación. Cada estándar de módem de alta velocidad tiene uno y se comunica con los módem con el mismo modelo. Cuando hay m A continuación cada una de las técnicas de modulación de estos:

 -  **QPSK**: 4 combinaciones válidas. Transmite 2 bits por símbolo. Se ven puntos con amplitud constante a 45, 135, 225 y 315 grados (ángulo al trazar línea desde origen).
 - **QAM-16**: Modulación de Amplitud en Cuadratura. Cuatro amplitudes y fases, para un total de 16 combinaciones. Transmite 4 bits por símbolo.  
 - **QAM-64**: 64 combinaciones. Transmite 6 bits por símbolo. 
 - 
![](https://cdn.discordapp.com/attachments/462125259382849546/1078061344449904670/image.png)

Para menores errores, resultantes de ruido y muchos puntos en el diagrama, se hace corrección de errores mediante la incorporación de bits adicionales. Conocido como **TCM** (Modulación por codificación de malla). Sus diagramas se pueden ver en la imagen anterior y son:

 - **V.32**: 32 puntos de constelación, transmite 4 bits y 1 de paridad por símbolo a 2400 baudios. Alcanza 9600 bps con corrección de errores.
 - **V.32 bis**: Transmite 6 bits de datos, 1 de paridad. 14,400 bps. Tiene 128 puntos con QAM-128. Fax-módems transmiten a esta velocidad.
 - **V.34**: Corre a 28,800 bps, 2400 baudios y 12 bits de datos por símbolo. 
 - **V.34 bis**: Transfiere 14 bits de datos por símbolo, 2400 baudios. Velocidad de 33,600.

Para mayores velocidades, algunos módems comprimen los datos. Casi todos los módems prueban la línea antes de empezar a transmitir datos del usuario y reducen la velocidad si falta calidad.  

Todos los módems permiten flujo de datos en ambas direcciones llamado **full duplex.** Si fuera de solo un sentido a la vez sería **semiduplex** y si es sólo en una dirección es **simplex**.

La mayoría de módems llegan a 33600 es debido al límite de Shannon es 35 kbps. Definido por la longitud promedio de circuitos locales donde cada vez que llega a uno (en la fuente y en el destino), se agrega ruido a la señal. Si se elimina uno, se puede llegar hasta a 70kbps, siendo una señal digital. El canal telefónico tiene un ancho de 4000 Hz y tiene 8000 muestras. Con 8 bits, se pueden transmitir hasta 6000 bps. Esto en EEUU, en Europa llegan a 64000, pero se eligió 56000 por estándar. Este estándar es **V.90** y tiene un canal de bajada de 56 kbps y 33.6 kbps de subida. A este le sigue **V.92** que tiene 48 kbps y la velocidad que será utilizada sería la mitad de los 30 segundos de módems antiguos. Permite que una llamada interrumpa Internet si tiene llamada en espera. 

## Líneas digitales de suscriptor

Para que los LECs compitieran con las industrias de TV de 10 Mbps y las de satélite de 50 Mbps, se ofrecieron nuevos servicios digitales para el circuito local, de **banda ancha**.  **xDSL**  (Línea Digital de Suscriptor) y el más popular **ADSL** (DSL Asimétrica).

Los módems transportaban voz humana, se optimizaban para esta razón pero resultaban lentos. En la oficina central, el cable pasa por un filtro que atenúa todas las frecuencias abajo de 300Hz y arriba de 3400 Hz donde se indica el ancho de banda como 4000Hz. El cliente se suscribe a xDSL, la línea de entrada se conecta a un conmutador sin filtro y el nuevo límite depende de la longitud, espesor y calidad del circuito local. Restringe la distancia a la que pueden ofrecer el servicio desde su oficina. Entre más baja la velocidad, más amplio el radio y menos atractivo el servicio, lo que significa menos clientes. xDSL se diseñó para servir en circuitos locales de par trenzado, no deben afectar las máquinas de fax ni teléfono, deben superar los 56kbps y funcionan por tarifa mensual. AT&T los ofreció dividiendo el circuito local de 1.1MHz en tres frecuencias: **POTS** (Servicio Telefónico Convencional), canal de subida y canal de bajada. Se conoce como multiplexión por división de frecuencia. El otro enfoque era DMT (Multitono discreto) que divide el espectro en 256 canales de 4312.5 Hz. El canal 0 usa POTS, 1-5 para evitar que señales de voz y datos interfieran entre sí. 250 canales restantes son: uno para el control de flujo ascendente, uno para el descendente y los demás para datos de usuarios. Las armónicas, diafonía y otros efectos mantienen a los sistemas pro debajo del límite teórico. Los proveedores pueden escoger 50-50 de flujo ascendente y descendente, pero la mayoría asigna entre 80/90 al descendente. De ahí sale la asimetría de ADSL. Comúnmente, se usan 32 ascendentes y el resto descendentes o  algunos de los ascendentes usarlos bidireccionales, pero estos deben cancelar el eco.

ADSL permite velocidades hasta 8 Mbps para el descendente y 1 Mbps para el ascendente. Por lo general se ofrece 512 kbps para ascendente y 64 kbps para el flujo ascendente; y 1 Mbps para descendente y 257 kbps para un servicio premium. Dentro de cada canal se utiliza una modulación similar a V.34, con 4000 baudios. La  calidad se monitorea y la tsa de datos se ajusta. Los datos se envían con QAM con máximo 15 bits por baudio. El ruido no deja alcanzar la taza excepto en trayectorias cortas con 8 Mbps. Se instala un NID (Dispositivo de Interfaz de Red), que delimita el inicio de la propiedad del cliente. Cerca un divisor, que es un filtro analógico que separa la banda de 0-4000 Hz para POTS que se enruta al teléfono y la de datos al modem. El módem ADSL procesa señales digitales para funcionar como 250 módems QAM operando a diferentes frecuencias. Se conectan a la computadora con velocidad alta a través de una tarjeta Ethernet en esta. En la oficina central se instala un divisor que filtra voz y la envía a su conmutador. las señales superiores de 26 kHz se enrutan hacia un **DSLAM** (Multiplexor de Acceso de línea Digital de Suscriptor) que contiene el procesador digital de los módems. Se extrae el flujo de bits y se envía al ISP. Esta separación facilita el despliegue de ADSL; solo se requieren el DSLAM y un divisor, otros requieren nuevo equipo. Del lado del cliente se instalan con un técnico, a menos que se use G.lite (G.992.2) para no instalar el divisor. En este se usa un microfiltro en cada conector, entre el teléfono/módem y el cable que elimina las frecuencias por abajo de 26 kHz, pero a costo de solo 1.5 Mbps. Aún requiere divisor en la oficina central. 

## Circuitos locales inalámbricos
 
 Las compañías pueden entrar en competencia con las compañías de teléfono locales, ILEC (LEC Obligada) y las candidatas probables son IXCs. Estas deben alquilar una oficina central, equiparla de conmutadores y tender fibra óptica para las centrales interurbanas para la red nacional; y además competir con mejores servicios y precios. Se les conoce como **CLEC** (LEC competitiva) y este proceso es muy costoso entonces utilizan circuitos con cable trenzado **WLL** (Circuito Local Inalámbrico). Entonces surgen la industria de la **inalámbrica fija**, donde el cliente desea una velocidad similar a ADSL, un técnico instala una antena  hacia la oficina central y el usuario no se mueve (cell handoff). Las WLL surgen cuando se añaden 2 canales de televisión educativa a 2.1 Ghz (6 MHz c/u). Una vez se popularizó se les asignó radio bidireccional y utilizadas para WLL, con microondas de 10-12 cm y rango de casi 50 km. Los 198 MHz fuero puestos en un servicio **MMDS** (Servicio de Distribución Multipunto y Multicanal) que se considera como MAN. Equipo fácil de conseguir con tecnología bien desarrollada, pero muchos usuarios comparten el ancho de banda en un espacio geográfico. El bajo ancho de banda obtuvo el interés de ondas milimétricas como alternativas. La FCC asignó un nuevo servicio a 1.3 GHz a un WLL llamado  **LMDS** (Servicio Local de Distribución Multipunto). LMDS son torres con antenas con un rango de 2-5 km que apuntan a direcciones diferentes que definen un sector (ondas milimétricas son altamente direccionales). Asigna un ancho de banda asimétrico, con prioridad al canal descendente. Cada uno puede contar de 36 Gbps descendente y 1 Mbps para todos los habitantes del sector. CLECs se dieron cuenta que con la inversión a las torres, pueden ingresar al negocio. Tiene problemas: las ondas se propagan en línea recta por lo cual debe haber una línea recta despejada y que los árboles y lluvia también las absorben.
 
Para estandarización la IEEE creó 802.16, denominado MAN inalámbrica, para telefonía digital, acceso a Internet, conexión de LANs, difusión por televisión, radio, etc. 

# Troncales y multiplexión
Para mantener trocales (alto o bajo ancho de banda) se han desarrollado esquemas complejo para multiplexar conversaciones una sola troncal física. Se dividen en dos categorías: : **FDM** (Multiplexión por División de Frecuencia) donde se divide la frecuencia en bandas de frecuencia, cada usuario con una banda; y **TDM** (Multiplexión por División de Tiempo) esperan su turno y obtienen una banda por un tiempo.

Radio difusión AM ilustra ambas clases. 1 MHz de 500 a 1500 kHz. A diferentes canales lógicos se les asigna frecuencias distintas y funcionan según el espectro con una separación para evitar interferencia. Algunas estaciones alternan la misma frecuencia entre música y publicidad; esta es multiplexión por división de tiempo.

## Multiplexión por división de frecuencia

En FDM, los filtros del ancho de banda utilizan 3000 Hz para voz. Cuando se multiplexan, se asignan 4000 para mantenerlos bien separados. Se eleva la frecuencia de canales de voz y se combinan porque no hay 2 canales que ocupen la misma porción del espectro. Hay superposiciones en canales adyacentes que se detectan como ruido no térmico, aún con separaciones entre canales (bandas de protección). 

Uno de los estándares más utilizados es 12 canales de voz de 4000 Hz multiplexados de la banda de 60 a 108 kHz. Se llaman **grupos**. La banda de 12 a 60 kHz  se usa para otro grupo. Algunas empresas usan de 48-56 que se basan en este grupo. Se pueden multiplexar 5 grupos (60 canales de voz) para un **supergrupo**. Un grupo maestro se compone de 5 supergrupos (CCITT) o 10 supergrupos. Otros llegan hasta 230000 canales de voz.

## Multiplexión por división de longitud de onda

Para los canales de fibra óptica se utiliza utiliza multiplexión por división de frecuencia a frecuencia muy alta **WDM** ( Multiplexión por División de Longitud de Onda), donde 4 fibras se juntan en un combinador óptico y forman una fibra compartida. En el extremo se dividen y cada una contiene un núcleo corto que filtra las longitudes de onda. Las señales se enrutan a su destino o se recombinan en diferentes formas para transporte adicional multiplexado. Siempre que tengan rango de frecuencia y los intervalos separados se pueden multiplexar en la fibra de largo alcance. Utiliza una rejilla de difracción, muy confiable. Los primeros tenían 8 canales, cada uno de 2.5 Gbps, en 1998 40 canales y  2.5 Gbps, 2001 96 canales de 10 Gbps. Los de 200 canales trabajan con espaciado de 0.1 mm, se le llama **DWDM** (WDM Densa). Una sola fibra es de unos GHz y para aumentar linealmente el ancho de anda se añaden canales paralelos a diferentes longitudes de onda. Como la banda de fibra es de 25000 GHz, hay espacio para 2500 canales de 10 Gbps, incluso a 1 bit/Hz. Los amplificadores ópticos, que pueden regenerar toda señal una vez cada 1000 km, sin múltiples conversiones óptico eléctricas. 

## Multiplexión por división de tiempo

Puede manejarse por dispositivos digitales con datos digitales. Para las señales analógicas se necesita una conversión de analógico a digital, para combinarse en una troncal. Las señales analógicas se digitalizan con un **codec** (codificador-decodificador) y producen números de 8 bits. Toma 8000 muestras por segundo para una banda de 4kHz. A esto se le llama PCM (Modulación por Codificación de Impulsos. Se utilizan distintos métodos:

 - T1: 24 canales de voz que se multiplexan juntos. Las señales analógicas se muestrean por asignación cíclica.  Cada canal inserta 8 bits, 7 de datos, uno de control. Una trama consiste de 192 bits y 1 para entramado, cada 125 µseg, para 1.544 Mbps. El bit número 193 se verifica para no perder sincronización, que, si lo hace, el receptor espera hasta que pueda generar el patrón de bits. 23 canales llevan datos, el otro lleva un patrón para sincronización. La señal analógica se cuantiza en 256 niveles en lugar de 128. En la **señalización por canal común**, el bit extra es 10101010 en tramas nones y contiene información para sincronización. En **señalización por canal común** cada canal tiene su propio subcanal de señalización, con 8 bits de usuario cada 6 tramas.
 - E1: Empaca 32 muestras de datos de 8 bits en la trama básica de 125 µseg. 30 canales se usan para información, 2 para señalización. Cada grupo de 4 tramas proporciona 64 bits de señalización y el resto para señalización por canal asociado.

Una vez la señal se digitaliza, se aplican técnicas para reducir los bits necesarios por canal. Codifican voz y digitalizan cualquier señal analógica. Se basan en que la señal cambia con lentitud comparado a la frecuencia de muestreo que vuelve la información digital de 7 a 8 bits redundantes. **Modulación diferencial por codificación de impulsos** es un método que transmite la diferencia entre el valor actual y el previo de la amplitud. Bastan 5 bits, es poco probable que haya saltos de 16 y si los hubiera se tendría que recuperar. Una variante requiere que cada valor difiera en 1 al predecesor. Se transmite un bit para demostrar si está uno arriba o abajo, se le llama **modulación delta**. Si cambia muy rápido, puede perder información.

Es mejor que la PCM diferencial porque trata de extrapolar valores previo para predecir el siguiente. El transmisor y receptor utilizan el mismo algoritmo y se les conoce como **codificación por predicción** que son útiles para reducir el tamaño de números por codificar. 

Este tipo permite que se multiplexen portadoras T1 en otras de orden más alto. Esto haciendo multiplexión de  flujos T1 a 1 flujo T2, que tienen unos bits de diferencia (6176 MBps y 6312 respectivamente) y la usan para entramar y recuperar en caso de perder sincronía. Esto también se hace con T3 o T4. Esto se ve en la siguiente imagen.


![](https://cdn.discordapp.com/attachments/462125259382849546/1078220322576269353/image.png)

# SONET/SDH

Buscando estandarización para TDM, en 1989 se produjo el estándar **SONET** (Red Óptica Síncrona) y un conjunto de recomendaciones llamadas **SDH** (Jerarquía Digital Síncrona). Todo el tráfico telefónico de larga distancia de EEUU y otros países viaja por SONET en capa física. Tenía los objetivos:

 1. Interconexión entre operadores telefónicos.
 2. Unificar los sistemas digitales de EEUU, europeo y japonés.
 3. Multiplexar varios canales digitales. Avanzar más allá de T4, continuando más allá de gigabits/seg.
 4. Proporcionar apoyo para operaciones, administración y mantenimiento (OAM).

Se quería convertir en un TDM tradicional, con ancho de banda que contuviera ranuras de tiempo para los distintos subcanales. Los intervalos se envían con suma precisión controlados por un reloj maestro al que están atados el remitente y emisor. Luego se propuso que la conmutación de celdas fuera la base de ATM para que llegaran a intervalos irregulares y asíncronos para diferenciarse de SONET.  SONET envía 810 bytes cada 125 µseg, haya o no datos. Tiene velocidad de 8000 tramas/seg y coincide con la tasa de PCM para telefonía digital.

Las tramas son rectángulos de 90 columnas y nueve de alto. Da 51.84 Mbps y se llama **STS-1** (Señal Síncrona de Transporte 1). Las primeras 3 columnas son para administración del sistemas. Las primeras 3 filas son encabezado de sección y se verifica al comienzo y final de sección y las siguiente 6 con el encabezado de línea que se genera y verifica al comienzo y final de cada línea. Las tramas son consecutivas; utiliza los 2 primeros bytes con un patrón para saber el inicio. El resto de columnas son datos de usuarios. Los **SPE** (Contenedor o Sobre de Carga Útil Síncrona) empiezan en cualquier parte de la trama. La primera fila de encabezado de línea tiene un apuntador al primer byte. La primera columna del SPE es encabezado de trayectoria extremo a extremo. Confiere flexibilidad e incluso pueden abarcar 2 tramas.

![](https://cdn.discordapp.com/attachments/462125259382849546/1078399128545005638/image.png)

En la figura anterior se ve la jerarquía de SONET. La portadora es lo mismo que la STS-n excepto por un reordenamiento de bits para sincronización. Las SDH empiezan en OC-3 porque no hay velocidades de 51.84 Mbps para los basados en CCITT.  La tasa de datos bruta incluye encabezados, la SPE los excluye y las de usuario solo tienen 86 columnas disponibles sin encabezados. Cuando no se multiplexa una portadora se añade una c y los flujos que lo conforman se entrelazan por columna en orden.

# Conmutación

Existen 2 técnicas de conmutación: de circuitos y de paquetes.

## Conmutación de circuitos

Con llamadas telefónicas, el sistema telefónico busca una trayectoria física desde el teléfono al receptor. Cuando una llamada  pasa por una oficina de conmutación se establece una conexión entre la línea de la que llegó y una de las salidas. Antes era el operador que conectaba el cable puenteador en los enchufes. Esa trayectoria puede ir por microondas que multiplexan miles de llamadas. Una vez que existe, es  se fija desde antes de enviar cualquier dato hasta que termine la llamada. Se debe dar una señal de petición que se transmita hasta el receptor y este confirme. Luego, el único retardo es el de la señal electromagnética (5 mseg cada 1000 km). No hay peligro de congestión.



## Conmutación de mensajes

No se estable la trayectoria. Cuando envía un bloque datos, este se almacena en la primera oficina de conmutación y después se reenvía. Se inspecciona por error y salta de nuevo (**almacenamiento y reenvío** o store and forward). Antes se perforaba una cinta de papel y se transmitía por una línea de comunicación para luego perforarse en la siguiente oficina (**oficina de arrancado de papel**), se arrancaba y se pasaba al siguiente.

## Conmutación de paquetes.

La conmutación de paquetes envía paquetes conforme se necesite y no tiene trayectoria dedicada. Establece un límite de tamaño de bloque, para almacenarlo en la memoria principal del enrutador. No se puede acaparar durante muchos milisegundos y esto provoca tráfico interactivo. A veces, se pueden enviar otros paquetes antes de que los anteriores terminen de llegar. Disminuye el retardo y mejora el rendimiento. Se usan en redes de computadoras. Distintos paquetes pueden seguir distintas trayectorias dependiendo de las condiciones de red y pueden llegar en desorden.

También es más tolerante a fallos; si falla la conmutación, todos los circuitos que se utilizaron se cancelan. La conmutación de paquetes puede enrutarse y evitar conmutadores averiados. En este no se reserva ancho de banda, por lo que debe esperar su turno para enviarse cada paquete. Por ende, puede fallar por congestión. No desperdicia ancho de banda y es más eficiente; no desperdicia recursos. 

No utiliza transmisión de almacenamiento y reenvío donde Un paquete se almacena en memoria de enrutador y se reenvía al siguiente. Los bits fluyen de manera continua y se evita retardo. En la de circuitos se utiliza cualquier tasa de transmisión, formato o entramado de bits. En la de paquetes se determinan los parámetros básicos. Otra diferencia es que en la de circuitos el cobro  basa en distancia y tiempo. En paquetes, el tiempo no es problema sino el volumen de tráfico. Los ISP cargan una tarifa mensual y es más fácil de entender para los clientes. 