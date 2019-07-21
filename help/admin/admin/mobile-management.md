---
description: Al habilitar la administración de móviles se activan las variables de soluciones móviles, que capturan el ciclo de vida y otras métricas de aplicaciones móviles.
seo-description: Al habilitar la administración de móviles se activan las variables de soluciones móviles, que capturan el ciclo de vida y otras métricas de aplicaciones móviles.
seo-title: Administración de móviles
solution: Analytics
title: Administración de móviles
topic: Herramientas de administración
uuid: d 09 edf 72-bb 91-422 d-b 22 c -7 b 6971 f 228 de
translation-type: tm+mt
source-git-commit: 6184104b5a46242c5973552298964e96ff671d7c

---


# Administración de móviles

Al habilitar la administración de móviles se activan las variables de soluciones móviles, que capturan el ciclo de vida y otras métricas de aplicaciones móviles.

Esta integración entre Adobe Analytics y Mobile Services:

* Le permite compartir sus datos de KPI (Indicador de rendimiento clave) de Mobile Services con Adobe Analytics.
* Le permite activar el seguimiento de ubicación.
* Agrega nuevos informes en Analytics &gt; Informes &gt; Aplicación móvil.
* Agrega 25 nuevas clasificaciones de Adobe Mobile.
* Agrega 5 nuevas métricas de Adobe Mobile.
* Añade nuevas dimensiones de Adobe Mobile.
* Sincroniza datos con Analytics cada 15 minutos.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Administración]** &gt; **[!UICONTROL Grupos de informes]** &gt; **[!UICONTROL Editar configuración]** &gt; **[!UICONTROL Administración]** de móviles &gt; **[!UICONTROL Informes de aplicaciones móviles]**.

## Paso 1. Habilitar Informes de aplicaciones {#section_FBADF80AED2B4978A904ABB770B3B931}

Habilite los Informes de aplicaciones 3.0 para medir las siguientes métricas:

* **Adquisición:** realización de un seguimiento de las URL de referencia para las campañas de descarga de la aplicación.
* **Ciclo de vida:** nivel base de los informes proporcionados por las mediciones enviadas con cada inicio de aplicación.
* **Acciones de aplicación:** informes y rutas basadas en acciones internas de la aplicación.
* **Valor de duración:** comprenda cómo acumulan valor los usuarios a lo largo del tiempo mediante los KPI de la aplicación (p. ej., adquisiciones, vistas de anuncios, vídeos completos, compartido en medios sociales y cargas de fotografías).
* **Eventos cronometrados:** cantidad de tiempo que transcurre (en la aplicación y en tiempo total) entre las acciones clave de la aplicación (como el tiempo transcurrido hasta la primera compra).

## Paso 2: Activar el seguimiento de ubicación {#section_2CCBD205191C4CA3B7B71A6F11FF97EC}

Activar el seguimiento de ubicación le permite:

* Realizar un seguimiento de los datos de latitud y longitud, y realizar informes al respecto, en Analysis Workspace y Mobile Services.
* Identificar, crear y visualizar puntos de interés (POI) específicos dentro de Mobile Services. Los POI deben definirse en el archivo de configuración del SDK para móviles.
* Realizar un seguimiento de señalizaciones Bluetooth (UUID, principal, secundaria y proximidad).

## Paso 3. (Opcional) Habilitar/Deshabilitar informes y atribuciones anteriores para visitas en segundo plano {#section_1708BCAA87AA4884986F7532759C5DD4}

Habilitar las visitas en segundo plano (las generadas cuando la aplicación está en segundo plano) significa que estas se tratan como visitas en primer plano normales. Ahora aparecen en los informes regulares, lo que también afecta a la atribución. Esta configuración solo suele ser deseable para mantener la coherencia con implementaciones anteriores.

Lo recomendable es “incluir las visitas en segundo plano” en un [grupo de informes virtuales](../../components/vrs/vrs-about.md). Esto le permite ver las visitas, pero no afecta negativamente a su recuento y al de visitantes.
Mobile classifications are enabled after you enable **[!UICONTROL Mobile Management]** &gt; **[!UICONTROL Mobile Application Reporting]**.

Las clasificaciones sirven para categorizar los valores en grupos y realizar informes sobre el nivel del grupo. Por ejemplo, puede clasificar todas las campañas de Búsqueda pagada en una categoría como “términos de música pop” e informar sobre el éxito de esa categoría respecto a métricas como Instancias (o pulsaciones) y la conversión en eventos exitosos.

| Clasificación | Definición |
|--- |--- |
| Fecha de primer lanzamiento | Fecha del primer inicio tras la instalación o reinstalación.   MM/DD/AAAA |
| ID de la aplicación | Almacena el nombre y la versión de la aplicación en el siguiente formato:   `[AppName] [BundleVersion]`  Por ejemplo, `myapp 1.1.` |
| Número de inicios | Número de veces que una aplicación se ha iniciado o se ha extraído del segundo plano. |
| Días transcurridos desde el primer uso | Número de días transcurridos desde que se ejecutó por primera vez. |
| Días transcurridos desde el último uso | Número de días transcurridos desde que se ejecutó por última vez. |
| Hora del día | Mide la hora de inicio de la aplicación y usa el formato numérico de 24 horas. Se utiliza en la partición de tiempo para determinar las horas de mayor uso. |
| Día de la semana | Número del día de la semana en el que se inició la aplicación. |
| Nombre del dispositivo | Almacena el nombre del dispositivo.  Cadena de dos dígitos separados por comas que identifica el dispositivo. El primer número representa generalmente la generación del dispositivo y el segundo número representa generalmente versiones de miembros diferentes de la familia del dispositivo. |
| Versión del sistema operativo | Versión del SO. |
| Resolución | Anchura por altura en píxeles reales. |
| Valor de duración (eVar) | Rellenado con métodos trackLifetimeValue. |
| Fuente de adquisición |  |
| Medio de adquisición |  |
| Término de adquisición |  |
| Contenido de adquisición |  |
| Nombre de adquisición |  |
| Ubicación (menos de 10 km) | Rellenado con métodos trackLocation. |
| Ubicación (menos de 100 metros) | Rellenado con métodos trackLocation. |
| Ubicación (menos de 1 m) | Rellenado con métodos trackLocation. |
| Nombre del punto de interés | Se rellena con métodos trackLocation cuando el dispositivo está en un punto de interés definido. |
| Distancia hasta el centro del punto de interés | Se rellena con métodos trackLocation cuando el dispositivo está en un punto de interés definido. |
| ID de mensaje en la aplicación |  |
| Mensaje en la aplicación en línea |  |
| Insertar inclusión |  |
| ID de carga útil |  |

