---
title: Dimensiones del ciclo de vida móvil
description: Dimensiones basadas en los datos recopilados con Mobile SDK.
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 23%

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
