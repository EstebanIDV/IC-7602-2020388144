

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
