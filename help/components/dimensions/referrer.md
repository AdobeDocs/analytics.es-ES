---
title: Referente
description: Dirección URL en la que se encontraba un visitante antes de hacer clic para ir al sitio.
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 49%

---


# Referente

La dimensión “Remitente del reenvío” indica en qué direcciones URL se encontraban los visitantes al hacer clic para llegar al sitio. Esta dimensión es útil para comprender qué direcciones URL específicas generan la mayor cantidad de tráfico en el sitio. Debe existir un vínculo en la dirección URL externa y un visitante debe hacer clic en él para que se muestre el elemento de dimensión.

>[!IMPORTANT]
>
>Debe configurar los [filtros URL internos](/help/admin/admin/internal-url-filter-admin.md) del grupo de informes para utilizar esta dimensión. Si no se configuran los filtros de URL internos, puede incluir direcciones URL internas o evitar que aparezcan direcciones URL externas.

El mismo informe puede mostrar diferentes resultados entre Analysis Workspace y Data Warehouse. Analysis Workspace informa del remitente del reenvío de cada página individual, excluyendo los valores que coinciden con los filtros de URL internos. Data Warehouse informa solamente el primer remitente del reenvío de la visita e ignora los filtros de URL internos.

## Rellene esta dimensión con datos

Esta dimensión se debe configurar en la interfaz de Analytics y necesita datos en solicitudes de imagen.

* Dentro de la implementación, esta dimensión recupera datos de la [`r`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement recopila estos datos mediante la variable JavaScript `document.referrer` en el explorador. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante Adobe Experience Platform Launch), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de consulta `r` en las solicitudes de imágenes.
* En de la interfaz de Analytics, debe configurar los [filtros URL internos](/help/admin/admin/internal-url-filter-admin.md) del grupo de informes. Si no se configuran los filtros de URL internos, puede incluir direcciones URL internas o evitar que aparezcan direcciones URL externas.

## Elementos de Dimension

Los elementos de Dimension incluyen direcciones URL que los visitantes pulsan en el sitio. If a hit does not have any referrer data, it groups under the dimension item `"Typed/Bookmarked"`. Este elemento de dimensión significa que no había ningún valor de remitente del reenvío, como si el visitante escribiera manualmente la dirección del explorador en la barra de direcciones o hiciera clic en un marcador. El elemento `"Typed/Bookmarked"` de dimensión también aparece para redirecciones que no admiten Analytics. Consulte [Redirecciones y alias](/help/technotes/redirects.md) en la guía del usuario de Technotes.

### Elementos de Dimension que contienen `googleusercontent.com`

Los usuarios pueden ver elementos de dimensión con el dominio `googleusercontent.com`.

* **Páginas** en caché: Las arañas de Google rastrean constantemente la web y almacenan copias de páginas en caso de que se desconecten. Estas páginas en caché están disponibles al lado de la mayoría de los resultados de búsqueda haciendo clic en el vínculo &quot;En caché&quot;. Cuando un usuario hace clic en este vínculo y vista el contenido que Google almacena en caché, `webcache.googleusercontent.com` es un elemento de dimensión típico.
* **Páginas traducidas**: Google ofrece un servicio de traducción robusto y conveniente. Al ver un sitio que utiliza este servicio, se origina desde `translate.googleusercontent.com`. Este elemento de dimensión aparece si el usuario hace clic en un vínculo para volver al contenido original.
