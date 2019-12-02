---
description: Preguntas más frecuentes sobre las fuentes de datos
keywords: Data Feed;job;pre column;post column;case sensitivity
solution: Analytics
title: Preguntas más frecuentes sobre las fuentes de datos
translation-type: tm+mt
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# Preguntas más frecuentes sobre las fuentes de datos

Preguntas más frecuentes sobre las fuentes de datos.

## ¿Cuál es la diferencia entre columnas con `post_` prefijo y columnas sin `post_` prefijo?

Las columnas sin el `post_` prefijo contienen datos exactamente como se enviaron a la recopilación de datos. Las columnas con un `post_` prefijo contienen el valor después del procesamiento. Algunos ejemplos que pueden cambiar un valor son la persistencia de variables, las reglas de procesamiento, las reglas de VISTA, la conversión de divisas u otra lógica de servidor que Adobe aplique. Adobe recomienda utilizar la `post_` versión de una columna siempre que sea posible.

If a column does not contain a `post_` version (for example, `visit_num`), then the column can be considered a post column.

## ¿Cómo gestionan las fuentes de datos la distinción entre mayúsculas y minúsculas?

En Adobe Analytics, la mayoría de las variables se consideran sin distinción de mayúsculas y minúsculas a efectos de los informes. Por ejemplo, 'nieve', 'Nieve', 'NIEVE' y 'sNow' se consideran todos como el mismo valor. La distinción entre mayúsculas y minúsculas se conserva en las fuentes de datos.

Si ve diferentes variaciones de mayúsculas y minúsculas del mismo valor entre columnas no posteriores y posteriores (por ejemplo, 'nieve' en la columna previa y 'Nieve' en la columna posterior), la implementación utiliza valores en mayúsculas y minúsculas en todo el sitio. Se pasó anteriormente por la variación de la distinción de mayúsculas y minúsculas en la columna posterior y se almacena en la cookie virtual, o se procesó aproximadamente en el mismo momento para el grupo de informes.