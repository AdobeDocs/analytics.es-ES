---
title: Tipos de sistemas operativos
description: El sistema operativo independientemente de la versión.
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
TQID: https://experienceleague.adobe.com/onZ7Wt7A44gd42hqmjqYHL7OF6VtBke1NDgu1tsnMIg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 40%
---
# Tipos de sistemas operativos

La [dimensión](overview.md) &quot;Tipos de sistemas operativos&quot; muestra el sistema operativo global que el visitante utilizó, independientemente de versiones específicas. Esta dimensión es útil para comprender no solo qué sistema operativo y versión específicos son los más comunes, sino también qué plataforma de sistema operativo utilizan los visitantes habituales.

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

Los elementos de Dimension incluyen el tipo de sistema operativo utilizado. Los ejemplos incluyen `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"` y `"Apple iOS"`.
