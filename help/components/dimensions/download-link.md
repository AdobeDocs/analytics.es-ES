---
title: Vínculo de descarga
description: Nombre del vínculo de descarga.
feature: Dimensions
exl-id: 078014a2-1f09-4177-9575-b44c5da25816
TQID: https://experienceleague.adobe.com/vok8Znalf6GBA1N0Z9GE1d31QpaUmD-d0bOsHB2Wehc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 9b4525e014170b72688044a6ead344b1bde8c39b
workflow-type: tm+mt
source-wordcount: 242
ht-degree: 28%

---

# Vínculo de descarga

El &quot;Vínculo de descarga&quot; [dimension](overview.md) indica los nombres de los vínculos de descarga implementados en el sitio. Esta dimensión es valiosa cuando desea obtener más información sobre el comportamiento del visitante en los vínculos de descarga como, por ejemplo:

* Qué archivos se descargan con mayor frecuencia del sitio.
* Si determinados archivos se descargan con mayor frecuencia durante períodos de tiempo específicos.
* Si los visitantes descargan diferentes tipos de archivos cuando se ofrecen.

## Rellene esta dimensión con datos

Esta dimensión recopila datos de la cadena de consulta [`pev2` ](/help/implement/validate/query-parameters.md) en solicitudes de imagen, según el valor de la cadena de consulta `pe`. La cadena de consulta `pe` determina qué dimensión de vínculo recibe el valor `pev2`:

* **[Vínculo personalizado](custom-link.md)**: `lnk_o`
* **Vínculo de descarga** (esta página): `lnk_d`
* **[Vínculo de salida](exit-link.md)**: `lnk_e`

Si no se proporciona `pev2`, se usa la dirección URL del vínculo (`pev1`) como valor de dimensión. Cuando se proporciona explícitamente un nombre de vínculo, la longitud máxima es de 100 bytes. Los valores derivados de la dirección URL del vínculo no están sujetos a este límite.

Para rellenar esta dimensión con AppMeasurement, envíe una solicitud de imagen [`tl()`](/help/implement/vars/functions/tl-method.md) con un argumento de tipo de vínculo de `"d"`. Establezca el argumento del nombre del vínculo en el valor deseado:

```js
s.tl(true,"d","Example download link");
```

## Elementos de dimensión

Dado que esta variable se basa en una cadena personalizada en la implementación, su organización determina cuáles son los elementos de dimensión. Adobe recomienda agrupar los vínculos en categorías significativas en función de sus necesidades de creación de informes. Si no se proporciona ningún nombre de vínculo, los elementos de dimensión aparecen como direcciones URL sin procesar. Estas direcciones URL sin procesar son más difíciles de interpretar en los informes, por lo que debe proporcionar un nombre de vínculo descriptivo siempre que sea posible.
