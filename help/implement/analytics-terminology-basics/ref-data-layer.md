---
description: Una “capa de datos” es un marco de objetos JavaScript que los desarrolladores insertan en las páginas.
keywords: Implementación de Analytics; layer layer; Digitaldata
seo-description: Una “capa de datos” es un marco de objetos JavaScript que los desarrolladores insertan en las páginas. Las herramientas de rastreo (incluidos los sistemas de Tag Management como Dynamic Tag Management) pueden utilizar las capas de datos para rellenar informes.
seo-title: Capa de datos
solution: Analytics
title: Capa de datos
topic: Desarrollador e implementación
uuid: dedb 2 a 50-06 f 3-4354-8993-a 25 d 4952 ce 1 e
translation-type: tm+mt
source-git-commit: 26c3cc9895c27d6abc452e0a4636771fb2415fb3

---


# Capa de datos

A _data layer_ is a framework of JavaScript objects that developers insert into pages. Las herramientas de datos se pueden utilizar en las herramientas de seguimiento (incluidos los sistemas de administración de etiquetas como Adobe Experience Platform Launch y Administración dinámica de etiquetas) para rellenar informes.

La implementación de una capa de datos en el sitio le ofrece un control y una flexibilidad absolutos sobre la implementación y simplifica el mantenimiento en fases futuras&#x200B;. Los nombres de estos objetos JavaScript son teóricamente arbitrarios, pero se recomienza utilizar una nomenclatura coherente y previsible. Es posible que los desarrolladores ya tengan una capa de datos o una preferencia para el formato. Existen algunos estándares diferentes que la comunidad de seguimiento ha creado como punto de partida. El documento de especificación [Capa de datos para la implementación de Analytics](assets/datalayer-documentation.pdf) utiliza el objeto W3C estándar “digitalData”, aceptado por la más amplia variedad de tecnologías de seguimiento, en caso de que necesite utilizar la capa de datos para algo más que esta implementación de DTM.
