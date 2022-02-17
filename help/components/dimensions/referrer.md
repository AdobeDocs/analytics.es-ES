---
title: Referente
description: Dirección URL en la que se encontraba un visitante antes de hacer clic para ir al sitio.
feature: Dimensions
exl-id: 146f0327-c73c-40f5-8cc1-584e31d163a2
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 100%

---

# Referente

La dimensión “Remitente del reenvío” indica en qué direcciones URL se encontraban los visitantes al hacer clic para llegar al sitio. Esta dimensión es útil para comprender qué direcciones URL específicas generan la mayor cantidad de tráfico en el sitio. Debe existir un vínculo en la dirección URL externa y un visitante debe hacer clic en él para que se muestre el elemento de dimensión.

>[!IMPORTANT]
>
>Debe configurar los [filtros URL internos](/help/admin/admin/internal-url-filter-admin.md) del grupo de informes para utilizar esta dimensión. Si no se configuran los filtros de URL internos, puede incluir direcciones URL internas o evitar que aparezcan direcciones URL externas.

El mismo informe puede mostrar diferentes resultados entre Analysis Workspace y Data Warehouse. Analysis Workspace informa del remitente del reenvío de cada página individual, excluyendo los valores que coinciden con los filtros de URL internos. Data Warehouse informa solamente del primer remitente del reenvío de la visita e ignora los filtros de URL internos.

## Rellene esta dimensión con datos

Esta dimensión se debe configurar en la interfaz de Analytics y necesita datos en solicitudes de imagen.

* Dentro de la implementación, esta dimensión recupera datos de la [`r`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement recopila estos datos mediante la variable JavaScript `document.referrer` en el explorador. Puede utilizar la anulación de la variable [`referrer`](/help/implement/vars/page-vars/referrer.md) para configurarla manualmente. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante etiquetas en Adobe Experience Platform), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de consulta `r` en las solicitudes de imágenes.
* En de la interfaz de Analytics, debe configurar los [filtros URL internos](/help/admin/admin/internal-url-filter-admin.md) del grupo de informes. Si no se configuran los filtros de URL internos, puede incluir direcciones URL internas o evitar que aparezcan direcciones URL externas.

## Elementos de dimensión

Los elementos de dimensión incluyen las direcciones URL en las que los visitantes hacen clic para llegar a su sitio. Si una visita no tiene datos de remitente del reenvío, se agrupa bajo el elemento de dimensión `"Typed/Bookmarked"`. Este elemento de dimensión significa que no hubo ningún valor de remitente del reenvío, como si el visitante escribiera manualmente la dirección del explorador en la barra de direcciones o hiciera clic en un marcador. El elemento de dimensión `"Typed/Bookmarked"` también aparece para redirecciones que no admiten Analytics. Consulte [Redirecciones y alias](/help/technotes/redirects.md) en la guía del usuario de Technotes.

### Elementos de dimensión que contienen `googleusercontent.com`

Los usuarios pueden ver elementos de dimensión con el dominio `googleusercontent.com`.

* **Páginas en caché**: Las arañas de Google rastrean constantemente la web y almacenan copias de páginas en caso de que se desconecten. Estas páginas en caché están disponibles junto a la mayoría de los resultados de búsqueda haciendo clic en el vínculo “En caché”. Cuando un usuario hace clic en este vínculo y visualiza el contenido que Google almacena en caché, `webcache.googleusercontent.com` es un elemento de dimensión típico.
* **Páginas traducidas**: Google ofrece un servicio de traducción robusto y conveniente. Al ver un sitio que utiliza este servicio, se origina desde `translate.googleusercontent.com`. Este elemento de dimensión aparece si el usuario hace clic en un vínculo para volver al contenido original.
