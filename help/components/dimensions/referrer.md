---
title: Referente
description: Dirección URL en la que se encontraba un visitante antes de hacer clic para ir al sitio.
feature: Dimensions
exl-id: 146f0327-c73c-40f5-8cc1-584e31d163a2
TQID: https://experienceleague.adobe.com/VE1bJD2ah1N9t-fHKc5GC0-pC4YmXEDkCwhVmI5rHZQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 449
ht-degree: 96%

---

# Referente

La [dimensión](overview.md) &quot;Remitente del reenvío&quot; indica en qué direcciones URL se encontraban los visitantes al hacer clic para llegar al sitio. Esta dimensión es útil para comprender qué direcciones URL específicas generan la mayor cantidad de tráfico en el sitio. Debe existir un vínculo en la dirección URL externa y un visitante debe hacer clic en él para que se muestre el elemento de dimensión.

>[!IMPORTANT]
>
>Debe configurar los [filtros URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) del grupo de informes para utilizar esta dimensión. Si no se configuran los filtros de URL internos, puede incluir direcciones URL internas o evitar que aparezcan direcciones URL externas.

El mismo informe puede mostrar diferentes resultados entre Analysis Workspace y Data Warehouse. Analysis Workspace informa del remitente del reenvío de cada página individual, excluyendo los valores que coinciden con los filtros de URL internos. Data Warehouse informa solamente del primer remitente del reenvío de la visita e ignora los filtros de URL internos.

## Rellene esta dimensión con datos

Esta dimensión se debe configurar en la interfaz de Analytics y necesita datos en solicitudes de imagen.

* Dentro de la implementación, esta dimensión recupera datos de la [`r`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement recopila estos datos mediante la variable JavaScript `document.referrer` en el explorador. Puede utilizar la anulación de la variable [`referrer`](/help/implement/vars/page-vars/referrer.md) para configurarla manualmente. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante etiquetas en Adobe Experience Platform), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de consulta `r` en las solicitudes de imágenes.
* En de la interfaz de Analytics, debe configurar los [filtros URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) del grupo de informes. Si no se configuran los filtros de URL internos, puede incluir direcciones URL internas o evitar que aparezcan direcciones URL externas.

## Elementos de dimensión

Los elementos de dimensión incluyen las direcciones URL en las que los visitantes hacen clic para llegar a su sitio. Si una visita no tiene datos de remitente del reenvío, se agrupa bajo el elemento de dimensión `"Typed/Bookmarked"`. Este elemento de dimensión significa que no hubo ningún valor de remitente del reenvío, como si el visitante escribiera manualmente la dirección del explorador en la barra de direcciones o hiciera clic en un marcador. El elemento de dimensión `"Typed/Bookmarked"` también aparece para redirecciones que no admiten Analytics. Consulte [Redirecciones y alias](/help/technotes/redirects.md) en la guía del usuario de Technotes.

### Elementos de dimensión que contienen `googleusercontent.com`

Los usuarios pueden ver elementos de dimensión con el dominio `googleusercontent.com`.

* **Páginas en caché**: Las arañas de Google rastrean constantemente la web y almacenan copias de páginas en caso de que se desconecten. Estas páginas en caché están disponibles junto a la mayoría de los resultados de búsqueda haciendo clic en el vínculo “En caché”. Cuando un usuario hace clic en este vínculo y visualiza el contenido que Google almacena en caché, `webcache.googleusercontent.com` es un elemento de dimensión típico.
* **Páginas traducidas**: Google ofrece un servicio de traducción robusto y conveniente. Al ver un sitio que utiliza este servicio, se origina desde `translate.googleusercontent.com`. Este elemento de dimensión aparece si el usuario hace clic en un vínculo para volver al contenido original.
