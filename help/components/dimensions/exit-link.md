---
title: Vínculo de salida
description: Nombre del vínculo de salida.
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
source-git-commit: 418e8d467ca29267314e14fba99783d0cb3d05a9
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 22%

---

# Vínculo de salida

El &quot;Vínculo de salida&quot; [dimension](overview.md) indica los nombres de los vínculos de salida implementados en el sitio. Los vínculos de salida rastrean los clics salientes que conducen a los visitantes fuera del dominio actual. Esta dimensión es valiosa cuando desea comprender en qué vínculos de salida se hace clic con mayor frecuencia.

## Rellene esta dimensión con datos

Esta dimensión recopila datos de la cadena de consulta [`pev2` ](/help/implement/validate/query-parameters.md) en solicitudes de imagen, según el valor de la cadena de consulta `pe`. La cadena de consulta `pe` determina qué dimensión de vínculo recibe el valor `pev2`:

* **[Vínculo personalizado](custom-link.md)**: `lnk_o`
* **[Vínculo de descarga](download-link.md)**: `lnk_d`
* **Vínculo de salida** (esta página): `lnk_e`

Si no se proporciona `pev2`, se usa la dirección URL del vínculo (`pev1`) como valor de dimensión. Cuando se proporciona explícitamente un nombre de vínculo, la longitud máxima es de 100 bytes. Los valores derivados de la dirección URL del vínculo no están sujetos a este límite.

Para rellenar esta dimensión con AppMeasurement, envíe una solicitud de imagen [`tl()`](/help/implement/vars/functions/tl-method.md) con un argumento de tipo de vínculo de `"e"`. Establezca el argumento del nombre del vínculo en el valor deseado:

```js
s.tl(true,"e","Example exit link");
```

## Elementos de dimensión

Dado que esta variable se basa en una cadena personalizada en la implementación, su organización determina cuáles son los elementos de dimensión. Adobe recomienda agrupar los vínculos en categorías significativas en función de sus necesidades de creación de informes. Si no se proporciona ningún nombre de vínculo, los elementos de dimensión aparecen como direcciones URL sin procesar. Estas direcciones URL sin procesar son más difíciles de interpretar en los informes, por lo que debe proporcionar un nombre de vínculo descriptivo siempre que sea posible.
