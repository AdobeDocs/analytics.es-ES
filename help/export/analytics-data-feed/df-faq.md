---
description: Preguntas más frecuentes sobre las fuentes de datos
keywords: Fuente de datos;trabajo;columna previa;columna posterior;distinción entre mayúsculas y minúsculas
title: Preguntas frecuentes sobre las fuentes de datos
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
translation-type: tm+mt
source-git-commit: c6d4095fdf86be52c7921aed84b9229ac3b27f82
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 58%

---

# Preguntas frecuentes sobre las fuentes de datos

Preguntas más frecuentes sobre las fuentes de datos.

## ¿Cuál es la diferencia entre columnas con prefijo `post_` y columnas sin un prefijo `post_`?

Las columnas sin el prefijo `post_` contienen datos exactamente como se enviaron a la recopilación de datos. Las columnas con un prefijo `post_` contienen el valor después del procesamiento. Algunos ejemplos que pueden cambiar un valor son la persistencia de variables, las reglas de procesamiento, las reglas de VISTA, la conversión de divisas u otra lógica del lado del servidor que Adobe aplique. Adobe recomienda utilizar la versión `post_` de una columna siempre que sea posible.

Si una columna no contiene una versión `post_` (por ejemplo: `visit_num`), se puede considerar que es una columna posterior.

## ¿Cómo gestionan las fuentes de datos la distinción entre mayúsculas y minúsculas?

En Adobe Analytics, la mayoría de las variables se consideran sin distinción de mayúsculas y minúsculas a efectos de los informes. Por ejemplo: “nieve”, “Nieve”, “NIEVE” y “nLeve” se consideran todos como un mismo valor. La distinción entre mayúsculas y minúsculas se conserva en las fuentes de datos.

Si ve diferentes variaciones de mayúsculas y minúsculas del mismo valor entre columnas no posteriores y posteriores (por ejemplo, “nieve” en la columna previa y “Nieve” en la columna posterior), la implementación utiliza valores en mayúsculas y minúsculas en todo el sitio. Se pasó anteriormente por la variación de la distinción de mayúsculas y minúsculas en la columna posterior y se almacena en la cookie virtual, o se procesó aproximadamente en el mismo momento para el grupo de informes.

## ¿Las reglas de bots de la Admin Console filtran bots incluidos en las fuentes de datos?

Las fuentes de datos no incluyen bots filtrados por las [reglas de bots de la Admin Console](https://docs.adobe.com/content/help/es-ES/analytics/admin/admin-tools/bot-removal/bot-removal.html).

## ¿Por qué veo varios valores `000` en la columna de fuente de datos `event_list` o `post_event_list`?

Algunos editores de hojas de cálculo, especialmente Microsoft Excel, redondean automáticamente números muy grandes. La columna `event_list` contiene muchos números delimitados por comas, lo que a veces hace que Excel la trate como un número elevado. Se redondean los últimos dígitos a `000`.

Adobe recomienda no abrir automáticamente los archivos `hit_data.tsv` en Microsoft Excel. En su lugar, utilice el cuadro de diálogo Importar datos de Excel y asegúrese de que todos los campos se tratan como texto.

## ¿Por qué no puedo extraer archivos &quot;por hora&quot; de datos que tengan más de 7 días?

Para los datos con más de 7 días de antigüedad, los archivos &quot;por hora&quot; de un día se combinan en un solo archivo &quot;Diario&quot;.

Ejemplo: Se crea una nueva fuente de datos el 9 de marzo de 2021 y los datos del 1 de enero de 2021 al 9 de marzo se entregan como &quot;por hora&quot;. Sin embargo, los archivos &quot;Por hora&quot; anteriores al 2 de marzo de 2021 se combinan en un solo archivo &quot;Diario&quot;. Puede extraer archivos &quot;por hora&quot; solo de datos que tengan menos de 7 días desde la fecha de creación. En este caso, del 2 de marzo al 9 de marzo.
