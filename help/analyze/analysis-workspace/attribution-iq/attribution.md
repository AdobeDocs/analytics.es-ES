---
description: 'null'
seo-description: 'null'
seo-title: Descripción general de IQ de atribución
title: Descripción general de IQ de atribución
uuid: bb 345642-4 f 45-4 fb 8-82 d 0-803248 dd 52 ea
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Descripción general de IQ de atribución

>[!IMPORTANT]
>
>IQ de atribución está disponible para todos los clientes en los SKU de Adobe Analytics Ultimate, Prime, Select y Foundation.

## Valor comercial de Attribution IQ {#section_E82B97114E1641A8AE911F57AEB3240A}

El “viaje del cliente” no es lineal y solo se puede predecir parcialmente. Es más orgánico, flexible y, a menudo, impredecible. Cada cliente avanza a su propio ritmo, y a menudo retrocede, se estanca, vuelve a comenzar, etc. Esto hace que sea difícil saber el impacto de los esfuerzos de marketing a lo largo del viaje del cliente. También dificulta los esfuerzos de juntar múltiples canales de datos para responder a preguntas comerciales y genera perspectivas de clientes incompletas.

Adobe Analytics Attribution IQ permite a los equipos de inteligencia moderna comprender de qué manera ocurre la interacción significativa a lo largo del viaje del cliente, identificando con inteligencia los puntos de inflexión que llevan a resultados de destino y optimizando, con eficacia, las iniciativas de marketing.

![](assets/attribution_iq_problem.png)

Adobe Analytics mejora la atribución al permitir lo siguiente:

* Definir la atribución más allá del contenido multimedia de pago: cualquier dimensión, métrica, canal o evento puede aplicarse a modelos (por ejemplo, búsqueda interna), no solo a campañas de marketing.
* Utilizar la comparación de modelos de atribución sin límites: compare dinámicamente todos los modelos que desee.
* Evitar cambios de implementación: con el procesamiento de tiempo de informes y las sesiones con reconocimiento de contexto, el contexto del viaje del cliente puede generarse y aplicarse en el tiempo de ejecución.
* Construir la sesión más adecuada para su situación de atribución.
* Desglosar la atribución por segmentos: compare fácilmente el rendimiento de sus canales de marketing en cualquier segmento importante (por ejemplo, clientes nuevos frente a repetidos, producto X frente a producto Y, nivel de fidelidad o CLV).
* Inspeccionar análisis de canales cruzados y de múltiples contactos mediante Diagramas de Venn e Histogramas, y resultados de atribución de tendencias.
* Analizar visualmente secuencias de marketing clave: explore las rutas que generaron una conversión visualmente con las visualizaciones de visitas en el orden previsto y flujo multinodal.
* Generar métricas calculadas: utilice todos los métodos de asignación de atribuciones que quiera.

## ¿Qué hace Attribution IQ? {#section_63B421E9E75B4CCEBA96726CAA37D73E}

Attribution IQ en Analysis Workspace permite agregar muchos tipos nuevos de modelos de atribución a las Tablas improvisadas, Visualizaciones y Métricas calculadas. Todos los modelos de atribución tienen dos componentes:

* Un **modelo de atribución** (es decir, Primer toque, Último toque, Lineal, etc.). El modelo describe la distribución de conversiones a las visitas en un grupo.
* Una **ventana de retrospectiva de atribución** (es decir, visita o visitante). La ventana de retrospectiva describe qué agrupamientos de visitas se consideran para cada modelo.

El siguiente ejemplo de viaje del cliente representa los puntos de contacto de un solo visitante que abarca tres visitas, tres conversiones y cuatro canales de marketing (búsqueda, visualización, social y correo electrónico):

![](assets/attribution_example.png)

## Atribución basada en instancias {#section_A81DBC3B19014CE3894131F1CF72736F}

La atribución en Analysis Workspace utiliza la “instancia” de cualquier dimensión, lo que significa que los modelos de atribución se aplican a los valores que se pasaron a Analytics (después de reglas de procesamiento, VISTA y Reglas de procesamiento de canales de marketing). En efecto, esto significa que no hay diferencia entre prop o eVar (o cualquier otra dimensión) a los fines del modelado de atribuciones. Las props pueden configurarse para persistir mediante cualquiera de las ventanas de retrospectiva o de los modelos más abajo, y no se utiliza la configuración de asignación y caducidad para eVars (tal como se especifica en la configuración de administración) cuando se aplican los modelos o las ventanas de retrospectiva de atribución.

## Ventana de retrospectiva de atribución {#section_A2782BB64171431EB370CDCD4AD8030D}

La ventana de retrospectiva de atribución es un agrupamiento de visitas al que se aplicará el modelo de atribución. Hay dos posibilidades de configuración de ventana de retrospectiva de atribución en Analysis Workspace: visita y visitante.

**Ventana de retrospectiva de visita**

La ventana de retrospectiva de visita es cualquier secuencia de actividad separada por 30 minutos de inactividad de forma predeterminada. Sin embargo, también se admiten las [Sesiones con reconocimiento de contexto](https://marketing.adobe.com/resources/help/en_US/reference/vrs-mobile-visit-processing.html) mediante [Procesamiento de tiempo de informes](https://marketing.adobe.com/resources/help/en_US/reference/vrs-report-time-processing.html) si prefiere cambiar ese valor predeterminado. Si utiliza la ventana de retrospectiva de atribución de visita dentro de un Grupo de informes virtuales (VRS) con una sesión personalizada, la ventana de retrospectiva de atribución utilizará la definición de visita personalizada como base de su cálculo. En el ejemplo anterior, cada visita se consideraría como una retrospectiva de atribución independiente.

**Ventana de retrospectiva de visitante**

La ventana de retrospectiva de visitante considerará la totalidad de visitas de un visitante dentro de la ventana de informes del Panel de Espacio de trabajo, más los meses completos que comprenden la ventana de informes. Por ejemplo, si el intervalo de fechas de la ventana de informes es del 15 de septiembre al 30 de septiembre, el intervalo de fechas de retrospectiva de visitante sería del 1 de septiembre al 30 de septiembre. Para obtener más información sobre la ventana de retrospectiva de visitante, consulte [Datos que aparecen fuera de la ventana de informes](https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html).

**Ejemplo de ventana de retrospectiva de atribución**

Para ilustrar el impacto de las ventanas de retrospectiva de atribución, aplicaremos un modelo Lineal (que da igual crédito a todos los puntos de contacto) a nuestro ejemplo anterior:

Cuando se utiliza la **ventana de retrospectiva de atribución de visita**, cada visita tiene su conversión distribuida de forma independiente:

* El/$ 10 de la primera visita se dividiría de forma equitativa entre Buscar, Mostrar, Social y Correo electrónico, cada recibido/$ 2,50.
* En la segunda visita, Buscar y enviar por correo electrónico recibiría la mitad de la conversión/$ 5, por lo que Correo electrónico y Búsqueda recibirían otro/$ 2,50.
* Por último, en la visita final, el correo electrónico recibiría todo el crédito por la conversión de/$ 2.

En la **ventana de retrospectiva de visitante**, todas las conversiones se consideran juntas; sin embargo, el cálculo es ligeramente más complejo debido al hecho de que existen múltiples conversiones.

* La primera conversión/$ 10 se dividiría de forma equitativa entre Buscar, Mostrar, Social y Correo electrónico.
* La conversión de segundo/$ 5 se dividiría entonces entre los canales presentes en esa visita, así como los canales anteriores de la visita anterior: Search = (2/6) */$ 5 =/$ 1.67, Display = (1/6) */$ 5 =/$ 0.83, Social = (1/6) */$ 5 =/$ 0.83, Email = (2/6) */$ 5 =/$ 1,67.
* Por último, la última conversión se dividiría en todos los canales para el visitante: Buscar = (2/7) */$ 2 =/$ 0,57, Mostrar = (1/7) */$ 2 =/$ 0.29, Social = (1/7) */$ 2 =/$ 0,29, Correo electrónico = (3/7) */$ 2 =/$ 0,86.

He aquí un resumen de los resultados en formato de tabla:

| Canal | Ingresos (Lineal/Visita) | Ingresos (Lineal/Visitante) |
|---|---|---|
| Buscar | /$5.00 | /$4.74 |
| Visualización | /$2.50 | /$3.62 |
| Social | /$2.50 | /$3.62 |
| Correo electrónico | /$7.00 | /$5.02 |
| Total | /$17.00 | /$17.00 |

Esta diferencia en la ventana de retrospectiva de atribución funciona de forma similar con todos los modelos de atribución que se describen más abajo.

## Modelos de atribución {#section_4B9E7F83AE0B451A992397E55C3F5871}

Analysis Workspace admite diez modelos de atribución diferentes: Primer toque, Último toque, Mismo toque, Lineal, Forma de U, Forma de J, J inversa, Deterioro de tiempo, Participación y Personalizado. A continuación, se muestran los detalles de cada uno con ejemplos ilustrativos:

<table id="table_A3EB34CD52314F0393FF0D12E5F9779D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Icono de interfaz de usuario </th> 
   <th colname="col2" class="entry"> Modelo de atribución </th> 
   <th colname="col3" class="entry"> Definición </th> 
   <th colname="col4" class="entry"> Cuándo se utiliza </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/last_touch.PNG" id="image_7D574182B1564109B0F1C3DD4FD9E8E9" /> </p> </td> 
   <td colname="col2"> <p>Último toque </p> </td> 
   <td colname="col3"> <p>El modelo Último toque da 100 % de crédito al punto de contacto que ocurre inmediatamente antes de la conversión. En el caso de arriba, el canal Correo electrónico obtendría crédito para todos los 17 USD en una retrospectiva de visita o visitante porque Correo electrónico ocurrió justo antes de las tres conversiones. </p> </td> 
   <td colname="col4"> <p>Este es el modelo de atribución más básico y común y se utiliza habitualmente para conversiones con un ciclo de consideración corto. </p> <p>Último toque lo utilizan comúnmente equipos que gestionan el marketing de búsqueda o que analizan palabras clave de búsqueda interna. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/first_touch.png" id="image_D8CD48CB39D64A0386CBA38397BB69B0" /> </p> </td> 
   <td colname="col2"> <p>Primer toque </p> </td> 
   <td colname="col3"> <p>El modelo Primer toque da 100 % de crédito al punto de contacto que ocurre primero en la ventana de retrospectiva de atribución. </p> <p>En el ejemplo anterior que utiliza la ventana de retrospectiva, 10 USD + 5 USD = 15 USD se darían al canal Búsqueda, y 2 USD se darían al canal Correo electrónico. Con una retrospectiva de visitante, todos los 17 USD se darían al canal Búsqueda porque ocurrió primero en todas las visitas de la ventana de informes. </p> </td> 
   <td colname="col4"> <p>Este es otro modelo de atribución común que resulta útil para analizar canales de marketing destinados a impulsar la diferenciación de la marca o impulsar la adquisición de clientes. </p> <p>Primer toque lo utilizan habitualmente equipos de marketing de Visualización o Social, pero también resulta excelente para evaluar la efectividad de recomendaciones de productos in situ. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/same_touch.png" id="image_7E093A65BA4048F0B46E1110D9569C84" /> </p> </td> 
   <td colname="col2"> <p>Mismo toque </p> </td> 
   <td colname="col3"> <p>El modelo Mismo toque da 100 % de crédito a la visita misma donde ocurrió la conversión. </p> <p>En nuestro ejemplo anterior, cada conversión tuvo lugar en una visita siguiente del punto de contacto de marketing previo; por ende, a todos los 17 USD se les daría el elemento de línea “Ninguno”. </p> </td> 
   <td colname="col4"> <p>Este es un modelo útil al evaluar el contenido o la experiencia del usuario que se presentó inmediatamente en el momento de la conversión. Los equipos de producto o diseño a menudo utilizarán esto para tener acceso a la efectividad de una página donde ocurre la conversión. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/linear.png" id="image_FB96E57837EE47B5B6AE0066CC6DCF45" /> </p> </td> 
   <td colname="col2"> <p>Lineal </p> </td> 
   <td colname="col3"> <p>El modelo Lineal es un modelo de múltiples contactos que da igual crédito a toda visita ocurrida que generó una conversión. </p> <p>En situaciones donde surgen múltiples órdenes dentro de la misma perspectiva de visita o visitante, se distribuye igual crédito entre todos los canales que tuvieron lugar antes de la conversión. </p> </td> 
   <td colname="col4"> <p>Este modelo es útil para conversiones con ciclos de consideración más largos o experiencias del usuario que necesitan interacción de clientes más frecuente/sistemática. </p> <p>La atribución Lineal la suelen utilizar equipos que miden la efectividad de notificaciones de aplicaciones móviles o con productos por suscripción. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/u_shaped.png" id="image_625BB199056D453E8DA8FA283A990DDD" /> </p> </td> 
   <td colname="col2"> <p>Forma de U </p> </td> 
   <td colname="col3"> <p>El modelo de Forma de U da 40 % de crédito a la primera interacción, 40 % de crédito a la última interacción, y comparte el 20 % restante entre cualesquiera interacciones en el medio. </p> <p>En retrospectivas de atribución con solo un punto de contacto, el 100 % del crédito se da al punto de contacto único, y en casos con solo dos, se da un 50 % del crédito a cada uno. </p> </td> 
   <td colname="col4"> <p>Este es un gran modelo para quienes valoran las interacciones ocurridas en primer o último lugar (introducidas o cerradas) en una conversión, pero que aún desean reconocer las interacciones de asistencia. </p> <p>La atribución de Forma de U la suelen utilizar equipos que adoptan un enfoque más balanceado y desean dar más crédito a canales que encontraron o cerraron una conversión. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/j_shaped.png" id="image_D062FD7277A947BC9802F8BDFC139427" /> </p> </td> 
   <td colname="col2"> <p>Forma de J </p> </td> 
   <td colname="col3"> <p>El modelo de Forma de J da 60 % de crédito a la última interacción, 20 % de crédito a la primera interacción, y comparte el 20 % restante entre cualesquiera interacciones en el medio. </p> <p>En retrospectivas de atribución con solo un punto de contacto, el 100 % del crédito se da al punto de contacto único, y en casos con solo dos, se da un 75 % al último punto de contacto y un 25 % al primero. </p> </td> 
   <td colname="col4"> <p>Al igual que la Forma de U, este es un gran modelo para quienes valoran las interacciones ocurridas primero o último (introducidas o cerradas) en una conversión, pero que desean destacar la interacción que se cerró en la conversión. </p> <p>La atribución de Forma de J la suelen utilizar equipos que adoptan un enfoque más balanceado y desean dar más crédito a canales que cerraron una conversión. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/inverse_j.png" id="image_20FFD4C9C9714901B3F54C049D129BC6" /> </p> </td> 
   <td colname="col2"> <p>J inversa </p> </td> 
   <td colname="col3"> <p>El modelo de J inversa da 60 % de crédito a la primera interacción, 20 % de crédito a la última interacción, y comparte el 20 % restante entre cualesquiera interacciones en el medio. </p> <p>En retrospectivas de atribución con solo un punto de contacto, el 100 % del crédito se da al punto de contacto único, y en casos con solo dos, se da un 75 % al primer punto de contacto y un 25 % al último. </p> </td> 
   <td colname="col4"> <p>Al igual que la Forma de U, este es un gran modelo para quienes valoran las interacciones ocurridas en primer o último lugar (introducidas o cerradas) en una conversión, pero que desean destacar la interacción que inició la conversión. </p> <p>La atribución de J inversa la suelen utilizar equipos que adoptan un enfoque más balanceado y desean dar más crédito a canales que iniciaron una conversión. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/custom.png" id="image_D46A787AC72248C7B28C402F5515B099" /> </p> </td> 
   <td colname="col2"> <p>Personalizado </p> </td> 
   <td colname="col3"> <p>El modelo Personalizado es un modelo basado en posiciones que permite especificar los pesos que desea dar a interacciones primeras (que inician), últimas (que cierran) y medias (que participan). </p> <p>Los valores especificados se normalizan al 100 % incluso si los números introducidos no suman 100. En retrospectivas de atribución con solo un punto de contacto, el 100 % del crédito se da al punto de contacto único, y en casos con solo dos, se ignora el parámetro “que participan”, y las primeras y últimas interacciones se ponderan mediante las ponderaciones de parámetros de modelo “que inician” y “que cierran”, normalizadas al 100 %. </p> </td> 
   <td colname="col4"> <p>Si la organización no está conforme con los valores predeterminados que Adobe Analytics proporciona, se puede utilizar un modelo personalizado para especificar las ponderaciones más lógicas para la organización. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/time_decay.png" id="image_7976721B60454944BF516FCF8484D3A2" /> </p> </td> 
   <td colname="col2"> <p>Deterioro de tiempo </p> </td> 
   <td colname="col3"> <p>El modelo Deterioro de tiempo sigue un deterioro exponencial con un parámetro personalizado de semivida (el valor predeterminado es siete días). </p> <p>El peso de cada canal depende de la cantidad de tiempo transcurrido entre el punto de contacto y la eventual conversión. A su vez, está determinado por la fórmula 2^(-t/vida media), donde “t” es la cantidad de tiempo entre un punto de contacto y conversión. Para retrospectivas con un solo punto de contacto, se da el 100 % del crédito a ese punto de contacto único, y para retrospectivas con dos puntos de contacto, el crédito es proporcional al tiempo de la conversión. </p> </td> 
   <td colname="col4"> <p>Este es un buen modelo para equipos que llevan a cabo promociones a través de un número de días predeterminado y que desean destacar los canales que ocurrieron con más frecuencia. </p> <p>La atribución Deterioro de tiempo la suelen utilizar equipos que llevan a cabo publicidades en vídeo o equipos que programan su marketing alrededor de un evento importante con una fecha predeterminada (como una conferencia o un evento deportivo). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><img  src="assets/participation.png" id="image_19DD3CA5C0F24F05835D8522C6708DE4" /> </p> </td> 
   <td colname="col2"> <p>Participación </p> </td> 
   <td colname="col3"> <p>La Participación da el 100 % de crédito a todos los puntos de contacto o canales únicos dentro de una ventana de retrospectiva de atribución. Con Participación, el número total de conversiones estará inflado en su informe en comparación con otros modelos de atribución. Observe que la participación desduplica canales que ocurren varias veces dentro de una sola ventana de retrospectiva de atribución antes de dar crédito. </p> <p>En nuestro ejemplo anterior, y proporcionada una ventana de retrospectiva de visitante, Búsqueda, Visualización, Social y Correo electrónico recibirían cada una 17 USD. Utilizando el mismo ejemplo con una ventana de retrospectiva de visita, Búsqueda recibiría 15 USD, Visualización recibiría 10 USD, Social recibiría 10 USD y Correo electrónico recibiría 17 USD. </p> </td> 
   <td colname="col4"> <p>Este modelo es excelente para análisis y descubrimiento a fin de comprender con qué frecuencia sus usuarios o clientes finales están expuestos a cualquier canal, página o interacción particular. </p> <p>Los equipos de medios a menudo utilizarán este modelo para calcular la velocidad de contenido, y las organizaciones minoristas a menudo utilizarán este modelo para comprender qué partes de su aplicación o sitio web están en la ruta crítica de conversión. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Canales de marketing y reglas de procesamiento de canales de marketing {#section_FCBF08A9D7C94B67B7AD76E8633E7916}

El Canal Primer toque y el Canal Último toque, como así también el Detalle de canal Primer toque y el Detalle de canal Último toque, pueden utilizarse con los nuevos modelos de atribución. Sin embargo, para evitar la confusión para su equipo en el futuro, se recomienda utilizar dos nuevas dimensiones en su lugar: **Canales de marketing** y **Detalle de canales de marketing**. Funcionan precisamente igual, pero no implican la confusión de la distinción “Primer toque” y “Último toque” en el nombre. Si no se aplica modelo de atribución, Canales de marketing y Detalle de canales de marketing darán los mismos resultados que Canal Último toque y Detalle de canal Último toque, respectivamente.

Al aplicar modelos de atribución ya sea al Canal Primer toque o al Canal Último toque, cualquier configuración de atribución será anulada por el modelo de atribución que ha seleccionado. Por lo tanto, mientras el nombre de la dimensión puede ser “Canal Primer toque”, si seleccionó el modelo Lineal (por ejemplo), los resultados reflejarían atribución lineal, no “Primer toque”.

Además, puesto que las variables de Canales de marketing dependen de la visita tradicional (tal como definen las Reglas de procesamiento de canales de marketing que se aplican durante el proceso de recopilación de datos), son inelegibles para uso con Sesiones con reconocimiento de contexto.

## Atribución en desgloses de clasificación {#section_F9DE21758C4643879BE05EEAE9A34E5A}

Los modelos de atribución pueden aplicarse a cualquier valor y su clasificación. En circunstancias donde un valor clasificado se desglosa por su clave, Analytics incluirá solamente las claves que están asociadas con ese valor clasificado particular. Por ejemplo, se aplica un modelo de atribución lineal a una eVar dada con los valores “manzana”, “plátano” y “zanahoria” clasificados a los valores “Frutas” y “Verduras”, donde el valor “Verduras” se desglosa por la eVar base y solo “zanahoria” aparecería en el desglose. De igual modo, “Frutas” desglosado por la eVar base solo mostraría “manzana” y “plátano” en los resultados de desglose incluso si el crédito de atribución se distribuyó en todos los tres valores de eVar base.

El comportamiento también se aplica a informes donde las dimensiones de Canales de marketing se desglosan por las dimensiones de Detalle de canales de marketing.

## Atribución para desgloses {#section_B2E87C768B6B4DBFA8EB7DB5E2DF881E}

Analysis Workspace permite realizar un desglose de cualquier valor por cualquier otra dimensión y especificar la misma o diferente configuración de atribución en el desglose. Por ejemplo, una dimensión Canal puede tener aplicada una atribución lineal, pero desglosar Canal por Campaña permite especificar un modelo de atribución diferente en el nivel de campaña.

Esto resulta útil para equipos que tienen un modelo de atribución en el nivel Canal (para dividir de forma justa entre canales), pero que tienen equipos individuales que desean utilizar un modelo de atribución separado en sus campañas individuales y necesitan los totales para sus campañas a fin de que coincidan con lo asignado en el nivel Canal.

## “Ninguno” en Attribution {#section_BC71DA030E45487AA3C3F6ED247A3C4A}

El elemento de línea “ninguno” es un elemento de línea general que representa todas las conversiones ocurridas donde no había valor de dimensión presente. Tradicionalmente, el elemento de línea “ninguno” solo existe en informes de eVar u otras dimensiones que tienen persistencia. Cuando se aplican modelos de atribución, puede aparecer un elemento de línea “ninguno” donde podía no haber existido previamente. Esto ocurre con mayor frecuencia cuando se aplican modelos de atribución a props que introducen un elemento de línea “ninguno” que no estaba presente previamente.

## Atribución para variables de diversos valores

Algunas dimensiones en Analytics pueden contener múltiples valores en una sola visita, como listVars, la variable de producto, las props de lista o eVars de merchandising. Analysis Workspace permite aplicar Attribution IQ a cualquiera de estos tipos de variables en el nivel de visita. El uso de la atribución de Foma de U (40/20/40) es un ejemplo para una sola visita:

| Número de visita | Variable de diversos valores | Evento de conversión | Porcentaje de crédito por la visita (Forma de U) |
|--- |--- |---|---|
| 1 | A,B,C | - | 40 % |
| 2 | D | - | 20 % |
| 3 | E,F | 1 | 40 % |

En este caso, A, B y C se encontraban al mismo tiempo en la visita 1, D se encontraba solo en la visita 2, y E y F se encontraban en la visita 3.

Attribution IQ da todo el crédito porcentual por la visita a cualesquiera valores presentes en la misma. En el ejemplo presente, A, B y C recibirán conversiones del 40 % o 0,4, D recibirá conversiones del 20 % o 0,2, y tanto E como F recibirán conversiones del 40 % o 0,4. Un informe que utilizara la atribución en Forma de U para las visitas anteriores produciría el siguiente resultado:

| Variable de diversos valores | Conversiones (en forma de U o Visita) |
|--- |---|
| A | 0,4 |
| B | 0,4 |
| C | 0,4 |
| D | 0,2 |
| E | 0,4 |
| F | 0,4 |
| Total | 1 |

>[!NOTE]
>Debido a la asignación a nivel de impacto de los modelos de atribución, la suma de cada elemento de línea del informe puede no ser igual al total debido a que cada valor recibe el porcentaje total de crédito perteneciente a la visita en la que estaba contenido.