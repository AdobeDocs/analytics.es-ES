---
title: Sistema operativo
description: El sistema operativo del visitante.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 9c3e65392d6e5929ce1ecefbc460c1fd5576aed8
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 42%

---

# Sistema operativo

El &quot;Sistema operativo&quot; [dimension](overview.md) muestra el sistema operativo y la versión que el visitante usó. Si tiene funciones en la propiedad web específicas del sistema operativo, esta dimensión le ayuda a comprender qué sistemas operativos son los más comunes.

## Rellene esta dimensión con datos

Esta dimensión hace referencia a una tabla de búsqueda interna de Adobe. El valor de búsqueda se basa en el encabezado HTTP `User-Agent` de las solicitudes de imagen. El Adobe se asocia con [DeviceAtlas](https://deviceatlas.com/) para mantener búsquedas entre el agente de usuario y el sistema operativo.

* Para implementaciones de AppMeasurement, esta dimensión funciona de forma predeterminada.
* Para implementaciones de SDK web, habilita [!UICONTROL Búsqueda de dispositivos] al [configurar una secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es).

## Elementos de dimensión

Los elementos de dimensión incluyen sistemas operativos que utilizan los visitantes. Los ejemplos incluyen `"Windows 10"`, `"OS X 10.15.7"` y `"Android 9"`.

## Seguimiento de versiones precisas del sistema operativo

A medida que el sector avanza hacia las sugerencias del cliente, algunas versiones de sistemas operativos están potencialmente combinadas. Por ejemplo, &quot;Windows 10&quot; y &quot;Windows 11&quot; se pueden agrupar en &quot;Windows 10&quot; si no recopila sugerencias de cliente de alta entropía. Consulte [Client hints](/help/technotes/client-hints.md) en la guía Technotes para obtener más información.
