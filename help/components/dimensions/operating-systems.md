---
title: Sistema operativo
description: El sistema operativo del visitante.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
TQID: 'https://experienceleague.adobe.com/WM6GQ-AhLmtudRWXF6lOez6DaVxMBU3rSaEb2UdsXdc'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 34%
---
# Sistema operativo

El &quot;Sistema operativo&quot; [dimension](overview.md) muestra el sistema operativo y la versión que el visitante usó. Si tiene funciones en la propiedad web específicas del sistema operativo, esta dimensión le ayuda a comprender qué sistemas operativos son los más comunes.

## Rellene esta dimensión con datos

Adobe deriva esta dimensión del encabezado HTTP `User-Agent`, comparándola con una tabla de búsqueda interna que Adobe mantiene en asociación con [DeviceAtlas](https://deviceatlas.com/). No hay ninguna variable que establecer.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (derivado del agente de usuario) |
| **Campo Web SDK / XDM** | Ninguno (derivado del agente de usuario) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | n/a |

* Para implementaciones de AppMeasurement, esta dimensión funciona de forma predeterminada.
* Para implementaciones de Web SDK, habilite [!UICONTROL Búsqueda de dispositivos] al [configurar una secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es).

## Elementos de dimensión

Los elementos de dimensión incluyen sistemas operativos que utilizan los visitantes. Los ejemplos incluyen `"Windows 10"`, `"OS X 10.15.7"` y `"Android 9"`.

## Seguimiento de versiones precisas del sistema operativo

A medida que el sector avanza hacia las sugerencias del cliente, algunas versiones de sistemas operativos están potencialmente combinadas. Por ejemplo, &quot;Windows 10&quot; y &quot;Windows 11&quot; se pueden agrupar en &quot;Windows 10&quot; si no recopila sugerencias de cliente de alta entropía. Consulte [Client hints](/help/technotes/client-hints.md) en la guía Technotes para obtener más información.
