---
title: Dominio de referencia original
description: El primer dominio de referencia en el que se encontraba un visitante antes de hacer clic en el sitio.
translation-type: tm+mt
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---


# Dominio de referencia original

La dimensión &#39;Dominio de referencia original&#39; informa el primer dominio de referencia en el que un visitante hizo clic para llegar al sitio. Una vez configurado, contiene el mismo valor para toda la duración de ese ID de visitante. Esta dimensión es útil para comprender qué sitios de terceros llevan el tráfico al sitio en un principio.

>[!IMPORTANT]
>
>Debe configurar los filtros [URL](/help/admin/admin/internal-url-filter-admin.md) internos del grupo de informes para utilizar esta dimensión. Si no se configuran los filtros de URL internos, puede incluir dominios internos o evitar que aparezcan dominios externos.

## Rellenar esta dimensión con datos

Esta dimensión requiere configuración tanto en la interfaz de Analytics como en la implementación.

* Dentro de la implementación, esta dimensión recupera datos de la cadena [`r` de](/help/implement/validate/query-parameters.md) consulta en solicitudes de imagen. AppMeasurement recopila estos datos mediante la variable JavaScript `document.referrer` en el explorador. Si utiliza una biblioteca de AppMeasurement (por ejemplo, a través de Adobe Experience Platform Launch), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de `r` consulta en las solicitudes de imagen.
* Dentro de la interfaz de Analytics, debe configurar los filtros [URL](/help/admin/admin/internal-url-filter-admin.md)internos del grupo de informes. Si no se configuran los filtros de URL internos, puede incluir dominios internos o evitar que aparezcan dominios externos.

Adobe persiste en el dominio de referencia original durante toda la vida del visitante. Si un visitante sale y hace clic en un vínculo de un dominio diferente en cualquier momento, el nuevo valor no se registra. Si desea ver nuevos valores, consulte [Dominio](referring-domain.md)de referencia.

## Elementos de Dimension

Los elementos de Dimension incluyen los dominios en los que los visitantes hacen clic hasta el sitio. Si una visita no tiene datos de remitente del reenvío (establecidos o persistentes), se agrupa en el elemento de dimensión `"None"`. Este elemento de dimensión significa que no había ningún valor de remitente del reenvío, como si el visitante escribiera manualmente la dirección del explorador en la barra de direcciones o hiciera clic en un marcador.

## Comparar el dominio de referencia con el dominio de referencia original

El dominio de referencia puede cambiar entre visitas. Por ejemplo: un visitante llega a su sitio a través de `google.com`y luego una semana después llega a su sitio a través de `twitter.com`. Finalmente realizan una compra en el sitio. Si se utiliza el dominio de referencia como dimensión con atribución de último toque, `twitter.com` se obtiene el crédito por la compra. Si utiliza el dominio de referencia original como dimensión, `google.com` obtiene crédito por la compra independientemente del modelo de atribución.

El dominio de referencia original nunca cambia durante toda la vida de un ID de visitante determinado.
