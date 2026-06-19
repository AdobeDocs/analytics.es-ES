---
title: Compatibilidad de dimensiones de Analytics
description: Referencia para dimensiones e informes de Analytics.
feature: Dimensions
exl-id: 1884bc20-b04d-4f9a-b057-2b2fbe53190d
TQID: https://experienceleague.adobe.com/WntN8KyUXgQUt8vvoHUZyQfTtEUSS3aPOF6pIDbJynk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: c9bb7ea6-c04f-4262-b69c-fbb8d91e3559
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 905
ht-degree: 47%

---

# Compatibilidad de dimensiones de Analytics

Esta página lista [dimensiones](overview.md) compatibles con sus respectivas capacidades de Analytics.

>[!NOTE]
>
>En esta lista se omiten los nombres de las variables personalizadas, clasificaciones y atributos de visitantes. Estos elementos de dimensión son específicos de cada grupo de informes.

## Dimensiones admitidas en Analysis Workspace

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de Dimension (utilizado en solicitudes de API) |
|---|---|
| Analytics for Target | `targetraw` |
| ID de públicos | `mcaudiences` |
| [Explorador](browser.md) | `browser` |
| [Tipo de explorador](browser-type.md) | `browsertype` |
| [Categoría](category.md) | `category` |
| [Ciudades](cities.md) | `geocity` |
| [Profundidad de color](color-depth.md) | `colordepth` |
| [Tipo de conexión](connection-type.md) | `connectiontype` |
| [Compatibilidad con cookies](cookie-support.md) | `cookie` |
| [Países](countries.md) | `geocountry` |
| [Lealtad del cliente](customer-loyalty.md) | `customerloyalty` |
| [Variables de conversión personalizadas](evar.md) | `evar1`, `evar2`, etc. |
| [Variables De Custom Insight](prop.md) | `prop1`, `prop2`, etc. |
| [Vínculo personalizado](custom-link.md) | `customlink` |
| [Días antes de la primera compra](days-before-first-purchase.md) | `daysbeforefirstpurchase` |
| [Días desde la última compra](days-since-last-purchase.md) | `dayssincelastpurchase` |
| [Dominio](domain.md) | `filtereddomain` |
| [Vínculo de descarga](download-link.md) | `downloadlink` |
| [Página de entrada](entry-dimensions.md) | `entrypage` |
| [Página de entrada original](entry-dimensions.md) | `entrypageoriginal` |
| [Vínculo de salida](exit-link.md) | `exitlink` |
| [Canal de primer contacto](first-touch-channel.md) | `firsttouchchannel` |
| [Detalles de canal de primer toque](first-touch-detail.md) | `firsttouchchanneldetail` |
| [Habilitado para Java](java-enabled.md) | `javaenabled` |
| [Idioma](language.md) | `language` |
| [Canal de último contacto](last-touch-channel.md) | `lasttouchchannel` |
| [Detalles de canal de último toque](last-touch-detail.md) | `lasttouchchanneldetail` |
| Variables de lista | `listvariables` |
| [Canal de mercadotecnia](marketing-channel.md) | `marketingchannel` |
| [Compatibilidad con audio móvil](mobile-dimensions.md) | `mobileaudiosupport` |
| [Operador de telefonía móvil](mobile-dimensions.md) | `mobilecarrier` |
| [Profundidad de color móvil](mobile-dimensions.md) | `mobilecolordepth` |
| [Compatibilidad con cookies móviles](mobile-dimensions.md) | `mobilecookiesupport` |
| [Dispositivo móvil](mobile-dimensions.md) | `mobiledevicename` |
| [Tipo de dispositivo móvil](mobile-dimensions.md) | `mobiledevicetype` |
| [Longitud máxima del correo electrónico móvil](mobile-dimensions.md) | `mobileemaillength` |
| [Compatibilidad con imágenes móviles](mobile-dimensions.md) | `mobileimagesupport` |
| [Fabricante móvil](mobile-dimensions.md) | `mobilemanufacturer` |
| [Sistema operativo móvil (obsoleto)](mobile-dimensions.md) | `mobileos` |
| [Altura de la pantalla móvil](mobile-dimensions.md) | `mobilescreenheight` |
| [Tamaño de pantalla móvil](mobile-dimensions.md) | `mobilescreensize` |
| [Ancho de pantalla móvil](mobile-dimensions.md) | `mobilescreenwidth` |
| [Longitud máxima de la dirección URL del explorador móvil](mobile-dimensions.md) | `mobileurllength` |
| [Compatibilidad con vídeo móvil](mobile-dimensions.md) | `mobilevideosupport` |
| [Resolución del monitor](monitor-resolution.md) | `monitorresolution` |
| [Sistema operativo](operating-systems.md) | `operatingsystem` |
| [Dominio de referencia original](original-referring-domain.md) | `referringdomainoriginal` |
| [Página](page.md) | `page` |
| [Páginas no encontradas](pages-not-found.md) | `pagesnotfound` |
| [Producto](product.md) | `product` |
| [Referente](referrer.md) | `referrer` |
| [Tipo de referente](referrer-type.md) | `referrertype` |
| [Dominio de referencia](referring-domain.md) | `referringdomain` |
| [Regiones](regions.md) | `georegion` |
| [Frecuencia de retorno](return-frequency.md) | `returnfrequency` |
| SC-TnT | `tntbase` |
| [Motor de búsqueda](search-engine.md) | `searchengine` |
| [Palabra clave de búsqueda](search-keyword.md) | `searchenginekeyword` |
| [Motor de búsqueda: natural](search-engine.md) | `searchenginenatural` |
| [Motor de búsqueda - De pago](search-engine.md) | `searchenginepaid` |
| [Palabra clave de búsqueda: natural](search-keyword.md) | `searchenginenaturalkeyword` |
| [Palabra clave de búsqueda: de pago](search-keyword.md) | `searchenginepaidkeyword` |
| [Clasificación de todas las páginas de búsqueda](all-search-page-rank.md) | `searchenginepagerank` |
| [Servidor](server.md) | `server` |
| [Visitas a una sola página](single-page-visits.md) | `singlepagevisits` |
| [Sección del sitio](site-section.md) | `sitesections` |
| [Tiempo empleado por visita (granular)](time-spent-per-visit.md) | `sitetime` |
| [Código de seguimiento](tracking-code.md) | `campaign` |
| [Área de mercado designada (DMA) de EE. UU.](us-dma.md) | `geodma` |
| [Estados de EE. UU.](us-states.md) | `state` |
| [Tiempo previo al evento](time-prior-to-event.md) | `timeprior` |
| [Tiempo empleado por visita - Agrupado](time-spent-per-visit.md) | `timespent` |
| [Profundidad de la visita](visit-depth.md) | `pathlength` |
| [Número de visita](visit-number.md) | `visitnumber` |
| [Código postal](zip-code.md) | `zip` |
| [AM / PM](am-pm.md) | `timepartampm` |
| [Altura del explorador - Agrupado](browser-height.md) | `browserheightbucketed` |
| [Anchura del explorador - Agrupado](browser-width.md) | `browserwidthbucketed` |
| [Día](day.md) | `daterangeday` |
| [Día del mes](day-of-month.md) | `timepartdayofmonth` |
| [Día de la semana](day-of-week.md) | `dayofweek` |
| [Día de la semana](day-of-week.md) | `timepartdayofweek` |
| [Día del año](day-of-year.md) | `timepartdayofyear` |
| [Días transcurridos desde la última visita](days-since-last-visit.md) | `dayssincelastvisit` |
| [Perspectivas personalizadas de entrada](entry-dimensions.md) | `entryprops` |
| [Variables de lista de entrada](entry-dimensions.md) | `entrylistvariables` |
| [Servidor de entrada](entry-dimensions.md) | `entryserver` |
| [Sección del sitio de entrada](entry-dimensions.md) | `entrysitesections` |
| [Perspectivas personalizadas de salida](exit-dimensions.md) | `exitprops` |
| [Variables de lista de salida](exit-dimensions.md) | `exitlistvariables` |
| [Página de salida](exit-dimensions.md) | `exitpage` |
| [Servidor de salida](exit-dimensions.md) | `exitserver` |
| [Sección de sitio de salida](exit-dimensions.md) | `exitsitesections` |
| [Profundidad de la visita](hit-depth.md) | `hitdepth` |
| [Tipo de visita](hit-type.md) | `customerperspective` |
| [Hora](hour.md) | `daterangehour` |
| [Hora del día](hour-of-day.md) | `timeparthourofday` |
| [Detalles de canal de mercadotecnia](marketing-detail.md) | `marketingchanneldetail` |
| [Minuto](minute.md) | `daterangeminute` |
| [Longitud máxima del marcador móvil](mobile-dimensions.md) | `mobilebookmarklength` |
| [Número de dispositivo móvil](mobile-dimensions.md) | `mobiledevicenumber` |
| [DRM móvil](mobile-dimensions.md) | `mobiledrm` |
| [Servicios de información móvil](mobile-dimensions.md) | `mobileinformationservices` |
| [VM Java móvil](mobile-dimensions.md) | `mobilejavavm` |
| [Decoración de correo móvil](mobile-dimensions.md) | `mobilemaildecoration` |
| [Protocolos de red móvil](mobile-dimensions.md) | `mobilenetprotocols` |
| [Pulsar y hablar móvil](mobile-dimensions.md) | `mobilepushtotalk` |
| [Mes](month.md) | `daterangemonth` |
| [Mes del año](month-of-year.md) | `timepartmonthofyear` |
| [Tipos de sistemas operativos](operating-system-types.md) | `operatingsystemgroup` |
| [Búsqueda de pago](paid-search.md) | `paidsearch` |
| [Compatibilidad con cookies persistentes](persistent-cookie-support.md) | `persistentcookie` |
| [Trimestre](quarter.md) | `daterangequarter` |
| [Trimestre del año](quarter-of-year.md) | `timepartquarterofyear` |
| Encuesta | `surveybase` |
| [Tiempo empleado en la página - Agrupado](time-spent-on-page.md) | `averagepagetime` |
| [Tiempo empleado en la página - Pormenorizado](time-spent-on-page.md) | `pagetimeseconds` |
| [Motivo de exclusión de seguimiento](tracking-opt-out-reason.md) | `optoutreason` |
| [Día de la semana / Fin de semana](weekday-weekend.md) | `timepartweekdayweekend` |
| [Semana](week.md) | `daterangeweek` |
| [Año](year.md) | `daterangeyear` |

## Dimensiones de reconocimiento de contenido compatibles únicamente con Analysis Workspace

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de Dimension (utilizado en solicitudes de API) |
|--- |--- |
| Activity Map XY | `clickmapxy` |
| ID de sesión de contenidos | `videosessionid` |
| Método de acceso de Nielsen | `nielsenaccmethod` |
| ID de aplicación de Nielsen | `nielsenappid` |
| Recurso de canal de Nielsen | `nielsenchannelasset` |
| Tipo de contenido de Nielsen | `nielsencontenttype` |

## Dimensiones de reconocimiento de contenido compatibles con Analysis Workspace

### Vídeo (servicios de medios de streaming)

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de Dimension (utilizado en solicitudes de API) |
|--- |--- |
| [Contenido](sm-core.md) | `video` |
| [Segmento de contenido](sm-core.md) | `videosegment` |
| [Tipo de contenido](sm-core.md) | `videocontenttype` |
| [Nombre del reproductor del anuncio](sm-ads.md) | `videoadplayername` |
| [Posición del anuncio en la secuencia](sm-ads.md) | `videoadinpod` |
| [Fotogramas perdidos](sm-quality.md) | `videoqoedroppedframecountevar` |
| [Errores](sm-quality.md) | `videoqoeerrorcountevar` |
| [Velocidad de bits media](sm-quality.md) | `videoqoebitrateaverageevar` |
| [Cambios de velocidad de bits](sm-quality.md) | `videoqoebitratechangecountevar` |
| [Duración total del búfer](sm-quality.md) | `videoqoebuffertimeevar` |
| [Eventos de búfer](sm-quality.md) | `videoqoebuffercountevar` |
| [Tiempo para el inicio](sm-quality.md) | `videoqoetimetostartevar` |
| [Pod de anuncios](sm-ads.md) | `videoadpod` |
| [Ruta de medios](sm-core.md) | `videopath` |
| [Anuncio](sm-ads.md) | `videoad` |
| [Nombre del reproductor de contenido](sm-core.md) | `videoplayername` |
| [Canal de contenido](sm-core.md) | `videochannel` |
| [Capítulo](sm-chapters.md) | `videochapter` |
| [Nombre de contenido (variable)](sm-core.md) | `videoname` |
| [Longitud del contenido (variable)](sm-core.md) | `videolength` |
| [Nombre del anuncio (variable)](sm-ads.md) | `videoadname` |
| [Duración del anuncio (variable)](sm-ads.md) | `videoadlength` |
| [Mostrar](sm-video-metadata.md) | `videoshow` |
| [Temporada](sm-video-metadata.md) | `videoseason` |
| [Episodio](sm-video-metadata.md) | `videoepisode` |
| [Red](sm-video-metadata.md) | `videonetwork` |
| [Tipo de programa](sm-video-metadata.md) | `videoshowtype` |
| [Cargas de publicidad](sm-ads.md) | `videoadload` |
| [MVPD](sm-video-metadata.md) | `videomvpd` |
| [Parte del día](sm-video-metadata.md) | `videodaypart` |
| [Anunciante](sm-ads.md) | `videoadadvertiser` |
| [ID de campaña](sm-ads.md) | `videoadcampaign` |
| [Género](sm-video-metadata.md) | `videogenre` |
| [Tipo de emisión](sm-core.md) | `videostreamtype` |
| [ID de error del reproductor SDK](sm-quality.md) | `videoqoeplayersdkerrors` |
| [Id. de error externo](sm-quality.md) | `videoqoeextneralerrors` |
| [Tipo de fuente de medios](sm-video-metadata.md) | `videofeedtype` |
| [Ruta de medios de entrada](entry-dimensions.md) | `entryvideopath` |
| [Ruta de medios de salida](exit-dimensions.md) | `exitvideopath` |
| [Género de entrada](entry-dimensions.md) | `entryvideogenre` |
| [Género de salida](exit-dimensions.md) | `exitvideogenre` |
| [Id. de error de SDK del reproductor de entrada](entry-dimensions.md) | `entryvideoqoeplayersdkerrors` |
| [Identificadores de error de SDK del reproductor de salida](exit-dimensions.md) | `exitvideoqoeplayersdkerrors` |
| [Id. de error externo de entrada](entry-dimensions.md) | `entryvideoqoeextneralerrors` |
| [Identificadores de error externo de salida](exit-dimensions.md) | `exitvideoqoeextneralerrors` |

### Adobe Social

Adobe Social está retirado.

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de Dimension (utilizado en solicitudes de API) |
|--- |--- |
| Términos | `socialterm` |
| Plataformas sociales/Propiedades | `socialcontentprovider` |
| Autores | `socialauthor` |
| Idioma | `sociallanguage` |
| Latitud y longitud | `sociallatlong` |
| Códigos de seguimiento de recurso | `socialassettrackingcode` |
| Propiedades sociales en propiedad | `socialaccountandappids` |
| Identificadores de publicación en propiedad | `socialownedpostids` |
| Definiciones sociales en propiedad | `socialinteractiontype` |
| Identificadores de propiedades en propiedad | `socialownedpropertyid` |
| Propiedades en propiedad frente a aplicaciones | `socialownedpropertypropertyvsapp` |
| Nombre de propiedades en propiedad | `socialownedpropertyname` |
| Definición de propiedades en propiedad frente a publicaciones | `socialowneddefinitionpropertyvspost` |
| Tipo de perspectivas de definición en propiedad | `socialowneddefinitioninsighttype` |
| Valor de perspectivas de definición en propiedad | `socialowneddefinitioninsightvalue` |
| Métrica de definición en propiedad | `socialowneddefinitionmetric` |
| Activo | `socialmediaid` |

### SDK móvil

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de Dimension (utilizado en solicitudes de API) |
|--- |--- |
| [Fecha de primer inicio](lifecycle-dimensions.md) | `mobileinstalldate` |
| [Id. de aplicación](lifecycle-dimensions.md) | `mobileappid` |
| [Número de inicios](lifecycle-dimensions.md) | `mobilelaunchnumber` |
| [Días transcurridos desde el primer uso](lifecycle-dimensions.md) | `mobiledayssincefirstuse` |
| [Días transcurridos desde el último uso](lifecycle-dimensions.md) | `mobiledayssincelastuse` |
| [Hora del día (SDK)](lifecycle-dimensions.md) | `mobilehourofday` |
| [Día de la semana (SDK)](lifecycle-dimensions.md) | `mobiledayofweek` |
| [Sistema operativo (SDK)](lifecycle-dimensions.md) | `mobileosenvironment` |
| [Días transcurridos desde la última actualización](lifecycle-dimensions.md) | `mobiledayssincelastupgrade` |
| [Veces que se ha iniciado desde la última actualización](lifecycle-dimensions.md) | `mobilelaunchessincelastupgrade` |
| [Nombre de dispositivo (SDK)](lifecycle-dimensions.md) | `mobiledevice` |
| [Versión del sistema operativo (SDK)](lifecycle-dimensions.md) | `mobileosversion` |
| [Beacon mayor](lifecycle-dimensions.md) | `mobilebeaconmajor` |
| [Beacon menor](lifecycle-dimensions.md) | `mobilebeaconminor` |
| [UUID de señalización](lifecycle-dimensions.md) | `mobilebeaconuuid` |
| [Proximidad del Beacon](lifecycle-dimensions.md) | `mobilebeaconproximity` |
| [Ubicación (menos de 10 km)](lifecycle-dimensions.md) | `latlon1` |
| [Ubicación (menos de 100 m)](lifecycle-dimensions.md) | `latlon23` |
| [Ubicación (menos de 1 m)](lifecycle-dimensions.md) | `latlon45` |
| [Nombre del punto de interés](lifecycle-dimensions.md) | `pointofinterest` |
| [Distancia hasta el centro del punto de interés](lifecycle-dimensions.md) | `pointofinterestdistance` |
| [Precisión de ubicación](lifecycle-dimensions.md) | `mobileplaceaccuracy` |
| [Categoría del lugar](lifecycle-dimensions.md) | `mobileplacecategory` |
| [ID del lugar](lifecycle-dimensions.md) | `mobileplaceid` |
| [Beacon mayor de entrada](lifecycle-dimensions.md) | `entrymobilebeaconmajor` |
| [Beacon mayor de salida](lifecycle-dimensions.md) | `exitmobilebeaconmajor` |
| [Beacon menor de entrada](lifecycle-dimensions.md) | `entrymobilebeaconminor` |
| [Beacon menor de salida](lifecycle-dimensions.md) | `exitmobilebeaconminor` |
| [UUID de Beacon de entrada](lifecycle-dimensions.md) | `entrymobilebeaconuuid` |
| [UUID de Beacon de salida](lifecycle-dimensions.md) | `exitmobilebeaconuuid` |
| [Proximidad del Beacon de entrada](lifecycle-dimensions.md) | `entrymobilebeaconproximity` |
| [Proximidad del Beacon de salida](lifecycle-dimensions.md) | `exitmobilebeaconproximity` |

### Adobe Advertising

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de Dimension (utilizado en solicitudes de API) |
|--- |--- |
| AMO EF ID | `amo_ef_id` |
| ID de AMO | `amo_cid` |

### Activity Map

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de Dimension (utilizado en solicitudes de API) |
|--- |--- |
| [Vínculo de Activity Map por región](activity-map-link-by-region.md) | `clickmaplinkbyregion` |
| [Región de Activity Map](activity-map-region.md) | `clickmapregion` |
| [Vínculo de Activity Map](activity-map-link.md) | `clickmaplink` |
| [Página de Activity Map](activity-map-page.md) | `clickmappage` |

### Integración de Nielsen

Para obtener más información sobre cómo implementar esta integración, consulte la [extensión de Nielsen](https://exchange.adobe.com/apps/ec/101361) en Adobe Exchange.

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de Dimension (utilizado en solicitudes de API) |
|--- |--- |
| Modelo de anuncio Nielsen | `nielsenadmodel` |
| Segmento C de Nielsen | `nielsensegmentc` |
| Segmento B de Nielsen | `nielsensegmentb` |
| Segmento A de Nielsen | `nielsensegmenta` |
| ID de contenido de Nielsen | `nielsencontentid` |
| Programa/recurso Nielsen | `nielsenasset` |
| VCID Nielsen | `nielsenvcid` |
| Opción de exclusión de Nielsen | `nielsenoptout` |
| ID + VCID de cliente de Nielsen | `nielsenclientidvcid` |
| ID de cliente de Nielsen | `nielsenclientid` |
| Opción de exclusión de Nielsen de entrada | `entrynielsenoptout` |
| Opción de exclusión de Nielsen de salida | `exitnielsenoptout` |
| ID + VCID de cliente Nielsen de entrada | `entrynielsenclientidvcid` |
| ID + VCID de cliente Nielsen de salida | `exitnielsenclientidvcid` |
| ID de cliente Nielsen de entrada | `entrynielsenclientid` |
| ID de cliente Nielsen de salida | `exitnielsenclientid` |

### Adobe Experience Manager (AEM)

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de Dimension (utilizado en solicitudes de API) |
|--- |--- |
| ID del recurso | `aemassetid` |
| Origen de recursos | `aemassetsource` |
| ID del recurso en el que se ha hecho clic | `aemclickedassetid` |
| ID del recurso de entrada | `entryaemassetid` |
| ID del recurso de salida | `exitaemassetid` |

### Adobe Campaign

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de Dimension (utilizado en solicitudes de API) |
|--- |--- |
| ID de envío ejecutado de Adobe Campaign | `ac_delivery_internal_name` |
