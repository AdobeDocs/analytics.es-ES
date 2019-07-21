---
title: Compatibilidad de dimensiones de Analytics
seo-title: Dimensiones y informes de Analytics compatibles con Analysis Workspace, Informes y análisis, o ambos.
description: Referencia para dimensiones e informes de Analytics.
seo-description: Dimensiones de Espacio de trabajo de análisis, dimensiones de Informes y análisis, dimensiones, dimensiones de R & A, Dimensiones de espacio de trabajo
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# Compatibilidad de dimensiones de Analytics

Este artículo de referencia enumera las dimensiones y los informes admitidos en Informes y análisis y Analysis Workspace, solo en Analysis Workspace y solo en Informes y análisis.

Recuerde que

* no son listas detalladas. Cada grupo de informes puede tener habilitados diferentes conjuntos de variables de producto. Además, cualquier grupo de informes puede tener cualquier cantidad de variables personalizadas habilitadas o deshabilitadas o asignadas a variables de producto. También hemos excluido los atributos y clasificaciones de visitantes, ya que son exclusivos para cada grupo de informes.

* There are some cases of overlap, where Analytics tools use different terms for what is essentially the same thing, for example: `browserwidth` and `browserwidthbucketed`.

## Dimensiones compatibles con Reports &amp; Analytics y con Analysis Workspace

| Nombre de dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|---|---|
| Analytics para Target | targetraw |
| ID de audiencias | mcaudiences |
| Explorador | browser |
| Tipo de navegador | browsertype |
| Categoría | category |
| Ciudades | geocity |
| Profundidad de color | colordepth |
| Tipo de conexión | connectiontype |
| Compatibilidad con cookies | cookie |
| Países | geocountry |
| Lealtad del cliente | customerloyalty |
| Variables de conversión personalizadas | evar 1, evar 2, etc. |
| Variables de perspectiva personalizadas | prop 1, prop 2, etc. |
| Vínculo personalizado | customlink |
| Días antes de la primera compra | daysbeforefirstpurchase |
| Días desde la última compra | dayssincelastpurchase |
| Dominio | filtereddomain |
| Vínculo de descarga | downloadlink |
| Página de entrada | entrypage |
| Original de página de entrada | entrypageoriginal |
| Vínculo de salida | exitlink |
| Canal de primer toque | firsttouchchannel |
| Detalles de canal de primer toque | firsttouchchanneldetail |
| Java habilitado | javaenabled |
| Idioma | language |
| Canal de último toque | lasttouchchannel |
| Detalles de canal de último toque | lasttouchchanneldetail |
| Variables de lista | listvariables |
| Canal de marketing | marketingchannel |
| Compatibilidad con el audio del dispositivo móvil | mobileaudiosupport |
| Operador de telefonía móvil | mobilecarrier |
| Profundidad de color del dispositivo móvil | mobilecolordepth |
| Compatibilidad con cookies del dispositivo móvil | mobilecookiesupport |
| Dispositivo móvil | mobiledevicename |
| Tipo de dispositivo móvil | mobiledevicetype |
| Longitud máxima del correo electrónico móvil | mobileemaillength |
| Compatibilidad con la imagen del dispositivo móvil | mobileimagesupport |
| Fabricante de dispositivos móviles | mobilemanufacturer |
| Sistema operativo móvil (obsoleto) | mobileos |
| Altura de la pantalla del dispositivo móvil | mobilescreenheight |
| Tamaño de la pantalla del dispositivo móvil | mobilescreensize |
| Ancho de la pantalla del dispositivo móvil | mobilescreenwidth |
| Longitud máxima de la dirección URL del explorador móvil | mobileurllength |
| Compatibilidad con el video del dispositivo móvil | mobilevideosupport |
| Resolución del monitor | monitorresolution |
| Sistema operativo | operatingsystem |
| Dominio de referencia original | referringdomainoriginal |
| Página | página |
| Páginas no encontradas | pagesnotfound |
| Producto | producto |
| Referrer | referrer |
| Tipo de referente | referrertype |
| Dominio de referencia | referringdomain |
| Regiones | georegion |
| Frecuencia de retorno | returnfrequency |
| SC-TnT | tntbase |
| Motor de búsqueda | searchengine |
| Palabra clave de búsqueda | searchenginekeyword |
| Motor de búsqueda: natural | searchenginenatural |
| Motor de búsqueda: de pago | searchenginepaid |
| Palabra clave de búsqueda: natural | searchenginenaturalkeyword |
| Palabra clave de búsqueda: de pago | searchenginepaidkeyword |
| Clasificación de todas las páginas de búsqueda | searchenginepagerank |
| Servidor | server |
| Visitas a una sola página | singlepagevisits |
| Sección del sitio | sitesections |
| Tiempo empleado por visita (granular) | sitetime |
| Código de seguimiento | campaign |
| Área de mercado designada (DMA) de EE.UU. | geodma |
| Estados Unidos | state |
| Tiempo previo al evento | timeprior |
| Tiempo empleado por visita - General | timespent |
| Profundidad de la visita | pathlength |
| Número de visitas | visitnumber |
| Código postal | zip |

## Dimensiones compatibles únicamente con Analysis Workspace

| Nombre de dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| AM/PM | timepartampm |
| Alto del explorador - Agrupado | browserheightbucketed |
| Ancho del explorador - Agrupado | browserwidthbucketed |
| Día | daterangeday |
| Día del mes | timepartdayofmonth |
| Día de la semana | dayofweek |
| Día de la semana | timepartdayofweek |
| Día del año | timepartdayofyear |
| Días transcurridos desde la última visita | dayssincelastvisit |
| Perspectivas personalizadas de entrada | entryprops |
| Variables de lista de entrada | entrylistvariables |
| Servidor de entrada | entryserver |
| Sección de sitio de entrada | entrysitesections |
| Perspectivas personalizadas de salida | exitprops |
| Variables de lista de salida | exitlistvariables |
| Salir de la página | exitpage |
| Servidor de salida | exitserver |
| Sección del sitio de salida | exitsitesections |
| Profundidad de acierto | hitdepth |
| Tipo de visita | hittype |
| Hora | daterangehour |
| Hora del día | timeparthourofday |
| Detalles de canal de marketing | marketingchanneldetail |
| Minuto | daterangeminute |
| Longitud máxima del marcador móvil | mobilebookmarklength |
| Número de dispositivo móvil | mobiledevicenumber |
| DRM móvil | mobiledrm |
| Servicios de información móvil | mobileinformationservices |
| Máquina virtual Java móvil | mobilejavavm |
| Decoración de correo móvil | mobilemaildecoration |
| Protocolos de red móvil | mobilenetprotocols |
| Pulsar y hablar móvil | mobilepushtotalk |
| Mes | daterangemonth |
| Mes del año | timepartmonthofyear |
| Tipos de sistemas operativos | operatingsystemgroup |
| Búsqueda de pago | paidsearch |
| Compatibilidad con cookies persistentes | persistentcookie |
| Trimestre | daterangequarter |
| Trimestre del año | timepartquarterofyear |
| Survey | surveybase |
| Tiempo empleado en la página - Agrupado | averagepagetime |
| Tiempo empleado en la página (granular) | pagetimeseconds |
| Motivo de omisión de seguimiento | optoutreason |
| Día de la semana/Fin de semana | timepartweekdayweekend |
| Semana | daterangeweek |
| Año | daterangeyear |

## Dimensiones de reconocimiento de contenido compatibles únicamente con Analysis Workspace

| Nombre de dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| Activity Map XY | clickmapxy |
| ID de sesión de medios | videosessionid |
| Método de acceso de Nielsen | nielsenaccmethod |
| ID de aplicación de Nielsen | nielsenappid |
| Recurso de canal de Nielsen | nielsenchannelasset |
| Tipo de contenido de Nielsen | nielsencontenttype |

## Dimensiones compatibles únicamente con Reports &amp; Analytics

| Nombre de dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| Altura del explorador | browserheight |
| Anchura del explorador | browserwidth |
| Clientes únicos diarios | dailyuniquecustomers |
| JavaScript | javascriptsupport |
| Versión de JavaScript | javascriptversion |
| Clientes únicos mensuales | monthlyuniquecustomers |
| Clientes únicos trimestrales | quarterlyuniquecustomers |
| Zonas horarias | timezone |
| Dominios de nivel superior | topleveldomain |
| Estado del visitante | legacystate |
| Clientes únicos semanales | weeklyuniquecustomers |
| Clientes únicos anuales | yearlyuniquecustomers |

## Informes preconfigurados en Reports &amp; Analytics

Reports &amp; Analytics contiene varios informes preconfigurados que, o bien no se asignan a una dimensión específica, o bien el informe utiliza una clase de dimensiones. Estos informes se enumeran aquí:

* Longitud de la dirección URL del marcador
* Exploradores
* Tipos de explorador
* Canal de conversión de campañas
* Canal de conversión del carro de compras
* Ciudades
* Clics hasta la página
* Países
* Venta cruzada
* Canal de eventos personalizados
* Compatibilidad con Decoration Mail
* Transmisión del número de dispositivo (ENCENDIDO/APAGADO)
* Dominios
* DRM
* Páginas de entrada
* Páginas de salida
* Visitas en el orden previsto
* Rutas completas
* ICities
* Servicios de información
* Versión de Java
* Idiomas
* Rutas más largas
* Espectadores simultáneos de medios
* Horario de medios
* Detalles de medios
* Información general de medios
* Resoluciones de monitor
* Protocolos de red
* Complementos de Netscape
* Página siguiente
* Flujo de página siguiente
* Sistema operativo
* Tipos de sistemas operativos
* Profundidad de página
* Resumen de página
* PathFinder
* Flujo de página anterior
* Página anterior
* PTT
* Canal de conversión de productos
* Canal de conversión de compra
* Dominios de referencia
* Regiones
* Recargas
* Motores de búsqueda: Todo
* Motores de búsqueda: Natural
* Motores de búsqueda: Pagado
* Palabras clave de búsqueda: Todo
* Palabras clave de búsqueda: Natural
* Palabras clave de búsqueda: Pagado
* Detalles de la actividad de Target
* Tiempo invertido en la página
* Zonas horarias
* Dominios de nivel superior
* DMA de EE. UU.
* Estados de EE. UU.
* Número de visitas
* Página principal del visitante

## Dimensiones de reconocimiento de contenido compatibles con Reports &amp; Analytics y con Analysis Workspace

### Vídeo (análisis de medios)

| Nombre de dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| Contenido | video |
| Segmento de contenido | videosegment |
| Tipo de contenido | videocontenttype |
| Nombre del reproductor del anuncio | videoadplayername |
| Posición del anuncio en la secuencia | videoadinpod |
| Fotogramas perdidos | videoqoedroppedframecountevar |
| Errores | videoqoeerrorcountevar |
| Velocidad de bits media | videoqoebitrateaverageevar |
| Cambios en la velocidad de bits | videoqoebitratechangecountevar |
| Duración total del búfer | videoqoebuffertimeevar |
| Eventos de búfer | videoqoebuffercountevar |
| Tiempo para el inicio | videoqoetimetostartevar |
| Pod de anuncios | videoadpod |
| Ruta de medios | videopath |
| Publicidad | videoad |
| Nombre del reproductor de contenido | videoplayername |
| Canal de contenido | videochannel |
| Capítulo | videochapter |
| Nombre del contenido (variable) | videoname |
| Duración del contenido (variable) | videolength |
| Nombre del anuncio (variable) | videoadname |
| Duración del anuncio (variable) | videoadlength |
| Show | videoshow |
| Temporada | videoseason |
| Episodio | videoepisode |
| Red | videonetwork |
| Tipo de programa | videoshowtype |
| Cargas publicitarias | videoadload |
| MVPD | videomvpd |
| Parte del día | videodaypart |
| Anunciante | videoadadvertiser |
| ID de campaña | videoadcampaign |
| Género | videogenre |
| Tipo de emisión | videostreamtype |
| ID de error de SDK de reproductor | videoqoeplayersdkerrors |
| ID de error externo | videoqoeexternalerrors |
| Tipo de fuente de medios | videofeedtype |
| Ruta de medios de entrada | entryvideopath |
| Ruta de medios de salida | exitvideopath |
| Género de entrada | entryvideogenre |
| Género de salida | exitvideogenre |
| Identificadores de error del SDK del reproductor de entrada | entryvideoqoeplayersdkerrors |
| Identificadores de error del SDK del reproductor de salida | exitvideoqoeplayersdkerrors |
| Identificadores de error externo de entrada | entryvideoqoeexternalerrors |
| Identificadores de error externo de salida | exitvideoqoeexternalerrors |

### Adobe Social

| Nombre de dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| Términos | socialterm |
| Plataformas sociales/Propiedades | socialcontentprovider |
| Autores | socialauthor |
| Idioma | sociallanguage |
| Latitud y longitud | sociallatlong |
| Códigos de seguimiento de recurso | socialassettrackingcode |
| Propiedades sociales en propiedad | socialaccountandappids |
| Identificadores de publicación en propiedad | socialownedpostids |
| Definiciones sociales en propiedad | socialinteractiontype |
| Identificadores de propiedades en propiedad | socialownedpropertyid |
| Propiedades en propiedad frente a aplicaciones | socialownedpropertypropertyvsapp |
| Nombre de propiedades en propiedad | socialownedpropertyname |
| Definición de propiedades en propiedad frente a publicaciones | socialowneddefinitionpropertyvspost |
| Tipo de perspectivas de definición en propiedad | socialowneddefinitioninsighttype |
| Valor de perspectivas de definición en propiedad | socialowneddefinitioninsightvalue |
| Métrica de definición en propiedad | socialowneddefinitionmetric |
| Activo | socialmediaid |

### SDK móvil

| Nombre de dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| Fecha de primer lanzamiento | mobileinstalldate |
| ID de la aplicación | mobileappid |
| Número de inicios | mobilelaunchnumber |
| Días transcurridos desde el primer uso | mobiledayssincefirstuse |
| Días transcurridos desde el último uso | mobiledayssincelastuse |
| Hora del día (SDK) | mobilehourofday |
| Día de la semana (SDK) | mobiledayofweek |
| Sistema operativo (SDK) | mobileosenvironment |
| Días transcurridos desde la última actualización | mobiledayssincelastupgrade |
| Veces que se ha iniciado desde la última actualización | mobilelaunchessincelastupgrade |
| Nombre del dispositivo (SDK) | mobiledevice |
| Versión del sistema operativo (SDK) | mobileosversion |
| Beacon mayor | mobilebeaconmajor |
| Beacon menor | mobilebeaconminor |
| Identificador único universal (UUID, universally unique indentifier) de Beacon | mobilebeaconuuid |
| Proximidad de Beacon | mobilebeaconproximity |
| Ubicación (menos de 10 km) | latlon1 |
| Ubicación (menos de 100 m) | latlon23 |
| Ubicación (menos de 1 m) | latlon45 |
| Nombre del punto de interés | pointofinterest |
| Distancia hasta el centro del punto de interés | pointofinterestdistance |
| Precisión de ubicación | mobileplaceaccuracy |
| Categoría del lugar | mobileplacecategory |
| ID del lugar | mobileplaceid |
| Beacon mayor de entrada | entrymobilebeaconmajor |
| Beacon mayor de salida | exitmobilebeaconmajor |
| Beacon menor de entrada | entrymobilebeaconminor |
| Beacon menor de salida | exitmobilebeaconminor |
| UUID de Beacon de entrada | entrymobilebeaconuuid |
| UUID de Beacon de salida | exitmobilebeaconuuid |
| Proximidad del Beacon de entrada | entrymobilebeaconproximity |
| Proximidad del Beacon de salida | exitmobilebeaconproximity |

### Adobe Advertising Cloud (AMO)

| Nombre de dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| AMO EF ID | amo_ef_id |
| ID de AMO | amo_cid |

### Activity Map

| Nombre de dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| Vínculo de Activity Map por región | clickmaplinkbyregion |
| Región de Activity Map | clickmapregion |
| Vínculo de Activity Map | clickmaplink |
| Página de Activity Map | clickmappage |

### Integración de Nielsen

Para obtener más información sobre la implementación de esta integración, visite [asociación con Nielsen](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/nielsen-partnership.html).

| Nombre de dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| Modelo de anuncio de Nielsen | nielsenadmodel |
| Segmento C de Nielsen | nielsensegmentc |
| Segmento B de Nielsen | nielsensegmentb |
| Segmento A de Nielsen | nielsensegmenta |
| ID de contenido de Nielsen | nielsencontentid |
| Programa/recurso Nielsen | nielsenasset |
| VCID Nielsen | nielsenvcid |
| Opción de exclusión de Nielsen | nielsenoptout |
| ID + VCID de cliente de Nielsen | nielsenclientidvcid |
| ID de cliente de Nielsen | nielsenclientid |
| Opción de exclusión de Nielsen de entrada | entrynielsenoptout |
| Opción de exclusión de Nielsen de salida | exitnielsenoptout |
| ID + VCID de cliente Nielsen de entrada | entrynielsenclientidvcid |
| ID + VCID de cliente Nielsen de salida | exitnielsenclientidvcid |
| ID de cliente Nielsen de entrada | entrynielsenclientid |
| ID de cliente Nielsen de salida | exitnielsenclientid |

### Adobe Experience Manager (AEM)

| Nombre de dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| Recurso | aemassetid |
| Origen de recursos | aemassetsource |
| ID del recurso en el que se ha hecho clic | aemclickedassetid |
| ID del recurso de entrada | entryaemassetid |
| ID del recurso de salida | exitaemassetid |

### Adobe Campaign

| Nombre de dimensión (visible en la interfaz de usuario de Analytics) | ID de dimensiones (utilizado en solicitudes de API) |
|--- |--- |
| ID de entrega ejecutada de Adobe Campaign | ac_delivery_internal_name |
