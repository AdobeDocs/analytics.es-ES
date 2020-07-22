---
title: Idioma
description: La configuración de idioma preferida en el explorador.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# Idioma

La dimensión &#39;Idioma&#39; muestra los idiomas principales en los que los visitantes prefieren ver el contenido. Esta dimensión es valiosa cuando desea comprender los idiomas preferidos más frecuentes de los visitantes para ayudar en los esfuerzos de localización.

>[!NOTE]
>
>Esta dimensión no recopila el idioma del sitio. Si desea recopilar el idioma del sitio en una dimensión, Adobe recomienda utilizar una variable personalizada, como una [eVar](evar.md).

## Rellenar esta dimensión con datos

Esta dimensión hace referencia a una tabla de búsqueda interna de Adobe. El valor de búsqueda se basa en el encabezado `Accept-Language` HTTP de las solicitudes de imagen. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante Adobe Experience Platform Launch), esta dimensión funciona de forma predeterminada.

## Elementos de dimensión

Los elementos de dimensión incluyen nombres descriptivos de los idiomas preferidos de los visitantes. Examples include `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"`, and `"Spanish (Spain)"`. Si una solicitud de imagen no contiene un idioma válido en el encabezado HTTP, el elemento de dimensión es `"None"`.
