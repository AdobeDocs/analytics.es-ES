---
description: Preguntas más frecuentes sobre las fuentes de datos
keywords: Data Feed;job;pre column;post column;case sensitivity
title: Preguntas frecuentes sobre las fuentes de datos
translation-type: tm+mt
source-git-commit: 966d1e8d47df03f6e4cedfedd62c1d3bc56a3606
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 86%

---


# Preguntas frecuentes sobre las fuentes de datos

Preguntas más frecuentes sobre las fuentes de datos.

## ¿Cuál es la diferencia entre columnas con prefijo `post_` y columnas sin un prefijo `post_`?

Las columnas sin el prefijo `post_` contienen datos exactamente como se enviaron a la recopilación de datos. Las columnas con un prefijo `post_` contienen el valor después del procesamiento. Algunos ejemplos que pueden cambiar un valor son la persistencia de variables, las reglas de procesamiento, las reglas de VISTA, la conversión de divisas u otra lógica del lado del servidor que Adobe aplique. Adobe recomienda utilizar la versión `post_` de una columna siempre que sea posible.

Si una columna no contiene una versión `post_` (por ejemplo: `visit_num`), se puede considerar que es una columna posterior.

## ¿Cómo gestionan las fuentes de datos la distinción entre mayúsculas y minúsculas?

En Adobe Analytics, la mayoría de las variables se consideran sin distinción de mayúsculas y minúsculas a efectos de los informes. Por ejemplo: “nieve”, “Nieve”, “NIEVE” y “nLeve” se consideran todos como un mismo valor. La distinción entre mayúsculas y minúsculas se conserva en las fuentes de datos.

Si ve diferentes variaciones de mayúsculas y minúsculas del mismo valor entre columnas no posteriores y posteriores (por ejemplo, “nieve” en la columna previa y “Nieve” en la columna posterior), la implementación utiliza valores en mayúsculas y minúsculas en todo el sitio. Se pasó anteriormente por la variación de la distinción de mayúsculas y minúsculas en la columna posterior y se almacena en la cookie virtual, o se procesó aproximadamente en el mismo momento para el grupo de informes.

## ¿Las reglas de bots de la consola de administración se filtran en las fuentes de datos?

Las fuentes de datos no incluyen bots filtrados por las reglas [de bots de la consola](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/bot-removal/bot-removal.html)de administración.
