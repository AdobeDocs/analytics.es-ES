---
description: La columna previa contiene los datos en el estado en el que se enviaron a la recopilación de datos. La columna posterior contiene el valor tras el procesamiento.
keywords: Data Feed;job;pre column;post column;case sensitivity
solution: Analytics
title: Columnas previas y posteriores
topic: Reports and analytics
uuid: a415327b-6151-4d08-b8b9-5aaa2348eb0c
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Columnas previas y posteriores

La columna previa contiene los datos en el estado en el que se enviaron a la recopilación de datos. La columna posterior contiene el valor tras el procesamiento.

Por ejemplo, la persistencia de la variable, las reglas de procesamiento, las reglas de VISTA y el cambio de divisas pueden modificar el valor final de una variable que aparece en la columna posterior. En la mayoría de los cálculos, es recomendable utilizar la columna posterior, a no ser que quiera aplicar una lógica empresarial personalizada (por ejemplo, si aplica una fórmula personalizada para determinar la atribución).

Si una columna no contiene una versión previa o posterior (por ejemplo, `visit_num`), se puede considerar que es una columna posterior. Columns prefixed with " `pre_`" typically contain data that was populated by Adobe and not sent by your implementation. For example, `pre_browser` is populated by Adobe, but `evar1` is populated by your implementation. Both of these columns have a " `post_`" column ( `post_browser`, `post_evar1`), which contains the value used by reporting.

## Con distinción de mayúsculas y minúsculas en valores {#section_F979E099BFAB4AFEBEA2D7E228963CE8}

La mayoría de las variables de Analytics se consideran variables con distinción de mayúsculas y minúsculas con fines de informes, lo que significa que se tienen en cuenta diferentes variaciones de la distinción de mayúsculas y minúsculas para que tengan el mismo valor ("nieve", "Nieve", "NIEVE" y "nIeve" se considera que tienen el mismo valor). Sin embargo, con fines de visualización, la distinción de mayúsculas y minúsculas se conserva porque la mayoría de los clientes prefieren poder realizar envíos en caracteres con distinción mixta para que se visualice en los informes.

Al procesar la fuente de datos, puede escribir valores en minúsculas con fines comparativos, aunque probablemente desee conservar las mayúsculas y minúsculas para la visualización.

Si ve diferentes variaciones de la distinción de mayúsculas y minúsculas del mismo valor entre las columnas previas y posteriores (por ejemplo, "nieve" en la columna previa y "Nieve" en la columna posterior), indica que está pasando por las dos versiones del mismo valor en su sitio. Se pasó anteriormente por la variación de la distinción de mayúsculas y minúsculas en la columna posterior y se almacena en la cookie virtual, o se procesó aproximadamente en el mismo momento para el grupo de informes. Por ejemplo:

Visita 1: s.list1="Tabby,Persian,Siamese";

Visita individual 2: s.list1="tabby,persian,siamese";

Si se informa de la visita principal 2 en la fuente de datos, la columna previa contendrá la misma cantidad de minúsculas y mayúsculas pasada en (tabby,persian,siamese), pero el valor de la visita 1 permanece para la visita y se informará en la columna posterior (que será Tabby,Persian,Siamese), debido a que las visitas 1 y 2 contienen exactamente el mismo valor si se lleva a cabo una comparación con distinción de mayúsculas y minúsculas.
