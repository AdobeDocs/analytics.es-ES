---
description: Datos de tabla que describen las columnas de las fuentes de datos.
keywords: Fuentes de datos, columnas
subtopic: data feeds
title: Referencia de columnas de datos
feature: Conceptos básicos de Reports & Analytics
uuid: 9042a274-7124-4323-8cd6-5c84ab3eef6d
exl-id: e1492147-6e7f-4921-b509-898e7efda596
source-git-commit: cddf2a76ca36914f133379959b7cbb5246bdd695
workflow-type: tm+mt
source-wordcount: '3405'
ht-degree: 99%

---

# Referencia de columnas de datos

Utilice esta página para conocer los datos contenidos en cada columna. La mayoría de las implementaciones no utilizan cada columna, por lo que se puede hacer referencia a esta página al determinar qué columnas incluir en una exportación de fuente de datos.

>[!IMPORTANT]
>
>Para cualquier columna determinada (por ejemplo, una que se defina como de 255 caracteres), una fuente de datos puede enviar caracteres adicionales debido a la adición de valores de escape de caracteres en una cadena. Tenga en cuenta estos caracteres adicionales potenciales si su implementación envía con regularidad valores que exceden los límites de caracteres.

## Columnas, descripciones y tipos de datos

>[!NOTE]
>
>La mayoría de las columnas contienen una columna similar con el prefijo `post_`. Las columnas de publicación muestran valores después de la lógica del lado del servidor, las reglas de procesamiento y las reglas de VISTA. Adobe recomienda usar columnas de publicación en la mayoría de los casos. Consulte [Preguntas frecuentes sobre fuentes de datos](../df-faq.md) para obtener más información.

| Nombre de la columna | Descripción de la columna | Tipo de datos |
| --- | --- | --- |
| `accept_language` | Enumera todos los idiomas aceptados, tal como se indica en la cabecera Accept-Language-HTTP de las solicitudes de imagen. | char(20) |
| `aemassetid` | Una variable de valores múltiples que corresponde a las ID de recursos (GUID) de un conjunto de recursos de Adobe Experience Manager. Incrementa los eventos de impresión. | text |
| `aemassetsource` | Identifica la fuente del evento de recursos. Se utiliza en Adobe Experience Manager. | varchar(255) |
| `aemclickedassetid` | ID de recurso de un recurso de Adobe Experience Manager. Incrementa los eventos de clic. | varchar(255) |
| `browser` | ID numérica del explorador. Se remite a la tabla de búsqueda `browser.tsv`. | int sin firmar |
| `browser_height` | Altura de la ventana del explorador en píxeles. | smallint sin firmar |
| `browser_width` | Anchura de la ventana del explorador en píxeles. | smallint sin firmar |
| `c_color` | Profundidad de bits de la paleta de colores. Se utiliza en el cálculo de la dimensión [Profundidad de color](/help/components/dimensions/color-depth.md). AppMeasurement utiliza la función JavaScript `screen.colorDepth()`. | char(20) |
| `campaign` | Variable utilizada en la dimensión [Código de seguimiento](/help/components/dimensions/tracking-code.md). | varchar(255) |
| `carrier` | Variable de integración de Adobe Advertising Cloud. Especifica el operador de telefonía móvil. Se remite a la tabla de búsqueda `carrier`. | varchar(100) |
| `channel` | Variable utilizada en la dimensión [Secciones del sitio](/help/components/dimensions/site-section.md). | varchar(100) |
| `click_action` | Ya no se utiliza. Dirección de vínculos en los que se ha hecho clic en la herramienta heredada Clickmap. | varchar(100) |
| `click_action_type` | Ya no se utiliza. Tipo de vínculo de la herramienta heredada Clickmap.<br>0: URL de HREF<br>1: ID personalizada<br>2: Evento onClick de JavaScript<br>3: Elemento de formulario | tinyint sin firmar |
| `click_context` | Ya no se utiliza. Nombre de la página en la que se ha hecho clic en vínculo. Forma parte de la herramienta heredada Clickmap. | varchar(255) |
| `click_context_type` | Ya no se utiliza. Indica si click_context tenía un nombre de página o si estaba vinculado a la URL de la página de forma predeterminada.<br>0: Dirección URL de la página<br>1: Nombre de la página | tinyint sin firmar |
| `click_sourceid` | Ya no se utiliza. ID numérica para la ubicación dentro de la página del enlace en el que se ha hecho clic. Forma parte de la herramienta heredada Clickmap. | int sin firmar |
| `click_tag` | Ya no se utiliza. Tipo de elemento HTML en el que se ha hecho clic. | char(10) |
| `clickmaplink` | Vínculo de Activity Map | varchar(255) |
| `clickmaplinkbyregion` | Vínculo de Activity Map por región | varchar(255) |
| `clickmappage` | Página de Activity Map | varchar(255) |
| `clickmapregion` | Región de Activity Map | varchar(255) |
| `code_ver` | Versión de la biblioteca de AppMeasurement que se ha utilizado para compilar y enviar la solicitud de imagen. | char(16) |
| `color` | ID de profundidad de color basada en el valor de la columna `c_color`. Se remite a la tabla de búsqueda `color_depth.tsv`. | smallint sin firmar |
| `connection_type` | ID numérica que representa el tipo de conexión. Variable utilizada en la dimensión [Tipo de conexión](/help/components/dimensions/connection-type.md). Se remite a la tabla de búsqueda `connection_type.tsv`. | tinyint sin firmar |
| `cookies` | Variable utilizada en la dimensión [Compatibilidad con cookies](/help/components/dimensions/cookie-support.md).<br>S: Habilitado<br>N: No habilitado<br>D: Desconocido | char(1) |
| `country` | ID numérica que representa el país desde el que provino el clic. Se utiliza en la dimensión [Países](/help/components/dimensions/countries.md). Utiliza la búsqueda `country.tsv`. | smallint sin firmar |
| `ct_connect_type` | En relación con la columna `connection_type`. Los valores más comunes son LAN/Wi-Fi, Operador de telefonía móvil y Módem. | char(20) |
| `curr_factor` | Determina el lugar decimal de la moneda y se utiliza para la conversión de monedas. Por ejemplo, USD utiliza dos lugares decimales, por lo que el valor de esta columna debe ser 2. | tinyint |
| `curr_rate` | El tipo de cambio vigente cuando se produjo la transacción. Adobe se asocia con XE para determinar el tipo de cambio del día. | decimal(24,12) |
| `currency` | El código de moneda que se ha utilizado durante la transición. | char(8) |
| `cust_hit_time_gmt` | Solo grupos de informes con marca de tiempo. La marca de tiempo enviada con la visita y basada en el Tiempo Unix. | int |
| `cust_visid` | Si se estableció una ID de visitante personalizada, aparece completada en esta columna. | varchar(255) |
| `daily_visitor` | Indicador que determina si la visita es un visitante nuevo diario. | tinyint sin firmar |
| `date_time` | La hora de la visita en un formato legible, basada en la zona horaria del grupo de informes. | datetime |
| `domain` | Variable utilizada en la dimensión [Dominio](/help/components/dimensions/domain.md). Basado en el punto de acceso a Internet del visitante. | varchar(100) |
| `duplicate_events` | Muestra cada evento que se contó como duplicado. | varchar(255) |
| `duplicate_purchase` | Indicador que señala que el evento de compra de esta visita se debe ignorar porque es un duplicado. | tinyint sin firmar |
| `duplicated_from` | Solo se utiliza en los grupos de informes que contienen las reglas de VISTA de copia de visita. Indica de qué grupo de informes se copió la visita. | varchar(40) |
| `ef_id` | `ef_id` que se usa en las integraciones de Adobe Advertising Cloud. | varchar(255) |
| `evar1 - evar250` | Variables personalizadas 1-250. Se utiliza en dimensiones [eVar](/help/components/dimensions/evar.md). Cada organización utiliza las eVars de forma diferente. El mejor lugar para obtener más información sobre cómo su organización completa las eVars respectivos sería un documento de diseño de soluciones que sea específico de su organización. | varchar(255) |
| `event_list` | Una lista separada con comas de las ID numéricas que representa los eventos activados en la visita. Incluye los eventos predeterminados y los eventos personalizados 1-1000. Utiliza la búsqueda `event.tsv`. | text |
| `exclude_hit` | Un indicador que señala que la visita no está incluida en la creación de informes. La columna `visit_num` no aumenta con las visitas excluidas.<br>1: No se usa. Parte de una función limpiada.<br>2: No se usa. Parte de una función limpiada.<br>3: Ya no se utiliza. Exclusión de agente de usuario<br>4: Exclusión basada en la dirección IP<br>5: Falta información clave de visitas, como `page_url`, `pagename`, `page_event` o `event_list`<br>6: JavaScript no ha procesado la visita correctamente<br>7: Exclusión específica de la cuenta, como en reglas VISTA<br>8: Sin usar. Exclusión alternativa específica de la cuenta.<br>9: No se usa. Parte de una función limpiada.<br>10: Código de moneda no válido<br>11: La visita individual no incluye una marca de tiempo en un grupo de informes solo de marca de tiempo o una visita que contiene una marca de tiempo en un grupo de informes que no es de marca de hora<br>12: No se usa. Parte de una función limpiada.<br>13: No se usa. Parte de una función limpiada.<br>14: La visita de Target que no coincide con una visita de Analytics<br>15: No se utiliza actualmente.<br>16: Visita de Advertising Cloud que no coincide con una visita de Analytics | tinyint sin firmar |
| `first_hit_page_url` | La primera URL del visitante. | varchar(255) |
| `first_hit_pagename` | Variable utilizada en la dimensión [Página de entrada original](/help/components/dimensions/entry-dimensions.md). El nombre de la página de entrada original del visitante. | varchar(100) |
| `first_hit_ref_domain` | Variable utilizada en la dimensión [Dominio de referencia original](/help/components/dimensions/original-referring-domain.md). Basado en `first_hit_referrer`. El primer dominio de referencia del visitante. | varchar(100) |
| `first_hit_ref_type` | ID numérica que representa el tipo de referente del primer referente del visitante. Utiliza la búsqueda `referrer_type.tsv`. | tinyint sin firmar |
| `first_hit_referrer` | La primera URL de referencia del visitante. | varchar(255) |
| `first_hit_time_gmt` | Marca de tiempo de la primera visita del visitante en Tiempo Unix. | int |
| `geo_city` | Nombre de la ciudad de la que provino la visita basado en la dirección IP. Se utiliza en la dimensión [Cities](/help/components/dimensions/cities.md). | char(32) |
| `geo_country` | Abreviatura del país del que provino la visita basada en la dirección IP. | char(4) |
| `geo_dma` | ID numérica del área demográfica de la que provino la visita basada en la dirección IP. Se utiliza en la dimensión [US DMA](/help/components/dimensions/us-dma.md). | int sin firmar |
| `geo_region` | Nombre del estado o región del que provino la visita basado en la dirección IP. Se utiliza en la dimensión [Regiones](/help/components/dimensions/regions.md). | char(32) |
| `geo_zip` | El código postal del que provino la visita basado en la dirección IP. Ayuda a rellenar la dimensión [Código postal](/help/components/dimensions/zip-code.md). Consulte también `zip`. | varchar(16) |
| `hier1 - hier5` | Se utiliza por variables de jerarquía. Contiene una lista delimitada de valores. El delimitador se selecciona en virtud de la configuración del grupo de informes. | varchar(255) |
| `hit_source` | Indica la fuente de la que provino la visita. Se facturan las fuentes de visitas 1, 2 y 6. <br>1: Solicitud de imagen estándar sin marca de tiempo <br>2: Solicitud de imagen estándar con marca de tiempo <br>3: Carga de la fuente de datos activa con marcas de tiempo<br>4: Sin usar <br>5: Carga genérica de la fuente de datos <br>6: Carga completa de la fuente de datos de procesamiento <br>7: Carga del origen de datos TransactionID <br>8: Ya no se utiliza; versiones anteriores de las fuentes de datos de Adobe Advertising Cloud <br>9: Ya no se utiliza; métricas resumen de Adobe Social <br>10: Envío del lado del servidor de Audience Manager utilizado | tinyint sin firmar |
| `hit_time_gmt` | La marca de tiempo de los servidores de recopilación de datos de visitas de Adobe que recibieron la visita, basada en la hora Unix. | int |
| `hitid_high` | Se utiliza en combinación con `hitid_low` para identificar una visita de forma exclusiva. | bigint sin firmar |
| `hitid_low` | Se utiliza en combinación con `hitid_high` para identificar una visita de forma exclusiva. | bigint sin firmar |
| `homepage` | Ya no se utiliza. Indicaba si la URL actual es la página de inicio del explorador. | char(1) |
| `hourly_visitor` | Un indicador que determina si la visita es un visitante nuevo por hora. | tinyint sin firmar |
| `ip` | Dirección IP basada en la cabecera HTTP de la solicitud de imagen. | char(20) |
| `ip2` | No se usa. Variable de referencia de backend para los grupos de informes que contienen reglas de VISTA basadas en una dirección IP. | char(20) |
| `j_jscript` | Versión de JavaScript admitida por el explorador. | char(5) |
| `java_enabled` | Indicador que señala si Java está habilitado. <br>S: Habilitado <br>N: No habilitado <br>D: Desconocido | char(1) |
| `javascript` | ID de búsqueda de la versión de JavaScript basado en `j_jscript`. Utiliza la tabla de búsqueda. | tinyint sin firmar |
| `language` | ID numérica de idioma. Utiliza la tabla de búsqueda `languages.tsv`. | smallint sin firmar |
| `last_hit_time_gmt` | Marca de tiempo (en Tiempo Unix) de la visita anterior. Se utiliza para calcular la dimensión [Días desde la última visita](/help/components/dimensions/days-since-last-visit.md). | int |
| `last_purchase_num` | Variable utilizada en la dimensión [Lealtad del cliente](/help/components/dimensions/customer-loyalty.md). Indica la cantidad de compras anteriores que realizó el visitante. <br>0: Sin compras previas (no es un cliente) <br>1: Una compra anterior (nuevo cliente) <br>2: Dos compras anteriores (cliente de devolución) <br>3: Tres o más compras anteriores (cliente fiel) | int sin firmar |
| `last_purchase_time_gmt` | Se utiliza para calcular la dimensión [Días desde la última compra](/help/components/dimensions/days-since-last-purchase.md). Marca de tiempo (en Tiempo Unix) de la última compra realizada. Para la primera compra y para los visitantes que no hayan realizado ninguna compra anteriormente, este valor es `0`. | int |
| `latlon1` | Ubicación (menos de 10 km) | varchar(255) |
| `latlon23` | Ubicación (menos de 100 m) | varchar(255) |
| `latlon45` | Ubicación (menos de 1 m) | varchar(255) |
| `mc_audiences` | Lista de las ID de segmento de Audience Manager a los que pertenece el visitante. | text |
| `mcvisid` | ID de visitante de Experience Cloud. Número de 128 bits que consiste en dos números de 64 bits concatenados aumentados a 19 dígitos. | varchar(255) |
| `mobile_id` | Si el usuario utiliza un dispositivo móvil, es el ID numérico del dispositivo. | int |
| `mobileaction` | Acción móvil. Se recopila automáticamente cuando se llama a `trackAction` en Mobile Services. Permite establecer automáticamente las rutas de acción en la aplicación. | varchar(100) |
| `mobileappid` | ID de la aplicación móvil. Almacena el nombre y la versión de la aplicación en el siguiente formato: `[AppName] [BundleVersion]` | varchar(255) |
| `mobileappperformanceappid` | Se utiliza en el conector de datos Apteligent. El ID de la aplicación utilizado en Apteligent. | varchar(255) |
| `mobileappperformancecrashid` | Se utiliza en el conector de datos Apteligent. ID de bloqueo utilizado en Apteligent. | varchar(255) |
| `mobileappstoreobjectid` | Se utiliza en el conector de datos Appfigures. ID de objeto de App Store. | varchar(255) |
| `mobilebeaconmajor` | Señalización principal de Mobile Services | varchar(100) |
| `mobilebeaconminor` | Señalización menor de Mobile Services | varchar(100) |
| `mobilebeaconproximity` | Proximidad de la señalización de Mobile Services | varchar(255) |
| `mobilebeaconuuid` | UUID de señalización de Mobile Services | varchar(100) |
| `mobilecampaigncontent` | Nombre o ID del contenido que muestra el vínculo. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| `mobilecampaignmedium` | Medio de marketing, como banner o correo electrónico. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| `mobilecampaignname` | Nombre de la campaña, también almacenada en la variable de campaña. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| `mobilecampaignsource` | Referente original, como newsletter o red de medios sociales. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| `mobilecampaignterm` | Palabras clave pagas u otros términos que desee rastrear con esta adquisición. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| `mobiledayofweek` | Número del día de la semana en que se abrió la aplicación. | varchar(255) |
| `mobiledayssincefirstuse` | Cantidad de días desde que la aplicación se ejecutó por primera vez. | varchar(255) |
| `mobiledayssincelastupgrade` | Recopilado desde la variable de datos de contexto a.DaysSinceLastUpgrade. Número de días que han transcurrido desde la sesión anterior. | varchar(255) |
| `mobiledayssincelastuse` | Cantidad de días desde que la aplicación se ejecutó por última vez. | varchar(255) |
| `mobiledeeplinkid` | Recopilado desde la variable de datos de contexto `a.deeplink.id`. Se utiliza en los informes de adquisición como identificador para el vínculo de adquisición móvil. | varchar(255) |
| `mobiledevice` | Nombre del dispositivo móvil. En iOS, se almacena como una cadena de 2 dígitos separados por una coma. El primer número representa la generación del dispositivo y el segundo, la familia del dispositivo. | varchar(255) |
| `mobilehourofday` | Define la hora del día en que se abrió la aplicación. Sigue el formato numérico de 24 horas. | varchar(255) |
| `mobileinstalldate` | Fecha de instalación del móvil. Proporciona la fecha de la primera vez que el usuario abrió la aplicación móvil. | varchar(255) |
| `mobilelaunchessincelastupgrade` | Recopilado desde la variable de datos de contexto a.LaunchesSinceUpgrade. Informa del número de inicios desde la última actualización. | varchar(255) |
| `mobilelaunchnumber` | Incrementa de uno en uno cada vez que se abre la aplicación móvil. | varchar(255) |
| `mobileltv` | Ya no se utiliza. Rellenado con métodos trackLifetimeValue. | varchar(255) |
| `mobilemessagebuttonname` | Recopilado desde la variable de datos de contexto `a.message.button.id`. Se utiliza para la mensajería integrada en la aplicación con el objetivo de identificar el botón que cerró el mensaje. | varchar(100) |
| `mobilemessageid` | ID de mensaje en la aplicación | varchar(255) |
| `mobilemessageonline` | Mensaje en línea en la aplicación | varchar(255) |
| `mobilemessagepushoptin` | Recopilado desde la variable de datos de contexto `a.push.optin`. Se establece en “true” cuando el usuario opta por la mensajería emergente; de lo contrario, el valor es “false”. | varchar(255) |
| `mobilemessagepushpayloadid` | Recopilado desde la variable de datos de contexto `a.push.payloadid`. Se utiliza en los mensajes emergentes como identificador de carga útil. | varchar(255) |
| `mobileosenvironment` | Recopilado desde la variable de datos de contexto `a.OSEnvironment`. Estados del entorno del sistema operativo, como Android o iOS. | varchar(255) |
| `mobileosversion` | Versión del sistema operativo de Mobile Services | varchar(255) |
| `mobileplaceaccuracy` | Recopilado desde la variable de datos de contexto `a.loc.acc`. Indica la precisión del GPS en metros en el momento de la recogida. | varchar(255) |
| `mobileplacecategory` | Recopilado desde la variable de datos de contexto `a.loc.category`. Describe la categoría de un lugar específico. | varchar(255) |
| `mobileplaceid` | Recopilado desde la variable de datos de contexto `a.loc.id`. Identificador de un punto de interés determinado. | varchar(255) |
| `mobilerelaunchcampaigncontent` | Contenido de inicio de Mobile Services | varchar(255) |
| `mobilerelaunchcampaignmedium` | Medio de inicio de Mobile Services | varchar(255) |
| `mobilerelaunchcampaignsource` | Origen del inicio de Mobile Services | varchar(255) |
| `mobilerelaunchcampaignterm` | Término de inicio de Mobile Services | varchar(255) |
| `mobilerelaunchcampaigntrackingcode` | Recopilado desde la variable de datos de contexto `a.launch.campaign.trackingcode`. Se utiliza en la adquisición como código de seguimiento para la campaña de inicio. | varchar(255) |
| `mobileresolution` | Resolución del dispositivo móvil. `[Width] x [Height]` en píxeles. | varchar(255) |
| `monthly_visitor` | Un indicador que señala que el visitante es exclusivo del mes actual. | tinyint sin firmar |
| `mvvar1` - `mvvar3` | Valores de variable de lista. Contiene una lista delimitada de valores personalizados en función de la implementación. | text |
| `namespace` | No se usa. Parte de una función limpiada. | varchar(50) |
| `new_visit` | Un indicador que determina si la visita actual es una nueva visita. Los servidores de Adobe lo establecen después de 30 minutos de inactividad de la visita. | tinyint sin firmar |
| `os` | ID numérica que representa el sistema operativo del visitante. Se basa en la columna`user_agent`. Utiliza la búsqueda `os`. | int sin firmar |
| `p_plugins` | Ya no se utiliza. Lista de plugins disponibles para el explorador. Utilizaba la función de JavaScript `navigator.plugins()`. | text |
| `page_event` | El tipo de visita que se envía en la solicitud de imagen (visita estándar, vínculo de descarga, vínculo personalizado, vínculo de salida). Consulte [Búsqueda de evento de página](datafeeds-page-event.md). | tinyint sin firmar |
| `page_event_var1` | Solo se utiliza en las solicitudes de imagen de seguimiento de vínculos. Es la URL del vínculo de descarga, el vínculo de salida o el vínculo personalizado en el que se ha hecho clic. | text |
| `page_event_var2` | Solo se utiliza en las solicitudes de imagen de seguimiento de vínculos. El nombre personalizado (si se especifica) del vínculo. | varchar(100) |
| `page_event_var3` | Ya no se utiliza. Contenía los datos de los módulos Survey y Media. Completaba los informes de vídeo heredados en las versiones anteriores de Adobe Analytics. | text |
| `page_type` | Se utilizaba para completar la dimensión [Páginas no encontradas](/help/components/dimensions/pages-not-found.md) y se usaba exclusivamente para las páginas 404. Esta variable debe estar vacía o debe contener el valor `ErrorPage`. | char(20) |
| `page_url` | La URL de la visita. En su variante posterior (post_page_url), el valor se elimina para las solicitudes de imagen de seguimiento de vínculos. | varchar(255) |
| `pagename` | Se utiliza para completar la dimensión [Página](/help/components/dimensions/page.md). Si la variable [`pagename`](/help/implement/vars/page-vars/pagename.md) está vacía, Analytics utiliza `page_url` en su lugar. | varchar(100) |
| `paid_search` | Un indicador que se establece si la visita coincide con la detección de búsquedas de pago. | tinyint sin firmar |
| `partner_plugins` | No se usa. Parte de una función limpiada. | varchar(255) |
| `persistent_cookie` | Se utiliza en la dimensión [Compatibilidad con cookies persistentes](/help/components/dimensions/persistent-cookie-support.md). Indica si el visitante admite las cookies que no se descartan después de cada visita. | char(1) |
| `plugins` | Ya no se utiliza. Lista de ID numéricas que corresponden a los plugins disponibles dentro del explorador. Utiliza la búsqueda `plugins.tsv`. | varchar(180) |
| `pointofinterest` | Nombre del punto de interés de Mobile Services | varchar(255) |
| `pointofinterestdistance` | Distancia de Mobile Services al centro de puntos de interés | varchar(255) |
| Columnas `post_` | Contiene el valor definitivo que se ha utilizado en los informes. Cada columna de publicación se completa después de la lógica del lado del servidor, las reglas de procesamiento y las reglas de VISTA. Adobe recomienda usar columnas de publicación en la mayoría de los casos. | Consulte la correspondiente columna de no publicación |
| `prev_page` | No se usa. Identificador propio de Adobe de la página anterior. | int sin firmar |
| `product_list` | Lista de productos tal como se transmite mediante la variable [`products`](/help/implement/vars/page-vars/products.md). Los productos están delimitados por comas, mientras que las propiedades de los productos individuales están delimitadas por punto y coma. | text |
| `product_merchandising` | No se usa. Utilice `product_list` en su lugar. | text |
| `prop1` -  `prop75` | Variables de tráfico personalizadas 1-75. Se utiliza en dimensiones [Prop](/help/components/dimensions/prop.md). | varchar(100) |
| `purchaseid` | Identificador único de una compra, tal y como se establece mediante la variable [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). Lo utiliza la columna `duplicate_purchase`. | char(20) |
| `quarterly_visitor` | Un indicador que determina si la visita es un visitante nuevo trimestral. | tinyint sin firmar |
| `ref_domain` | Se basa en la columna de referentes. El dominio de referencia de la visita. Se utiliza en la dimensión [Dominio de referencia](/help/components/dimensions/referring-domain.md). | varchar(100) |
| `ref_type` | Una ID numérica que representa el tipo de referente de la visita. Se utiliza en la dimensión [Tipo de remitente del reenvío](/help/components/dimensions/referrer-type.md). <br>1: Dentro del sitio<br>2: Otros sitios web <br>3: Motores de búsqueda <br>4: Disco duro <br>5: USENET <br>6: Escritos o marcadores (sin referente) <br>7: Correo electrónico <br>8: Sin JavaScript <br>9: Redes sociales | tinyint sin firmar |
| `referrer` | URL de la página anterior. Se utiliza en la dimensión [Remitente del reenvío](/help/components/dimensions/referrer.md). Tenga en cuenta que mientras `referrer` utiliza un tipo de datos de varchar(255), `post_referrer` emplea un tipo de datos de varchar(244). | varchar(255) |
| `resolution` | ID numérico que representa la resolución del monitor. Se utiliza en la dimensión [Resolución del monitor](/help/components/dimensions/monitor-resolution.md). Utiliza la tabla de búsqueda `resolution.tsv`. | smallint sin firmar |
| `s_kwcid` | ID de palabra clave utilizado en las integraciones de Adobe Advertising Cloud. | varchar(255) |
| `s_resolution` | Valor no procesado de resolución de pantalla. Se recopila mediante la función de JavaScript `screen.width x screen.height`. | char(20) |
| `search_engine` | ID numérica que representa el Motor de búsqueda que refirió al visitante a su sitio. Utiliza la búsqueda `search_engines.tsv`. | smallint sin firmar |
| `search_page_num` | Lo utiliza la dimensión [Rango de todas las páginas de búsqueda](/help/components/dimensions/all-search-page-rank.md). Indica en qué página de resultados de búsqueda apareció su sitio antes de que el usuario hiciera clic para acceder a su sitio. | smallint sin firmar |
| `secondary_hit` | Indicador que hace un seguimiento de las visitas secundarias. Por lo general, se origina a partir del etiquetado de grupos múltiples y las reglas de VISTA que copian las visitas. | tinyint sin firmar |
| `service` | No se usa. Utilice `page_event` en su lugar. | char(2) |
| `socialaccountandappids` | Ya no se utiliza. Cuenta social e ID de aplicación. | varchar(255) |
| `socialassettrackingcode` | Ya no se utiliza. Variable de campaña en redes sociales. | varchar(255) |
| `socialauthor` | Ya no se utiliza. Variable de autores en redes sociales. | varchar(255) |
| `socialcontentprovider` | Ya no se utiliza. Plataformas sociales/Propiedades | varchar(255) |
| `socialinteractiontype` | Ya no se utiliza. Tipo de interacción social | varchar(255) |
| `sociallanguage` | Ya no se utiliza. Idioma de red social | varchar(255) |
| `sociallatlong` | Ya no se utiliza. Latitud o longitud de la red social | varchar(255) |
| `socialowneddefinitioninsighttype` | Ya no se utiliza. Tipo de datos de definición con propiedad social | varchar(255) |
| `socialowneddefinitioninsightvalue` | Ya no se utiliza. Valor de datos de definición con propiedad social | varchar(255) |
| `socialowneddefinitionmetric` | Ya no se utiliza. Métrica de la definición con propiedad social | varchar(255) |
| `socialowneddefinitionpropertyvspost` | Ya no se utiliza. Propiedad de definición con propiedad social frente a publicación | varchar(255) |
| `socialownedpostids` | Ya no se utiliza. ID de publicación con propiedad social | varchar(255) |
| `socialownedpropertyid` | Ya no se utiliza. ID de propiedad social | varchar(255) |
| `socialownedpropertyname` | Ya no se utiliza. Nombre de la propiedad social | varchar(255) |
| `socialownedpropertypropertyvsapp` | Ya no se utiliza. Propiedad social frente a aplicación | varchar(255) |
| `state` | Variable de estado. | varchar(50) |
| `stats_server` | No es de uso. Servidor interno de Adobe que ha procesado la visita. | char(30) |
| `t_time_info` | Hora local del visitante. El formato es: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| `tnt` | Se utiliza en las integraciones de Adobe Target. | text |
| `tnt_action` | Se utiliza en las integraciones de Adobe Target. | text |
| `tnt_post_vista` | Ya no se utiliza. Utilice `post_tnt` en su lugar. | text |
| `transactionid` | Un identificador exclusivo donde, más tarde, se pueden cargar diversos puntos de datos a través de fuentes de datos. Recopilado mediante la variable [`transactionID`](/help/implement/vars/page-vars/transactionid.md). | text |
| `truncated_hit` | Un indicador que señala que se ha truncado la solicitud de imagen. Indica que se ha recibido una visita parcial. <br>S: Se truncó la visita; visita parcial recibida <br>N: La visita no se truncó; visita completa recibida | char(1) |
| `ua_color` | Ya no se utiliza. Anteriormente, se utilizaba como alternativa a la profundidad de color. | char(20) |
| `ua_os` | Ya no se utiliza. Anteriormente, se utilizaba como alternativa al sistema operativo. | char(80) |
| `ua_pixels` | Ya no se utiliza. Anteriormente, se utilizaba como alternativa a la anchura y la altura del explorador. | char(20) |
| `user_agent` | El grupo desconocido que se envía en la cabecera HTTP de la solicitud de imagen. | text |
| `user_hash` | No es de uso. Hash de la ID del grupo de informes. Utilice `username` en su lugar. | int sin firmar |
| `user_server` | Utilizado en la dimensión [Servidor](/help/components/dimensions/server.md). | varchar(100) |
| `userid` | No es de uso. La ID numérica de la ID del grupo de informes. Utilice `username` en su lugar. | int sin firmar |
| `username` | ID del grupo de informes para la visita. | char(40) |
| `va_closer_detail` | Variable utilizada en la dimensión [Detalle del último contacto](/help/components/dimensions/last-touch-detail.md). | varchar(255) |
| `va_closer_id` | ID numérico que identifica la dimensión [Canal del último contacto](/help/components/dimensions/last-touch-channel.md). La búsqueda de esta ID se puede encontrar en el Administrador de canales de marketing. | tinyint sin firmar |
| `va_finder_detail` | Variable utilizada en la dimensión [Detalle del primer contacto](/help/components/dimensions/first-touch-detail.md). | varchar(255) |
| `va_finder_id` | ID numérico que identifica la dimensión [Canal del primer contacto](/help/components/dimensions/first-touch-channel.md). La búsqueda de esta ID se puede encontrar en el Administrador de canales de marketing. | tinyint sin firmar |
| `va_instance_event` | Indicador que identifica las [instancias](/help/components/metrics/instances.md) de Canal de marketing. | tinyint sin firmar |
| `va_new_engagement` | Indicador que identifica las [nuevas interacciones](/help/components/metrics/new-engagements.md) en Canal de marketing. | tinyint sin firmar |
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
| `videoqoebitrateaverageevar` | Tasa de bits promedio de la calidad de vídeo | varchar(255) |
| `videoqoebitratechangecountevar` | Recuento de cambios en la calidad de vídeo | varchar(255) |
| `videoqoebuffercountevar` | Recuento de búferes en la calidad de vídeo | varchar(255) |
| `videoqoebuffertimeevar` | Hora de búfer de la calidad de vídeo | varchar(255) |
| `videoqoedroppedframecountevar` | Recuento de marcos de descenso de calidad de vídeo | varchar(255) |
| `videoqoeerrorcountevar` | Recuento de errores de calidad de vídeo | varchar(255) |
| `videoqoeextneralerrors` | Errores externos de la calidad del vídeo | text |
| `videoqoeplayersdkerrors` | Errores del SDK de calidad del vídeo | text |
| `videoqoetimetostartevar` | Hora de inicio de calidad de vídeo | varchar(255) |
| `videoseason` | Temporada del vídeo | varchar(255) |
| `videosegment` | Segmento de vídeo | varchar(255) |
| `videoshow` | Programa del vídeo | varchar(255) |
| `videoshowtype` | Tipo de programa del vídeo | varchar(255) |
| `videostreamtype` | Tipo de flujo de vídeo | varchar(255) |
| `visid_high` | Se utiliza en combinación con `visid_low` para identificar un visitante de forma exclusiva. | bigint sin firmar |
| `visid_low` | Se utiliza en combinación con `visid_high` para identificar un visitante de forma exclusiva. | bigint sin firmar |
| `visid_new` | Indicador que identifica si la visita contiene una ID de visitante generada recientemente. | char(1) |
| `visid_timestamp` | Si la ID de visitante se ha generado recientemente, proporciona la marca de tiempo (en Tiempo Unix) del momento en que se generó la ID de visitante. | int |
| `visid_type` | No para uso externo; Adobe lo utiliza internamente para procesar optimizaciones. ID numérica que representa el método utilizado para identificar al visitante.<br>0: VisitorID personalizado o desconocido/no aplicable<br>1: IP y reserva del agente de usuario <br>2: Encabezado de suscriptor móvil HTTP <br>3: Valor de la cookie heredada (`s_vi`) <br>4: Valor de la cookie de reserva (`s_fid`) <br>5: Servicio de identidad | tinyint sin firmar |
| `visit_keywords` | Variable utilizada en la dimensión [Palabra clave de búsqueda](/help/components/dimensions/search-keyword.md). Esta columna utiliza un límite de caracteres no estándar de varchar(244) para dar cabida a la lógica back-end que utiliza Adobe. | varchar(244) |
| `visit_num` | Variable utilizada en la dimensión [Número de visitas](/help/components/dimensions/visit-number.md). Empieza en 1 y aumenta cada vez que se inicia una nueva visita por visitante. | int sin firmar |
| `visit_page_num` | Variable utilizada en la dimensión [Profundidad de visita](/help/components/dimensions/hit-depth.md). Aumenta de uno en uno con cada visita que genera el usuario. Restablece cada visita. | int sin firmar |
| `visit_ref_domain` | Se basa en la columna `visit_referrer`. El primer dominio de referencia de la visita. | varchar(100) |
| `visit_ref_type` | ID numérica que representa el tipo de referente del primer referente de la visita. Utiliza la tabla de búsqueda `referrer_type.tsv`. | tinyint sin firmar |
| `visit_referrer` | El primer referente de la visita. | varchar(255) |
| `visit_search_engine` | ID numérica del primer motor de búsqueda de la visita. Utiliza la búsqueda `search_engines.tsv`. | smallint sin firmar |
| `visit_start_page_url` | La primera URL de la visita. | varchar(255) |
| `visit_start_pagename` | El primer nombre de página de la visita. | varchar(100) |
| `visit_start_time_gmt` | Marca de tiempo (en Tiempo Unix) de la primera visita. | int |
| `weekly_visitor` | Indicador que determina si la visita es un visitante nuevo semanal. | tinyint sin firmar |
| `yearly_visitor` | Indicador que determina si la visita es un visitante nuevo anual. | tinyint sin firmar |
| `zip` | Ayuda a rellenar la dimensión [Código postal](/help/components/dimensions/zip-code.md). Consulte también `geo_zip`. | varchar(50) |

## Columnas vacías

La siguiente lista de columnas no se utiliza y no contiene datos:

* `mobileacquisitionclicks`
* `mobileactioninapptime`
* `mobileactiontotaltime`
* `mobileappperformanceaffectedusers`
* `mobileappperformanceappid.app-perf-app-name`
* `mobileappperformanceappid.app-perf-platform`
* `mobileappperformancecrashes`
* `mobileappperformancecrashid.app-perf-crash-name`
* `mobileappperformanceloads`
* `mobileappstoreavgrating`
* `mobileappstoredownloads`
* `mobileappstoreinapprevenue`
* `mobileappstoreinapproyalties`
* `mobileappstoreobjectid.app-store-user`
* `mobileappstoreobjectid.application-name`
* `mobileappstoreobjectid.application-version`
* `mobileappstoreobjectid.appstore-name`
* `mobileappstoreobjectid.category-name`
* `mobileappstoreobjectid.country-name`
* `mobileappstoreobjectid.device-manufacturer`
* `mobileappstoreobjectid.device-name`
* `mobileappstoreobjectid.in-app-name`
* `mobileappstoreobjectid.platform-name-version`
* `mobileappstoreobjectid.rank-category-type`
* `mobileappstoreobjectid.region-name`
* `mobileappstoreobjectid.review-comment`
* `mobileappstoreobjectid.review-title`
* `mobileappstoreoneoffrevenue`
* `mobileappstoreoneoffroyalties`
* `mobileappstorepurchases`
* `mobileappstorerank`
* `mobileappstorerankdivisor`
* `mobileappstorerating`
* `mobileappstoreratingdivisor`
* `mobileavgprevsessionlength`
* `mobilecrashes`
* `mobilecrashrate`
* `mobiledailyengagedusers`
* `mobiledeeplinkid.name`
* `mobileinstalls`
* `mobilelaunches`
* `mobileltvtotal`
* `mobilemessageclicks`
* `mobilemessageid.dest`
* `mobilemessageid.name`
* `mobilemessageid.type`
* `mobilemessageimpressions`
* `mobilemessagepushpayloadid.name`
* `mobilemessageviews`
* `mobilemonthlyengagedusers`
* `mobileplacedwelltime`
* `mobileplaceentry`
* `mobileplaceexit`
* `mobileprevsessionlength`
* `mobilerelaunchcampaigntrackingcode.name`
* `mobileupgrades`
* `socialaveragesentiment`
* `socialaveragesentiment (deprecated)`
* `socialfbstories`
* `socialfbstorytellers`
* `socialinteractioncount`
* `sociallikeadds`
* `sociallink`
* `sociallink (deprecated)`
* `socialmentions`
* `socialpageviews`
* `socialpostviews`
* `socialproperty`
* `socialproperty (deprecated)`
* `socialpubcomments`
* `socialpubposts`
* `socialpubrecommends`
* `socialpubsubscribers`
* `socialterm`
* `socialtermslist`
* `socialtermslist (deprecated)`
* `socialtotalsentiment`
* `sourceid`
* `videoauthorized`
* `videoaverageminuteaudience`
* `videochaptercomplete`
* `videochapterstart`
* `videochaptertime`
* `videopause`
* `videopausecount`
* `videopausetime`
* `videoplay`
* `videoprogress10`
* `videoprogress25`
* `videoprogress50`
* `videoprogress75`
* `videoprogress96`
* `videoqoebitrateaverage`
* `videoqoebitratechange`
* `videoqoebuffer`
* `videoqoedropbeforestart`
* `videoqoedroppedframes`
* `videoqoeerror`
* `videoresume`
* `videototaltime`
* `videouniquetimeplayed`
