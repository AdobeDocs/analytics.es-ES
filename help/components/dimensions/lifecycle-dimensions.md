---
title: Dimensiones del ciclo de vida móvil
description: Dimensiones basadas en los datos recopilados con Mobile SDK.
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
TQID: 'https://experienceleague.adobe.com/VUN8x5eMzIfJ9VGw76v2pWfKWU7b-ct-kI6liwWTObw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 6fd4400b33fcfc8bc3cd3ffc54fa738fef3441ef
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 8%
---
# Dimensiones del ciclo de vida móvil

>[!BEGINSHADEBOX]

*Esta página hace referencia a datos rastreados con frecuencia a través de Adobe Experience Platform Mobile SDK. Para obtener información de dispositivos móviles que usan el agente de usuario, consulte [Dimensiones de búsqueda móvil](mobile-dimensions.md). Para las métricas rastreadas con el SDK móvil, consulte [Métricas del ciclo vital móvil](../metrics/lifecycle-metrics.md).*

>[!ENDSHADEBOX]

| Nombre de dimensión de ciclo vital | Descripción | Variable de datos de contexto |
| --- | --- | --- |
| **[!UICONTROL Fecha de primer inicio]** | La fecha en la que la aplicación se ejecutó por primera vez después de instalarla o reinstalarla, en formato `M/d/yyyy`. | `a.InstallDate` |
| **[!UICONTROL Nombre de dispositivo (SDK)]** | El nombre del dispositivo que recopila SDK. | `a.DeviceName` |
| **[!UICONTROL Versión del sistema operativo (SDK)]** | El nombre y la versión del sistema operativo que recopila SDK. | `a.OSVersion` |
| **[!UICONTROL Resolución (SDK)]** | Resolución de pantalla del dispositivo en píxeles, como ancho x alto. | `a.Resolution` |
| **[!UICONTROL Source de adquisición]** | El referente original de una campaña de adquisición de aplicación, como un boletín informativo o una red de medios sociales. | `a.referrer.campaign.source` |
| **[!UICONTROL Id. de aplicación]** | El nombre y la versión de la aplicación con el formato `AppName BundleVersion (app version code)`. Por ejemplo, `MyAppName 1.1(1)`. | `a.AppID` |
| **[!UICONTROL Medium de adquisición]** | Medio de marketing de una campaña de adquisición de aplicación, como un banner o un correo electrónico. | `a.referrer.campaign.medium` |
| **[!UICONTROL Término de adquisición]** | Palabras clave pagas u otros términos asociados con una campaña de adquisición de aplicación. | `a.referrer.campaign.term` |
| **[!UICONTROL Contenido de adquisición]** | Nombre o ID del contenido que muestra el vínculo de adquisición de la aplicación. | `a.referrer.campaign.content` |
| **[!UICONTROL Nombre de adquisición]** | Nombre de la campaña de adquisición de aplicación. | `a.referrer.campaign.name` |
| **[!UICONTROL Ubicación (menos de 10 km)]** | Latitud y longitud del visitante, con precisión del primer decimal. Por ejemplo, `040.9` `-111.9`. | `a.loc.lat.a` + `a.loc.lon.a` |
| **[!UICONTROL Ubicación (menos de 100 m)]** | Latitud y longitud del visitante, con precisión del tercer decimal. Por ejemplo, `040.932` `-111.931`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| **[!UICONTROL Ubicación (menos de 1 m)]** | Latitud y longitud del visitante, con precisión del quinto decimal. Por ejemplo, `040.93231` `-111.93152`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| **[!UICONTROL Nombre del punto de interés]** | El nombre del punto de interés (PDI) en el que se encuentra el dispositivo. Cuando se usa la extensión [Places](https://developer.adobe.com/client-sdks/solution/places/), este valor es el nombre de región de Places. | `a.loc.poi` |
| **[!UICONTROL Distancia hasta el centro del punto de interés]** | La distancia entre el dispositivo y el centro del punto de interés en el que se encuentra el dispositivo. | `a.loc.dist` |
| **[!UICONTROL Número de inicios]** | El número de veces que la aplicación se inició o se sacó del segundo plano. | `a.Launches` |
| **[!UICONTROL Días transcurridos desde el primer uso]** | Cantidad de días desde que la aplicación se ejecutó por primera vez. | `a.DaysSinceFirstUse` |
| **[!UICONTROL Nombre de acción]** | Nombre de la acción enviada en una llamada de `trackAction`. | `a.action` |
| **[!UICONTROL Valor de duración (evar)]** | El valor de duración de un usuario, como compras acumuladas en el tiempo, visualizaciones de anuncios, visualizaciones de vídeo completas o usos compartidos en medios sociales. | `a.ltv.amount` |
| **[!UICONTROL Beacon mayor]** | El ID principal de la señalización cerca de la que se encuentra el dispositivo. | `a.beacon.major` |
| **[!UICONTROL Beacon menor]** | El ID menor de la señalización cerca de la que se encuentra el dispositivo. | `a.beacon.minor` |
| **[!UICONTROL UUID de señalización]** | El UUID de la señalización cerca de la que se encuentra el dispositivo. | `a.beacon.uuid` |
| **[!UICONTROL Proximidad del Beacon]** | La proximidad del dispositivo a la señalización: `0` (desconocido), `1` (inmediato), `2` (cerca) o `3` (lejos). | `a.beacon.prox` |
| **[!UICONTROL Días transcurridos desde el último uso]** | Número de días transcurridos desde que se usó la aplicación por última vez. | `a.DaysSinceLastUse` |
| **[!UICONTROL Hora del día (SDK)]** | Hora a la que se inició la aplicación, en formato de 24 horas. Útil para la partición de tiempo a fin de determinar las horas de mayor uso. | `a.HourOfDay` |
| **[!UICONTROL Día de la semana (SDK)]** | El día de la semana en que se inició la aplicación. | `a.DayOfWeek` |
| **[!UICONTROL Id. de punto de interés]** | El ID del punto de interés en el que se encuentra el dispositivo. Cuando se usa la extensión [Places](https://developer.adobe.com/client-sdks/solution/places/), este valor es el ID de región de Places. | `a.loc.poi.id` |

>[!NOTE]
>
>Algunas de estas dimensiones se rellenan con métodos de la versión heredada de Mobile Services SDK (4.x), que ya no es compatible. Adobe Experience Platform Mobile SDK no los rellena automáticamente:
>
>* **Dimensiones de adquisición** ([!UICONTROL Source de adquisición], [!UICONTROL Medium], [!UICONTROL Término], [!UICONTROL Contenido] y [!UICONTROL Nombre]): Rellenado por Adquisición de aplicación móvil, que el SDK móvil [no admite](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/comparison/).
>* **[!UICONTROL Ubicación] dimensiones y [!UICONTROL Distancia al centro del punto de interés]**: Rellenado con el método 4.x `trackLocation`. Mobile SDK reemplaza este método con la extensión [Places](https://developer.adobe.com/client-sdks/solution/places/), que rellena [!UICONTROL Nombre del punto de interés] y [!UICONTROL ID del punto de interés].
>* **[!UICONTROL Valor de duración (evar)]**: Rellenado con el método 4.x `trackLifetimeValueIncrease`.
>* **Dimensiones de señalización** ([!UICONTROL Beacon mayor], [!UICONTROL menor], [!UICONTROL UUID] y [!UICONTROL Proximidad]): Rellenado con el método 4.x `trackBeacon`. Para enviar datos de señalizaciones con Mobile SDK, consulte [Señalizaciones de seguimiento](https://developer.adobe.com/client-sdks/solution/adobe-analytics/track-beacon/).
>
>Consulte [Migración de la biblioteca móvil de Adobe (v4) a Experience Platform Analytics](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/analytics/) para obtener más información.
