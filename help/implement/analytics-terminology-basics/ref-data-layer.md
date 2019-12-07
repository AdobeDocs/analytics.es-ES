---
description: Una “capa de datos” es un marco de objetos JavaScript que los desarrolladores insertan en las páginas.
keywords: Analytics Implementation;data layer;digitalData
title: Capa de datos
topic: Developer and implementation
uuid: dedb2a50-06f3-4354-8993-a25d4952ce1e
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Capa de datos

Una _capa de datos_ es un marco de objetos JavaScript que los desarrolladores insertan en las páginas. Las herramientas de rastreo (incluidos los sistemas de administración de etiquetas como Adobe Experience Platform Launch o Dynamic Tag Management) pueden utilizar las capas de datos para rellenar informes.

La implementación de una capa de datos en el sitio le ofrece un control y una flexibilidad absolutos sobre la implementación y simplifica el mantenimiento en fases futuras&#x200B;. Los nombres de estos objetos JavaScript son teóricamente arbitrarios, pero se recomienza utilizar una nomenclatura coherente y previsible. Los desarrolladores pueden disponer ya de una capa de datos, o tener preferencias acerca del formato. Existen algunos estándares diferentes que la comunidad de seguimiento ha creado como punto de partida. El documento de especificación [Capa de datos para la implementación de Analytics](assets/datalayer-documentation.pdf) utiliza el objeto W3C estándar “digitalData”, aceptado por la más amplia variedad de tecnologías de seguimiento, en caso de que necesite utilizar la capa de datos para algo más que esta implementación de DTM.
