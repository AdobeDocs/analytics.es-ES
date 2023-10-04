---
title: Dimensiones del ciclo vital móvil
description: Dimension en función de los datos recopilados mediante el SDK para móviles.
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
source-git-commit: d940428e1cbe1be6d8263e986e8b641ec18aace1
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 57%

---

# Dimensiones del ciclo vital móvil

*Esta página hace referencia a datos que se rastrean comúnmente mediante el SDK para móviles de Adobe Experience Platform. Para obtener información de dispositivos móviles que utilizan el agente de usuario, consulte [Dimensiones de búsqueda móvil](mobile-dimensions.md). Para las métricas rastreadas con el SDK móvil, consulte [Métricas del ciclo vital móviles](../metrics/lifecycle-metrics.md).*

| Nombre de dimensión de ciclo vital | Descripción | Variable de datos de contexto |
| --- | --- | --- |
| [!UICONTROL Fecha de primer lanzamiento] | | Por determinar |
| [!UICONTROL Nombre del dispositivo (SDK)] | | `a.DeviceName` |
| [!UICONTROL Versión del sistema operativo (SDK)] | | `a.OSVersion` |
| [!UICONTROL Resolución (SDK)] | | `a.Resolution` |
| [!UICONTROL Fuente de adquisición] | | `a.referrer.campaign.source` |
| [!UICONTROL ID de la aplicación] | | `a.AppID` |
| [!UICONTROL Medio de adquisición] | | `a.referrer.campaign.medium` |
| [!UICONTROL Término de adquisición] | | `a.referrer.campaign.term` |
| [!UICONTROL Contenido de adquisición] | | `a.refferer.campaign.content` |
| [!UICONTROL Nombre de adquisición] | | `a.referrer.campaign.name` |
| [!UICONTROL Ubicación (menos de 10 km)] | | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL Ubicación (menos de 100 m)] | | `a.loc.lat.b` + `a.loc.lon.b` |
| [!UICONTROL Ubicación (menos de 1 m)] | | `a.loc.lat.c` + `a.loc.lon.c` |
| [!UICONTROL Nombre del punto de interés] | | `a.loc.poi` |
| [!UICONTROL Distancia hasta el centro del punto de interés] | | `a.loc.dist` |
| [!UICONTROL Número de inicios] | | `a.Launches` |
| [!UICONTROL Días transcurridos desde el primer uso] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Nombre de la acción] | | Por determinar |
| [!UICONTROL Valor de duración (eVar)] | | `a.ltv.amount` |
| [!UICONTROL Beacon mayor] | | Por determinar |
| [!UICONTROL Beacon menor] | | Por determinar |
| [!UICONTROL Identificador único universal (UUID, universally unique indentifier) de Beacon] | | Por determinar |
| [!UICONTROL Proximidad de Beacon] | | Por determinar |
| [!UICONTROL Días transcurridos desde el último uso] | | `a.DaysSinceFirstUse` |
| [!UICONTROL Hora del día (SDK)] | | `a.HourOfDay` |
| [!UICONTROL Día de la semana (SDK)] | | `a.DayOfWeek` |
| [!UICONTROL ID del punto de interés] | | Por determinar |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
