---
title: Idioma
description: El idioma preferido configurado para el explorador.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 80%

---


# Idioma

La dimensión “Idioma” muestra los idiomas principales en los que los visitantes prefieren ver el contenido. Esta dimensión es valiosa cuando desea comprender los idiomas preferidos más frecuentes de los visitantes para ayudar en las tareas de localización.

>[!NOTE]
>
>Esta dimensión no recopila el idioma del sitio. Si desea recopilar el idioma del sitio en una dimensión, Adobe recomienda utilizar una variable personalizada, como una [eVar](evar.md).

## Rellene esta dimensión con datos

Esta dimensión hace referencia a una tabla de búsqueda interna de Adobe. El valor de búsqueda se basa en el encabezado HTTP `Accept-Language` de las solicitudes de imagen. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante Adobe Experience Platform Launch), esta dimensión funciona de forma predeterminada.

## Elementos de Dimension

Los elementos Dimension incluyen nombres descriptivos de los idiomas preferidos de los visitantes. Los ejemplos incluyen `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"` y `"Spanish (Spain)"`. If an image request does not contain a valid language in the HTTP header, the dimension item is `"None"`.
