---
title: Resolución del monitor
description: Resolución del monitor del visitante en píxeles.
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
TQID: 'https://experienceleague.adobe.com/d3AuMT0seRbZpuKVGPeWo98Bkhc8tcJIP6gt4y-rq38'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
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
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 51%
---
# Resolución del monitor

La &#39;Resolución del monitor&#39; [dimensión](overview.md) muestra la altura y anchura de la pantalla activa en píxeles. Esta dimensión es útil cuando desea saber dónde está el “pliegue” en el sitio para los visitantes o en qué medida pueden ampliar los visitantes su ventana del explorador. Conocer la ubicación del pliegue permite optimizar la visualización del contenido.

Esta dimensión es diferente a la [altura](browser-height.md) y la [anchura](browser-width.md) del explorador. La altura y la anchura del explorador es el número de píxeles dentro del espacio del explorador visible, mientras que la resolución del monitor es el número de píxeles de todo el monitor. Si desea ver la diferencia entre estas dos variables en su propio equipo, abra la consola del explorador (F12 en la mayoría de los exploradores) y copie y pegue el siguiente código en la consola:

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "; Browser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

Las dimensiones del explorador son siempre más pequeñas que la resolución del monitor, ya que las dimensiones del explorador no incluyen la navegación del explorador ni los bordes.

## Rellene esta dimensión con datos

La resolución del monitor se recopila automáticamente del lado del cliente a partir de las propiedades `screen.width` y `screen.height` del explorador. Funciona de forma predeterminada en cualquier implementación de AppMeasurement o Web SDK (etiquetas); no hay ninguna variable que establecer. Si recopila datos fuera de AppMeasurement o de Web SDK (por ejemplo, a través de la API), envíe el valor en solicitudes de imagen. Si falta o si una biblioteca de recopilación de datos no puede recopilar la resolución del monitor, esos datos se muestran en [!UICONTROL `Not Specified`].

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (recopilado automáticamente) |
| **Campo Web SDK / XDM** | Ninguno (recopilado automáticamente) |
| **Parámetro de consulta** | [`s`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **etiqueta XML** | [`<resolution>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Límite de bytes** | 20 bytes |
| **Persistencia** | N/A |

## Elementos de dimensión

Los elementos de dimensión incluyen todas las resoluciones de monitor recopiladas. Los valores de ejemplo incluyen `1920 x 1080`, `1366 x 768` y `1280 x 720`.
