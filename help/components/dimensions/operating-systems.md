---
title: Sistema operativo
description: El sistema operativo del visitante.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
TQID: https://experienceleague.adobe.com/WM6GQ-AhLmtudRWXF6lOez6DaVxMBU3rSaEb2UdsXdc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 178
ht-degree: 45%

---

# Sistema operativo

El &quot;Sistema operativo&quot; [dimension](overview.md) muestra el sistema operativo y la versión que el visitante usó. Si tiene funciones en la propiedad web específicas del sistema operativo, esta dimensión le ayuda a comprender qué sistemas operativos son los más comunes.

## Rellene esta dimensión con datos

Esta dimensión hace referencia a una tabla de búsqueda interna de Adobe. El valor de búsqueda se basa en el encabezado HTTP `User-Agent` de las solicitudes de imagen. Adobe se asocia con [DeviceAtlas](https://deviceatlas.com/) para mantener búsquedas entre el agente de usuario y el sistema operativo.

* Para implementaciones de AppMeasurement, esta dimensión funciona de forma predeterminada.
* Para implementaciones de Web SDK, habilite [!UICONTROL Búsqueda de dispositivos] al [configurar una secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es).

## Elementos de dimensión

Los elementos de dimensión incluyen sistemas operativos que utilizan los visitantes. Los ejemplos incluyen `"Windows 10"`, `"OS X 10.15.7"` y `"Android 9"`.

## Seguimiento de versiones precisas del sistema operativo

A medida que el sector avanza hacia las sugerencias del cliente, algunas versiones de sistemas operativos están potencialmente combinadas. Por ejemplo, &quot;Windows 10&quot; y &quot;Windows 11&quot; se pueden agrupar en &quot;Windows 10&quot; si no recopila sugerencias de cliente de alta entropía. Consulte [Client hints](/help/technotes/client-hints.md) en la guía Technotes para obtener más información.
