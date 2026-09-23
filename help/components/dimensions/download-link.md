---
title: Vínculo de descarga
description: Nombre del vínculo de descarga.
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
TQID: https://experienceleague.adobe.com/vok8Znalf6GBA1N0Z9GE1d31QpaUmD-d0bOsHB2Wehc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 27%
---
# Vínculo de descarga

El &quot;Vínculo de descarga&quot; [dimension](overview.md) indica los nombres de los vínculos de descarga implementados en el sitio. Esta dimensión es valiosa cuando desea obtener más información sobre el comportamiento del visitante en los vínculos de descarga como, por ejemplo:

* Qué archivos se descargan con mayor frecuencia del sitio.
* Si determinados archivos se descargan con mayor frecuencia durante períodos de tiempo específicos.
* Si los visitantes descargan diferentes tipos de archivos cuando se ofrecen.

## Rellene esta dimensión con datos

Esta dimensión está completada por [llamadas de seguimiento de vínculos (`tl()`)](/help/implement/vars/functions/tl-method.md). No hay ninguna variable dedicada que establecer. En su lugar, envíe una solicitud de imagen `tl()` con un argumento de tipo de vínculo de `"d"` y establezca el argumento de nombre de vínculo en el valor deseado. La cadena de consulta `pe` enruta el nombre del vínculo a la dimensión de vínculo correcta (`lnk_o` para [vínculos personalizados](custom-link.md), `lnk_d` para [vínculos de descarga](download-link.md) y `lnk_e` para [vínculos de salida](exit-link.md)). Si no se proporciona un nombre de vínculo, la dirección URL del vínculo se utiliza como valor de dimensión y los valores derivados de la URL no están sujetos al límite de bytes.

```js
s.tl(true,"d","Example download link");
```

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | [`tl()`](/help/implement/vars/functions/tl-method.md) |
| **Campo Web SDK / XDM** | Ninguno |
| **Parámetro de consulta** | [`pev2`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **etiqueta XML** | [`<linkName>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Límite de bytes** | 100 bytes |
| **Persistencia** | Hit |

## Elementos de dimensión

Dado que esta variable se basa en una cadena personalizada en la implementación, su organización determina cuáles son los elementos de dimensión. Adobe recomienda agrupar los vínculos en categorías significativas en función de sus necesidades de creación de informes. Si no se proporciona ningún nombre de vínculo, los elementos de dimensión aparecen como direcciones URL sin procesar. Estas direcciones URL sin procesar son más difíciles de interpretar en los informes, por lo que debe proporcionar un nombre de vínculo descriptivo siempre que sea posible.
