---
title: Explorador
description: Nombre y versión del explorador utilizado.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
TQID: https://experienceleague.adobe.com/J6rDfVwmRZpRLrultdurQkRih2HcPygjcjwO0bkms5E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
source-wordcount: '310'
ht-degree: 35%
---
# Explorador

El &#39;[!UICONTROL explorador]&#39; [dimensión](overview.md) informa del nombre y la versión del explorador que envía la visita. Esta dimensión es útil cuando desea medir los exploradores más comunes que utilizan los visitantes. Al probar las nuevas versiones del sitio, puede ejecutar esas pruebas en los exploradores principales de esta dimensión para maximizar los esfuerzos de control de calidad.

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

Los elementos de dimensión incluyen los nombres y las versiones de los exploradores utilizados. Las distintas versiones del mismo explorador son elementos de dimensión independientes.

Algunos elementos de dimensión contienen `"(unknown version)"` en lugar de su número de versión. Este elemento de dimensión hace referencia a una versión reciente del explorador que Adobe aún no ha agregado a sus tablas de búsqueda. Dado que los navegadores se actualizan con frecuencia, la `"(unknown version)"` de un navegador determinado es común y temporal. Adobe suele actualizar las tablas de búsqueda durante las revisiones de mantenimiento mensuales.

Algunos elementos de dimensión contienen `.999` como número de versión menor, como `"Chrome 148.999"`. Este valor indica que Adobe no pudo determinar de forma fiable la versión secundaria del explorador. Cuando los exploradores Chrome o Edge envían solicitudes sin [sugerencias del cliente](/help/technotes/client-hints.md), la versión secundaria de la cadena del agente de usuario no se considera de confianza. En lugar de inflar elementos de dimensión con versiones menores potencialmente inexactas, Adobe reemplaza esas versiones menores con `.999`. Del mismo modo, si algún explorador informa de un número de versión inusualmente alto (por encima de 99999), Adobe lo normaliza a `999.999`.
