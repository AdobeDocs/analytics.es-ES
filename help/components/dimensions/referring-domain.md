---
title: Dominio de referencia
description: Dominio general en el que se encontraba un visitante antes de hacer clic en el sitio.
exl-id: 9e04cb62-6526-4d84-aff7-c962c0ce42b5
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '492'
ht-degree: 100%

---

# Dominio de referencia

La dimensión “Dominio de referencia” indica los dominios en los que los visitantes hacen clic para llegar al sitio. Esta dimensión es útil para comprender qué sitios de terceros generan la mayor cantidad de tráfico en el suyo. Debe existir un vínculo en el sitio externo y un visitante debe hacer clic en él para que se muestre el elemento de dimensión.

>[!IMPORTANT]
>
>Debe configurar los [filtros URL internos](/help/admin/admin/internal-url-filter-admin.md) del grupo de informes para utilizar esta dimensión. Si no se configuran los filtros de URL internos, puede incluir dominios internos o evitar que aparezcan dominios externos.

El mismo informe puede mostrar diferentes resultados entre Analysis Workspace y Data Warehouse. Analysis Workspace informa del dominio de referencia de cada página individual, excluyendo los valores que coinciden con los filtros de URL internos. Data Warehouse informa solamente del primer dominio de referencia de la visita e ignora los filtros de URL internos.

## Rellene esta dimensión con datos

Esta dimensión se debe configurar en la interfaz de Analytics y necesita datos en solicitudes de imagen.

* Dentro de la implementación, esta dimensión recupera datos de la [`r`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement recopila estos datos mediante la variable JavaScript `document.referrer` en el explorador. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante Adobe Experience Platform Launch), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de consulta `r` en las solicitudes de imágenes.
* En de la interfaz de Analytics, debe configurar los [filtros URL internos](/help/admin/admin/internal-url-filter-admin.md) del grupo de informes. Si no se configuran los filtros de URL internos, puede incluir dominios internos o evitar que aparezcan dominios externos.

Adobe persiste en el dominio de referencia de una visita. Si un visitante sale y hace clic a través de un vínculo en un dominio diferente en una sola visita, el nuevo valor se actualiza y persiste durante el resto de la visita. Si solo desea ver el valor original, consulte [Dominio de referencia original](original-referring-domain.md).

## Elementos de dimensión

Los elementos de dimensión incluyen los dominios en los que los visitantes hacen clic para llegar a su sitio. Si una visita no tiene datos de remitente del reenvío (establecidos o persistentes), se agrupa bajo el elemento de dimensión `"Typed/Bookmarked"`. Este elemento de dimensión significa que no hubo ningún valor de remitente del reenvío, como si el visitante escribiera manualmente la dirección del explorador en la barra de direcciones o hiciera clic en un marcador. El elemento de dimensión `"Typed/Bookmarked"` también aparece para redirecciones que no admiten Analytics. Consulte [Redirecciones y alias](/help/technotes/redirects.md) en la guía del usuario de Technotes.

### Elementos de dimensión que contienen `googleusercontent.com`

Los usuarios pueden ver elementos de dimensión con el dominio `googleusercontent.com`.

* **Páginas en caché**: Las arañas de Google rastrean constantemente la web y almacenan copias de páginas en caso de que se desconecten. Estas páginas en caché están disponibles junto a la mayoría de los resultados de búsqueda haciendo clic en el vínculo “En caché”. Cuando un usuario hace clic en este vínculo y visualiza el contenido que Google almacena en caché, `googleusercontent.com` es el elemento de dimensión.
* **Páginas traducidas**: Google ofrece un servicio de traducción robusto y conveniente. Al ver un sitio que utiliza este servicio, se origina desde `googleusercontent.com`. Este elemento de dimensión aparece si el usuario hace clic en un vínculo para volver al contenido original.
