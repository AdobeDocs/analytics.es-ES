---
title: Vínculo personalizado
description: Nombre del vínculo personalizado.
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
source-git-commit: 5c1d50fa09b0fad228f24018de2b062d09b0fe5f
workflow-type: tm+mt
source-wordcount: '242'
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
