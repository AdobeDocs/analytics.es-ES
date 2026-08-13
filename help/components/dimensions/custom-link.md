---
title: Vínculo personalizado
description: Nombre del vínculo personalizado.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
TQID: https://experienceleague.adobe.com/x4IAGJjozPnLsft1e9xs68L6TNDJbHW0H4Z23p9EDNg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 9b4525e014170b72688044a6ead344b1bde8c39b
workflow-type: tm+mt
source-wordcount: 242
ht-degree: 21%

---

# Vínculo personalizado

El &quot;Vínculo personalizado&quot; [dimension](overview.md) indica los nombres de los vínculos personalizados implementados en el sitio. Los vínculos personalizados son un mecanismo de seguimiento flexible para cualquier interacción que no sea una descarga de archivo o navegación saliente. Algunos ejemplos comunes son los clics en botones, la navegación interna o las interacciones de formularios. Esta dimensión es valiosa cuando desea comprender con cuál de estas interacciones se relacionan más los visitantes.

## Rellene esta dimensión con datos

Esta dimensión recopila datos de la cadena de consulta [`pev2` ](/help/implement/validate/query-parameters.md) en solicitudes de imagen, según el valor de la cadena de consulta `pe`. La cadena de consulta `pe` determina qué dimensión de vínculo recibe el valor `pev2`:

* **Vínculo personalizado** (esta página): `lnk_o`
* **[Vínculo de descarga](download-link.md)**: `lnk_d`
* **[Vínculo de salida](exit-link.md)**: `lnk_e`

Si no se proporciona `pev2`, se usa la dirección URL del vínculo (`pev1`) como valor de dimensión. Cuando se proporciona explícitamente un nombre de vínculo, la longitud máxima es de 100 bytes. Los valores derivados de la dirección URL del vínculo no están sujetos a este límite.

Para rellenar esta dimensión con AppMeasurement, envíe una solicitud de imagen [`tl()`](/help/implement/vars/functions/tl-method.md) con un argumento de tipo de vínculo de `"o"`. Establezca el argumento del nombre del vínculo en el valor deseado:

```js
s.tl(true,"o","Example custom link");
```

## Elementos de dimensión

Dado que esta variable se basa en una cadena personalizada en la implementación, su organización determina cuáles son los elementos de dimensión. Adobe recomienda agrupar los vínculos en categorías significativas en función de sus necesidades de creación de informes. Si no se proporciona ningún nombre de vínculo, los elementos de dimensión aparecen como direcciones URL sin procesar. Estas direcciones URL sin procesar son más difíciles de interpretar en los informes, por lo que debe proporcionar un nombre de vínculo descriptivo siempre que sea posible.
