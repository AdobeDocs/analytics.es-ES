---
description: Datos de tabla que describen las columnas de las fuentes de datos.
keywords: Fuente de datos;columnas
seo-description: Datos de tabla que describen las columnas de las fuentes de datos.
seo-title: Referencia de columnas de datos
solution: Analytics
subtopic: fuentes de datos
title: Referencia de columnas de datos
topic: Reports and Analytics
uuid: 9042a274-7124-4323-8cd6-5c84ab3eef6d
translation-type: tm+mt
source-git-commit: 2ea071c4d4f675c74770396610219d405a07a0e1

---


# Referencia de columnas de datos

Utilice esta página para conocer los datos contenidos en cada columna. La mayoría de las implementaciones no utilizan cada columna, por lo que se puede hacer referencia a esta página al determinar qué columnas incluir en una exportación de fuente de datos.

> [!IMPORTANT] Para cualquier columna dada (por ejemplo, una que está definida como 255 caracteres), una fuente de datos puede enviar caracteres adicionales debido a la adición de caracteres que escapan los valores en una cadena. Tenga en cuenta este tema si la implementación envía con regularidad valores que exceden los límites de caracteres.

## Columnas, descripciones y tipos de datos

> [!NOTE] La mayoría de las columnas contienen una columna similar con un prefijo de `post_`. Las columnas de publicación muestran valores después de la lógica del lado del servidor, las reglas de procesamiento y las reglas de VISTA. Adobe recomienda usar columnas de publicación en la mayoría de los casos.

| Nombre de la columna | Descripción de la columna | Tipo de datos |
| --- | --- | --- |
| accept_language | Enumera todos los idiomas aceptados, tal como se indica en la cabecera Accept-Language-HTTP de las solicitudes de imagen. | char(20) |
| aemassetid | Una variable de valores múltiples que corresponde a las ID de recursos (GUID) de un conjunto de recursos de Adobe Experience Manager. Incrementa los eventos de impresión. | text |
| aemassetsource | Identifica la fuente del evento de recursos. Se utiliza en Adobe Experience Manager. | varchar(255) |
| aemclickedassetid | ID de recurso de un recurso de Adobe Experience Manager. Incrementa los eventos de clic. | varchar(255) |
| browser | ID numérica del explorador. Se remite a la tabla de búsqueda de browser.tsv. | int sin firmar |
| browser_height | Altura de la ventana del explorador en píxeles. | smallint sin firmar |
| browser_width | Anchura de la ventana del explorador en píxeles. | smallint sin firmar |
| c_color | Profundidad de bits de la paleta de colores. Se utiliza en el cálculo de la dimensión Profundidad de color. Utiliza la función de JavaScript screen.colorDepth(). | char(20) |
| campaign | Variable utilizada en la dimensión Código de seguimiento. | varchar(255) |
| carrier | Variable de integración de Adobe Advertising Cloud. Especifica el operador de telefonía móvil. Se remite a la tabla de búsqueda de operadores. | varchar(100) |
| channel | Variable utilizada en la dimensión Secciones del sitio. | varchar(100) |
| click_action | Ya no se utiliza. Dirección de vínculos en los que se ha hecho clic en la herramienta heredada Clickmap. | varchar(100) |
| click_action_type | Ya no se utiliza. Tipo de vínculo de la herramienta heredada Clickmap.<br>0: HREF URL<br>1: ID<br>2 personalizada: Evento<br>onClick de JavaScript 3: Elemento de formulario | tinyint sin firmar |
| click_context | Ya no se utiliza. Nombre de la página en la que se ha hecho clic en vínculo. Forma parte de la herramienta heredada Clickmap. | varchar(255) |
| click_context_type | Ya no se utiliza. Indica si click_context tenía un nombre de página o si estaba vinculado a la URL de la página de forma predeterminada.<br>0: Dirección URL<br>de la página 1: Nombre de la página | tinyint sin firmar |
| click_sourceid | Ya no se utiliza. ID numérica para la ubicación dentro de la página del enlace en el que se ha hecho clic. Forma parte de la herramienta heredada Clickmap. | int sin firmar |
| click_tag | Ya no se utiliza. Tipo de elemento HTML en el que se ha hecho clic. | char(10) |
| clickmaplink | Página de link | varchar(255) |
| clickmaplinkbyregion | Vínculo de Activity Map por región | varchar(255) |
| clickmappage | Página de Activity Map | varchar(255) |
| clickmapregion | Región de Mapa de actividades | varchar(255) |
| code_ver | Versión de la biblioteca de AppMeasurement que se ha utilizado para compilar y enviar la solicitud de imagen. | char(16) |
| color | ID de profundidad de color basada en el valor de la columna c_color. Se remite a la tabla de búsqueda de color_depth.tsv. | smallint sin firmar |
| connection_type | ID numérica que representa el tipo de conexión. Variable utilizada en la dimensión Tipo de conexión. Se remite a la tabla de búsqueda de connection_type.tsv. | tinyint sin firmar |
| cookies | Variable utilizada en la dimensión Compatibilidad con cookies.<br>Y:<br>EnabledN:<br>DisabledU: Desconocido | char(1) |
| country | ID numérica que representa el país desde el que provino el clic. Adobe se asocia con Digital Envoy para hacer coincidir las direcciones IP con los países. Utiliza la búsqueda de country.tsv. | smallint unsigned |
| ct_connect_type | Se relaciona con la columna connection_type. Los valores más comunes son LAN/Wi-Fi, Operador de telefonía móvil y Módem. | char(20) |
| curr_factor | Determina el lugar decimal de la moneda y se utiliza para la conversión de monedas. Por ejemplo, USD utiliza dos lugares decimales, por lo que el valor de esta columna debe ser 2. | tinyint |
| curr_rate | El tipo de cambio vigente cuando se produjo la transacción. Adobe se asocia con XE para determinar el tipo de cambio del día. | decimal(24,12) |
| currency | El código de moneda que se ha utilizado durante la transición. | char(8) |
| cust_hit_time_gmt | Solo grupos de informes con marca de tiempo. La marca de tiempo enviada con la visita y basada en el Tiempo Unix. | int |
| cust_visid | Si se estableció una ID de visitante personalizada, aparece completada en esta columna. | varchar(255) |
| daily_visitor | Indicador que determina si la visita es un visitante nuevo diario. | tinyint sin firmar |
| date_time | La hora de la visita en un formato legible, basada en la zona horaria del grupo de informes. | datetime |
| domain | Variable utilizada en la dimensión Dominio. Se basa en el proveedor de servicios de Internet (ISP) del usuario. | varchar(100) |
| duplicate_events | Muestra cada evento que se contó como duplicado. | varchar(255) |
| duplicate_purchase | Indicador que señala que el evento de compra de esta visita se debe ignorar porque es un duplicado. | tinyint sin firmar |
| duplicated_from | Solo se utiliza en los grupos de informes que contienen las reglas de VISTA de copia de visita. Indica de qué grupo de informes se copió la visita. | varchar(40) |
| ef_id | El ef_id utilizado en las integraciones de Adobe Advertising Cloud. | varchar(255) |
| evar1-evar250 | Variables personalizadas 1-250. Cada organización utiliza las eVars de forma diferente. El mejor lugar para obtener más información sobre cómo su organización completa las eVars respectivos sería un documento de diseño de soluciones que sea específico de su organización. | varchar(255) |
| event_list | Una lista separada con comas de las ID numéricas que representa los eventos activados en la visita. Incluye los eventos predeterminados y los eventos personalizados 1-1000. Utiliza la búsqueda de event.tsv. | text |
| exclude_hit | Un indicador que señala que la visita no está incluida en la creación de informes. The visit_num column is not incremented for excluded hits.<br>1: Not used. Parte de una función eliminada.<br>2: Not used. Parte de una función eliminada.<br>3: No longer used. Exclusión<br>de agente de usuario 4: Exclusión basada en la dirección<br>IP 5: Falta la información de visitas vitales, como page_url, pagename, page_event o event_list<br>6: JavaScript no procesó correctamente la visita<br>7: Exclusión específica de la cuenta, como en una regla<br>VISTA 8: No se usa. Exclusión alternativa específica de la cuenta.<br>9: Not used. Parte de una función eliminada.<br>10: Código<br>de moneda no válido 11: La visita individual no incluye una marca de tiempo en un grupo de informes solo de marca de tiempo o una visita que contiene una marca de tiempo en un grupo<br>de informes que no es de marca de hora 12: No se usa. Parte de una función eliminada.<br>13: No se usa. Parte de una función eliminada.<br>14: Visita de Target que no coincide con una visita<br>de Analytics 15: No se está utilizando actualmente.<br>16: Visita de Advertising Cloud que no coincide con una visita de Analytics | tinyint sin firmar |
| first_hit_page_url | La primera URL del visitante. | varchar(255) |
| first_hit_pagename | Variable utilizada en la dimensión Página de entrada original. El nombre de la página de entrada original del visitante. | varchar(100) |
| first_hit_ref_domain | Variable utilizada en la dimensión Dominio de referencia original. Se basa en first_hit_referrer. El primer dominio de referencia del visitante. | varchar(100) |
| first_hit_ref_type | ID numérica que representa el tipo de referente del primer referente del visitante. Utiliza la búsqueda de referrer_type.tsv. | tinyint sin firmar |
| first_hit_referrer | La primera URL de referencia del visitante. | varchar(255) |
| first_hit_time_gmt | Marca de tiempo de la primera visita del visitante en Tiempo Unix. | int |
| geo_city | Nombre de la ciudad de la que provino la visita basado en la dirección IP. Adobe se asocia con Digital Envoy para hacer coincidir las direcciones IP con las ciudades. | char(32) |
| geo_country | Abreviatura del país del que provino la visita basada en la dirección IP. Adobe se asocia con Digital Envoy para hacer coincidir las direcciones IP con los países. | char(4) |
| geo_dma | ID numérica del área demográfica de la que provino la visita basada en la dirección IP. Adobe se asocia con Digital Envoy para hacer coincidir las direcciones IP con las áreas demográficas. | int sin firmar |
| geo_region | Nombre del estado o región del que provino la visita basado en la dirección IP. Adobe se asocia con Digital Envoy para hacer coincidir las direcciones IP con los estados o regiones. | char(32) |
| geo_zip | El código postal del origen de la visita, según la IP. Adobe se asocia con Digital Envoy para hacer coincidir las direcciones IP con los códigos postales. | varchar(16) |
| hier1 - hier5 | Se utiliza por variables de jerarquía. Contiene una lista delimitada de valores. El delimitador se selecciona en virtud de la configuración del grupo de informes. | varchar(255) |
| hit_source | Indica la fuente de la que provino la visita. <br>1: Solicitud de imagen estándar sin marca de hora <br>2: Solicitud de imagen estándar con marca de hora <br>3: Carga del origen de datos activo con marcas de hora <br>4: No utilizado <br>5: Carga genérica de fuentes de datos <br>6: Carga completa del origen de datos de procesamiento <br>7: Carga del origen de datos TransactionID <br>8: Ya no se utiliza; Versiones anteriores de las fuentes de datos de Adobe Advertising Cloud <br>9: Ya no se utiliza; Métricas de resumen de Adobe Social | tinyint sin firmar |
| hit_time_gmt | La marca de tiempo de los servidores de recopilación de datos de Adobe que recibieron la visita se basa en la hora Unix. | int |
| hitid_high | Se utiliza en combinación con hitid_low para identificar una visita de forma exclusiva. | bigint sin firmar |
| hitid_low | Se utiliza en combinación con hitid_high para identificar una visita de forma exclusiva. | bigint sin firmar |
| homepage | Ya no se utiliza. Indicaba si la URL actual es la página de inicio del explorador. | char(1) |
| hourly_visitor | Un indicador que determina si la visita es un visitante nuevo por hora. | tinyint sin firmar |
| ip | Dirección IP basada en la cabecera HTTP de la solicitud de imagen. | char(20) |
| ip2 | No se utiliza. Variable de referencia de backend para los grupos de informes que contienen reglas de VISTA basadas en una dirección IP. | char(20) |
| j_jscript | Versión de JavaScript admitida por el explorador. | char(5) |
| java_enabled | Indicador que señala si Java está habilitado. <br>Y: Habilitado <br>N: <br>U deshabilitada: Desconocido | char(1) |
| javascript | ID de búsqueda de la versión de JavaScript basado en j_jscript. Utiliza la tabla de búsqueda. | tinyint sin firmar |
| language | ID numérica de idioma. Utiliza la tabla de búsqueda de languages.tsv. | smallint sin firmar |
| last_hit_time_gmt | Marca de tiempo (en Tiempo Unix) de la visita anterior. Se utiliza para calcular la dimensión Días desde la última visita. | int |
| last_purchase_num | Variable utilizada en la dimensión Lealtad del cliente. Indica la cantidad de compras anteriores que realizó el visitante. <br>0: No prior purchases (not a customer) 1: 1 prior purchase (new customer) 2: 2 prior purchases (return customer) 3: 3 or more prior purchases (loyal customer)<br><br><br> | int sin firmar |
| last_purchase_time_gmt | Se utiliza para calcular la dimensión Días desde la última compra. Marca de tiempo (en Tiempo Unix) de la última compra realizada. Para la primera compra y para los visitantes que no hayan realizado ninguna compra anteriormente, este valor es 0. | int |
| latlon1 | Ubicación (menos de 10 km) | varchar(255) |
| latlon23 | Ubicación (menos de 100 m) | varchar(255) |
| latlon45 | Ubicación (menos de 1 m) | varchar(255) |
| mc_audiences | Lista de las ID de segmento de Audience Manager a los que pertenece el visitante. | text |
| mcvisid | ID de visitante de Experience Cloud. Número de 128 bits que consiste en dos números de 64 bits concatenados aumentados a 19 dígitos. | varchar(255) |
| mobile_id | Si el usuario utiliza un dispositivo móvil, el ID numérico del dispositivo. | int |
| mobileaction | Acción móvil. Automatically collected when trackAction is called in Mobile Services. Permite establecer automáticamente las rutas de acción en la aplicación. | varchar(100) |
| mobileappid | ID de la aplicación móvil. Almacena el nombre y la versión de la aplicación en el siguiente formato:[AppName] [BundleVersion] | varchar(255) |
| mobileappperformanceappid | Used in the Apteligent data connector. The App ID used in Apteligent. | varchar(255) |
| mobileappperformancecrashid | Used in the Apteligent data connector. The crash ID used in Apteligent. | varchar(255) |
| mobileappstoreobjectid | Used in the Appfigures data connector. ID del objeto de App Store | varchar(255) |
| mobilebeaconmajor | Mobile Services beacon major | varchar(100) |
| mobilebeaconminor | Mobile Services beacon minor | varchar(100) |
| mobilebeaconproximity | Mobile Services beacon proximity | varchar(255) |
| mobilebeaconuuid | Mobile Services beacon UUID | varchar(100) |
| mobilecampaigncontent | El nombre o ID del contenido que se muestra en el vínculo. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| mobilecampaignmedium | El medio de marketing, como banners o correo electrónico. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| mobilecampaignname | Nombre de la campaña, también almacenada en la variable de campaña. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| mobilecampaignsource | Referente original, como un boletín de noticias o una red de medios sociales. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| mobilecampaignterm | Palabras clave de pago u otros términos con los que quiera realizar un seguimiento de esta adquisición. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| mobiledayofweek | Número del día de la semana en que se abrió la aplicación. | varchar(255) |
| mobiledayssincefirstuse | Cantidad de días desde que la aplicación se ejecutó por primera vez. | varchar(255) |
| mobiledayssincelastupgrade | Recopilado desde la variable de datos de contexto a.DaysSinceLastUpgrade. The number of days that have passed since the previous session. | varchar(255) |
| mobiledayssincelastuse | Cantidad de días desde que la aplicación se ejecutó por última vez. | varchar(255) |
| mobiledeeplinkid | Recopilado desde la variable de datos de contexto a.<span>deeplink</span>.id. Se utiliza en los informes de adquisición como identificador para el vínculo de adquisición móvil. | varchar(255) |
| mobiledevice | Nombre del dispositivo móvil. En iOS, se almacena como una cadena de 2 dígitos separados por una coma. El primer número representa la generación del dispositivo y el segundo, la familia del dispositivo. | varchar(255) |
| mobilehourofday | Define la hora del día en que se abrió la aplicación. Sigue el formato numérico de 24 horas. | varchar(255) |
| mobileinstalldate | Fecha de instalación del móvil. Proporciona la fecha de la primera vez que el usuario abrió la aplicación móvil. | varchar(255) |
| mobilelaunchessincelastupgrade | Recopilado desde la variable de datos de contexto a.LaunchesSinceUpgrade. Informa del número de inicios desde la última actualización. | varchar(255) |
| mobilelaunchnumber | Incrementa de uno en uno cada vez que se abre la aplicación móvil. | varchar(255) |
| mobileltv | Ya no se utiliza. Rellenado con métodos trackLifetimeValue. | varchar(255) |
| mobilemessagebuttonname | Recopilado desde la variable de datos de contexto a.<span>message</span>.button.id. Se utiliza para la mensajería en la aplicación para identificar el botón que cerró el mensaje. | varchar(100) |
| mobilemessageid | ID de mensaje en la aplicación | varchar(255) |
| mobilemessageonline | Mensaje en línea en la aplicación | varchar(255) |
| mobilemessagepushoptin | Recopilado desde la variable de datos de contexto a.push.optin. Se establece en "true" cuando el usuario opta por la mensajería push; de lo contrario, el valor es "false". | varchar(255) |
| mobilemessagepushpayloadid | Recopilado desde la variable de datos de contexto a.push.payloadid. Se utiliza en los mensajes push como identificador de carga útil. | varchar(255) |
| mobileosenvironment | Recopilado desde la variable de datos de contexto a.OSEnenvironment. Estados del entorno del sistema operativo, como Android o iOS. | varchar(255) |
| mobileosversion | Versión del sistema operativo de Mobile Services | varchar(255) |
| mobileplaceaccuracy | Recopilado desde la variable de datos de contexto a.loc.acc. Indica la precisión del GPS en metros en el momento de la recogida. | varchar(255) |
| mobileplacecategory | Recopilado desde la variable de datos de contexto a.loc.category. Describe la categoría de un lugar específico. | varchar(255) |
| mobileplaceid | Collected from the context data variable a.loc.id. <span></span> Identificador de un punto de interés determinado. | varchar(255) |
| mobilerelaunchcampaign content | Contenido de inicio de Mobile Services | varchar(255) |
| mobilerelaunchcampaignmedium | Medio de inicio de Mobile Services | varchar(255) |
| mobilerelaunchcampaign ignsource | Origen de inicio de Mobile Services | varchar(255) |
| mobilerelaunchcampaignTérmino | Término de inicio de Mobile Services | varchar(255) |
| mobilerelaunchcampaign trackingcode | Recopilado desde la variable de datos de contexto a.launch.campaign.trackingcode. Se utiliza en la adquisición como código de seguimiento para la campaña de inicio. | varchar(255) |
| mobileresolution | Resolución del dispositivo móvil. Anchura por altura en píxeles. | varchar(255) |
| monthly_visitor | Un indicador que señala que el visitante es exclusivo del mes actual. | tinyint sin firmar |
| mvvar1 - mvvar3 | Valores de variable de lista. Contiene una lista delimitada de valores personalizados en función de la implementación. | text |
| namespace | No se utiliza. Hace muchos años, formaba parte de una función que luego se descartó. | varchar(50) |
| new_visit | Un indicador que determina si la visita actual es una nueva visita. Los servidores de Adobe lo establecen después de 30 minutos de inactividad de la visita. | tinyint sin firmar |
| os | ID numérica que representa el sistema operativo del visitante. Se basa en la columna user_agent. Utiliza la búsqueda de os. | int sin firmar |
| p_plugins | Ya no se utiliza. Lista de plugins disponibles para el explorador. Utilizaba la función de JavaScript navigator.plugins(). | text |
| page_event | El tipo de visita que se envía en la solicitud de imagen (visita estándar, vínculo de descarga, vínculo personalizado, vínculo de salida). See [Page event lookup](datafeeds-page-event.md). | tinyint sin firmar |
| page_event_var1 | Solo se utiliza en las solicitudes de imagen de seguimiento de vínculos. Es la URL del vínculo de descarga, el vínculo de salida o el vínculo personalizado en el que se ha hecho clic. | text |
| page_event_var2 | Solo se utiliza en las solicitudes de imagen de seguimiento de vínculos. El nombre personalizado (si se especifica) del vínculo. | varchar(100) |
| page_event_var3 | Ya no se utiliza. Contenía los datos de los módulos Survey y Media. Completaba los informes de vídeo heredados en las versiones anteriores de Adobe Analytics. | text |
| page_type | Se utilizaba para completar la dimensión Páginas no encontradas y se usaba exclusivamente para las páginas 404. Esta variable debe estar vacía o debe contener "ErrorPage". | char(20) |
| page_url | La URL de la visita. No se utiliza en las solicitudes de imagen de seguimiento de vínculos. | varchar(255) |
| pagename | Se utiliza para completar la dimensión Páginas. Si la variable de nombre de página está vacía, Analytics utiliza page_url en su lugar. | varchar(100) |
| paid_search | Un indicador que se establece si la visita coincide con la detección de búsquedas de pago. | tinyint sin firmar |
| partner_plugins | No se utiliza. Hace muchos años, formaba parte de una función que luego se descartó. | varchar(255) |
| persistent_cookie | La utiliza la dimensión Compatibilidad con cookies persistentes. Indica si el visitante admite las cookies que no se descartan después de cada visita. | char(1) |
| plugins | Ya no se utiliza. Lista de ID numéricas que corresponden a los plugins disponibles dentro del explorador. Utiliza la búsqueda de plugins.tsv. | varchar(180) |
| pointofinterest | Mobile Services point of interest name | varchar(255) |
| pointofinterestdistance | Distancia de Mobile Services al centro de puntos de interés | varchar(255) |
| post_ columns | Contiene el valor definitivo que se ha utilizado en los informes. Cada columna de publicación se completa después de la lógica del lado del servidor, las reglas de procesamiento y las reglas de VISTA. Adobe recomienda usar columnas de publicación en la mayoría de los casos. | Consulte la correspondiente columna de no publicación |
| prev_page | No se utiliza. Identificador de la página anterior registrada de Adobe | int unsigned |
| product_list | Lista de productos tal como se transmite mediante la variable de productos. Los productos están delimitados por comas, mientras que las propiedades de los productos individuales están delimitadas por punto y coma. | text |
| product_merchandising | No se utiliza. Se usa product_list en su lugar. | text |
| prop1 - prop75 | Variables de tráfico personalizadas 1-75. | varchar(100) |
| purchaseid | Identificador exclusivo de una compra como se establece mediante la variable s_purchaseID. Lo utiliza la columna duplicate_purchase. | char(20) |
| quarterly_visitor | Un indicador que determina si la visita es un visitante nuevo trimestral. | tinyint sin firmar |
| ref_domain | Se basa en la columna de referentes. El dominio de referencia de la visita. | varchar(100) |
| ref_type | Una ID numérica que representa el tipo de referente de la visita.<br>1: Dentro del sitio<br>2: Otros sitios web <br>3: Motores de búsqueda <br>4: Disco duro <br>5: USENET <br>6: Escritos o marcadores (sin referente) <br>7: Correo electrónico <br>8: Sin JavaScript <br>9: Redes sociales | tinyint sin firmar |
| referrer | URL de la página anterior. | varchar(255) |
| resolution | ID numérico que representa la resolución del monitor. Completa la dimensión Resolución del monitor. Utiliza la tabla de búsqueda de resolution.tsv. | smallint unsigned |
| s_kwcid | Keyword ID used in Adobe Advertising Cloud integrations. | varchar(255) |
| s_resolution | Valor no procesado de resolución de pantalla. Se recopila mediante la función de JavaScript screen.width x screen-height. | char(20) |
| sampled_hit | Ya no se utiliza. Anteriormente, se utilizaba para muestreo en Ad Hoc Analysis. | char(1) |
| search_engine | ID numérica que representa el Motor de búsqueda que refirió al visitante a su sitio. Utiliza la búsqueda de search_engines.tsv. | smallint unsigned |
| search_page_num | Lo utiliza la dimensión Rango de todas las páginas de búsqueda. Indica en qué página de resultados de búsqueda apareció su sitio antes de que el usuario hiciera clic para acceder a su sitio. | smallint unsigned |
| secondary_hit | Indicador que hace un seguimiento de las visitas secundarias. Por lo general, se origina a partir del etiquetado de grupos múltiples y las reglas de VISTA que copian las visitas. | tinyint sin firmar |
| service | No se utiliza. Se usa page_event en su lugar. | char(2) |
| socialaccountandappids | Ya no se utiliza. Cuenta social e ID de aplicación. | varchar(255) |
| socialassettrackingcode | Ya no se utiliza. Variable de campaña en redes sociales. | varchar(255) |
| socialauthor | Ya no se utiliza. Variable de autores en redes sociales. | varchar(255) |
| socialcontentprovider | Ya no se utiliza. Plataformas sociales/Propiedades | varchar(255) |
| socialinteractiontype | Ya no se utiliza. Tipo de interacción social | varchar(255) |
| sociallanguage | Ya no se utiliza. Idioma de red social | varchar(255) |
| sociallatlong | Ya no se utiliza. Latitud o longitud de la red social | varchar(255) |
| socialowneddefinitioninsighttype | Ya no se utiliza. Tipo de datos de definición con propiedad social | varchar(255) |
| socialowneddefinitioninsightvalue | Ya no se utiliza. Valor de datos de definición con propiedad social | varchar(255) |
| socialowneddefinitionmetric | Ya no se utiliza. Métrica de la definición con propiedad social | varchar(255) |
| socialowneddefinitionpropertyvspost | Ya no se utiliza. Propiedad de definición con propiedad social frente a publicación | varchar(255) |
| socialownedpostids | Ya no se utiliza. ID de publicación con propiedad social | varchar(255) |
| socialownedpropertyid | Ya no se utiliza. ID de propiedad social | varchar(255) |
| socialownedpropertyname | Ya no se utiliza. Nombre de la propiedad social | varchar(255) |
| socialownedpropertypropertyvsapp | Ya no se utiliza. Propiedad social frente a aplicación | varchar(255) |
| state | Variable de estado. | varchar(50) |
| stats_server | No es de uso. Servidor interno de Adobe que ha procesado la visita. | char(30) |
| t_time_info | Hora local del visitante. El formato es el siguiente: M/D/AAAA HH:MM:SS Mes (0-11, 0=enero) Desplazamiento de zona horaria (en minutos) | varchar(100) |
| tnt | Se utiliza en las integraciones de Adobe Target. | text |
| tnt_action | Se utiliza en las integraciones de Adobe Target. | text |
| tnt_post_vista | Ya no se utiliza. Se usa post_tnt en su lugar. | text |
| transactionid | Un identificador exclusivo donde, más tarde, se pueden cargar diversos puntos de datos a través de fuentes de datos. | text |
| truncated_hit | Un indicador que señala que se ha truncado la solicitud de imagen. Indica que se ha recibido una visita parcial. <br>Y: Se truncó la visita; visita parcial recibida <br>N: La visita no se truncó; visita completa recibida | char(1) |
| ua_color | Ya no se utiliza. Anteriormente, se utilizaba como alternativa a la profundidad de color. | char(20) |
| ua_os | Ya no se utiliza. Anteriormente, se utilizaba como alternativa al sistema operativo. | char(80) |
| ua_pixels | Ya no se utiliza. Anteriormente, se utilizaba como alternativa a la anchura y la altura del explorador. | char(20) |
| user_agent | El grupo desconocido que se envía en la cabecera HTTP de la solicitud de imagen. | text |
| user_hash | No es de uso. Hash de la ID del grupo de informes. Se usa username en su lugar. | int unsigned |
| user_server | Variable utilizada en la dimensión de Servidores. | varchar(100) |
| userid | No es de uso. La ID numérica de la ID del grupo de informes. Se usa username en su lugar. | int sin firmar |
| username | La ID del grupo de informes de la visita. | char(40) |
| va_closer_detail | Variable utilizada en la dimensión Detalle del último contacto. | varchar(255) |
| va_closer_id | ID numérica que identifica la dimensión Canal del último contacto. La búsqueda de esta ID se puede encontrar en el Administrador de canales de marketing. | tinyint sin firmar |
| va_finder_detail | Variable utilizada en la dimensión Detalle del primer contacto. | varchar(255) |
| va_finder_id | ID numérica que identifica la dimensión Canal del primer contacto. La búsqueda de esta ID se puede encontrar en el Administrador de canales de marketing. | tinyint sin firmar |
| va_instance_event | Indicador que identifica las instancias de Canal de marketing. Lo utiliza la métrica de Instancias de último contacto de canal de marketing. | tinyint sin firmar |
| va_new_engagement | Indicador que identifica las nuevas interacciones en canales de marketing. Lo utiliza la métrica de Nuevas interacciones. | tinyint sin firmar |
| video | Contenido de vídeo | varchar(255) |
| videoad | Nombre del anuncio de vídeo | varchar(255) |
| videoadinpod | Anuncio de vídeo en posición de pod | varchar(255) |
| videoadlength | Duración de la publicidad de vídeo | varchar(255) |
| videoadload | Cargas de anuncios de vídeo | varchar(255) |
| videoadname | Nombre del anuncio de vídeo | varchar(255) |
| videoadplayername | Nombre del reproductor de anuncios de vídeo | varchar(255) |
| videoadpod | Pod de anuncios de vídeo | varchar(255) |
| videoanunciser | Anunciante de vídeo | varchar(255) |
| videoaudioálbum | Álbum de audio de vídeo | varchar(255) |
| videoaudioartista | Artista de audio de vídeo | varchar(255) |
| videoaudioauthor | Autor de audio de vídeo | varchar(255) |
| videoaudiolabel | Etiqueta de audio de vídeo | varchar(255) |
| videoaudiopublisher | Editor de audio de vídeo | varchar(255) |
| videoaudiostation | Estación de audio de vídeo | varchar(255) |
| videocampaña | Campaña de vídeo | varchar(255) |
| videochannel | Canal de vídeo | varchar(255) |
| videochapter | Nombre del capítulo de vídeo | varchar(255) |
| videocontenttype | Tipo de contenido de vídeo. Se establece automáticamente como "Vídeo" para todas las vistas de vídeo | varchar(255) |
| videodaypart | Parte del día del vídeo | varchar(255) |
| videoepisode | Episodio de vídeo | varchar(255) |
| videofeedtype | Tipo de fuente de vídeo | varchar(255) |
| videogenre | Género de vídeo | text |
| videolength | Duración del vídeo | varchar(255) |
| videomvpd | MVPD de vídeo | varchar(255) |
| videoname | Nombre del vídeo | varchar(255) |
| videonetwork | Red de vídeo | varchar(255) |
| videopath | Ruta de vídeo | varchar(100) |
| videoplayername | Nombre del reproductor de vídeo | varchar(255) |
| videoqoebitrateaverageevar | Tasa de bits promedio de la calidad de vídeo | varchar(255) |
| videoqoebitratechangecountevar | Recuento de cambios en la calidad de vídeo | varchar(255) |
| videoqoebuffercountevar | Recuento de búferes en la calidad de vídeo | varchar(255) |
| videoqoebuffertimeevar | Tiempo de búfer de calidad del vídeo | varchar(255) |
| videoqoedroppedframecountevar | Recuento de marcos de descenso de calidad de vídeo | varchar(255) |
| videoqoeerrorcountevar | Recuento de errores de calidad de vídeo | varchar(255) |
| videoqoeexternalerrors | Errores externos de calidad de vídeo | text |
| videoqoeplayersdkerrors | Errores del SDK de calidad de vídeo | text |
| videoqoetimetostartevar | Hora de inicio de calidad de vídeo | varchar(255) |
| videoseason | Temporada de vídeo | varchar(255) |
| videosegment | Segmento de vídeo | varchar(255) |
| videoshow | Programa de vídeo | varchar(255) |
| videoshowtype | Tipo de programa de vídeo | varchar(255) |
| videostreamtype | Tipo de flujo de vídeo | varchar(255) |
| visid_high | Se utiliza en combinación con visid_low para identificar una visita de forma exclusiva. | bigint sin firmar |
| visid_low | Se utiliza en combinación con visid_high para identificar una visita de forma exclusiva. | bigint sin firmar |
| visid_new | Indicador que identifica si la visita contiene una ID de visitante generada recientemente. | char(1) |
| visid_timestamp | Si la ID de visitante se ha generado recientemente, proporciona la marca de tiempo (en Tiempo Unix) del momento en que se generó la ID de visitante. | int |
| visid_type | ID numérica que representa qué método se ha utilizado para identificar al visitante. <br>0: VisitorID personalizado <br>1: IP y reserva del agente de usuario <br>2: Encabezado de suscriptor móvil HTTP <br>3: Valor de cookie heredado (s_vi) <br>4: Valor de cookie de reserva (s_fid) <br>5: Servicio de identidad | tinyint sin firmar |
| visit_keywords | Variable utilizada en la dimensión Palabra clave de búsqueda. Esta columna utiliza un límite de caracteres no estándar para dar cabida a la lógica back-end utilizada por Adobe. | varchar(244) |
| visit_num | Variable utilizada en la dimensión Número de visitas. Empieza en 1 y aumenta cada vez que se inicia una nueva visita por visitante. | int unsigned |
| visit_page_num | Variable utilizada en la dimensión Profundidad de visita. Aumenta de uno en uno con cada visita que genera el usuario. Restablece cada visita. | int unsigned |
| visit_ref_domain | Se basa en la columna de visit_referrer. El primer dominio de referencia de la visita. | varchar(100) |
| visit_ref_type | ID numérica que representa el tipo de referente del primer referente de la visita. Utiliza la tabla de búsqueda de referrer_type.tsv. | tinyint sin firmar |
| visit_referrer | El primer referente de la visita. | varchar(255) |
| visit_search_engine | ID numérica del primer motor de búsqueda de la visita. Utiliza la tabla de búsqueda de search_engines.tsv. | smallint unsigned |
| visit_start_page_url | La primera URL de la visita. | varchar(255) |
| visit_start_pagename | El primer nombre de página de la visita. | varchar(100) |
| visit_start_time_gmt | Marca de tiempo (en Tiempo Unix) de la primera visita. | int |
| weekly_visitor | Indicador que determina si la visita es un visitante nuevo semanal. | tinyint sin firmar |
| yearly_visitor | Indicador que determina si la visita es un visitante nuevo anual. | tinyint sin firmar |
| zip | Se utiliza para completar la dimensión Código postal. | varchar(50) |

## Columnas vacías

La siguiente lista de columnas no se utiliza y no contiene datos:

* mobileacquisitionclicks
* mobileactioninapptime
* mobileactiontotaltime
* mobileappejecuanceaffectedusers
* mobileappperformance ceappid<span>.</span>app-perf-app-name
* mobileappperformance ceappid<span>.</span>app-perf-platform
* mobileappejecuancecrashes
* mobileappperformance ancecrashid<span>.</span>app-perf-crash-name
* mobileappejecuanceloads
* mobileappstoreavgrating
* mobileappstoredownloads
* mobileappstoreinapprevención
* mobileappstoreinappostulosos
* mobileappstoreobjetid<span>.</span>app-store-user
* mobileappstoreobjetid<span>.</span>application-name
* mobileappstoreobjetid<span>.</span>application-version
* mobileappstoreobjetid<span>.</span>appstore-name
* mobileappstoreobjetid<span>.</span>category-name
* mobileappstoreobjetid<span>.</span>country-name
* mobileappstoreobjetid<span>.</span>fabricante del dispositivo
* mobileappstoreobjetid<span>.</span>device-name
* mobileappstoreobjetid<span>.</span>in-app-name
* mobileappstoreobjetid<span>.</span>platform-name-version
* mobileappstoreobjetid<span>.</span>rank-category-type
* mobileappstoreobjetid<span>.</span>region-name
* mobileappstoreobjetid<span>.</span>review-comment
* mobileappstoreobjetid<span>.</span>revisión-título
* mobileappstoreoneoffrevenue
* mobileappstoreoneoffroyalty
* mobileappstorepurchases
* mobileappstorerank
* mobileappstorerankdivisor
* mobileappstorerating
* mobileappstoreratingdivisor
* mobileavgprevsessionlength
* mobilecrashes
* mobilecrashrate
* mobiledailyengagedusers
* mobiledeeplinkid<span>.</span>name
* mobileinstalls
* mobilelaunches
* mobileltvtotal
* mobilemessageclicks
* mobilemessageid<span>.</span>dest
* mobilemessageid<span>.</span>name
* mobilemessageid<span>.</span>type
* mobilemessageimpressions
* mobilemessagepushpayloadid<span><span>.</span></span>name
* mobilemessageviews
* mobilemonthlyengagedusers
* mobileplacedwelltime
* mobileplaceentry
* mobileplaceexit
* mobileprevsessionlength
* mobilerelaunchcampaign trackingcode<span><span>.</span></span>name
* mobileupgrades
* socialaveragesentiment
* socialaveragesentiment (desaprobada)
* socialfbstories
* socialfbstorytellers
* socialinteractioncount
* sociallikeadds
* sociallink
* sociallink (desaprobada)
* socialmentions
* socialpageviews
* socialpostviews
* socialproperty
* socialproperty (desaprobada)
* socialpubcomments
* socialpubposts
* socialpubrecommends
* socialpubsubscribers
* socialterm
* socialtermslist
* socialtermslist (desaprobada)
* socialtotalsentiment
* sourceid
* videoauthorized
* videoaverageminuteaudience
* videochaptercomplete
* videochapterstart
* videochaptertime
* videopause
* videopausecount
* videopausetime
* videoplay
* videoprogress10
* videoprogress25
* videoprogress50
* videoprogress75
* videoprogress96
* videoqoebitrateaverage
* videoqoebitratechange
* videoqoebuffer
* videoqoedropbeforestart
* videoqoedroppedframes
* videoqoeerror
* videoresume
* videototaltime
* videouniquetimeplay
