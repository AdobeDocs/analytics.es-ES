---
description: Datos de tabla que describen las columnas de las fuentes de datos.
keywords: Fuentes de datos, columnas
subtopic: data feeds
title: Referencia de columnas de datos
feature: Data Feeds
exl-id: e1492147-6e7f-4921-b509-898e7efda596
source-git-commit: 25a50bafe355443e52969f24922ce4a40742e338
workflow-type: tm+mt
source-wordcount: '3690'
ht-degree: 58%

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

Las actualizaciones anteriores de esta tabla se encuentran en el [historial de confirmaciones en GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md).

| Nombre de la columna | Descripción de columna | Tipo de datos |
| --- | --- | --- |
| **`accept_language`** | Enumera todos los idiomas aceptados, tal como se indica en el encabezado Accept-Language-HTTP de las solicitudes de imagen. | char(20) |
| **`adload`** | Cargas de anuncios de medios | varchar(255) |
| **`aemassetid`** | Variable de varios valores que corresponde a los ID de recurso (GUID) de un conjunto de Adobe Experience Manager Assets. Aumenta Los Eventos De Impresión. | texto |
| **`aemassetsource`** | Identifica el origen del evento del recurso. Se utiliza en Adobe Experience Manager. | varchar(255) |
| **`aemclickedassetid`** | ID de recurso de un recurso de Adobe Experience Manager. Incrementa los eventos de clic. | varchar(255) |
| **`browser`** | ID numérica que representa el explorador. Se remite a la tabla de búsqueda `browser.tsv`. | int sin firmar |
| **`browser_height`** | La dimensión [Altura del explorador](/help/components/dimensions/browser-height.md). | smallint sin firmar |
| **`browser_width`** | El [Ancho Del Explorador](/help/components/dimensions/browser-width.md) | smallint sin firmar |
| **`c_color`** | Profundidad de bits de la paleta de colores. Se utiliza en el cálculo de la dimensión [Profundidad de color](/help/components/dimensions/color-depth.md). AppMeasurement utiliza la función JavaScript `screen.colorDepth()`. | char(20) |
| **`campaign`** | La dimensión [Código de seguimiento](/help/components/dimensions/tracking-code.md). | varchar(255) |
| **`carrier`** | Variable de integración de Adobe Advertising. Especifica el operador de telefonía móvil. El valor clave de `carrier.tsv` [Búsqueda dinámica](dynamic-lookups.md). | varchar(100) |
| **`ch_hdr`** | Sugerencias del cliente recopiladas mediante el encabezado de petición HTTP. | texto |
| **`ch_js`** | Sugerencias del cliente recopiladas mediante la API de JavaScript de sugerencias del cliente agente de usuario. | texto |
| **`channel`** | Dimensión de [secciones del sitio](/help/components/dimensions/site-section.md). | varchar(100) |
| **`clickmaplink`** | Vínculo de Activity Map | varchar(255) |
| **`clickmaplinkbyregion`** | Vínculo de Activity Map por región | varchar(255) |
| **`clickmappage`** | Página de Activity Map | varchar(255) |
| **`clickmapregion`** | Región de Activity Map | varchar(255) |
| **`code_ver`** | Versión de la API o del SDK cliente utilizado para compilar y enviar la solicitud de imagen. | char(16) |
| **`color`** | ID de profundidad de color basada en el valor de la columna `c_color`. Se remite a la tabla de búsqueda `color_depth.tsv`. | smallint sin firmar |
| **`connection_type`** | ID numérico que representa el tipo de conexión. La dimensión [Tipo de conexión](/help/components/dimensions/connection-type.md). Se remite a la tabla de búsqueda `connection_type.tsv`. | tinyint sin firmar |
| **`cookies`** | La dimensión [Compatibilidad con cookies](/help/components/dimensions/cookie-support.md).<br>S: Habilitado<br>N: No habilitado<br>D: Desconocido | char(1) |
| **`country`** | ID numérica que representa el país del visitante. Se remite a la tabla de búsqueda `country.tsv`. | smallint sin firmar |
| **`ct_connect_type`** | En relación con la columna `connection_type`. Los valores más comunes son LAN/Wi-Fi, Operador de telefonía móvil y Módem. | char(20) |
| **`curr_factor`** | Determina la posición decimal de la moneda y se utiliza para la conversión de moneda. Por ejemplo, USD utiliza dos decimales, por lo que el valor de esta columna sería `2`. | tinyint |
| **`curr_rate`** | El tipo de cambio cuando se produjo la transacción. Adobe se asocia con XE para determinar el tipo de cambio del día actual. | decimal(24,12) |
| **`currency`** | El código de moneda que se utilizó durante la transacción. Configurado con [`currencyCode`](/help/implement/vars/config-vars/currencycode.md). | char(8) |
| **`cust_hit_time_gmt`** | Solo grupos de informes con marca de tiempo. La marca de tiempo enviada con la visita y basada en el Tiempo UNIX®. | int |
| **`cust_visid`** | El ID de visitante personalizado, si se establece con [`visitorID`](/help/implement/vars/config-vars/visitorid.md). | varchar(255) |
| **`customer_perspective`** | Determina si la visita es una visita en segundo plano de un dispositivo móvil. Consulte [Sesiones según el contexto](/help/components/vrs/vrs-mobile-visit-processing.md) para obtener más información. | tinyint sin firmar |
| **`daily_visitor`** | Un indicador que determina si la visita es un visitante nuevo diario. | tinyint sin firmar |
| **`dataprivacyconsentoptin`** | Dimensión [Inclusión en la administración de consentimiento](/help/components/dimensions/cm-opt-in.md). Puede haber varios valores por visita, separados por una barra vertical (`\|`). Los valores válidos incluyen `DMP` y `SELL`. | varchar(100) |
| **`dataprivacyconsentoptout`** | Dimensión [Exclusión de la administración de consentimiento](/help/components/dimensions/cm-opt-out.md). Puede haber varios valores por visita, separados por una barra vertical (`\|`). Los valores válidos incluyen `SSF`, `DMP` y `SELL`. | varchar(100) |
| **`dataprivacydmaconsent`** | Valor que identifica si se adquiere el consentimiento para enviar datos de Adobe Analytics a través de Adobe Advertising a proveedores de publicidad de terceros (como Google). Consulte [Consentimiento de publicidad](/help/components/dimensions/ad-consent.md) para obtener más información. | varchar(100) |
| **`date_time`** | La hora de la visita en un formato legible, basada en la zona horaria del grupo de informes. | datetime |
| **`domain`** | La dimensión [Dominio](/help/components/dimensions/domain.md). Basado en el punto de acceso a Internet del visitante. | varchar(100) |
| **`duplicate_events`** | Enumera cada evento que se contó como duplicado. | varchar(255) |
| **`duplicate_purchase`** | Un indicador que determina si el evento de compra de esta visita se ignora porque es un duplicado. | tinyint sin firmar |
| **`duplicated_from`** | Solo se utiliza en los grupos de informes que contienen las reglas de VISTA de copia de visita. Indica de qué grupo de informes se copió la visita. | varchar(40) |
| **`ef_id`** | `ef_id` que se usa en las integraciones de Adobe Advertising. | varchar(255) |
| **`evar1 - evar250`** | Variables personalizadas 1-250. Se utiliza en dimensiones [eVar](/help/components/dimensions/evar.md). Cada organización utiliza las eVars de forma diferente. El mejor lugar para obtener más información sobre cómo su organización rellena las eVars respectivas sería un [documento de diseño de solución](/help/implement/prepare/solution-design.md) específico de su organización. | varchar(255) |
| **`event_list`** | Lista separada por comas de los ID numéricos que representan los eventos activados en la visita. Incluye eventos predeterminados y [eventos personalizados 1-1000](/help/components/metrics/custom-events.md). Utiliza la búsqueda `event.tsv`. | texto |
| **`exclude_hit`** | Un indicador que determina si la visita se excluye de la creación de informes. La columna `visit_num` no aumenta con las visitas excluidas.<br>1: No se usa. Parte de una función limpiada.<br>2: No se usa. Parte de una función limpiada.<br>3: Ya no se utiliza. Exclusión de agente de usuario<br>4: Exclusión basada en la dirección IP<br>5: Falta información clave de visitas, como `page_url`, `pagename`, `page_event` o `event_list`<br>6: JavaScript no ha procesado la visita correctamente<br>7: Exclusión específica de la cuenta, como en reglas VISTA<br>8: Sin usar. Exclusión alternativa específica de la cuenta.<br>9: No se usa. Parte de una función limpiada.<br>10: Código de moneda no válido<br>11: La visita individual no incluye una marca de tiempo en un grupo de informes solo de marca de tiempo o una visita que contiene una marca de tiempo en un grupo de informes que no es de marca de hora<br>12: No se usa. Parte de una función limpiada.<br>13: No se usa. Parte de una función limpiada.<br>14: La visita de Target que no coincide con una visita de Analytics<br>15: No se utiliza actualmente.<br>16: Visita de Advertising Cloud que no coincide con una visita de Analytics | tinyint sin firmar |
| **`first_hit_page_url`** | La primera URL del visitante. | varchar(255) |
| **`first_hit_pagename`** | La dimensión [Página de entrada original](/help/components/dimensions/entry-dimensions.md). El nombre de la página de entrada original del visitante. | varchar(100) |
| **`first_hit_ref_domain`** | La dimensión [Dominio de referencia original](/help/components/dimensions/original-referring-domain.md). Basado en `first_hit_referrer`. El primer dominio de referencia del visitante. | varchar(100) |
| **`first_hit_ref_type`** | ID numérica que representa el tipo de referente del primer referente del visitante. Se remite a la tabla de búsqueda `referrer_type.tsv`. | tinyint sin firmar |
| **`first_hit_referrer`** | La primera URL de referencia del visitante. | varchar(255) |
| **`first_hit_time_gmt`** | Marca de tiempo de la primera visita del visitante en tiempo UNIX®. | int |
| **`geo_city`** | El nombre de la ciudad de la que provino la visita basado en la dirección IP. Se utiliza en la dimensión [Cities](/help/components/dimensions/cities.md). | char(32) |
| **`geo_country`** | Abreviatura del país del que provino la visita basada en la dirección IP. Se utiliza en la dimensión [Países.](/help/components/dimensions/countries.md) | char(4) |
| **`geo_dma`** | ID numérica del área demográfica de la que provino la visita basada en la dirección IP. Se utiliza en la dimensión [US DMA](/help/components/dimensions/us-dma.md). | int sin firmar |
| **`geo_region`** | El nombre del estado o región del que provino la visita basada en la dirección IP. Se utiliza en la dimensión [Regiones](/help/components/dimensions/regions.md). | char(32) |
| **`geo_zip`** | El código postal del que provino la visita basada en la dirección IP. Ayuda a rellenar la dimensión [Código postal](/help/components/dimensions/zip-code.md). Consulte también `zip`. | varchar(16) |
| **`hit_source`** | Origen del que provino la visita. Se facturan las fuentes de visitas 1, 2 y 6. <br>1: Solicitud de imagen estándar sin marca de tiempo <br>2: Solicitud de imagen estándar con marca de tiempo <br>3: Carga de la fuente de datos activa con marcas de tiempo<br>4: Sin usar <br>5: Carga genérica de la fuente de datos <br>6: Carga completa de la fuente de datos de procesamiento <br>7: Carga del origen de datos TransactionID <br>8: Ya no se utiliza; versiones anteriores de las fuentes de datos de Adobe Advertising Cloud <br>9: Ya no se utiliza; métricas resumen de Adobe Social <br>10: Envío del lado del servidor de Audience Manager utilizado | tinyint sin firmar |
| **`hit_time_gmt`** | La marca de tiempo de los servidores de recopilación de datos de visitas de Adobe que recibieron la visita, basada en el tiempo UNIX®. | int |
| **`hitid_high`** | Se utiliza en combinación con `hitid_low` para identificar una visita. | bigint sin firmar |
| **`hitid_low`** | Se utiliza con `hitid_high` para identificar una visita. | bigint sin firmar |
| **`hourly_visitor`** | Un indicador que determina si la visita es un visitante nuevo por hora. | tinyint sin firmar |
| **`ip`** | La dirección IPv4, basada en el encabezado HTTP de la solicitud de imagen. Exclusivo de forma mutua para `ipv6`; si esta columna contiene una dirección IP no oculta, `ipv6` está en blanco. | char(20) |
| **`ipv6`** | La dirección IPv6 comprimida, si está disponible. Exclusivo de forma mutua para `ip`; si esta columna contiene una dirección IP no oculta, `ip` está en blanco. | varchar(40) |
| **`j_jscript`** | Versión de JavaScript admitida por el explorador. | char(5) |
| **`java_enabled`** | [[!UICONTROL Java habilitado]](/help/components/dimensions/java-enabled.md). <br>S: Habilitado<br>N: No habilitado<br>D: Desconocido | char(1) |
| **`javascript`** | Identificador de búsqueda de la versión de JavaScript basado en `j_jscript`. Se remite a la tabla de búsqueda `javascript_version`. | tinyint sin firmar |
| **`language`** | ID numérica que representa el idioma del visitante. Se remite a la tabla de búsqueda `languages.tsv`. | smallint sin firmar |
| **`last_hit_time_gmt`** | Marca de tiempo (en tiempo UNIX®) de la visita anterior. Se utiliza para calcular la dimensión [[!UICONTROL Días desde la última visita]](/help/components/dimensions/days-since-last-visit.md). | int |
| **`last_purchase_num`** | La dimensión [Lealtad del cliente](/help/components/dimensions/customer-loyalty.md). Indica la cantidad de compras anteriores que realizó el visitante. <br>0: Sin compras previas (no es un cliente) <br>1: Una compra anterior (nuevo cliente) <br>2: Dos compras anteriores (cliente de devolución) <br>3: Tres o más compras anteriores (cliente fiel) | int sin firmar |
| **`last_purchase_time_gmt`** | Se utiliza para calcular la dimensión [[!UICONTROL Días desde la última compra]](/help/components/dimensions/days-since-last-purchase.md). Marca de tiempo (en tiempo UNIX®) de la última compra realizada. Para la primera compra y para los visitantes que no hayan realizado ninguna compra anteriormente, este valor es `0`. | int |
| **`latlon1`** | Ubicación (menos de 10 km) | varchar(255) |
| **`latlon23`** | Ubicación (menos de 100 m) | varchar(255) |
| **`latlon45`** | Ubicación (menos de 1 m) | varchar(255) |
| **`mc_audiences`** | Lista de ID de segmento de Audience Manager a los que pertenece el visitante. La columna `post_mc_audiences` cambia el delimitador a `--**--`. | texto |
| **`mcvisid`** | ID de visitante de Experience Cloud. Número de 128 bits formado por dos números concatenados de 64 bits seguidos de 19 dígitos. | varchar(255) |
| **`mobile_id`** | Si el usuario utiliza un dispositivo móvil, es el ID numérico del dispositivo. El valor clave de `mobile_attributes.tsv` [Búsqueda dinámica](dynamic-lookups.md). | int |
| **`mobileaction`** | Acción móvil. Se recopila automáticamente cuando se llama a `trackAction` en implementaciones móviles. Permite establecer automáticamente las rutas de acción en la aplicación. | varchar(100) |
| **`mobileappid`** | ID de la aplicación móvil. Almacena el nombre y la versión de la aplicación en el siguiente formato: `[AppName] [BundleVersion]`.  | varchar(255) |
| **`mobileappperformanceappid`** | Se utiliza en el conector de datos Apteligent. El ID de la aplicación utilizado en Apteligent. | varchar(255) |
| **`mobileappperformancecrashid`** | Se utiliza en el conector de datos Apteligent. ID de bloqueo utilizado en Apteligent. | varchar(255) |
| **`mobileappstoreobjectid`** | Se utiliza en el conector de datos [!DNL Appfigures]. ID de objeto de App Store. | varchar(255) |
| **`mobilebeaconmajor`** | Señalización principal de Mobile Services | varchar(100) |
| **`mobilebeaconminor`** | Señalización menor de Mobile Services | varchar(100) |
| **`mobilebeaconproximity`** | Proximidad de la señalización de Mobile Services | varchar(255) |
| **`mobilebeaconuuid`** | UUID de señalización de Mobile Services | varchar(100) |
| **`mobilecampaigncontent`** | Nombre o ID del contenido que muestra el vínculo. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| **`mobilecampaignmedium`** | Medio de marketing, como banner o correo electrónico. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| **`mobilecampaignname`** | El nombre de la campaña, también almacenado en la variable de campaña. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| **`mobilecampaignsource`** | Referente original, como newsletter o red de medios sociales. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| **`mobilecampaignterm`** | Palabras clave pagas u otros términos que desee rastrear con esta adquisición. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| **`mobiledayofweek`** | Número del día de la semana en que se abrió la aplicación. | varchar(255) |
| **`mobiledayssincefirstuse`** | Cantidad de días desde que la aplicación se ejecutó por primera vez. | varchar(255) |
| **`mobiledayssincelastuse`** | Cantidad de días desde que la aplicación se ejecutó por última vez. | varchar(255) |
| **`mobiledeeplinkid`** | Recopilado desde la variable de datos de contexto `a.deeplink.id`. Se utiliza en los informes de adquisición como identificador para el vínculo de adquisición móvil. | varchar(255) |
| **`mobiledevice`** | Nombre del dispositivo móvil. En iOS, se almacena como una cadena de 2 dígitos separados por comas. El primer número representa la generación del dispositivo y el segundo número representa la familia del dispositivo. | varchar(255) |
| **`mobilehourofday`** | Define la hora del día en que se inició la aplicación. Sigue el formato numérico de 24 horas. | varchar(255) |
| **`mobileinstalldate`** | Fecha de instalación del móvil. Proporciona la fecha de la primera vez que se abre la aplicación móvil. | varchar(255) |
| **`mobilelaunchnumber`** | Incrementa de uno en uno cada vez que se abre la aplicación móvil. | varchar(255) |
| **`mobilemessagebuttonname`** | Recopilado desde la variable de datos de contexto `a.message.button.id`. Se utiliza para la mensajería integrada en la aplicación con el objetivo de identificar el botón que cerró el mensaje. | varchar(100) |
| **`mobilemessageid`** | ID de mensaje en la aplicación | varchar(255) |
| **`mobilemessageonline`** | Mensaje en línea en la aplicación | varchar(255) |
| **`mobilemessagepushoptin`** | Recopilado desde la variable de datos de contexto `a.push.optin`. Se establece en “true” cuando el usuario opta por la mensajería emergente; de lo contrario, el valor es “false”. | varchar(255) |
| **`mobilemessagepushpayloadid`** | Recopilado desde la variable de datos de contexto `a.push.payloadid`. Se utiliza en los mensajes emergentes como identificador de carga útil. | varchar(255) |
| **`mobileosversion`** | Versión del sistema operativo de Mobile Services | varchar(255) |
| **`mobileplaceaccuracy`** | Recopilado desde la variable de datos de contexto `a.loc.acc`. Indica la precisión del GPS en metros en el momento de la recogida. | varchar(255) |
| **`mobileplacecategory`** | Recopilado desde la variable de datos de contexto `a.loc.category`. Describe la categoría de un lugar específico. | varchar(255) |
| **`mobileplaceid`** | Recopilado desde la variable de datos de contexto `a.loc.id`. Identificador de un punto de interés determinado. | varchar(255) |
| **`mobilepushoptin`** | Inclusión push de Mobile Services | varchar(255) |
| **`mobilepushpayloadid`** | ID de carga útil push de Mobile Services | varchar(255) |
| **`mobilerelaunchcampaigncontent`** | Contenido de inicio de Mobile Services | varchar(255) |
| **`mobilerelaunchcampaignmedium`** | Medio de inicio de Mobile Services | varchar(255) |
| **`mobilerelaunchcampaignsource`** | Origen del inicio de Mobile Services | varchar(255) |
| **`mobilerelaunchcampaignterm`** | Término de inicio de Mobile Services | varchar(255) |
| **`mobilerelaunchcampaigntrackingcode`** | Recopilado desde la variable de datos de contexto `a.launch.campaign.trackingcode`. Se utiliza en la adquisición como código de seguimiento para la campaña de inicio. | varchar(255) |
| **`mobileresolution`** | Resolución del dispositivo móvil. `[Width] x [Height]` en píxeles. | varchar(255) |
| **`monthly_visitor`** | Un indicador que determina si el visitante es único en el mes actual. | tinyint sin firmar |
| **`mvvar1`** - `mvvar3` | [Valores de variable de lista](/help/implement/vars/page-vars/list.md). Contiene una lista delimitada de valores personalizados en función de la implementación. Las columnas `post_mvvar1` - `post_mvvar3` reemplazan el delimitador original por `--**--`. | texto |
| **`mvvar1_instances`** - `mvvar3_instances` | Los valores de variable de lista que se establecieron en la visita actual. Reemplaza el delimitador original por `--**--`. Las columnas `post` no suelen contener datos. | texto |
| **`new_visit`** | Un indicador que determina si la visita actual es una visita nueva. Configurado por Adobe tras 30 minutos de inactividad de la visita. | tinyint sin firmar |
| **`os`** | ID numérica que representa el sistema operativo del visitante. Se basa en la columna`user_agent`. El valor clave de `operating_system.tsv` búsqueda estándar y `operating_system_type.tsv` [Búsqueda dinámica](dynamic-lookups.md). | int sin firmar |
| **`page_event`** | El tipo de visita que se envía en la solicitud de imagen (visita estándar, vínculo de descarga, vínculo personalizado, vínculo de salida). Consulte [Búsqueda de evento de página](datafeeds-page-event.md). | tinyint sin firmar |
| **`page_event_var1`** | Solo se utiliza en solicitudes de imagen de seguimiento de vínculos. Dirección URL del vínculo de descarga, de salida o personalizado en el que se hizo clic. | texto |
| **`page_event_var2`** | Solo se utiliza en solicitudes de imagen de seguimiento de vínculos. El nombre personalizado (si se especifica) del vínculo. Establece [vínculo personalizado](/help/components/dimensions/custom-link.md), [vínculo de descarga](/help/components/dimensions/download-link.md) o [vínculo de salida](/help/components/dimensions/exit-link.md) según el valor de `page_event`. | varchar(100) |
| **`page_type`** | Dimensión [Páginas no encontradas](/help/components/dimensions/pages-not-found.md), que se usa generalmente para páginas 404. | char(20) |
| **`page_url`** | La URL de la visita. Tenga en cuenta que `post_page_url` se ha eliminado para las solicitudes de imagen de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)) y usa un tipo de datos de varchar(255). | texto |
| **`pagename`** | La dimensión [Página](/help/components/dimensions/page.md). Si la variable [`pagename`](/help/implement/vars/page-vars/pagename.md) está vacía, Analytics utiliza `page_url` en su lugar. | varchar(100) |
| **`pagename_no_url`** | Similar a `pagename`, excepto que no vuelve a `page_url`. Solo la columna `post` está disponible. | varchar(100) |
| **`paid_search`** | Un indicador que determina si la visita coincide con la detección de búsqueda de pago. | tinyint sin firmar |
| **`persistent_cookie`** | Se utiliza en la dimensión [Compatibilidad con cookies persistentes](/help/components/dimensions/persistent-cookie-support.md). Indica si el visitante admite cookies que no se descartan después de cada visita. | char(1) |
| **`pointofinterest`** | Nombre del punto de interés de Mobile Services | varchar(255) |
| **`pointofinterestdistance`** | Distancia de Mobile Services al centro de puntos de interés | varchar(255) |
| Columnas **`post_`** | Contiene el valor que se utiliza finalmente en los informes. Cada columna post se rellena después de la lógica del lado del servidor, las reglas de procesamiento y las reglas de VISTA. Adobe recomienda usar columnas de publicación en la mayoría de los casos. | Consulte la columna correspondiente no posterior |
| **`product_list`** | La variable de página [`products`](/help/implement/vars/page-vars/products.md). Ayuda a rellenar varias dimensiones y métricas, entre ellas [Categoría](/help/components/dimensions/category.md), [Producto](/help/components/dimensions/product.md), [Unidades](/help/components/metrics/units.md) e [Ingresos](/help/components/metrics/revenue.md). | texto |
| **`prop1`** - `prop75` | Variables de tráfico personalizadas 1-75. Se utiliza en dimensiones [Prop](/help/components/dimensions/prop.md). | varchar(100) |
| **`purchaseid`** | Identificador único de una compra, tal y como se establece mediante la variable [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). Lo utiliza la columna `duplicate_purchase`. | char(20) |
| **`quarterly_visitor`** | Un indicador que determina si la visita es un visitante nuevo trimestral. | tinyint sin firmar |
| **`ref_domain`** | La dimensión [Dominio de referencia](/help/components/dimensions/referring-domain.md). Basado en la columna `referrer`. | varchar(100) |
| **`ref_type`** | ID numérico que representa el tipo de referente de la visita. Se utiliza en la dimensión [Tipo de referente](/help/components/dimensions/referrer-type.md). <p>1: Dentro del sitio</p><p>2: Otros sitios web</p> <p>3: Motores de búsqueda</p> <p>4: Disco duro</p> <p>5: USENET</p> <p>6: Escrito o añadido como marcador (sin referente)</p> <p>7: Correo electrónico</p> <p>8: Sin JavaScript</p> <p>9: Redes sociales</p><p>10: Herramientas de IA conversacional</p> | tinyint sin firmar |
| **`referrer`** | La dimensión [Referente](/help/components/dimensions/referrer.md). Tenga en cuenta que mientras `referrer` utiliza un tipo de datos de varchar(255), `post_referrer` emplea un tipo de datos de varchar(244). | varchar(255) |
| **`resolution`** | ID numérico que representa la resolución del monitor. Se utiliza en la dimensión [Resolución del monitor](/help/components/dimensions/monitor-resolution.md). Utiliza la tabla de búsqueda `resolution.tsv`. | smallint sin firmar |
| **`s_kwcid`** | ID de palabra clave utilizado en las integraciones de Adobe Advertising. | varchar(255) |
| **`s_resolution`** | Valor no procesado de resolución de pantalla. Se recopila mediante la función de JavaScript `screen.width x screen.height`. | char(20) |
| **`search_engine`** | ID numérica que representa el motor de búsqueda que refirió al visitante a su sitio. Se utiliza en [dimensiones del motor de búsqueda](/help/components/dimensions/search-engine.md). Se remite a la tabla de búsqueda `search_engines.tsv`. | smallint sin firmar |
| **`search_page_num`** | Lo utiliza la dimensión [Rango de todas las páginas de búsqueda](/help/components/dimensions/all-search-page-rank.md). Indica en qué página de resultados de búsqueda apareció su sitio antes de que se hiciera clic para acceder a él. | smallint sin firmar |
| **`secondary_hit`** | Un indicador que determina si la visita es una visita secundaria. Este indicador generalmente se origina a partir del etiquetado de grupos múltiples y las reglas de VISTA que copian las visitas. | tinyint sin firmar |
| **`sourceid`** | ID de origen | int sin firmar |
| **`state`** | Variable de estado. | varchar(50) |
| **`stats_server`** | No es útil. Servidor interno de Adobe que ha procesado la visita. | char(30) |
| **`t_time_info`** | Hora local del visitante. El formato es: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| **`tnt`** | Se utiliza en las integraciones de Adobe Target. Representa todas las pruebas para las que está cualificado actualmente. El formato es: `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`. | texto |
| **`tnt_action`** | Se utiliza en las integraciones de Adobe Target. Representa todas las pruebas para las que se calificó la visita. | texto |
| **`tnt_instances`** | Se utiliza en las integraciones de Adobe Target. Variable de instancias de Target. | texto |
| **`transactionid`** | Un identificador exclusivo donde, más tarde, se pueden cargar diversos puntos de datos a través de fuentes de datos. Recopilado mediante la variable [`transactionID`](/help/implement/vars/page-vars/transactionid.md). | texto |
| **`truncated_hit`** | Un indicador que indica que se truncó la solicitud de imagen. Indica que se ha recibido una visita parcial. <br>S: Se truncó la visita; visita parcial recibida <br>N: La visita no se truncó; visita completa recibida | char(1) |
| **`user_agent`** | La cadena del agente de usuario enviada en el encabezado HTTP de la solicitud de imagen. | texto |
| **`user_hash`** | No es útil. Hash en el ID del grupo de informes. Utilice `username` en su lugar. | int sin firmar |
| **`user_server`** | Utilizado en la dimensión [Servidor](/help/components/dimensions/server.md). | varchar(100) |
| **`userid`** | No es útil. ID numérica de la ID del grupo de informes. Utilice `username` en su lugar. | int sin firmar |
| **`username`** | ID del grupo de informes para la visita. | char(40) |
| **`va_closer_detail`** | La dimensión [Detalles de último contacto](/help/components/dimensions/last-touch-detail.md). | varchar(255) |
| **`va_closer_id`** | Identificador numérico que identifica la dimensión [Canal de último contacto](/help/components/dimensions/last-touch-channel.md). La búsqueda de este ID se encuentra en el Administrador de canales de marketing. | tinyint sin firmar |
| **`va_finder_detail`** | La dimensión [Detalles de primer contacto](/help/components/dimensions/first-touch-detail.md). | varchar(255) |
| **`va_finder_id`** | Identificador numérico que identifica la dimensión [Canal de primer contacto](/help/components/dimensions/first-touch-channel.md). La búsqueda de este ID se encuentra en el Administrador de canales de marketing. | tinyint sin firmar |
| **`va_instance_event`** | Un indicador que identifica el canal de marketing [Instancias](/help/components/metrics/instances.md). | tinyint sin firmar |
| **`va_new_engagement`** | Un indicador que identifica las [nuevas participaciones](/help/components/metrics/new-engagements.md) del canal de marketing. | tinyint sin firmar |
| **`video`** | La dimensión de servicios de medios de transmisión [Contenido](/help/components/dimensions/sm-core.md). | varchar(255) |
| **`videoad`** | La dimensión de servicios de medios de streaming [Ad](/help/components/dimensions/sm-ads.md). | varchar(255) |
| **`videoadinpod`** | La dimensión de servicios de medios de streaming [Ad in pod position](/help/components/dimensions/sm-ads.md). | varchar(255) |
| **`videoadlength`** | La dimensión [Longitud del anuncio (variable)](/help/components/dimensions/sm-ads.md) de servicios de medios de transmisión. | entero |
| **`videoadload`** | El [anuncio carga](/help/components/dimensions/sm-ads.md) la dimensión de servicios de medios de transmisión. | varchar(255) |
| **`videoadname`** | La dimensión [Nombre del anuncio (variable)](/help/components/dimensions/sm-ads.md) de servicios de medios de transmisión. | varchar(255) |
| **`videoadplayername`** | La dimensión de servicios de medios de streaming [Nombre del reproductor del anuncio](/help/components/dimensions/sm-ads.md). | varchar(255) |
| **`videoadpod`** | La dimensión de servicios de medios de streaming [Ad pod](/help/components/dimensions/sm-ads.md). | varchar(255) |
| **`videoadvertiser`** | La dimensión de servicios de medios de streaming [Anunciante](/help/components/dimensions/sm-ads.md). | varchar(255) |
| **`videoaudioalbum`** | La dimensión de servicios de medios de transmisión [Album](/help/components/dimensions/sm-audio-metadata.md). | varchar(255) |
| **`videoaudioartist`** | La dimensión de servicios de medios de streaming [Artist](/help/components/dimensions/sm-audio-metadata.md). | varchar(255) |
| **`videoaudioauthor`** | La dimensión de servicios de medios de streaming [Author](/help/components/dimensions/sm-audio-metadata.md). | varchar(255) |
| **`videoaudiolabel`** | La dimensión de servicios de medios de streaming [Label](/help/components/dimensions/sm-audio-metadata.md). | varchar(255) |
| **`videoaudiopublisher`** | La dimensión de servicios de medios de transmisión [Publicador](/help/components/dimensions/sm-audio-metadata.md). | varchar(255) |
| **`videoaudiostation`** | La dimensión de servicios de medios de transmisión [Station](/help/components/dimensions/sm-audio-metadata.md). | varchar(255) |
| **`videocampaign`** | La dimensión de servicios de medios de streaming [Campaign ID](/help/components/dimensions/sm-ads.md). | varchar(255) |
| **`videochannel`** | La dimensión de servicios de medios de transmisión [Canal de contenido](/help/components/dimensions/sm-core.md). | varchar(255) |
| **`videochapter`** | La dimensión de servicios de medios de transmisión [Chapter](/help/components/dimensions/sm-chapters.md). | varchar(255) |
| **`videocontenttype`** | La dimensión de servicios de medios de transmisión [Tipo de contenido](/help/components/dimensions/sm-core.md). | varchar(255) |
| **`videodaypart`** | La dimensión de servicios de medios de streaming [Day part](/help/components/dimensions/sm-video-metadata.md). | varchar(255) |
| **`videoepisode`** | La dimensión de servicios de medios de transmisión [Episode](/help/components/dimensions/sm-video-metadata.md). | varchar(255) |
| **`videofeedtype`** | La dimensión de servicios de medios de streaming [Tipo de fuente de medios](/help/components/dimensions/sm-video-metadata.md). | varchar(255) |
| **`videogenre`** | La dimensión de servicios de medios de streaming [Genre](/help/components/dimensions/sm-video-metadata.md). Esta dimensión permite varios valores en la misma visita, delimitados por una coma. | texto |
| **`videolength`** | La dimensión [Longitud del contenido (variable)](/help/components/dimensions/sm-core.md) de los servicios de medios de transmisión. | entero |
| **`videomvpd`** | La dimensión de servicios de medios de streaming [MVPD](/help/components/dimensions/sm-video-metadata.md). | varchar(255) |
| **`videoname`** | La dimensión de servicios de medios de transmisión [Content name (variable)](/help/components/dimensions/sm-core.md). | varchar(255) |
| **`videonetwork`** | La dimensión de servicios de medios de transmisión [Red](/help/components/dimensions/sm-video-metadata.md). | varchar(255) |
| **`videopath`** | La dimensión de servicios de medios de transmisión [Ruta de medios](/help/components/dimensions/sm-core.md). | varchar(100) |
| **`videoplayername`** | La dimensión de servicios de medios de transmisión [Nombre del reproductor de contenido](/help/components/dimensions/sm-core.md). | varchar(255) |
| **`videotime`** | La métrica de servicios de medios de streaming [Tiempo invertido en contenido](/help/components/metrics/sm-core.md). | entero |
| **`videoqoebitrateaverageevar`** | La dimensión de servicios de medios de transmisión [Velocidad de bits promedio](/help/components/dimensions/sm-quality.md). | varchar(255) |
| **`videoqoebitratechangecountevar`** | La [velocidad de bits cambia](/help/components/dimensions/sm-quality.md) la dimensión de servicios de medios de transmisión. | varchar(255) |
| **`videoqoebuffercountevar`** | La dimensión de servicios de medios de transmisión [Eventos de búfer](/help/components/dimensions/sm-quality.md). | varchar(255) |
| **`videoqoebuffertimeevar`** | La dimensión [Duración total del búfer](/help/components/dimensions/sm-quality.md) de los servicios de medios de transmisión. | varchar(255) |
| **`videoqoedroppedframecountevar`** | La dimensión de servicios de medios de transmisión [fotogramas perdidos](/help/components/dimensions/sm-quality.md). | varchar(255) |
| **`videoqoeerrorcountevar`** | La dimensión de servicios de medios de transmisión [Errores](/help/components/dimensions/sm-quality.md). | varchar(255) |
| **`videoqoeextneralerrors`** | La dimensión [ID de error externo](/help/components/dimensions/sm-quality.md) de servicios de medios de transmisión. Esta dimensión permite varios valores en la misma visita. | texto |
| **`videoqoeplayersdkerrors`** | La dimensión de servicios de medios de streaming [ID de error del reproductor SDK](/help/components/dimensions/sm-quality.md). Esta dimensión permite varios valores en la misma visita. | texto |
| **`videoqoetimetostartevar`** | La dimensión de servicios de medios de transmisión [Hora de inicio](/help/components/dimensions/sm-quality.md). | varchar(255) |
| **`videoseason`** | La dimensión de servicios de medios de streaming [Season](/help/components/dimensions/sm-video-metadata.md). | varchar(255) |
| **`videosegment`** | La dimensión de servicios de medios de transmisión [Segmento de contenido](/help/components/dimensions/sm-core.md). | varchar(255) |
| **`videoshow`** | La dimensión de servicios de medios de streaming [Show](/help/components/dimensions/sm-video-metadata.md). | varchar(255) |
| **`videoshowtype`** | La dimensión de servicios de medios de streaming [Tipo de programa](/help/components/dimensions/sm-video-metadata.md). | varchar(255) |
| **`videostreamtype`** | La dimensión [Tipo de emisión](/help/components/dimensions/sm-core.md) de servicios de medios de transmisión. | varchar(255) |
| **`visid_high`** | Se utiliza con `visid_low` para identificar un visitante de forma exclusiva. | bigint sin firmar |
| **`visid_low`** | Se utiliza con `visid_high` para identificar un visitante de forma exclusiva. | bigint sin firmar |
| **`visid_new`** | Un indicador que determina si la visita contiene un ID de visitante recién generado. | char(1) |
| **`visid_timestamp`** | Si se genera un ID de visitante recientemente, proporciona la marca de tiempo en UNIX® la hora en la que se generó el ID de visitante. | int |
| **`visid_type`** | No para uso externo; Adobe lo utiliza internamente para procesar optimizaciones. ID numérica que representa el método utilizado para identificar al visitante.<br>`0`: ID de visitante personalizado o desconocido/no aplicable<br>`1`: IP y reserva del agente de usuario <br>`2`: encabezado de suscriptor móvil HTTP <br>`3`: valor de la cookie heredada (`s_vi`) <br>`4`: valor de la cookie de reserva (`s_fid`) <br>`5`: servicio de identidad | tinyint sin firmar |
| **`visit_keywords`** | Dimensión [Search keyword](/help/components/dimensions/search-keyword.md). Esta columna utiliza un límite de caracteres no estándar de varchar(244) para dar cabida a la lógica back-end que utiliza Adobe. | varchar(244) |
| **`visit_num`** | La dimensión [Número de visita](/help/components/dimensions/visit-number.md). Empieza en 1 y aumenta cada vez que se inicia una nueva visita por visitante. | int sin firmar |
| **`visit_page_num`** | La dimensión [Profundidad de la visita](/help/components/dimensions/hit-depth.md). Aumenta en 1 por cada visita que genera el visitante. Restablece cada visita. | int sin firmar |
| **`visit_ref_domain`** | Se basa en la columna `visit_referrer`. El primer dominio de referencia de la visita. | varchar(100) |
| **`visit_ref_type`** | ID numérica que representa el tipo de referente del primer referente de la visita. Se remite a la tabla de búsqueda `referrer_type.tsv`. | tinyint sin firmar |
| **`visit_referrer`** | El primer referente de la visita. | varchar(255) |
| **`visit_search_engine`** | ID numérica que representa el primer motor de búsqueda de la visita. Se remite a la tabla de búsqueda `search_engines.tsv`. | smallint sin firmar |
| **`visit_start_page_url`** | La primera URL de la visita. | varchar(255) |
| **`visit_start_pagename`** | El valor Nombre de página en la primera visita individual de la visita. | varchar(100) |
| **`visit_start_time_gmt`** | Marca de tiempo (en tiempo UNIX®) de la primera visita. | int |
| **`weekly_visitor`** | Un indicador que determina si la visita es un visitante nuevo semanal. | tinyint sin firmar |
| **`yearly_visitor`** | Un indicador que determina si la visita es un visitante nuevo anual. | tinyint sin firmar |
| **`zip`** | Ayuda a rellenar la dimensión [Código postal](/help/components/dimensions/zip-code.md). Consulte también `geo_zip`. | varchar(50) |

{style="table-layout:auto"}

## Columnas no utilizadas o retiradas

La siguiente lista de columnas no se utiliza, se retira o no contiene valor en los informes. Algunas de estas columnas están vinculadas a características que se han puesto de sol, mientras que otras ya no son necesarias debido a características nuevas y más sólidas. La mayoría de estas columnas no contienen datos; las columnas que podrían contener datos no son compatibles con las bibliotecas de recopilación de datos actuales y no son dimensiones disponibles en Analysis Workspace.

* `adclassificationcreative`
* `click_action`
* `click_action_type`
* `click_context`
* `click_context_type`
* `click_sourceid`
* `click_tag`
* `hier1` - `hier5`
* `homepage`
* `ip2`
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
* `mobiledayssincelastupgrade`
* `mobiledeeplinkid.name`
* `mobileinstalls`
* `mobilelaunches`
* `mobilelaunchessincelastupgrade`
* `mobileltv`
* `mobileltvtotal`
* `mobilemessageclicks`
* `mobilemessageid.dest`
* `mobilemessageid.name`
* `mobilemessageid.type`
* `mobilemessageimpressions`
* `mobilemessagepushpayloadid.name`
* `mobilemessageviews`
* `mobilemonthlyengagedusers`
* `mobileosenvironment`
* `mobileplacedwelltime`
* `mobileplaceentry`
* `mobileplaceexit`
* `mobileprevsessionlength`
* `mobilerelaunchcampaigntrackingcode.name`
* `mobileupgrades`
* `namespace`
* `p_plugins`
* `page_event_var3`
* `partner_plugins`
* `plugins`
* `prev_page`
* `product_merchandising`
* `sampled_hit`
* `service`
* `socialaccountandappids`
* `socialassettrackingcode`
* `socialauthor`
* `socialaveragesentiment`
* `socialaveragesentiment (deprecated)`
* `socialcontentprovider`
* `socialfbstories`
* `socialfbstorytellers`
* `socialinteractioncount`
* `socialinteractiontype`
* `sociallanguage`
* `sociallatlong`
* `sociallikeadds`
* `sociallink`
* `sociallink (deprecated)`
* `socialmentions`
* `socialowneddefinitioninsighttype`
* `socialowneddefinitioninsightvalue`
* `socialowneddefinitionmetric`
* `socialowneddefinitionpropertyvspost`
* `socialownedpostids`
* `socialownedpropertyid`
* `socialownedpropertyname`
* `socialownedpropertypropertyvsapp`
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
* `survey`
* `survey_instances`
* `tnt_post_vista`
* `ua_color`
* `ua_os`
* `ua_pixels`
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

>[!MORELIKETHIS]
>
>[Asignación de variables de objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md)
>[Asignación de variables de objeto de datos &#x200B;](/help/implement/aep-edge/data-var-mapping.md)
