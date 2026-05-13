---
title: Dimensiones del ciclo de vida móvil
description: Dimensiones basadas en los datos recopilados con Mobile SDK.
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
TQID: https://experienceleague.adobe.com/VUN8x5eMzIfJ9VGw76v2pWfKWU7b-ct-kI6liwWTObw
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 180
ht-degree: 25%

---

# Dimensiones del ciclo de vida móvil

*Esta página hace referencia a datos que se rastrean comúnmente a través de Adobe Experience Platform Mobile SDK. Para obtener información de dispositivos móviles que usan el agente de usuario, consulte [Dimensiones de búsqueda móvil](mobile-dimensions.md). Para las métricas rastreadas con el SDK móvil, consulte [Métricas del ciclo vital móvil](../metrics/lifecycle-metrics.md).*

| Nombre de dimensión de ciclo vital | Descripción | Variable de datos de contexto |
| --- | --- | --- |
| [!UICONTROL Fecha de primer inicio] | | |
| [!UICONTROL Nombre de dispositivo (SDK)] | | `a.DeviceName` |
| [!UICONTROL Versión del sistema operativo (SDK)] | | `a.OSVersion` |
| [!UICONTROL Resolución (SDK)] | | `a.Resolution` |
| [!UICONTROL Source de adquisición] | | `a.referrer.campaign.source` |
| [!UICONTROL Id. de aplicación] | | `a.AppID` |
| [!UICONTROL Medium de adquisición] | | `a.referrer.campaign.medium` |
| [!UICONTROL Término de adquisición] | | `a.referrer.campaign.term` |
| [!UICONTROL Contenido de adquisición] | | `a.refferer.campaign.content` |
| [!UICONTROL Nombre de adquisición] | | `a.referrer.campaign.name` |
| [!UICONTROL Ubicación (menos de 10 km)] | Latitud y longitud del visitante, con precisión del primer decimal. Por ejemplo, `040.9` `-111.9`. | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL Ubicación (menos de 100 m)] | Latitud y longitud del visitante, con precisión del tercer decimal. Por ejemplo, `040.932` `-111.931`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| [!UICONTROL Ubicación (menos de 1 m)] | Latitud y longitud del visitante, con precisión del quinto decimal. Por ejemplo, `040.93231` `-111.93152`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| [!UICONTROL Nombre del punto de interés] | | `a.loc.poi` |
| [!UICONTROL Distancia hasta el centro del punto de interés] | | `a.loc.dist` |
| [!UICONTROL Número de inicios] | | `a.Launches` |
| [!UICONTROL Días transcurridos desde el primer uso] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Nombre de acción] | | |
| [!UICONTROL Valor de duración (evar)] | | `a.ltv.amount` |
| [!UICONTROL Beacon mayor] | | |
| [!UICONTROL Beacon menor] | | |
| [!UICONTROL UUID de señalización] | | |
| [!UICONTROL Proximidad del Beacon] | | |
| [!UICONTROL Días transcurridos desde el último uso] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Hora del día (SDK)] | | `a.HourOfDay` |
| [!UICONTROL Día de la semana (SDK)] | | `a.DayOfWeek` |
| [!UICONTROL Id. de punto de interés] | | |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
