---
title: s_objectID
description: Ayude a Activity Map a identificar vínculos únicos en el sitio.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# s_objectID

La `s_objectID` variable proporciona un identificador único para un vínculo. Se utiliza para que los informes de [Activity Map](/help/analyze/activity-map/activity-map.md) sean más precisos. Si tiene vínculos en una página que cambian con frecuencia, puede utilizar la `s_objectID` variable para indicar a Activity Map la ubicación de un vínculo único y así agrupar correctamente los datos como desee.

Si la precisión de Mapa de actividades es crucial para su organización, Adobe recomienda incluir la `s_objectID` variable en el `onClick` caso de vínculos en su sitio. Consulte los casos [de uso del seguimiento de vínculos de](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-use-case.md) Activity Map en la guía del usuario de Análisis para obtener más información.

## ID de objeto en Adobe Experience Platform Launch

No hay un campo dedicado en Launch para utilizar esta variable. Utilice el editor de código personalizado, siguiendo la sintaxis de AppMeasurement.

## s_objectID en el editor de código personalizado AppMeasurement e Launch

La `s_objectID` variable es una variable global, lo que significa que opera independientemente del objeto de seguimiento de Analytics (`s` de forma predeterminada). Los valores válidos para esta variable pueden ser cualquier cadena de hasta 100 bytes de longitud. Si no se define esta variable, Activity Map utiliza la dirección URL del vínculo como identificador para el vínculo.

Esta variable suele configurarse en el `onClick` caso de un vínculo HTML.

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

> [!NOTE] Incluya siempre el punto y coma que termina una instrucción JavaScript. El punto y coma es necesario para que Activity Map funcione.

## Casos de uso

La `s_objectID` variable es valiosa siempre que desee aumentar la precisión en los informes de Activity Map.

### Agregar vínculos de contenido altamente dinámico

Algunos sitios tienen contenido altamente dinámico, como sitios de noticias o sitios minoristas con artículos que se rotan con frecuencia. Dado que Activity Map utiliza la dirección URL del vínculo como identificador de forma predeterminada, es difícil comprender las áreas en las que se hace más clic en las páginas donde los vínculos cambian con frecuencia. Si utiliza los vínculos `s_objectID` dentro de estos vínculos, Activity Map comprende qué vínculos se pueden agregar, independientemente de las direcciones URL a las que apunten.

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

Independientemente del punto de los vínculos o de la frecuencia con la que los cambie, Activity Map agrega datos en función del valor de `s_objectID`.

### Mantener los vínculos separados en una página

Algunos sitios tienen vínculos que apuntan a la misma ubicación en diferentes lugares. Por ejemplo: un vínculo a la página principal en el encabezado y el pie de página del sitio. Dado que estos vínculos tienen la misma dirección URL, Activity Map agrega sus datos. Puede separarlos mediante la `s_objectID` variable:

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

Aunque los vínculos apunten a la misma dirección URL, Activity Map puede utilizar la `s_objectID` variable para distinguirlos correctamente en los informes.
