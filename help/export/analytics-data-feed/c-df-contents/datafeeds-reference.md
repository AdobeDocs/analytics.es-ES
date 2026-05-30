---
description: Datos de tabla que describen las columnas de las fuentes de datos.
keywords: Fuentes de datos, columnas
subtopic: data feeds
title: Referencia de columnas de datos
feature: Data Feeds
exl-id: e1492147-6e7f-4921-b509-898e7efda596
TQID: https://experienceleague.adobe.com/EcbkWUUxHG0e3O8f9f8G5yBAqYHb-tocQygeWY2Zqfc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: b7156124-d291-4de4-ac0c-ed17d8078449
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
  - id: c9bb7ea6-c04f-4262-b69c-fbb8d91e3559
  - id: ce57bdb9-8bbb-4c80-b9ab-e52598027bb9
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: fe0a7292-80bc-407a-b456-64170267d1cc
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 056ca9d821d97cc6109266e3fb8c8aec9d66792a
workflow-type: tm+mt
source-wordcount: 4148
ht-degree: 78%

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

Las actualizaciones anteriores de esta tabla se encuentran en el [historial de confirmaciones en GitHub](https://github.com/AdobeDocs/analytics.es-ES/commits/main/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md).

| Publicar | Nombre de la columna | Descripción de la columna | Tipo de datos |
| ---: | :--- | --- | --- |
| | **`accept_language`** | Enumera todos los idiomas aceptados, tal como se indica en el encabezado Accept-Language-HTTP de las solicitudes de imagen. | char(20) |
| **`post_`** | **`adload`** | Cargas de anuncios de medios | varchar(255) |
| **`post_`** | **`aemassetid`** | Variable de varios valores que corresponde a los ID de recurso (GUID) de un conjunto de recursos de Adobe Experience Manager. Aumenta los eventos de impresión. | texto |
| **`post_`** | **`aemassetsource`** | Identifica el origen del evento del recurso. Se utiliza en Adobe Experience Manager. | varchar(255) |
| **`post_`** | **`aemclickedassetid`** | ID de recurso de un recurso de Adobe Experience Manager. Incrementa los eventos de clic. | varchar(255) |
| **`post_`** | **`amo_cid`** | La dimensión [AMO ID](/help/components/dimensions/amo-id.md), utilizada en las integraciones de Adobe Advertising. | varchar(255) |
| **`post_`** | **`amo_ef_id`** | La dimensión [AMO EF ID](/help/components/dimensions/amo-ef-id.md), utilizada en las integraciones de Adobe Advertising. | varchar(255) |
| | **`browser`** | Un ID numérico que representa el explorador. Se remite a la tabla de búsqueda `browser.tsv`. | int sin firmar |
| **`post_`** | **`browser_height`** | La dimensión [Altura del explorador](/help/components/dimensions/browser-height.md). | smallint sin firmar |
| **`post_`** | **`browser_width`** | El [Ancho del explorador](/help/components/dimensions/browser-width.md) | smallint sin firmar |
| **`post_`** | **`campaign`** | La dimensión [Código de seguimiento](/help/components/dimensions/tracking-code.md). | varchar(255) |
| | **`carrier`** | Variable de integración de Adobe Advertising. Especifica el operador de telefonía móvil. El valor clave de `carrier.tsv` [Búsqueda dinámica](dynamic-lookups.md). | varchar(100) |
| **`post_`** | **`channel`** | La dimensión [Secciones del sitio](/help/components/dimensions/site-section.md). | varchar(100) |
| | **`ch_hdr`** | Sugerencias del cliente recopiladas mediante el encabezado de petición HTTP. | texto |
| | **`ch_js`** | Sugerencias del cliente recopiladas mediante la API de JavaScript de sugerencias del cliente agente de usuario. | texto |
| **`post_`** | **`clickmaplink`** | La dimensión [vínculo de Activity Map](/help/components/dimensions/activity-map-link.md). | varchar(255) |
| **`post_`** | **`clickmaplinkbyregion`** | La dimensión [vínculo de Activity Map por región](/help/components/dimensions/activity-map-link-by-region.md). | varchar(255) |
| **`post_`** | **`clickmappage`** | La dimensión [página de Activity Map](/help/components/dimensions/activity-map-page.md). | varchar(255) |
| **`post_`** | **`clickmapregion`** | La dimensión [región de Activity Map](/help/components/dimensions/activity-map-region.md). | varchar(255) |
| | **`code_ver`** | Versión de la API o del SDK cliente utilizado para compilar y enviar la solicitud de imagen. | char(16) |
| | **`color`** | ID de profundidad de color basada en el valor de la columna `c_color`. Se remite a la tabla de búsqueda `color_depth.tsv`. | smallint sin firmar |
| | **`connection_type`** | ID numérica que representa la dimensión [Tipo de conexión](/help/components/dimensions/connection-type.md). Se remite a la tabla de búsqueda `connection_type.tsv`. | tinyint sin firmar |
| **`post_`** | **`cookies`** | Dimensión [Compatibilidad con cookies](/help/components/dimensions/cookie-support.md).<br>Y: Habilitado<br>N: Deshabilitado<br>U: Desconocido | char(1) |
| | **`country`** | Un ID numérico que representa el país del visitante. Se remite a la tabla de búsqueda `country.tsv`. | smallint sin firmar |
| **`post_`** | **`currency`** | El código de moneda que se ha utilizado durante la transacción. Configurado mediante [`currencyCode`](/help/implement/vars/config-vars/currencycode.md). | char(8) |
| | **`ct_connect_type`** | En relación con la columna `connection_type`. Los valores más comunes son LAN/Wi-Fi, operador de telefonía móvil y módem. | char(20) |
| | **`curr_factor`** | Determina la posición decimal de la moneda. Se utiliza para la conversión de moneda. Por ejemplo, USD utiliza dos decimales, por lo que el valor de esta columna sería `2`. | tinyint |
| | **`curr_rate`** | El tipo de cambio cuando se produjo la transacción. Adobe se asocia con XE para determinar el tipo de cambio del día actual. | decimal(24,12) |
| **`post_`** | **`customer_perspective`** | Determina si la visita fue una visita móvil en segundo plano. Consulte [Sesiones según el contexto](/help/components/vrs/vrs-mobile-visit-processing.md) para obtener más información. | tinyint sin firmar |
| **`post_`** | **`cust_hit_time_gmt`** | Solo grupos de informes con marca de tiempo. La marca de tiempo enviada con la visita y basada en el Tiempo UNIX®. | int |
| **`post_`** | **`cust_visid`** | El ID de visitante personalizado, si se establece mediante [`visitorID`](/help/implement/vars/config-vars/visitorid.md). | varchar(255) |
| | **`c_color`** | Profundidad de bits de la paleta de colores. Se utiliza en el cálculo de la dimensión [Profundidad de color](/help/components/dimensions/color-depth.md). AppMeasurement utiliza la función JavaScript `screen.colorDepth()`. | char(20) |
| | **`daily_visitor`** | Un indicador que determina si la visita es un visitante nuevo diario. | tinyint sin firmar |
| | **`dataprivacyconsentoptin`** | Dimensión [Inclusión en la gestión del consentimiento](/help/components/dimensions/cm-opt-in.md). Puede haber varios valores por visita, separados por una barra vertical (`\|`). Los valores válidos incluyen `DMP` y `SELL`. | varchar(100) |
| | **`dataprivacyconsentoptout`** | Dimensión [Exclusión de la gestión del consentimiento](/help/components/dimensions/cm-opt-out.md). Puede haber varios valores por visita, separados por una barra vertical (`\|`). Los valores válidos incluyen `SSF`, `DMP` y `SELL`. | varchar(100) |
| | **`date_time`** | La hora de la visita en un formato legible, basada en la zona horaria del grupo de informes. | datetime |
| | **`domain`** | Dimensión [Dominio](/help/components/dimensions/domain.md). Basado en el punto de acceso a Internet del visitante. | varchar(100) |
| | **`duplicated_from`** | Solo se utiliza en los grupos de informes que contienen las reglas de VISTA de copia de visita. Indica de qué grupo de informes se copió la visita. | varchar(40) |
| | **`duplicate_events`** | Enumera cada evento que se contó como duplicado. | varchar(255) |
| | **`duplicate_purchase`** | Un indicador que determina que el evento de compra de esta visita se ignora porque es un duplicado. | tinyint sin firmar |
| **`post_`** | **`ef_id`** | El EF ID, utilizado en las integraciones de Adobe Advertising. | varchar(255) |
| **`post_`** | **`evar1 - evar250`** | Variables personalizadas 1-250. Se utiliza en dimensiones [eVar](/help/components/dimensions/evar.md). Cada organización utiliza las eVars de forma diferente. El mejor lugar para obtener más información sobre cómo su organización rellena las eVars respectivas sería un [documento de diseño de solución](/help/implement/prepare/solution-design.md) específico de su organización. | varchar(255) |
| **`post_`** | **`event_list`** | Lista separada por comas de los ID numéricos que representan los eventos activados en la visita. Incluye eventos de comercio y [eventos personalizados 1-1000](/help/components/metrics/custom-events.md). Utiliza la búsqueda `event.tsv`. | texto |
| | **`exclude_hit`** | Un indicador que determina si la visita se excluye de la creación de informes. La columna `visit_num` no se incrementa para las visitas excluidas.<br>1: No se usa. Parte de una característica desechada.<br>2: no se usa. Parte de una característica desechada.<br>3: ya no se usa. Exclusión de agente de usuario<br>4: Exclusión basada en la dirección IP<br>5: Falta información clave de visitas, como `page_url`, `pagename`, `page_event` o `event_list`<br>6: JavaScript no ha procesado la visita correctamente<br>7: Exclusión específica de la cuenta, como en reglas VISTA<br>8: Sin usar. Exclusión alternativa específica de la cuenta.<br>9: No se usa. Parte de una característica desechada.<br>10: Código de moneda no válido<br>11: La visita individual no contiene una marca de tiempo en un grupo de informes solo de marca de tiempo o una visita que contiene una marca de tiempo en un grupo de informes que no es de marca de hora<br>12: No se usa. Parte de una característica desechada.<br>13: No se usa. Parte de una característica desechada.<br>14: La visita de Target que no coincide con una visita de Analytics<br>15: No se usa actualmente.<br>16: La visita de Adobe Advertising que no coincide con una visita de Analytics | tinyint sin firmar |
| | **`first_hit_pagename`** | Dimensión [Página de entrada original](/help/components/dimensions/entry-dimensions.md). El nombre de la página de entrada original del visitante. | varchar(100) |
| | **`first_hit_page_url`** | La primera URL del visitante. | varchar(255) |
| | **`first_hit_referrer`** | La primera URL de referencia del visitante. | varchar(255) |
| | **`first_hit_ref_domain`** | Dimensión [Dominio de referencia original](/help/components/dimensions/original-referring-domain.md). Basado en `first_hit_referrer`. El primer dominio de referencia del visitante. | varchar(100) |
| | **`first_hit_ref_type`** | Un ID numérico que representa el tipo de referente del primer referente del visitante. Se remite a la tabla de búsqueda `referrer_type.tsv`. | tinyint sin firmar |
| | **`first_hit_time_gmt`** | Marca de tiempo de la primera visita del visitante en tiempo UNIX®. | int |
| | **`geo_city`** | El nombre de la ciudad de la que provino la visita basada en la dirección IP. Se utiliza en la dimensión [Cities](/help/components/dimensions/cities.md). | char(32) |
| | **`geo_country`** | Abreviatura del país del que provino la visita basada en la dirección IP. Se utiliza en la dimensión [Países.](/help/components/dimensions/countries.md) | char(4) |
| | **`geo_dma`** | Un ID numérico del área demográfica de la que provino la visita basada en la dirección IP. Se utiliza en la dimensión [US DMA](/help/components/dimensions/us-dma.md). | int sin firmar |
| | **`geo_region`** | El nombre del estado o región del que provino la visita basada en la dirección IP. Se utiliza en la dimensión [Regiones](/help/components/dimensions/regions.md). | char(32) |
| | **`geo_zip`** | El código postal del que provino la visita basada en la dirección IP. Ayuda a rellenar la dimensión [Código postal](/help/components/dimensions/zip-code.md). Consulte también `zip`. | varchar(16) |
| | **`hitid_high`** | Se utiliza en combinación con `hitid_low` para identificar una visita. | bigint sin firmar |
| | **`hitid_low`** | Se utiliza en combinación con `hitid_high` para identificar una visita. | bigint sin firmar |
| | **`hit_source`** | Indica la fuente de la que provino la visita. Se facturan las fuentes de visitas 1 y 2. <br>1: Solicitud de imagen estándar sin marca de tiempo <br>2: Solicitud de imagen estándar con marca de tiempo <br>3: Carga del origen de datos activo con marcas de tiempo <br>4: No utilizado <br>5: Carga genérica del origen de datos <br>6: Ya no se utiliza; carga completa del origen de datos de procesamiento <br>7: Carga del origen de datos TransactionID <br>8: Ya no se utiliza; Versiones anteriores de los orígenes de datos de Adobe Advertising <br>9: Ya no se utiliza; Métricas de resumen de Adobe Social <br>10: Reenvío del lado del servidor de Audience Manager utilizado | tinyint sin firmar |
| | **`hit_time_gmt`** | La marca de tiempo de los servidores de recopilación de datos de visitas de Adobe que recibieron la visita, basada en el tiempo UNIX®. | int |
| | **`hourly_visitor`** | Un indicador que determina si la visita es un visitante nuevo por hora. | tinyint sin firmar |
| | **`ip`** | La dirección IPv4, basada en el encabezado HTTP de la solicitud de imagen. Exclusivo de forma mutua para `ipv6`; si esta columna contiene una dirección IP no oculta, `ipv6` está en blanco. | char(20) |
| | **`ipv6`** | La dirección IPv6 comprimida, si está disponible. Exclusivo de forma mutua para `ip`; si esta columna contiene una dirección IP no oculta, `ip` está en blanco. | varchar(40) |
| | **`javascript`** | ID de búsqueda de la versión de JavaScript basado en `j_jscript`. Se remite a la tabla de búsqueda `javascript_version`. | tinyint sin firmar |
| **`post_`** | **`java_enabled`** | [[!UICONTROL Java habilitado]](/help/components/dimensions/java-enabled.md). <br>S: Habilitado<br>N: No habilitado<br>D: Desconocido | char(1) |
| | **`j_jscript`** | Versión de JavaScript admitida por el explorador. | char(5) |
| | **`language`** | ID numérico que representa el idioma del visitante. Se remite a la tabla de búsqueda `languages.tsv`. | smallint sin firmar |
| | **`last_hit_time_gmt`** | Marca de tiempo (en tiempo UNIX®) de la visita anterior. Se utiliza para calcular la dimensión [[!UICONTROL Días desde la última visita]](/help/components/dimensions/days-since-last-visit.md). | int |
| | **`last_purchase_num`** | Dimensión [Lealtad del cliente](/help/components/dimensions/customer-loyalty.md). Indica la cantidad de compras anteriores que realizó el visitante. <br>0: Sin compras previas (no es un cliente) <br>1: Una compra anterior (nuevo cliente) <br>2: Dos compras anteriores (cliente de devolución) <br>3: Tres o más compras anteriores (cliente fiel) | int sin firmar |
| | **`last_purchase_time_gmt`** | Se utiliza para calcular la dimensión [[!UICONTROL Días desde la última compra]](/help/components/dimensions/days-since-last-purchase.md). Marca de tiempo (en tiempo UNIX®) de la última compra realizada. Para la primera compra y para los visitantes que no hayan realizado ninguna compra anteriormente, este valor es `0`. | int |
| | **`latlon1`** | Ubicación (menos de 10 km) | varchar(255) |
| | **`latlon23`** | Ubicación (menos de 100 m) | varchar(255) |
| | **`latlon45`** | Ubicación (menos de 1 m) | varchar(255) |
| | **`mcvisid`** | ID de visitante de CX Enterprise. Número de 128 bits formado por dos números concatenados de 64 bits con relleno hasta 19 dígitos. | varchar(255) |
| **`post_`** | **`mc_audiences`** | Lista de ID de segmento de Audience Manager a los que pertenece el visitante. La columna `post_mc_audiences` cambia el delimitador a `--**--`. | texto |
| **`post_`** | **`mobileaction`** | Acción móvil. Se recopila automáticamente cuando se llama a `trackAction` en implementaciones móviles. Permite establecer automáticamente las rutas de acción en la aplicación. | varchar(100) |
| **`post_`** | **`mobileappid`** | ID de la aplicación móvil. Almacena el nombre y la versión de la aplicación en el siguiente formato: `[AppName] [BundleVersion]`. | varchar(255) |
| | **`mobileappperformanceappid`** | Se utiliza en el conector de datos Apteligent. El ID de la aplicación utilizado en Apteligent. | varchar(255) |
| | **`mobileappperformancecrashid`** | Se utiliza en el conector de datos Apteligent. ID de bloqueo utilizado en Apteligent. | varchar(255) |
| | **`mobileappstoreobjectid`** | Se utiliza en el conector de datos [!DNL Appfigures]. ID de objeto de App Store. | varchar(255) |
| | **`mobilebeaconmajor`** | Señalización principal de Mobile Services | varchar(100) |
| | **`mobilebeaconminor`** | Señalización menor de Mobile Services | varchar(100) |
| | **`mobilebeaconproximity`** | Proximidad de la señalización de Mobile Services | varchar(255) |
| | **`mobilebeaconuuid`** | UUID de señalización de Mobile Services | varchar(100) |
| **`post_`** | **`mobilecampaigncontent`** | Nombre o ID del contenido que muestra el vínculo. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| **`post_`** | **`mobilecampaignmedium`** | Medio de marketing, como banner o correo electrónico. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| **`post_`** | **`mobilecampaignname`** | Nombre de la campaña, también almacenada en la variable de campaña. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| **`post_`** | **`mobilecampaignsource`** | Referente original, como newsletter o red de medios sociales. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| **`post_`** | **`mobilecampaignterm`** | Palabras clave pagas u otros términos que desee rastrear con esta adquisición. Rellenado por Adquisición de aplicación móvil. | varchar(255) |
| **`post_`** | **`mobiledayofweek`** | Número del día de la semana en que se abrió la aplicación. | varchar(255) |
| **`post_`** | **`mobiledayssincefirstuse`** | Cantidad de días desde que la aplicación se ejecutó por primera vez. | varchar(255) |
| **`post_`** | **`mobiledayssincelastuse`** | Cantidad de días desde que la aplicación se ejecutó por última vez. | varchar(255) |
| | **`mobiledeeplinkid`** | Recopilado desde la variable de datos de contexto `a.deeplink.id`. Se utiliza en los informes de adquisición como identificador para el vínculo de adquisición móvil. | varchar(255) |
| **`post_`** | **`mobiledevice`** | Nombre del dispositivo móvil. En iOS, se almacena como una cadena de 2 dígitos separados por comas. El primer número representa la generación del dispositivo y el segundo representa miembros diferentes de la familia del dispositivo. | varchar(255) |
| **`post_`** | **`mobilehourofday`** | Define la hora del día en que se inició la aplicación. Sigue el formato numérico de 24 horas. | varchar(255) |
| **`post_`** | **`mobileinstalldate`** | Fecha de instalación del móvil. Proporciona la fecha de la primera vez que se abre la aplicación móvil. | varchar(255) |
| **`post_`** | **`mobilelaunchnumber`** | Incrementa de uno en uno cada vez que se abre la aplicación móvil. | varchar(255) |
| **`post_`** | **`mobilemessagebuttonname`** | Recopilado desde la variable de datos de contexto `a.message.button.id`. Se utiliza para la mensajería integrada en la aplicación con el objetivo de identificar el botón que cerró el mensaje. | varchar(100) |
| **`post_`** | **`mobilemessageid`** | ID de mensaje en la aplicación | varchar(255) |
| **`post_`** | **`mobilemessageonline`** | Mensaje en línea en la aplicación | varchar(255) |
| **`post_`** | **`mobilemessagepushoptin`** | Recopilado desde la variable de datos de contexto `a.push.optin`. Se establece en “true” cuando el usuario opta por la mensajería emergente; de lo contrario, el valor es “false”. | varchar(255) |
| **`post_`** | **`mobilemessagepushpayloadid`** | Recopilado desde la variable de datos de contexto `a.push.payloadid`. Se utiliza en los mensajes emergentes como identificador de carga útil. | varchar(255) |
| **`post_`** | **`mobileosversion`** | Versión del sistema operativo de Mobile Services | varchar(255) |
| | **`mobileplaceaccuracy`** | Recopilado desde la variable de datos de contexto `a.loc.acc`. Indica la precisión del GPS en metros en el momento de la recogida. | varchar(255) |
| | **`mobileplacecategory`** | Recopilado desde la variable de datos de contexto `a.loc.category`. Describe la categoría de un lugar específico. | varchar(255) |
| | **`mobileplaceid`** | Recopilado desde la variable de datos de contexto `a.loc.id`. Identificador de un punto de interés determinado. | varchar(255) |
| **`post_`** | **`mobilepushoptin`** | Inclusión push de Mobile Services | varchar(255) |
| **`post_`** | **`mobilepushpayloadid`** | ID de carga útil push de Mobile Services | varchar(255) |
| | **`mobilerelaunchcampaigncontent`** | Contenido de inicio de Mobile Services | varchar(255) |
| | **`mobilerelaunchcampaignmedium`** | Medio de inicio de Mobile Services | varchar(255) |
| | **`mobilerelaunchcampaignsource`** | Origen del inicio de Mobile Services | varchar(255) |
| | **`mobilerelaunchcampaignterm`** | Término de inicio de Mobile Services | varchar(255) |
| | **`mobilerelaunchcampaigntrackingcode`** | Recopilado desde la variable de datos de contexto `a.launch.campaign.trackingcode`. Se utiliza en la adquisición como código de seguimiento para la campaña de inicio. | varchar(255) |
| **`post_`** | **`mobileresolution`** | Resolución del dispositivo móvil. `[Width] x [Height]` en píxeles. | varchar(255) |
| | **`mobile_id`** | Si el usuario utiliza un dispositivo móvil, es el ID numérico del dispositivo. El valor clave de `mobile_attributes.tsv` [Búsqueda dinámica](dynamic-lookups.md). | int |
| | **`monthly_visitor`** | Un indicador que determina si el visitante es único en el mes actual. | tinyint sin firmar |
| **`post_`** | **`mvvar1`** - **`mvvar3`** | Valores de [lista de variable](/help/implement/vars/page-vars/list.md). Contiene una lista delimitada de valores personalizados en función de la implementación. Las columnas `post_mvvar1` - `post_mvvar3` reemplazan el delimitador original por `--**--`. | texto |
| **`post_`** | **`mvvar1_instances`** - **`mvvar3_instances`** | Los valores de variable de lista que se establecieron en la visita actual. Reemplaza el delimitador original por `--**--`. Las columnas `post` no suelen contener datos. | texto |
| | **`new_visit`** | Un indicador que determina si la visita actual es una visita nueva. Configurado por Adobe tras 30 minutos de inactividad de la visita. | tinyint sin firmar |
| | **`os`** | ID numérico que representa el sistema operativo del visitante. Se basa en la columna `user_agent`. El valor clave de `operating_system.tsv` búsqueda estándar y `operating_system_type.tsv` [Búsqueda dinámica](dynamic-lookups.md). | int sin firmar |
| **`post_`** | **`pagename`** | Dimensión [Página](/help/components/dimensions/page.md). Si la variable [`pagename`](/help/implement/vars/page-vars/pagename.md) está vacía, Analytics utiliza `page_url` en su lugar. | varchar(100) |
| **`post_`** | **`pagename_no_url`** | Similar a `pagename`, excepto que no vuelve a `page_url`. Solo la columna `post` está disponible. | varchar(100) |
| **`post_`** | **`page_event`** | El tipo de visita que se envía en la solicitud de imagen (visita estándar, vínculo de descarga, vínculo personalizado, vínculo de salida). Consulte [Búsqueda de evento de página](datafeeds-page-event.md). | tinyint sin firmar |
| **`post_`** | **`page_event_var1`** | Solo se utiliza en solicitudes de imagen de seguimiento de vínculos. URL del vínculo de descarga, de salida o personalizado en el que se hizo clic. | texto |
| **`post_`** | **`page_event_var2`** | Solo se utiliza en solicitudes de imagen de seguimiento de vínculos. Nombre personalizado (si se especifica) del vínculo. Establece el [vínculo personalizado](/help/components/dimensions/custom-link.md), el [vínculo de descarga](/help/components/dimensions/download-link.md) o el [vínculo de salida](/help/components/dimensions/exit-link.md), según el valor de `page_event`. | varchar(100) |
| **`post_`** | **`page_type`** | Dimensión [Páginas no encontradas](/help/components/dimensions/pages-not-found.md), que se usa generalmente para páginas 404. | char(20) |
| **`post_`** | **`page_url`** | **`page_url`**: dirección URL de la visita. Utiliza un tipo de datos de texto.<br>**`post_page_url`**: Eliminado para las solicitudes de imagen de seguimiento de vínculos ([`tl()`](/help/implement/vars/functions/tl-method.md)). Utiliza un tipo de datos de varchar(255). | text<br>varchar(255) |
| | **`paid_search`** | Un indicador que se determina si la visita coincide con la detección de búsquedas de pago. | tinyint sin firmar |
| **`post_`** | **`persistent_cookie`** | Se utiliza en la dimensión [Compatibilidad con cookies persistentes](/help/components/dimensions/persistent-cookie-support.md). Indica si el visitante admite cookies que no se descartan después de cada visita. | char(1) |
| **`post_`** | **`pointofinterest`** | Nombre del punto de interés de Mobile Services | varchar(255) |
| **`post_`** | **`pointofinterestdistance`** | Distancia de Mobile Services al centro de puntos de interés | varchar(255) |
| **`post_`** | **`product_list`** | La variable de página [`products`](/help/implement/vars/page-vars/products.md). Ayuda a rellenar varias dimensiones y métricas, entre ellas [Categoría](/help/components/dimensions/category.md), [Producto](/help/components/dimensions/product.md), [Unidades](/help/components/metrics/units.md) e [Ingresos](/help/components/metrics/revenue.md). | texto |
| **`post_`** | **`prop1`** - **`prop75`** | Variables de tráfico personalizadas 1-75. Se utiliza en dimensiones [Prop](/help/components/dimensions/prop.md). | varchar(100) |
| **`post_`** | **`purchaseid`** | Identificador único de una compra, tal y como se establece mediante la variable [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). Lo utiliza la columna `duplicate_purchase`. | char(20) |
| | **`quarterly_visitor`** | Un indicador que determina si la visita es un visitante nuevo trimestral. | tinyint sin firmar |
| **`post_`** | **`referrer`** | Dimensión [Referente](/help/components/dimensions/referrer.md). Tenga en cuenta que mientras `referrer` utiliza un tipo de datos de varchar(255), `post_referrer` emplea un tipo de datos de varchar(244). | varchar(255)<br>varchar(244) |
| | **`ref_domain`** | Dimensión [Dominio de referencia](/help/components/dimensions/referring-domain.md). Se basa en la columna`referrer`. | varchar(100) |
| | **`ref_type`** | ID numérico que representa el tipo de referente de la visita. Se usa en la dimensión [Tipo de referente](/help/components/dimensions/referrer-type.md).<br>1: Dentro del sitio<br>2: Otros sitios web<br>3: Motores de búsqueda<br>4: Disco duro<br>5: USENET<br>6: Escritos o marcadores (sin referente)<br>7: Correo electrónico<br>8: Sin JavaScript<br>9: Redes sociales<br>10: Herramientas de IA conversacional | tinyint sin firmar |
| | **`resolution`** | ID numérico que representa la resolución del monitor. Se utiliza en la dimensión [Resolución del monitor](/help/components/dimensions/monitor-resolution.md). Utiliza la tabla de búsqueda `resolution.tsv`. | smallint sin firmar |
| **`post_`** | **`search_engine`** | ID numérico que representa el motor de búsqueda que redirigió al visitante a su sitio. Se utiliza en dimensiones del [motor de búsqueda](/help/components/dimensions/search-engine.md). Se remite a la tabla de búsqueda `search_engines.tsv`. | smallint sin firmar |
| | **`search_page_num`** | Lo utiliza la dimensión [Rango de todas las páginas de búsqueda](/help/components/dimensions/all-search-page-rank.md). Indica en qué página de resultados de búsqueda apareció su sitio antes de que se hiciera clic para acceder a él. | smallint sin firmar |
| | **`secondary_hit`** | Un indicador que determina si la visita es una visita secundaria. Por lo general, este indicador se origina a partir del etiquetado de grupos múltiples y las reglas de VISTA que copian las visitas. | tinyint sin firmar |
| | **`sourceid`** | ID de origen | int sin firmar |
| | **`stats_server`** | Sin uso. Servidor interno de Adobe que ha procesado la visita. | char(30) |
| **`post_`** | **`s_kwcid`** | ID de palabra clave utilizado en las integraciones de Adobe Advertising. | varchar(255) |
| | **`s_resolution`** | Valor no procesado de resolución de pantalla. Se recopila mediante la función de JavaScript `screen.width x screen.height`. | char(20) |
| **`post_`** | **`tnt`** | Se utiliza en las integraciones de Adobe Target. Representa todas las pruebas para las que está cualificado actualmente. El formato es: `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`. | texto |
| **`post_`** | **`tnt_action`** | Se utiliza en las integraciones de Adobe Target. Representa todas las pruebas para las que se calificó la visita. | texto |
| | **`tnt_instances`** | Se utiliza en las integraciones de Adobe Target. Variable de instancias de Target. | texto |
| **`post_`** | **`transactionid`** | Un identificador único donde, más tarde, se pueden cargar diversos puntos de datos a través de fuentes de datos. Recopilado mediante la variable [`transactionID`](/help/implement/vars/page-vars/transactionid.md). | texto |
| | **`truncated_hit`** | Un indicador que indica que se truncó la solicitud de imagen (se recibió una visita parcial). <br>S: Se truncó la visita; visita parcial recibida <br>N: La visita no se truncó; visita completa recibida | char(1) |
| **`post_`** | **`t_time_info`** | Hora local del visitante. El formato es: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| | **`userid`** | Sin uso. ID numérico del ID del grupo de informes. Utilice `username` en su lugar. | int sin firmar |
| | **`username`** | ID del grupo de informes para la visita. | char(40) |
| | **`user_agent`** | La cadena del agente de usuario enviada en el encabezado HTTP de la solicitud de imagen. | texto |
| | **`user_hash`** | Sin uso. Hash en el ID del grupo de informes. Utilice `username` en su lugar. | int sin firmar |
| **`post_`** | **`user_server`** | Utilizado en la dimensión [Servidor](/help/components/dimensions/server.md). | varchar(100) |
| | **`va_closer_detail`** | Dimensión [Detalles de último contacto](/help/components/dimensions/last-touch-detail.md). | varchar(255) |
| | **`va_closer_id`** | ID numérico que identifica la dimensión [Canal del último contacto](/help/components/dimensions/last-touch-channel.md). La búsqueda de este ID se encuentra en el administrador de canales de marketing. | tinyint sin firmar |
| | **`va_finder_detail`** | Dimensión [Detalles de primer contacto](/help/components/dimensions/first-touch-detail.md). | varchar(255) |
| | **`va_finder_id`** | ID numérico que identifica la dimensión [Canal del primer contacto](/help/components/dimensions/first-touch-channel.md). La búsqueda de este ID se encuentra en el administrador de canales de marketing. | tinyint sin firmar |
| | **`va_instance_event`** | Un indicador que identifica [Instancias](/help/components/metrics/instances.md) del canal de marketing. | tinyint sin firmar |
| | **`va_new_engagement`** | Un indicador que identifica las [nuevas participaciones](/help/components/metrics/new-engagements.md) del canal de marketing. | tinyint sin firmar |
| **`post_`** | **`video`** | Dimensión de servicios de medios de streaming [Contenido](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/content). | varchar(255) |
| **`post_`** | **`videoad`** | Dimensión de servicios de medios de streaming [Publicidad](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/ad). | varchar(255) |
| **`post_`** | **`videoadinpod`** | Dimensión de servicios de medios de streaming [Posición del anuncio en la secuencia](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/ad-in-pod-position). | varchar(255) |
| **`post_`** | **`videoadlength`** | Dimensión de servicios de medios de transmisión [Longitud del anuncio (variable)](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/ad-length). | entero |
| **`post_`** | **`videoadname`** | Dimensión de servicios de medios de streaming [Nombre del anuncio (variable)](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/ad-name). | varchar(255) |
| **`post_`** | **`videoadplayername`** | Dimensión de servicios de medios de streaming [Nombre del reproductor del anuncio](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/ad-player-name). | varchar(255) |
| **`post_`** | **`videoadpod`** | Dimensión de servicios de medios de streaming [Pod del anuncio](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/ad-pod). | varchar(255) |
| **`post_`** | **`videoadvertiser`** | Dimensión de servicios de medios de streaming [Anunciante](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/advertiser). | varchar(255) |
| | **`videoaudioalbum`** | Dimensión de servicios de medios de streaming [Álbum](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/album). | varchar(255) |
| | **`videoaudioartist`** | Dimensión de servicios de medios de streaming [Artista](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/artist). | varchar(255) |
| | **`videoaudioauthor`** | Dimensión de servicios de medios de streaming [Autor](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/author). | varchar(255) |
| | **`videoaudiolabel`** | Dimensión de servicios de medios de streaming [Etiqueta](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/label). | varchar(255) |
| | **`videoaudiopublisher`** | Dimensión de servicios de medios de streaming [Editor](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/publisher). | varchar(255) |
| | **`videoaudiostation`** | Dimensión de servicios de medios de streaming [Estación](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/station). | varchar(255) |
| **`post_`** | **`videocampaign`** | Dimensión de servicios de medios de streaming [ID de campaña](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/campaign-id). | varchar(255) |
| **`post_`** | **`videochannel`** | Dimensión de servicios de medios de streaming [Canal de contenido](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/content-channel). | varchar(255) |
| **`post_`** | **`videochapter`** | Dimensión de servicios de medios de streaming [Capítulo](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/chapter). | varchar(255) |
| **`post_`** | **`videocontenttype`** | Dimensión de servicios de medios de streaming [Tipo de contenido](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/content-type). | varchar(255) |
| **`post_`** | **`videodaypart`** | Dimensión de servicios de medios de streaming [Momento del día](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/day-part). | varchar(255) |
| **`post_`** | **`videoepisode`** | Dimensión de servicios de medios de streaming [Capítulo](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/episode). | varchar(255) |
| **`post_`** | **`videofeedtype`** | Dimensión de servicios de medios de streaming [Tipo de fuente de medios](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/media-feed-type). | varchar(255) |
| **`post_`** | **`videogenre`** | Dimensión de servicios de medios de streaming [Género](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/genre). Esta dimensión permite varios valores en la misma visita, delimitados por una coma. | texto |
| **`post_`** | **`videolength`** | Dimensión de servicios de medios de streaming [Longitud del contenido (variable)](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/content-length). | entero |
| **`post_`** | **`videomvpd`** | Dimensión de servicios de medios de streaming [MVPD](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/mvpd). | varchar(255) |
| **`post_`** | **`videoname`** | Dimensión de servicios de medios de streaming [Nombre del contenido (variable)](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/content-name). | varchar(255) |
| **`post_`** | **`videonetwork`** | Dimensión de servicios de medios de streaming [Red](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/network). | varchar(255) |
| **`post_`** | **`videopath`** | Dimensión de servicios de medios de streaming [Ruta de medios](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/media-path). | varchar(100) |
| **`post_`** | **`videoplayername`** | Dimensión de servicios de medios de streaming [Nombre del reproductor de contenido](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/content-player-name). | varchar(255) |
| **`post_`** | **`videoqoebitrateaverageevar`** | Dimensión de servicios de medios de streaming [Bitrate promedio](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/average-bitrate). | varchar(255) |
| **`post_`** | **`videoqoebitratechangecountevar`** | Dimensión de servicios de medios de streaming [Cambios en bitrate](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/bitrate-changes). | varchar(255) |
| **`post_`** | **`videoqoebuffercountevar`** | Dimensión de servicios de medios de streaming [Eventos de búfer](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/buffer-events). | varchar(255) |
| **`post_`** | **`videoqoebuffertimeevar`** | Dimensión de servicios de medios de streaming [Duración total del búfer](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/total-buffer-duration). | varchar(255) |
| **`post_`** | **`videoqoedroppedframecountevar`** | Dimensión de servicios de medios de streaming [Fotogramas perdidos](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/dropped-frames). | varchar(255) |
| **`post_`** | **`videoqoeerrorcountevar`** | Dimensión de servicios de medios de streaming [Errores](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/errors). | varchar(255) |
| | **`videoqoeextneralerrors`** | Dimensión de servicios de medios de streaming [ID de error externo](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/external-error-ids). Esta dimensión permite varios valores en la misma visita. | texto |
| **`post_`** | **`videoqoeplayersdkerrors`** | Dimensión de servicios de medios de streaming [ID de error del reproductor SDK](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/player-sdk-error-ids). Esta dimensión permite varios valores en la misma visita. | texto |
| **`post_`** | **`videoqoetimetostartevar`** | Dimensión de servicios de medios de streaming [Tiempo para el inicio](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/time-to-start). | varchar(255) |
| **`post_`** | **`videoseason`** | Dimensión de servicios de medios de streaming [Temporada](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/season). | varchar(255) |
| **`post_`** | **`videosegment`** | Dimensión de servicios de medios de streaming [Segmento de contenido](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/content-segment). | varchar(255) |
| **`post_`** | **`videosessionid`** | La dimensión de servicios de medios de streaming [ID de sesión de medios](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/media-session-id). | varchar(255) |
| **`post_`** | **`videoshow`** | Dimensión de servicios de medios de streaming [Programa](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/show). | varchar(255) |
| **`post_`** | **`videoshowtype`** | Dimensión de servicios de medios de streaming [Tipo de programa](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/show-type). | varchar(255) |
| | **`videostreamtype`** | Dimensión de servicios de medios de streaming [Tipo de emisión](https://experienceleague.adobe.com/es/docs/media-analytics/using/reporting/dimensions/stream-type). | varchar(255) |
| **`post_`** | **`visid_high`** | Se utiliza con `visid_low` para identificar un visitante de forma exclusiva. | bigint sin firmar |
| **`post_`** | **`visid_low`** | Se utiliza con `visid_high` para identificar un visitante de forma exclusiva. | bigint sin firmar |
| | **`visid_new`** | Un indicador que determina si la visita contiene un ID de visitante recién generado. | char(1) |
| | **`visid_timestamp`** | Si el ID de visitante se ha generado recientemente, proporciona la marca de tiempo en tiempo UNIX® del momento en que se generó el ID de visitante. | int |
| **`post_`** | **`visid_type`** | No para uso externo; Adobe lo utiliza internamente para procesar optimizaciones. Identificador numérico que representa el método utilizado para identificar al visitante.<br>`0`: Id. de visitante personalizado o desconocido/no aplicable<br>`1`: IP y reserva del agente de usuario <br>`2`: Encabezado de suscriptor móvil HTTP <br>`3`: Valor de la cookie heredada (`s_vi`) <br>`4`: Valor de la cookie de reserva (`s_fid`) <br>`5`: Servicio de identidad | tinyint sin firmar |
| **`post_`** | **`visit_keywords`** | Dimensión [Palabra clave de búsqueda](/help/components/dimensions/search-keyword.md). Esta columna utiliza un límite de caracteres no estándar de varchar(244) para dar cabida a la lógica back-end que utiliza Adobe. La columna posprocesada es `**post_keywords**`, no `**post_visit_keywords**`. | varchar(244) |
| | **`visit_num`** | Dimensión [Número de visitas](/help/components/dimensions/visit-number.md). Empieza en 1 y aumenta cada vez que se inicia una nueva visita por visitante. | int sin firmar |
| | **`visit_page_num`** | Dimensión [Profundidad de la visita](/help/components/dimensions/hit-depth.md). Aumenta en 1 por cada visita que genera el visitante. Restablece cada visita. | int sin firmar |
| | **`visit_referrer`** | El primer referente de la visita. | varchar(255) |
| | **`visit_ref_domain`** | Se basa en la columna `visit_referrer`. El primer dominio de referencia de la visita. | varchar(100) |
| | **`visit_ref_type`** | ID numérico que representa el tipo de referente del primer referente de la visita. Se remite a la tabla de búsqueda `referrer_type.tsv`. | tinyint sin firmar |
| | **`visit_search_engine`** | ID numérico que representa el primer motor de búsqueda de la visita. Se remite a la tabla de búsqueda `search_engines.tsv`. | smallint sin firmar |
| | **`visit_start_pagename`** | [Página](/help/components/dimensions/page.md) de la primera visita. | varchar(100) |
| | **`visit_start_page_url`** | URL de la primera visita individual de la visita. | varchar(255) |
| | **`visit_start_time_gmt`** | Marca de tiempo (en tiempo UNIX®) de la primera visita. | int |
| | **`weekly_visitor`** | Indicador que determina si la visita es un visitante nuevo semanal. | tinyint sin firmar |
| | **`yearly_visitor`** | Indicador que determina si la visita es un visitante nuevo anual. | tinyint sin firmar |
| **`post_`** | **`zip`** | Ayuda a rellenar la dimensión [Código postal](/help/components/dimensions/zip-code.md). Consulte también `geo_zip`. | varchar(50) |

## Columnas no utilizadas o retiradas

La siguiente lista de columnas no se utiliza, se ha retirado o no contiene valor en la creación de informes. Algunas de estas columnas están vinculadas a funciones que se han retirado, mientras que otras ya no son necesarias debido a funciones nuevas y más sólidas. La mayoría de estas columnas no contienen datos; las columnas que aún podrían contener datos no son compatibles con las bibliotecas de recopilación de datos actuales y no son dimensiones disponibles en Analysis Workspace.

| Publicar | Nombre de la columna |
| ---: | :--- |
| `post_` | `adclassificationcreative` |
| | `click_action` |
| | `click_action_type` |
| | `click_context` |
| | `click_context_type` |
| | `click_sourceid` |
| | `click_tag` |
| | `dataprivacydmaconsent` |
| `post_` | `hier1` - `hier5` |
| | `homepage` |
| | `ip2` |
| | `mobileacquisitionclicks` |
| | `mobileactioninapptime` |
| | `mobileactiontotaltime` |
| | `mobileappperformanceaffectedusers` |
| | `mobileappperformanceappid.app-perf-app-name` |
| | `mobileappperformanceappid.app-perf-platform` |
| | `mobileappperformancecrashes` |
| | `mobileappperformancecrashid.app-perf-crash-name` |
| | `mobileappperformanceloads` |
| | `mobileappstoreavgrating` |
| | `mobileappstoredownloads` |
| | `mobileappstoreinapprevenue` |
| | `mobileappstoreinapproyalties` |
| | `mobileappstoreobjectid.app-store-user` |
| | `mobileappstoreobjectid.application-name` |
| | `mobileappstoreobjectid.application-version` |
| | `mobileappstoreobjectid.appstore-name` |
| | `mobileappstoreobjectid.category-name` |
| | `mobileappstoreobjectid.country-name` |
| | `mobileappstoreobjectid.device-manufacturer` |
| | `mobileappstoreobjectid.device-name` |
| | `mobileappstoreobjectid.in-app-name` |
| | `mobileappstoreobjectid.platform-name-version` |
| | `mobileappstoreobjectid.rank-category-type` |
| | `mobileappstoreobjectid.region-name` |
| | `mobileappstoreobjectid.review-comment` |
| | `mobileappstoreobjectid.review-title` |
| | `mobileappstoreoneoffrevenue` |
| | `mobileappstoreoneoffroyalties` |
| | `mobileappstorepurchases` |
| | `mobileappstorerank` |
| | `mobileappstorerankdivisor` |
| | `mobileappstorerating` |
| | `mobileappstoreratingdivisor` |
| | `mobileavgprevsessionlength` |
| | `mobilecrashes` |
| | `mobilecrashrate` |
| | `mobiledailyengagedusers` |
| | `mobiledayssincelastupgrade` |
| | `mobiledeeplinkid.name` |
| | `mobileinstalls` |
| | `mobilelaunches` |
| | `mobilelaunchessincelastupgrade` |
| `post_` | `mobileltv` |
| | `mobileltvtotal` |
| `post_` | `mobilemessageclicks` |
| `post_` | `mobilemessageid.dest` |
| `post_` | `mobilemessageid.name` |
| `post_` | `mobilemessageid.type` |
| `post_` | `mobilemessageimpressions` |
| `post_` | `mobilemessagepushpayloadid.name` |
| `post_` | `mobilemessageviews` |
| | `mobilemonthlyengagedusers` |
| | `mobileosenvironment` |
| | `mobileplacedwelltime` |
| | `mobileplaceentry` |
| | `mobileplaceexit` |
| | `mobileprevsessionlength` |
| | `mobilerelaunchcampaigntrackingcode.name` |
| | `mobileupgrades` |
| | `namespace` |
| | `p_plugins` |
| `post_` | `page_event_var3` |
| `post_` | `partner_plugins` |
| | `plugins` |
| | `prev_page` |
| | `product_merchandising` |
| | `sampled_hit` |
| | `service` |
| `post_` | `socialaccountandappids` |
| `post_` | `socialassettrackingcode` |
| `post_` | `socialauthor` |
| `post_` | `socialaveragesentiment` |
| `post_` | `socialaveragesentiment (deprecated)` |
| `post_` | `socialcontentprovider` |
| `post_` | `socialfbstories` |
| `post_` | `socialfbstorytellers` |
| `post_` | `socialinteractioncount` |
| `post_` | `socialinteractiontype` |
| `post_` | `sociallanguage` |
| `post_` | `sociallatlong` |
| `post_` | `sociallikeadds` |
| `post_` | `sociallink` |
| `post_` | `sociallink (deprecated)` |
| `post_` | `socialmentions` |
| `post_` | `socialowneddefinitioninsighttype` |
| `post_` | `socialowneddefinitioninsightvalue` |
| `post_` | `socialowneddefinitionmetric` |
| `post_` | `socialowneddefinitionpropertyvspost` |
| `post_` | `socialownedpostids` |
| `post_` | `socialownedpropertyid` |
| `post_` | `socialownedpropertyname` |
| `post_` | `socialownedpropertypropertyvsapp` |
| `post_` | `socialpageviews` |
| `post_` | `socialpostviews` |
| `post_` | `socialproperty` |
| `post_` | `socialproperty (deprecated)` |
| `post_` | `socialpubcomments` |
| `post_` | `socialpubposts` |
| `post_` | `socialpubrecommends` |
| `post_` | `socialpubsubscribers` |
| `post_` | `socialterm` |
| `post_` | `socialtermslist` |
| `post_` | `socialtermslist (deprecated)` |
| `post_` | `socialtotalsentiment` |
| `post_` | `state` |
| `post_` | `survey` |
| | `survey_instances` |
| | `tnt_post_vista` |
| | `ua_color` |
| | `ua_os` |
| | `ua_pixels` |
| | `videoadload` |
| `post_` | `videoauthorized` |
| | `videoaverageminuteaudience` |
| | `videochaptercomplete` |
| | `videochapterstart` |
| | `videochaptertime` |
| | `videopause` |
| | `videopausecount` |
| | `videopausetime` |
| | `videoplay` |
| | `videoprogress10` |
| | `videoprogress25` |
| | `videoprogress50` |
| | `videoprogress75` |
| | `videoprogress96` |
| | `videoqoebitrateaverage` |
| | `videoqoebitratechange` |
| | `videoqoebuffer` |
| | `videoqoedropbeforestart` |
| | `videoqoedroppedframes` |
| | `videoqoeerror` |
| | `videoresume` |
| | `videotime` |
| | `videototaltime` |
| | `videouniquetimeplayed` |

>[!MORELIKETHIS]
>
>[Asignación de variables de objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md)
>[Asignación de variables de objeto de datos](/help/implement/aep-edge/data-var-mapping.md)
