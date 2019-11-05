---
description: Debe satisfacer los siguientes requisitos de solución, servicio y código de Experience Cloud para implementar el reenvío de servidor. Estos requisitos también incluyen instrucciones para comprobar versiones del código y obtener las bibliotecas de código más actualizadas.
seo-description: Debe satisfacer los siguientes requisitos de solución, servicio y código de Experience Cloud para implementar el reenvío de servidor. Estos requisitos también incluyen instrucciones para comprobar versiones del código y obtener las bibliotecas de código más actualizadas.
seo-title: Requisitos para el reenvío del lado del servidor
solution: Audience Manager
title: Requisitos para el reenvío del lado del servidor
uuid: e52c9292-b2ed-4782-9594-c813e4f894e1
translation-type: tm+mt
source-git-commit: bc46011a48aa18e33ba6f1912223857f5a664f35

---


# Requisitos para el reenvío del lado del servidor

Debe satisfacer los siguientes requisitos de solución, servicio y código de Experience Cloud para implementar el reenvío de servidor. Estos requisitos también incluyen instrucciones para comprobar versiones del código y obtener las bibliotecas de código más actualizadas.

## Requisitos de solución

El reenvío del lado del servidor funciona con [Analytics](https://www.adobe.com/data-analytics-cloud/analytics.html) y [Audience Manager](https://www.adobe.com/data-analytics-cloud/audience-manager.html) o con [Audiencias](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html).

## Requisitos de servidor

El reenvío de servidor requiere el servicio [de identidad](https://marketing.adobe.com/resources/help/en_US/mcvid/). El servicio de identidad proporciona un ID universal que identifica a los visitantes del sitio en todas las soluciones de Experience Cloud. Debe implementar el servicio de ID para que el reenvío del lado del servidor funcione.

## Versiones de código

El reenvío del lado del servidor requiere la versión 1.5 (o posterior) de las bibliotecas de código abajo indicadas. Es recomendable utilizar las versiones más recientes, no las versiones mínimas que se señalan.

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### Determinación de la versión de su biblioteca de código

Cualquier herramienta que supervise las solicitudes HTTP realizadas por un navegador puede mostrar el número de versión de su código AppMeasurement y de la API de visitante. The `AppMeasurement_Module_AudienceManagement.js` does not contain or return a version ID. Los siguientes ejemplos muestran el aspecto del ID de versión del código de `AppMeasurement.js` y `VisitorAPI.js`.

* `AppMeasurement.js`:: El depurador de [Adobe](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html) devuelve la versión de AppMeasurement de este modo: `Version of Code | JS-1.5.1`. Otras herramientas pueden utilizar una etiqueta distinta, pero el valor siempre sigue el patrón `JS-X.X.X`, donde `X` es un número de versión.
* `VisitorAPI.js`:: Busque el `d_visid_ver` parámetro. It will show you the Visitor ID service like this: `d_visid_ver: 1.5.5`. El código de la API de visitante anterior a la versión 1.5.2 no incluía número de versión. Probablemente esté utilizando una biblioteca de código antigua (y deba actualizarla) si los resultados de monitorización no devuelven un número de versión.
