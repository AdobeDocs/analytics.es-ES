---
title: charSet
description: La variable charSet determina qué codificación utiliza Adobe para analizar la solicitud de imagen.
feature: Appmeasurement Implementation
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/bPK-uLu-IgKnJWGpAUnS7cmRm808jhetzm-Cyd2R39o'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 235
ht-degree: 66%

---

# charSet

Adobe utiliza la variable `charSet` para convertir datos entrantes a UTF-8 para almacenamiento y generación de informes de Analytics. La mayoría de los sitios no necesitan establecer esta variable.

Establezca esta variable solo si observa valores ilegibles ([mojibake](https://es.wikipedia.org/wiki/Mojibake)) en los informes. Esta variable se puede configurar página por página si el sitio utiliza diferentes codificaciones en diferentes páginas.

## Conjunto de caracteres en Web SDK

Actualmente, Web SDK solo admite UTF-8 y no proporciona opciones para cambiar la codificación.

## Conjunto de caracteres en la extensión de Adobe Analytics

Conjunto de caracteres es un campo en el acordeón [!UICONTROL General] al configurar la extensión de Adobe Analytics en la recopilación de datos de Adobe Experience Platform.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
1. Expanda el acordeón [!UICONTROL General], que muestra el campo [!UICONTROL Conjunto de caracteres].

Puede utilizar un conjunto de caracteres preestablecido o un conjunto de caracteres personalizado. Evite cambiar el valor de `UTF-8` a menos que vea valores ilegibles en los informes.

## s.charSet en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `charSet` es una cadena. Si tiene valores ilegibles en Adobe Analytics, establezca esta variable con el mismo valor que la etiqueta HTML `<meta charset="">` del sitio.

```js
s.charSet = "UTF-8";
```
