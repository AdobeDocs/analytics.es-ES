---
title: Dimensiones del ciclo vital móvil
description: Dimension en función de los datos recopilados mediante el SDK para móviles.
feature: Dimensions
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 55%

---

# Dimensiones del ciclo vital móvil

*Esta página hace referencia a datos que se rastrean comúnmente mediante el SDK para móviles de Adobe Experience Platform. Para obtener información de dispositivos móviles que utilizan el agente de usuario, consulte [Dimensiones de búsqueda móvil](mobile-dimensions.md). Para las métricas rastreadas con el SDK móvil, consulte [Métricas del ciclo vital móviles](../metrics/lifecycle-metrics.md).*

| Nombre de dimensión de ciclo vital | Descripción | Variable de datos de contexto |
| --- | --- | --- |
| [!UICONTROL Fecha de primer lanzamiento] | | TBD (¿es la fecha de instalación?) |
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
