---
title: Compatibilidad de dimensiones de Analytics
description: Referencia para dimensiones e informes de Analytics.
exl-id: 1884bc20-b04d-4f9a-b057-2b2fbe53190d
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '985'
ht-degree: 100%

---

# Compatibilidad de dimensiones de Analytics

Esta página enumera las dimensiones admitidas en sus respectivas funciones de Analytics.

>[!NOTE]
>
>En esta lista se omiten los nombres de las variables personalizadas, clasificaciones y atributos de visitantes. Estos elementos de dimensión son específicos de cada grupo de informes.

>[!NOTE]
>
>Hay algunas superposiciones en las que las herramientas de Analytics utilizan términos diferentes para dimensiones similares. Por ejemplo, Reports &amp; Analytics utiliza `browserwidth` mientras que Analysis Workspace utiliza `browserwidthbucketed`.

## Dimensiones compatibles con Reports &amp; Analytics y con Analysis Workspace

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|---|---|
| Analytics for Target | `targetraw` |
| ID de audiencias | `mcaudiences` |
| Explorador | `browser` |
| Tipo de navegador | `browsertype` |
| Categoría | `category` |
| Ciudades | `geocity` |
| Profundidad de color | `colordepth` |
| Tipo de conexión | `connectiontype` |
| Compatibilidad con cookies | `cookie` |
| Países | `geocountry` |
| Lealtad del cliente | `customerloyalty` |
| Variables de conversión personalizadas | `evar1`, `evar2`, etc. |
| Variables de Custom Insight | `prop1`, `prop2`, etc. |
| Vínculo personalizado | `customlink` |
| Días antes de la primera compra | `daysbeforefirstpurchase` |
| Días desde la última compra | `dayssincelastpurchase` |
| Dominio | `filtereddomain` |
| Vínculo de descarga | `downloadlink` |
| Página de entrada | `entrypage` |
| Página de entrada original | `entrypageoriginal` |
| Vínculo de salida | `exitlink` |
| Canal de primer contacto | `firsttouchchannel` |
| Detalles de canal de primer contacto | `firsttouchchanneldetail` |
| Habilitado para Java | `javaenabled` |
| Idioma | `language` |
| Canal de último contacto | `lasttouchchannel` |
| Detalles de canal de último contacto | `lasttouchchanneldetail` |
| Variables de lista | `listvariables` |
| Canal de marketing | `marketingchannel` |
| Compatibilidad con el audio del dispositivo móvil | `mobileaudiosupport` |
| Operador de telefonía móvil | `mobilecarrier` |
| Profundidad de color del dispositivo móvil | `mobilecolordepth` |
| Compatibilidad con cookies del dispositivo móvil | `mobilecookiesupport` |
| Dispositivo móvil | `mobiledevicename` |
| Tipo de dispositivo móvil | `mobiledevicetype` |
| Longitud máxima del correo electrónico móvil | `mobileemaillength` |
| Compatibilidad con la imagen del dispositivo móvil | `mobileimagesupport` |
| Fabricante de dispositivos móviles | `mobilemanufacturer` |
| Sistema operativo móvil (obsoleto) | `mobileos` |
| Altura de la pantalla del dispositivo móvil | `mobilescreenheight` |
| Tamaño de la pantalla del dispositivo móvil | `mobilescreensize` |
| Ancho de la pantalla del dispositivo móvil | `mobilescreenwidth` |
| Longitud máxima de la dirección URL del explorador móvil | `mobileurllength` |
| Compatibilidad con el vídeo del dispositivo móvil | `mobilevideosupport` |
| Resolución del monitor | `monitorresolution` |
| Sistema operativo | `operatingsystem` |
| Dominio de referencia original | `referringdomainoriginal` |
| Página | `page` |
| Páginas no encontradas | `pagesnotfound` |
| Product | `product` |
| Referente | `referrer` |
| Tipo de referente | `referrertype` |
| Dominio de referencia | `referringdomain` |
| Regiones | `georegion` |
| Frecuencia de retorno | `returnfrequency` |
| SC-TnT | `tntbase` |
| Motor de búsqueda | `searchengine` |
| Palabra clave de búsqueda | `searchenginekeyword` |
| Motor de búsqueda - Naturales | `searchenginenatural` |
| Motor de búsqueda: de pago | `searchenginepaid` |
| Palabra clave de búsqueda: natural | `searchenginenaturalkeyword` |
| Palabra clave de búsqueda: de pago | `searchenginepaidkeyword` |
| Clasificación de todas las páginas de búsqueda | `searchenginepagerank` |
| Server | `server` |
| Visitas de página única | `singlepagevisits` |
| Sección del sitio | `sitesections` |
| Tiempo empleado por visita (granular) | `sitetime` |
| Código de seguimiento | `campaign` |
| Área de mercado designada (DMA) de EE.UU. | `geodma` |
| Estados estadounidenses | `state` |
| Tiempo previo al evento | `timeprior` |
| Tiempo empleado por visita - General | `timespent` |
| Profundidad de la visita | `pathlength` |
| Número de visita | `visitnumber` |
| Código postal | `zip` |

## Dimensiones compatibles únicamente con Analysis Workspace

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| AM/PM | `timepartampm` |
| Altura del explorador: Agrupado | `browserheightbucketed` |
| Anchura del explorador: Agrupado | `browserwidthbucketed` |
| Día | `daterangeday` |
| Día del mes | `timepartdayofmonth` |
| Día de la semana | `dayofweek` |
| Día de la semana | `timepartdayofweek` |
| Día del año | `timepartdayofyear` |
| Días transcurridos desde la última visita | `dayssincelastvisit` |
| Acceder a Custom Insights | `entryprops` |
| Variables de lista de entrada | `entrylistvariables` |
| Servidor de entrada | `entryserver` |
| Sección de sitio de entrada | `entrysitesections` |
| Salir de Custom Insights | `exitprops` |
| Variables de lista de salida | `exitlistvariables` |
| Salir de la página | `exitpage` |
| Servidor de salida | `exitserver` |
| Sección del sitio de salida | `exitsitesections` |
| Profundidad de visita | `hitdepth` |
| Tipo de visita | `hittype` |
| Hora | `daterangehour` |
| Hora del día | `timeparthourofday` |
| Detalles del canal de marketing | `marketingchanneldetail` |
| Minuto | `daterangeminute` |
| Longitud máxima del marcador móvil | `mobilebookmarklength` |
| Número de dispositivo móvil | `mobiledevicenumber` |
| DRM móvil | `mobiledrm` |
| Servicios de información móvil | `mobileinformationservices` |
| Máquina virtual Java móvil | `mobilejavavm` |
| Decoración de correo móvil | `mobilemaildecoration` |
| Protocolos de red móvil | `mobilenetprotocols` |
| Pulsar y hablar móvil | `mobilepushtotalk` |
| Mes | `daterangemonth` |
| Mes del año | `timepartmonthofyear` |
| Tipos de sistemas operativos | `operatingsystemgroup` |
| Búsqueda de pago | `paidsearch` |
| Compatibilidad con cookies persistentes | `persistentcookie` |
| Trimestre | `daterangequarter` |
| Trimestre del año | `timepartquarterofyear` |
| Encuesta | `surveybase` |
| Tiempo empleado en la página - Agrupado | `averagepagetime` |
| Tiempo empleado en la página (granular) | `pagetimeseconds` |
| Motivo de exclusión de seguimiento | `optoutreason` |
| Día de la semana/Fin de semana | `timepartweekdayweekend` |
| Semana | `daterangeweek` |
| Año | `daterangeyear` |

## Dimensiones de reconocimiento de contenido compatibles únicamente con Analysis Workspace

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| Activity Map XY | `clickmapxy` |
| ID de sesión de contenidos | `videosessionid` |
| Método de acceso de Nielsen | `nielsenaccmethod` |
| ID de aplicación de Nielsen | `nielsenappid` |
| Recurso de canal de Nielsen | `nielsenchannelasset` |
| Tipo de contenido de Nielsen | `nielsencontenttype` |

## Dimensiones compatibles únicamente con Reports &amp; Analytics

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| Altura del explorador | `browserheight` |
| Anchura del explorador | `browserwidth` |
| Clientes únicos diarios | `dailyuniquecustomers` |
| JavaScript | `javascriptsupport` |
| Versión de JavaScript | `javascriptversion` |
| Clientes únicos mensuales | `monthlyuniquecustomers` |
| Clientes únicos trimestrales | `quarterlyuniquecustomers` |
| Zonas horarias | `timezone` |
| Dominios de nivel superior | `topleveldomain` |
| Estado del visitante | `legacystate` |
| Clientes únicos semanales | `weeklyuniquecustomers` |
| Clientes únicos anuales | `yearlyuniquecustomers` |

## Dimensiones de reconocimiento de contenido compatibles con Reports &amp; Analytics y con Analysis Workspace

### Vídeo (análisis de medios)

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| Contenido | `video` |
| Segmento de contenido | `videosegment` |
| Tipo de contenido | `videocontenttype` |
| Nombre del reproductor del anuncio | `videoadplayername` |
| Posición del anuncio en la secuencia | `videoadinpod` |
| Fotogramas perdidos | `videoqoedroppedframecountevar` |
| Errores | `videoqoeerrorcountevar` |
| Velocidad de bits media | `videoqoebitrateaverageevar` |
| Cambios en la velocidad de bits | `videoqoebitratechangecountevar` |
| Duración total del búfer | `videoqoebuffertimeevar` |
| Eventos de búfer | `videoqoebuffercountevar` |
| Tiempo para el inicio | `videoqoetimetostartevar` |
| Pod de anuncios | `videoadpod` |
| Ruta de medios | `videopath` |
| Publicidad | `videoad` |
| Nombre del reproductor de contenido | `videoplayername` |
| Canal de contenido | `videochannel` |
| Capítulo | `videochapter` |
| Nombre del contenido (variable) | `videoname` |
| Duración del contenido (variable) | `videolength` |
| Nombre del anuncio (variable) | `videoadname` |
| Duración del anuncio (variable) | `videoadlength` |
| Show | `videoshow` |
| Temporada | `videoseason` |
| Episodio | `videoepisode` |
| Red | `videonetwork` |
| Tipo de programa | `videoshowtype` |
| Cargas publicitarias | `videoadload` |
| MVPD | `videomvpd` |
| Parte del día | `videodaypart` |
| Anunciante | `videoadadvertiser` |
| ID de campaña | `videoadcampaign` |
| Género | `videogenre` |
| Tipo de emisión | `videostreamtype` |
| ID de error de SDK de reproductor | `videoqoeplayersdkerrors` |
| ID de error externo | `videoqoeextneralerrors` |
| Tipo de fuente de contenidos | `videofeedtype` |
| Ruta de medios de entrada | `entryvideopath` |
| Ruta de medios de salida | `exitvideopath` |
| Género de entrada | `entryvideogenre` |
| Género de salida | `exitvideogenre` |
| Identificadores de error del SDK del reproductor de entrada | `entryvideoqoeplayersdkerrors` |
| Identificadores de error del SDK del reproductor de salida | `exitvideoqoeplayersdkerrors` |
| Identificadores de error externo de entrada | `entryvideoqoeextneralerrors` |
| Identificadores de error externo de salida | `exitvideoqoeextneralerrors` |

### Adobe Social

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
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

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| Fecha de primer lanzamiento | `mobileinstalldate` |
| ID de la aplicación | `mobileappid` |
| Número de inicios | `mobilelaunchnumber` |
| Días transcurridos desde el primer uso | `mobiledayssincefirstuse` |
| Días transcurridos desde el último uso | `mobiledayssincelastuse` |
| Hora del día (SDK) | `mobilehourofday` |
| Día de la semana (SDK) | `mobiledayofweek` |
| Sistema operativo (SDK) | `mobileosenvironment` |
| Días transcurridos desde la última actualización | `mobiledayssincelastupgrade` |
| Veces que se ha iniciado desde la última actualización | `mobilelaunchessincelastupgrade` |
| Nombre del dispositivo (SDK) | `mobiledevice` |
| Versión del sistema operativo (SDK) | `mobileosversion` |
| Beacon mayor | `mobilebeaconmajor` |
| Beacon menor | `mobilebeaconminor` |
| Identificador único universal (UUID, universally unique indentifier) de Beacon | `mobilebeaconuuid` |
| Proximidad de Beacon | `mobilebeaconproximity` |
| Ubicación (menos de 10 km) | `latlon1` |
| Ubicación (menos de 100 m) | `latlon23` |
| Ubicación (menos de 1 m) | `latlon45` |
| Nombre del punto de interés | `pointofinterest` |
| Distancia hasta el centro del punto de interés | `pointofinterestdistance` |
| Precisión de ubicación | `mobileplaceaccuracy` |
| Categoría del lugar | `mobileplacecategory` |
| ID del lugar | `mobileplaceid` |
| Beacon mayor de entrada | `entrymobilebeaconmajor` |
| Beacon mayor de salida | `exitmobilebeaconmajor` |
| Beacon menor de entrada | `entrymobilebeaconminor` |
| Beacon menor de salida | `exitmobilebeaconminor` |
| UUID de Beacon de entrada | `entrymobilebeaconuuid` |
| UUID de Beacon de salida | `exitmobilebeaconuuid` |
| Proximidad del Beacon de entrada | `entrymobilebeaconproximity` |
| Proximidad del Beacon de salida | `exitmobilebeaconproximity` |

### Adobe Advertising Cloud (AMO)

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| AMO EF ID | `amo_ef_id` |
| ID de AMO | `amo_cid` |

### Activity Map

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| Vínculo de Activity Map por región | `clickmaplinkbyregion` |
| Región de Activity Map | `clickmapregion` |
| Vínculo de Activity Map | `clickmaplink` |
| Página de Activity Map | `clickmappage` |

### Integración de Nielsen

Para obtener más información sobre la implementación de esta integración, visite la [Extensión Nielsen](https://exchange.adobe.com/experiencecloud.details.101361.html).

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| Modelo de anuncio de Nielsen | `nielsenadmodel` |
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

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| ID del recurso | `aemassetid` |
| Origen de recursos | `aemassetsource` |
| ID del recurso en el que se ha hecho clic | `aemclickedassetid` |
| ID del recurso de entrada | `entryaemassetid` |
| ID del recurso de salida | `exitaemassetid` |

### Adobe Campaign

| Nombre de la dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| ID de entrega ejecutada de Adobe Campaign | `ac_delivery_internal_name` |
