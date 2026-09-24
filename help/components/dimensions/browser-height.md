---
title: 'Altura del explorador: Agrupado'
description: Altura de la ventana del explorador en píxeles.
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
TQID: https://experienceleague.adobe.com/-MSFtBJDaiG0yYL6ZdpzbPY80uFJbdxB0gyBtKAkFzY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 40%
---
# Altura del explorador

La [dimensión](overview.md) &quot;Altura del explorador: agrupado&quot; muestra la altura de la ventana del explorador, clasificada en grupos predefinidos. Esta dimensión es útil cuando desea saber dónde está el “pliegue” en el sitio para los visitantes. Conocer la ubicación del pliegue permite optimizar la visualización del contenido.

Esta dimensión es diferente a la altura de la pantalla. La altura del explorador es el número de píxeles dentro del espacio visible del explorador, mientras que la altura de la pantalla es la altura de todo el monitor en píxeles. Si desea ver la diferencia entre estas dos variables en su propio equipo, abra la consola del explorador (F12 en la mayoría de los exploradores) y copie y pegue el siguiente código en la consola:

```javascript
console.log(`Browser height: ${window.innerHeight} pixels\nScreen height: ${screen.height} pixels`);
```

La altura del explorador suele ser menor o igual que la altura de la pantalla, ya que la altura del explorador no incluye la navegación del explorador ni los bordes.

>[!NOTE]
>
>Data Warehouse también proporciona una dimensión &#39;[!UICONTROL Alto del explorador - granular]&#39;, que indica el alto de píxel exacto en lugar de agrupar valores en bloques predefinidos.

## Rellene esta dimensión con datos

La altura del explorador se recopila automáticamente del lado del cliente a partir de la propiedad `window.innerHeight` del explorador. Funciona de forma predeterminada en cualquier implementación de AppMeasurement o Web SDK (etiquetas); no hay ninguna variable que establecer. Si recopila datos fuera de AppMeasurement o de Web SDK (por ejemplo, a través de la API), envíe el valor en la primera visita individual de cada visita. Si la altura del explorador se ajusta a mitad de la visita, el ajuste no se registra.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (recopilado automáticamente) |
| **Campo Web SDK / XDM** | Ninguno (recopilado automáticamente) |
| **Parámetro de consulta** | [`bh`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **etiqueta XML** | [`<browserHeight>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Intervalo de valores** | 0 - 65 535 |
| **Persistencia** | Visita |

## Elementos de dimensión

Los elementos de Dimension incluyen todas las alturas recopiladas del navegador, clasificadas en grupos predefinidos. Por ejemplo, si la altura del explorador de un hit es `720`, se agrupa en el elemento de dimensión `700 to 799`.
