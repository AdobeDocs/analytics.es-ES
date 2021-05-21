---
title: s_objectID
description: Ayude a Activity Map a identificar vínculos únicos en el sitio.
exl-id: 7c0cb750-2bfe-41ca-ab27-30dda4b3a7fa
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '401'
ht-degree: 100%

---

# s_objectID

La variable `s_objectID` proporciona un identificador único para un vínculo. Se utiliza para que los informes de [Activity Map](/help/analyze/activity-map/activity-map.md) sean más precisos. Si en una página tiene vínculos que cambian con frecuencia, puede utilizar la variable `s_objectID` para indicarle a Activity Map la ubicación de un vínculo único y así agrupar correctamente los datos como desee.

Si la precisión de Activity Map es crucial para su empresa, Adobe recomienda incluir la variable `s_objectID` en el evento `onClick` de los vínculos en su sitio. Para obtener más información, consulte los [casos prácticos del seguimiento de vínculos de Activity Map](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-use-case.md) en la Guía del usuario sobre Análisis.

## ID de objeto en Adobe Experience Platform Launch

No hay un campo específico en Launch para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## “s_objectID” en el editor de código personalizado de AppMeasurement y Launch

La variable `s_objectID` es una variable global, lo que significa que opera independientemente del objeto de seguimiento de Analytics (`s` de forma predeterminada). Los valores válidos para esta variable pueden ser cualquier cadena de hasta 100 bytes de longitud. Si no se define esta variable, Activity Map utiliza la dirección URL del vínculo como identificador para este.

Esta variable suele configurarse en el evento `onClick` de un enlace HTML.

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

>[!NOTE]
>
>Incluya siempre el punto y coma que termina una instrucción de JavaScript. Se necesita el punto y coma para que Activity Map funcione.

## Casos prácticos

La variable `s_objectID` es útil siempre que desee aumentar la precisión en los informes de Activity Map.

### Añadir vínculos de contenido altamente dinámico

Algunos sitios incluyen contenido altamente dinámico, como sitios de noticias o sitios minoristas con artículos que varían con frecuencia. Dado que Activity Map utiliza la dirección URL del vínculo como identificador de forma predeterminada, es difícil comprender las áreas en las que se hace más clic en las páginas donde los vínculos cambian con frecuencia. Si utiliza `s_objectID` dentro de estos vínculos, Activity Map comprende qué vínculos se pueden agregar, independientemente de las direcciones URL a las que apunten.

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

Sin importar adónde dirigen los vínculos o la frecuencia con la que se cambian, Activity Map añade datos en función del valor de `s_objectID`.

### Mantener los vínculos separados en una página

Algunos sitios tienen vínculos que llevan a la misma ubicación en diferentes lugares. Por ejemplo: Un vínculo a la página principal en el encabezado y al final del sitio. Dado que estos vínculos tienen la misma dirección URL, Activity Map añade sus datos. Puede separarlos mediante la variable `s_objectID`:

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

Aunque los vínculos creen acceso a la misma dirección URL, Activity Map puede utilizar la variable `s_objectID` para distinguirlos correctamente en los informes.
