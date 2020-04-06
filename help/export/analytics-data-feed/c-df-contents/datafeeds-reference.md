---
description: Datos de tabla que describen las columnas de las fuentes de datos.
keywords: Data Feed;columns
subtopic: data feeds
title: Referencia de columnas de datos
topic: Reports and analytics
uuid: 9042a274-7124-4323-8cd6-5c84ab3eef6d
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Referencia de columnas de datos

Utilice esta página para conocer los datos contenidos en cada columna. La mayoría de las implementaciones no utilizan cada columna, por lo que se puede hacer referencia a esta página al determinar qué columnas incluir en una exportación de fuente de datos.

>[!IMPORTANT] Para cualquier columna determinada (por ejemplo, una que se defina como de 255 caracteres), una fuente de datos puede enviar caracteres adicionales debido a la adición de valores de escape de caracteres en una cadena. Tenga en cuenta estos caracteres adicionales potenciales si su implementación envía con regularidad valores que exceden los límites de caracteres.

## Columnas, descripciones y tipos de datos

>[!NOTE]La mayoría de las columnas contienen una columna similar con el prefijo `post_`. Las columnas de publicación muestran valores después de la lógica del lado del servidor, las reglas de procesamiento y las reglas de VISTA. Adobe recomienda usar columnas de publicación en la mayoría de los casos. Consulte [Preguntas frecuentes sobre fuentes de datos](../df-faq.md) para obtener más información.

| Nombre de columna | Descripción de columna | Tipo de datos |
| --- | --- | --- |
| `accept_language` | Lista todos los idiomas aceptados, como se indica en el encabezado Accept-Language HTTP de una solicitud de imagen. | char(20) |
| `aemassetid` | Variable multivalor que corresponde al ID de recurso (GUID) de un conjunto de recursos de Adobe Experience Manager. Aumenta Los Eventos De Impresión. | text |
| `aemassetsource` | Identifica el origen del evento de recursos. Se utiliza en Adobe Experience Manager. | varchar(255) |
| `aemclickedassetid` | ID de recurso de un recurso de Adobe Experience Manager. Aumenta los Eventos de clics. | varchar(255) |
| `browser` | ID numérico del explorador. Hace referencia a la tabla de búsqueda browser.tsv. | int sin firmar |
| `browser_height` | Altura en píxeles de la ventana del navegador. | smallint sin firmar |
| `browser_width` | Anchura en píxeles de la ventana del explorador. | smallint sin firmar |
| `c_color` | Profundidad de bits de la paleta de colores. Se utiliza como parte del cálculo de la dimensión Profundidad de color. Utiliza la función de JavaScript screen.colorDepth(). | char(20) |
| `campaign` | Variable utilizada en la dimensión Código de seguimiento. | varchar(255) |
| `carrier` | Variable de integración de Adobe Advertising Cloud. Especifica el operador de telefonía móvil. Hace referencia a la tabla de búsqueda de portadora. | varchar(100) |
| `channel` | Variable utilizada en la dimensión Secciones del sitio. | varchar(100) |
| `click_action` | Ya no se utiliza. Dirección del vínculo donde se hizo clic en la herramienta Clickmap heredada. | varchar(100) |
| `click_action_type` | Ya no se utiliza. Tipo de vínculo de la herramienta Clickmap heredada.<br>0: URL de HREF<br>1: ID personalizada<br>2: Evento onClick de JavaScript<br>3: Elemento de formulario | tinyint sin firmar |
| `click_context` | Ya no se utiliza. Nombre de la página donde se produjo el clic en el vínculo. Parte de la herramienta Clickmap heredada. | varchar(255) |
| `click_context_type` | Ya no se utiliza. Indica si click_context tenía un nombre de página o establecía de forma predeterminada la dirección URL de la página.<br>0: Dirección URL de la página<br>1: Nombre de la página | tinyint sin firmar |
| `click_sourceid` | Ya no se utiliza. ID numérico para la ubicación en la página del vínculo en el que se hizo clic. Parte de la herramienta Clickmap heredada. | int sin firmar |
| `click_tag` | Ya no se utiliza. Tipo de elemento HTML en el que se hizo clic. | char(10) |
| `clickmaplink` | Vínculo de mapa de Actividad | varchar(255) |
| `clickmaplinkbyregion` | Vínculo de Activity Map por región | varchar(255) |
| `clickmappage` | Página de Activity Map | varchar(255) |
| `clickmapregion` | Región de Activity Map | varchar(255) |
| `code_ver` | Versión de la biblioteca AppMeasurement utilizada para compilar y enviar la solicitud de imagen. | char(16) |
| `color` | ID de profundidad de color basado en el valor de la columna c_color. Hace referencia a la tabla de búsqueda color_depth.tsv. | smallint sin firmar |
| `connection_type` | ID numérico que representa el tipo de conexión. Variable utilizada en la dimensión Tipo de conexión. Hace referencia a la tabla de búsqueda connection_type.tsv. | tinyint sin firmar |
| `cookies` | Variable utilizada en la dimensión Compatibilidad con cookies.<br>S: Habilitado<br>N: No habilitado<br>D: Desconocido | char(1) |
| `country` | ID numérico que representa el país del que procede la visita. Adobe se asocia con Digital Envoy para hacer coincidir la dirección IP con el país. Utiliza la búsqueda country.tsv. | smallint sin firmar |
| `ct_connect_type` | Relacionado con la columna connection_type. Los valores más comunes son LAN/Wifi, Operador de telefonía móvil y Módem. | char(20) |
| `curr_factor` | Determina la posición decimal de la moneda y se utiliza para la conversión de moneda. Por ejemplo, USD utiliza dos decimales, por lo que el valor de esta columna sería 2. | tinyint |
| `curr_rate` | Tipo de cambio cuando se produjo la transacción. Adobe se asocia con XE para determinar el tipo de cambio del día actual. | decimal(24,12) |
| `currency` | El código de moneda que se utilizó durante la transacción. | char(8) |
| `cust_hit_time_gmt` | Solo los grupos de informes con marca de tiempo habilitada. La marca de tiempo enviada con la visita, según la hora Unix. | int |
| `cust_visid` | Si se establece un ID de visitante personalizado, se rellena en esta columna. | varchar(255) |
| `daily_visitor` | Marca para determinar si la visita es un nuevo visitante diario. | tinyint sin firmar |
| `date_time` | La hora de la visita en formato legible, según la zona horaria del grupo de informes. | datetime |
| `domain` | Variable utilizada en la dimensión Dominio. Basado en el proveedor de servicio de Internet del usuario (ISP). | varchar(100) |
| `duplicate_events` | Lista cada evento que se contó como duplicado. | varchar(255) |
| `duplicate_purchase` | Marca que indica que el evento de compra de esta visita se debe ignorar porque es un duplicado. | tinyint sin firmar |
| `duplicated_from` | Solo se utiliza en los grupos de informes que contienen reglas de copia de visitas VISTA. Indica de qué grupo de informes se copió la visita. | varchar(40) |
| `ef_id` | El ef_id utilizado en integraciones de Adobe Advertising Cloud. | varchar(255) |
| `evar1 - evar250` | Variables personalizadas 1-250. Cada organización utiliza eVars de manera diferente. El mejor lugar para obtener más información sobre cómo su organización rellena las eVars respectivas sería un documento de diseño de soluciones específico para su organización. | varchar(255) |
| `event_list` | lista separada por comas de ID numéricos que representan eventos activados en la visita. Incluye los eventos predeterminados y los eventos personalizados 1-1000. Utiliza la búsqueda de evento.tsv. | text |
| `exclude_hit` | El indicador que indica que la visita se excluye del sistema de informes. La columna visit_num no aumenta para las visitas excluidas.<br>1: No se usa. Parte de una función limpiada.<br>2: No se usa. Parte de una función limpiada.<br>3: Ya no se utiliza. Exclusión de agente de usuario<br>4: Exclusión basada en la dirección IP<br>5: Falta la información de visitas vitales, como page_url, pagename, page_event o event_list<br>6: JavaScript no procesó correctamente la visita<br>7: Exclusión específica de la cuenta, como en una regla VISTA<br>8: No utilizada. Exclusión alternativa específica de la cuenta.<br>9: No se usa. Parte de una función limpiada.<br>10: Código de moneda no válido<br>11: La visita individual no incluye una marca de tiempo en un grupo de informes solo de marca de tiempo o una visita que contiene una marca de tiempo en un grupo<br>de informes que no es de marca de hora 12: No se usa. Parte de una función limpiada.<br>13: No se usa. Parte de una función limpiada.<br>14: La visita de Target que no coincide con una visita de Analytics<br>15: No se utiliza actualmente.<br>16: Visita de Advertising Cloud que no coincide con una visita de Analytics | tinyint sin firmar |
| `first_hit_page_url` | La primera URL del visitante. | varchar(255) |
| `first_hit_pagename` | Variable utilizada en la dimensión Página de entrada original. El nombre de la página de entrada original del visitante. | varchar(100) |
| `first_hit_ref_domain` | Variable utilizada en la dimensión Dominio de referencia original. Basado en first_hit_remitente del reenvío. El primer dominio de referencia del visitante. | varchar(100) |
| `first_hit_ref_type` | ID numérico que representa el tipo de remitente del reenvío del primer remitente del reenvío del visitante. Utiliza la búsqueda remitente del reenvío_type.tsv. | tinyint sin firmar |
| `first_hit_referrer` | La primera URL de referencia del visitante. | varchar(255) |
| `first_hit_time_gmt` | Marca de hora de la primera visita individual del visitante en tiempo Unix. | int |
| `geo_city` | Nombre de la ciudad de la que proviene la visita, según la IP. Adobe se asocia con Digital Envoy para hacer coincidir la dirección IP con la ciudad. | char(32) |
| `geo_country` | Abreviación del país del que procede la visita, basada en la IP. Adobe se asocia con Digital Envoy para hacer coincidir la dirección IP con el país. | char(4) |
| `geo_dma` | ID numérico del área demográfica de la que procede la visita, según la IP. Adobe se asocia con Digital Envoy para comparar la dirección IP con el área demográfica. | int sin firmar |
| `geo_region` | Nombre del estado o región de donde proviene la visita, según la IP. Adobe se asocia con Digital Envoy para hacer coincidir la dirección IP con el estado o la región. | char(32) |
| `geo_zip` | El código postal del que provino la visita basado en la dirección IP. Adobe se asocia con Digital Envoy para que coincida la dirección IP con el código postal. | varchar(16) |
| `hier1 - hier5` | Utilizado por variables de jerarquía. Contiene una lista delimitada de valores. El delimitador se elige en la configuración del grupo de informes. | varchar(255) |
| `hit_source` | Indica la fuente de la que provino la visita. <br>1: Solicitud de imagen estándar sin marca de tiempo <br>2: Solicitud de imagen estándar con marca de tiempo <br>3: Carga del origen de datos activo con marcas de tiempo<br>4: No utilizado <br>5: Carga genérica del origen de datos <br>6: Carga completa del origen de datos de procesamiento <br>7: Carga del origen de datos TransactionID <br>8: Ya no se utiliza; Versiones anteriores de los orígenes de datos de Adobe Advertising Cloud <br>9: Ya no se utiliza; Métricas de resumen de Adobe Social | tinyint sin firmar |
| `hit_time_gmt` | La marca de tiempo de los servidores de recopilación de datos de visitas de Adobe que recibieron la visita, basada en la hora Unix. | int |
| `hitid_high` | Se utiliza en combinación con hitid_low para identificar de forma exclusiva una visita. | bigint sin firmar |
| `hitid_low` | Se utiliza en combinación con hitid_high para identificar de forma exclusiva una visita. | bigint sin firmar |
| `homepage` | Ya no se utiliza. Se indica si la dirección URL actual es la página principal del explorador. | char(1) |
| `hourly_visitor` | Indicador para determinar si la visita es un nuevo visitante por hora. | tinyint sin firmar |
| `ip` | Dirección IP, basada en el encabezado HTTP de la solicitud de imagen. | char(20) |
| `ip2` | No se usa. Variable de referencia back-end para los grupos de informes que contienen reglas de VISTA basadas en la dirección IP. | char(20) |
| `j_jscript` | Versión de JavaScript admitida por el explorador. | char(5) |
| `java_enabled` | Indicador que señala si Java está habilitado. <br>S: Habilitado <br>N: No habilitado<br>D: Desconocido | char(1) |
| `javascript` | ID de búsqueda de la versión de JavaScript, basado en j_jscript. Utiliza la tabla de búsqueda. | tinyint sin firmar |
| `language` | ID numérica del idioma. Utiliza la tabla de búsqueda languages.tsv. | smallint sin firmar |
| `last_hit_time_gmt` | Marca de hora (en tiempo Unix) de la visita anterior. Se utiliza para calcular la dimensión Días desde la última visita. | int |
| `last_purchase_num` | Variable utilizada en la dimensión Lealtad del cliente. Indica la cantidad de compras anteriores que realizó el visitante. <br>0: Sin compras previas (no es un cliente) <br>1: Una compra anterior (nuevo cliente) <br>2: Dos compras anteriores (cliente de devolución) <br>3: Tres o más compras anteriores (cliente fiel) | int sin firmar |
| `last_purchase_time_gmt` | Se utiliza en la dimensión Días desde la última compra. Marca de hora (en tiempo Unix) de la última compra realizada. Para compras y visitantes que no hayan realizado una compra antes, este valor es 0. | int |
| `latlon1` | Ubicación (menos de 10 km) | varchar(255) |
| `latlon23` | Ubicación (menos de 100 m) | varchar(255) |
| `latlon45` | Ubicación (menos de 1 m) | varchar(255) |
| `mc_audiences` | Lista de los ID de segmentos del Administrador de Audiencias a los que pertenece el visitante. | text |
| `mcvisid` | ID de visitante de Experience Cloud. Número de 128 bits formado por dos números de 64 bits concatenados con un margen de 19 dígitos. | varchar(255) |
| `mobile_id` | Si el usuario utiliza un dispositivo móvil, es el ID numérico del dispositivo. | int |
| `mobileaction` | Acción móvil. Se recopila automáticamente cuando se llama a trackAction en Mobile Services. Permite establecer automáticamente las rutas de acción en la aplicación. | varchar(100) |
| `mobileappid` | ID de aplicación móvil. Stores the application name and version in the following format:[AppName] [BundleVersion] | varchar(255) |
| `mobileappperformanceappid` | Se utiliza en el conector de datos Apteligent. El ID de la aplicación utilizado en Apteligent. | varchar(255) |
| `mobileappperformancecrashid` | Se utiliza en el conector de datos Apteligent. ID de bloqueo utilizado en Apteligent. | varchar(255) |
| `mobileappstoreobjectid` | Se utiliza en el conector de datos Appfigures. ID de objeto de App Store | varchar(255) |
| `mobilebeaconmajor` | Señalización principal de Mobile Services | varchar(100) |
| `mobilebeaconminor` | Señalización menor de Mobile Services | varchar(100) |
| `mobilebeaconproximity` | Proximidad de la señalización de Mobile Services | varchar(255) |
| `mobilebeaconuuid` | UUID de señalización de Mobile Services | varchar(100) |
| `mobilecampaigncontent` | Nombre o ID del contenido que muestra el vínculo. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| `mobilecampaignmedium` | Medio de marketing, como banner o correo electrónico. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| `mobilecampaignname` | Nombre de la campaña, también almacenada en la variable de campaña. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| `mobilecampaignsource` | remitente del reenvío original, como newsletter o red de medios sociales. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| `mobilecampaignterm` | Palabras clave pagas u otros términos que desee rastrear con esta adquisición. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| `mobiledayofweek` | Número del día laborable en el que se inició la aplicación. | varchar(255) |
| `mobiledayssincefirstuse` | Número de días transcurridos desde que se ejecutó la aplicación por primera vez. | varchar(255) |
| `mobiledayssincelastupgrade` | Recopilado desde la variable de datos de contexto a.DaysSinceLastUpgrade. Número de días que han transcurrido desde la sesión anterior. | varchar(255) |
| `mobiledayssincelastuse` | Número de días transcurridos desde la última ejecución de la aplicación. | varchar(255) |
| `mobiledeeplinkid` | Recopilado desde la variable de datos de contexto a.<span>deeplink</span>.id. Se utiliza en los informes de adquisición como identificador para el vínculo de adquisición móvil. | varchar(255) |
| `mobiledevice` | Nombre del dispositivo móvil. En iOS, se almacena como una cadena de dos dígitos separada por comas. El primer número representa la generación del dispositivo y el segundo número representa la familia del dispositivo. | varchar(255) |
| `mobilehourofday` | Define la hora del día en que se inició la aplicación. Sigue el formato numérico de 24 horas. | varchar(255) |
| `mobileinstalldate` | Fecha de instalación del dispositivo móvil. Proporciona la fecha de la primera vez que un usuario abre la aplicación móvil. | varchar(255) |
| `mobilelaunchessincelastupgrade` | Recopilado desde la variable de datos de contexto a.LaunchesSinceUpgrade. Informa del número de inicios desde la última actualización. | varchar(255) |
| `mobilelaunchnumber` | Se incrementa en uno cada vez que se inicia la aplicación móvil. | varchar(255) |
| `mobileltv` | Ya no se utiliza. Rellenado con métodos trackLifetimeValue. | varchar(255) |
| `mobilemessagebuttonname` | Recopilado desde la variable de datos de contexto a.<span>message</span>.button.id. Se utiliza para la mensajería integrada en la aplicación con el objetivo de identificar el botón que cerró el mensaje. | varchar(100) |
| `mobilemessageid` | ID de mensaje en la aplicación | varchar(255) |
| `mobilemessageonline` | Mensaje en línea en la aplicación | varchar(255) |
| `mobilemessagepushoptin` | Recopilado desde la variable de datos de contexto a.push.optin. Se establece en “true” cuando el usuario opta por la mensajería emergente; de lo contrario, el valor es “false”. | varchar(255) |
| `mobilemessagepushpayloadid` | Recopilado desde la variable de datos de contexto a.push.payloadid. Se utiliza en los mensajes emergentes como identificador de carga útil. | varchar(255) |
| `mobileosenvironment` | Recopilado desde la variable de datos de contexto a.OSEnvironment. Estados del entorno del sistema operativo, como Android o iOS. | varchar(255) |
| `mobileosversion` | Versión del sistema operativo de Mobile Services | varchar(255) |
| `mobileplaceaccuracy` | Recopilado desde la variable de datos de contexto a.loc.acc. Indica la precisión del GPS en metros en el momento de la recogida. | varchar(255) |
| `mobileplacecategory` | Recopilado desde la variable de datos de contexto a.loc.category. Describe la categoría de un lugar específico. | varchar(255) |
| `mobileplaceid` | Recopilado desde la variable de datos de contexto a.<span>loc</span>.id. Identificador de un punto de interés determinado. | varchar(255) |
| `mobilerelaunchcampaigncontent` | Contenido de inicio de Mobile Services | varchar(255) |
| `mobilerelaunchcampaignmedium` | Medio de inicio de Mobile Services | varchar(255) |
| `mobilerelaunchcampaignsource` | Origen del inicio de Mobile Services | varchar(255) |
| `mobilerelaunchcampaignterm` | Término de inicio de Mobile Services | varchar(255) |
| `mobilerelaunchcampaigntrackingcode` | Recopilado desde la variable de datos de contexto a.launch.campaign.trackingcode. Se utiliza en la adquisición como código de seguimiento para la campaña de inicio. | varchar(255) |
| `mobileresolution` | Resolución del dispositivo móvil. Anchura x altura en píxeles. | varchar(255) |
| `monthly_visitor` | Marca que indica que el visitante es único para el mes actual. | tinyint sin firmar |
| `mvvar1` - `mvvar3` | Valores de variables de Lista. Contiene una lista delimitada de valores personalizados según la implementación. | text |
| `namespace` | No se usa. Parte de una característica eliminada hace muchos años. | varchar(50) |
| `new_visit` | Marca que determina si la visita actual es una nueva visita. Lo establecen los servidores de Adobe tras 30 minutos de inactividad de la visita. | tinyint sin firmar |
| `os` | ID numérico que representa el sistema operativo del visitante. Basado en la columna user_agent. Utiliza la búsqueda de resultados. | int sin firmar |
| `p_plugins` | Ya no se utiliza. Lista de complementos disponibles para el explorador. Se utiliza la función de JavaScript navigator.plugins(). | text |
| `page_event` | El tipo de visita que se envía en la solicitud de imagen (visita estándar, vínculo de descarga, vínculo personalizado, vínculo de salida). Consulte [Búsqueda de evento de página](datafeeds-page-event.md). | tinyint sin firmar |
| `page_event_var1` | Solo se usa en solicitudes de imagen de seguimiento de vínculos. Se hizo clic en la dirección URL del vínculo de descarga, de salida o personalizado. | text |
| `page_event_var2` | Solo se usa en solicitudes de imagen de seguimiento de vínculos. Nombre personalizado (si se especifica) del vínculo. | varchar(100) |
| `page_event_var3` | Ya no se utiliza. Contiene datos de Encuesta y módulo multimedia. Se han rellenado informes de vídeo heredados en versiones anteriores de Adobe Analytics. | text |
| `page_type` | Se utiliza para rellenar la dimensión Páginas no encontradas, utilizada exclusivamente para 404 páginas. Esta variable debe estar vacía o contener &quot;ErrorPage&quot;. | char(20) |
| `page_url` | Dirección URL de la visita. No se utiliza en solicitudes de imagen de seguimiento de vínculos. | varchar(255) |
| `pagename` | Se utiliza para rellenar la dimensión Páginas. Si la variable pagename está vacía, Analytics utiliza page_url en su lugar. | varchar(100) |
| `paid_search` | Marca que se establece si la visita coincide con la detección de búsqueda paga. | tinyint sin firmar |
| `partner_plugins` | No se usa. Parte de una característica eliminada hace muchos años. | varchar(255) |
| `persistent_cookie` | Utilizado por la dimensión Compatibilidad con cookies persistentes. Indica si el visitante admite cookies que no se descartan después de cada visita. | char(1) |
| `plugins` | Ya no se utiliza. Lista de ID numéricos que corresponden a complementos disponibles en el explorador. Utiliza la búsqueda de plugins.tsv. | varchar(180) |
| `pointofinterest` | Nombre del punto de interés de Mobile Services | varchar(255) |
| `pointofinterestdistance` | Distancia de Mobile Services al centro de puntos de interés | varchar(255) |
| `post_ columns` | Contiene el valor utilizado en última instancia en los informes. Cada columna posterior se rellena después de la lógica del lado del servidor, las reglas de procesamiento y las reglas de VISTA. Adobe recomienda usar columnas de publicación en la mayoría de los casos. | Consulte la columna correspondiente no posterior |
| `prev_page` | No se usa. Identificador de la página anterior registrada de Adobe. | int sin firmar |
| `product_list` | La lista del producto se pasa a través de la variable products. Los productos están delimitados por comas, mientras que las propiedades de producto individuales están delimitadas por punto y coma. | text |
| `product_merchandising` | No se usa. Utilice product_lista en su lugar. | text |
| `prop1` - `prop75` | Variables de tráfico personalizadas 1-75. | varchar(100) |
| `purchaseid` | Identificador único de una compra, tal como se establece mediante la variable s_purchaseID. Utilizado por la columna duplicado_purchase. | char(20) |
| `quarterly_visitor` | Marca para determinar si la visita es un nuevo visitante trimestral. | tinyint sin firmar |
| `ref_domain` | Basado en la columna remitente del reenvío. Dominio de referencia de la visita. | varchar(100) |
| `ref_type` | Un ID numérico que representa el tipo de referencia de la visita.<br>1: Dentro del sitio<br>2: Otros sitios web <br>3: Motores de búsqueda <br>4: Disco duro <br>5: USENET <br>6: Escritos o marcadores (sin referente) <br>7: Correo electrónico <br>8: Sin JavaScript <br>9: Redes sociales | tinyint sin firmar |
| `referrer` | Dirección URL de la página anterior. Tenga en cuenta que mientras `referrer` utiliza un tipo de datos de varchar(255), `post_referrer` utiliza un tipo de datos de varchar(244). | varchar(255) |
| `resolution` | ID numérico que representa la resolución del monitor. Rellena la dimensión Resolución del monitor. Utiliza la tabla de búsqueda resolution.tsv. | smallint sin firmar |
| `s_kwcid` | ID de palabra clave utilizado en las integraciones de Adobe Advertising Cloud. | varchar(255) |
| `s_resolution` | Valor de resolución de pantalla sin procesar. Se reúne mediante la función de JavaScript screen.width x screen.height. | char(20) |
| `sampled_hit` | Ya no se utiliza. Anteriormente se usaba para el muestreo en Análisis ad hoc. | char(1) |
| `search_engine` | ID numérica que representa el motor de búsqueda que dirigió el visitante a su sitio. Utiliza la búsqueda search_engine.tsv. | smallint sin firmar |
| `search_page_num` | Utilizado por la dimensión Clasificación de todas las páginas de búsqueda. Indica en qué página de resultados de búsqueda apareció el sitio antes de que el usuario hiciera clic en el sitio. | smallint sin firmar |
| `secondary_hit` | Marca que rastrea visitas secundarias. Normalmente se origina a partir del etiquetado de grupos múltiples y las reglas de VISTA que copian las visitas. | tinyint sin firmar |
| `service` | No se usa. Utilice page_evento en su lugar. | char(2) |
| `socialaccountandappids` | Ya no se utiliza. Cuenta social e ID de aplicación | varchar(255) |
| `socialassettrackingcode` | Ya no se utiliza. Variable de campaña social | varchar(255) |
| `socialauthor` | Ya no se utiliza. Variable Autores sociales | varchar(255) |
| `socialcontentprovider` | Ya no se utiliza. Plataformas sociales/Propiedades | varchar(255) |
| `socialinteractiontype` | Ya no se utiliza. Tipo de interacción social | varchar(255) |
| `sociallanguage` | Ya no se utiliza. Idioma social | varchar(255) |
| `sociallatlong` | Ya no se utiliza. Latitud social/Longitud | varchar(255) |
| `socialowneddefinitioninsighttype` | Ya no se utiliza. Tipo de perspectiva de definición con propiedad social | varchar(255) |
| `socialowneddefinitioninsightvalue` | Ya no se utiliza. Valor de perspectiva de definición propiedad de Social | varchar(255) |
| `socialowneddefinitionmetric` | Ya no se utiliza. Métrica de definición de propiedad social | varchar(255) |
| `socialowneddefinitionpropertyvspost` | Ya no se utiliza. Propiedad de definición de propiedad social vs. publicación | varchar(255) |
| `socialownedpostids` | Ya no se utiliza. ID de anuncio de propiedad social | varchar(255) |
| `socialownedpropertyid` | Ya no se utiliza. ID de propiedad social | varchar(255) |
| `socialownedpropertyname` | Ya no se utiliza. Nombre de propiedad social | varchar(255) |
| `socialownedpropertypropertyvsapp` | Ya no se utiliza. Propiedad social vs. aplicación | varchar(255) |
| `state` | Variable de estado. | varchar(50) |
| `stats_server` | No es de uso. Servidor interno de Adobe que ha procesado la visita. | char(30) |
| `t_time_info` | Hora local del visitante. El formato es el siguiente: M/D/AAAA HH:MM:SS Mes (0-11, 0=enero) Desplazamiento de zona horaria (en minutos) | varchar(100) |
| `tnt` | Se utiliza en integraciones de Adobe Destinatario. | text |
| `tnt_action` | Se utiliza en integraciones de Adobe Destinatario. | text |
| `tnt_post_vista` | Ya no se utiliza. Utilice post_tnt en su lugar. | text |
| `transactionid` | Un identificador único en el que se pueden cargar varios puntos de datos más adelante mediante fuentes de datos. | text |
| `truncated_hit` | Un indicador que indica que se truncó la solicitud de imagen. Indica que se ha recibido una visita parcial. <br>S: Se truncó la visita; visita parcial recibida <br>N: La visita no se truncó; visita completa recibida | char(1) |
| `ua_color` | Ya no se utiliza. Anteriormente se utilizaba como alternativa para la profundidad de color. | char(20) |
| `ua_os` | Ya no se utiliza. Anteriormente se utilizaba como alternativa para el sistema operativo. | char(80) |
| `ua_pixels` | Ya no se utiliza. Anteriormente se utilizaba como alternativa para la altura y la anchura del explorador. | char(20) |
| `user_agent` | Cadena del agente de usuario enviada en el encabezado HTTP de la solicitud de imagen. | text |
| `user_hash` | No es de uso. Hash en la ID del grupo de informes. Utilice el nombre de usuario en su lugar. | int sin firmar |
| `user_server` | Variable utilizada en la dimensión Servidor. | varchar(100) |
| `userid` | No es de uso. ID numérico para la ID del grupo de informes. Utilice el nombre de usuario en su lugar. | int sin firmar |
| `username` | ID del grupo de informes para la visita. | char(40) |
| `va_closer_detail` | Variable utilizada en la dimensión Detalles de último toque. | varchar(255) |
| `va_closer_id` | ID numérico que identifica la dimensión de Canal de último toque. La búsqueda de este ID se encuentra en el Administrador de Canales de marketing. | tinyint sin firmar |
| `va_finder_detail` | Variable utilizada en la dimensión Detalles de primer toque. | varchar(255) |
| `va_finder_id` | ID numérico que identifica la dimensión de Canal de primer toque. La búsqueda de este ID se encuentra en el Administrador de Canales de marketing. | tinyint sin firmar |
| `va_instance_event` | Marca para identificar instancias de Marketing Canal. Utilizado por la métrica Instancias de último toque de Marketing Canal. | tinyint sin firmar |
| `va_new_engagement` | Marca para identificar nuevos compromisos de Marketing Canal. Utilizado por la métrica Nuevos compromisos. | tinyint sin firmar |
| `video` | Contenido del vídeo | varchar(255) |
| `videoad` | Nombre del anuncio de vídeo | varchar(255) |
| `videoadinpod` | Anuncio de vídeo en posición del pod | varchar(255) |
| `videoadlength` | Duración del anuncio de vídeo | varchar(255) |
| `videoadload` | Cargas del anuncio de vídeo | varchar(255) |
| `videoadname` | Nombre del anuncio de vídeo | varchar(255) |
| `videoadplayername` | Nombre del reproductor del anuncio de vídeo | varchar(255) |
| `videoadpod` | Pod del anuncio de vídeo | varchar(255) |
| `videoadvertiser` | Anunciante del vídeo | varchar(255) |
| `videoaudioalbum` | Álbum del audio del vídeo | varchar(255) |
| `videoaudioartist` | Artista del audio del vídeo | varchar(255) |
| `videoaudioauthor` | Autor del audio del vídeo | varchar(255) |
| `videoaudiolabel` | Etiqueta del audio del vídeo | varchar(255) |
| `videoaudiopublisher` | Editor del audio del vídeo | varchar(255) |
| `videoaudiostation` | Estación del audio del vídeo | varchar(255) |
| `videocampaign` | Campaña del vídeo | varchar(255) |
| `videochannel` | Canal de vídeo | varchar(255) |
| `videochapter` | Nombre del capítulo del vídeo | varchar(255) |
| `videocontenttype` | Tipo de contenido de vídeo. Se establece automáticamente como “Vídeo” para todas las vistas de vídeo | varchar(255) |
| `videodaypart` | Parte del día del vídeo | varchar(255) |
| `videoepisode` | Episodio del vídeo | varchar(255) |
| `videofeedtype` | Tipo de fuente de vídeo | varchar(255) |
| `videogenre` | Género del vídeo | text |
| `videolength` | Duración del vídeo | varchar(255) |
| `videomvpd` | MVPD del vídeo | varchar(255) |
| `videoname` | Nombre del vídeo | varchar(255) |
| `videonetwork` | Red del vídeo | varchar(255) |
| `videopath` | Ruta de vídeo | varchar(100) |
| `videoplayername` | Nombre del reproductor de vídeo | varchar(255) |
| `videoqoebitrateaverageevar` | Velocidad media de bits de calidad del vídeo | varchar(255) |
| `videoqoebitratechangecountevar` | Recuento de cambios en la calidad del vídeo | varchar(255) |
| `videoqoebuffercountevar` | Recuento de búfer de calidad de vídeo | varchar(255) |
| `videoqoebuffertimeevar` | Hora de búfer de la calidad de vídeo | varchar(255) |
| `videoqoedroppedframecountevar` | Cantidad de fotogramas perdidos de calidad de vídeo | varchar(255) |
| `videoqoeerrorcountevar` | Recuento de errores de calidad del vídeo | varchar(255) |
| `videoqoeextneralerrors` | Errores externos de la calidad del vídeo | text |
| `videoqoeplayersdkerrors` | Errores del SDK de calidad del vídeo | text |
| `videoqoetimetostartevar` | Tiempo de inicio de la calidad del vídeo | varchar(255) |
| `videoseason` | Temporada del vídeo | varchar(255) |
| `videosegment` | Segmento de vídeo | varchar(255) |
| `videoshow` | Programa del vídeo | varchar(255) |
| `videoshowtype` | Tipo de programa del vídeo | varchar(255) |
| `videostreamtype` | Tipo de flujo de vídeo | varchar(255) |
| `visid_high` | Se utiliza en combinación con visid_low para identificar una visita de forma única. | bigint sin firmar |
| `visid_low` | Se utiliza en combinación con visid_high para identificar de forma exclusiva una visita. | bigint sin firmar |
| `visid_new` | Marca para identificar si la visita contiene un ID de visitante recién generado. | char(1) |
| `visid_timestamp` | Si el ID de visitante se ha generado recientemente, proporciona la marca de tiempo (en tiempo Unix) del momento en que se generó el ID de visitante. | int |
| `visid_type` | ID numérica que representa qué método se ha utilizado para identificar al visitante. <br>0: VisitorID personalizado <br>1: IP y reserva del agente de usuario <br>2: Encabezado de suscriptor móvil HTTP <br>3: Valor de la cookie heredada (s_vi) <br>4: Valor de cookie de reserva (s_fid) <br>5: Servicio de identidad | tinyint sin firmar |
| `visit_keywords` | Variable utilizada en la dimensión Palabra clave de búsqueda. Esta columna utiliza un límite de caracteres no estándar para dar cabida a la lógica back-end utilizada por Adobe. | varchar(244) |
| `visit_num` | Variable utilizada en la dimensión Número de visita. Inicio en 1 y aumenta cada vez que una nueva visita inicio por visitante. | int sin firmar |
| `visit_page_num` | Variable utilizada en la dimensión Profundidad de acierto. Aumenta en 1 por cada visita que genera el usuario. Restablece cada visita. | int sin firmar |
| `visit_ref_domain` | Basado en la columna visit_remitente del reenvío. El primer dominio de referencia de la visita. | varchar(100) |
| `visit_ref_type` | ID numérico que representa el tipo de remitente del reenvío del primer remitente del reenvío de la visita. Utiliza la tabla de búsqueda remitente del reenvío_type.tsv. | tinyint sin firmar |
| `visit_referrer` | El primer remitente del reenvío de la visita. | varchar(255) |
| `visit_search_engine` | ID numérica del primer motor de búsqueda de la visita. Utiliza la tabla de búsqueda search_engine.tsv. | smallint sin firmar |
| `visit_start_page_url` | La primera dirección URL de la visita. | varchar(255) |
| `visit_start_pagename` | Nombre de la primera página de la visita. | varchar(100) |
| `visit_start_time_gmt` | Marca de hora (en tiempo Unix) de la primera visita individual de la visita. | int |
| `weekly_visitor` | Marca para determinar si la visita es un nuevo visitante semanal. | tinyint sin firmar |
| `yearly_visitor` | Indicador para determinar si la visita es un nuevo visitante anual. | tinyint sin firmar |
| `zip` | Se utiliza para rellenar la dimensión Código postal. | varchar(50) |

## Columnas vacías

La siguiente lista de columnas no se utiliza y no contiene datos:

* mobileacquisitionclicks
* mobileactioninapptime
* mobileactiontotaltime
* mobileappperformanceaffectedusers
* mobileappperformanceappid<span>.</span>app-perf-app-name
* mobileappperformanceappid<span>.</span>app-perf-platform
* mobileappperformancecrashes
* mobileappperformancecrashid<span>.</span>app-perf-crash-name
* mobileappperformanceloads
* mobileappstoreavgrating
* mobileappstoredownloads
* mobileappstoreinapprevenue
* mobileappstoreinapproyalties
* mobileappstoreobjectid<span>.</span>app-store-user
* mobileappstoreobjectid<span>.</span>application-name
* mobileappstoreobjectid<span>.</span>application-version
* mobileappstoreobjectid<span>.</span>appstore-name
* mobileappstoreobjectid<span>.</span>category-name
* mobileappstoreobjectid<span>.</span>country-name
* mobileappstoreobjectid<span>.</span>device-manufacturer
* mobileappstoreobjectid<span>.</span>device-name
* mobileappstoreobjectid<span>.</span>in-app-name
* mobileappstoreobjectid<span>.</span>platform-name-version
* mobileappstoreobjectid<span>.</span>rank-category-type
* mobileappstoreobjectid<span>.</span>region-name
* mobileappstoreobjectid<span>.</span>review-comment
* mobileappstoreobjectid<span>.</span>review-title
* mobileappstoreoneoffrevenue
* mobileappstoreoneoffroyalties
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
* mobilerelaunchcampaigntrackingcode<span><span>.</span></span>name
* mobileupgrades
* socialaveragesentiment
* socialaveragesentiment (en desuso)
* socialfbstories
* socialfbstorytellers
* socialinteractioncount
* sociallikeadds
* sociallink
* sociallink (en desuso)
* socialmentions
* socialpageviews
* socialpostviews
* socialproperty
* socialproperty (en desuso)
* socialpubcomments
* socialpubposts
* socialpubrecommends
* socialpubsubscribers
* socialterm
* socialtermslist
* socialtermslist (en desuso)
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
* videouniquetimeplayed
