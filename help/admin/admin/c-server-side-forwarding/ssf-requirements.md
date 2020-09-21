---
description: Debe satisfacer los siguientes requisitos de solución, servicio y código de Experience Cloud para implementar el reenvío de lado del servidor. Estos requisitos también incluyen instrucciones para comprobar versiones del código y obtener las bibliotecas de código más actualizadas.
solution: Audience Manager
title: Requisitos para el reenvío del lado del servidor
uuid: e52c9292-b2ed-4782-9594-c813e4f894e1
translation-type: ht
source-git-commit: 327fdfd6a6d6bfe1c7bae9825fc8812b5ac7d095
workflow-type: ht
source-wordcount: '321'
ht-degree: 100%

---


# Requisitos para el reenvío del lado del servidor

Debe satisfacer los siguientes requisitos de solución, servicio y código de Experience Cloud para implementar el reenvío de lado del servidor. Estos requisitos también incluyen instrucciones para comprobar versiones del código y obtener las bibliotecas de código más actualizadas.

## Requisitos de solución

El reenvío del lado del servidor funciona con [Analytics](https://www.adobe.com/es/analytics/adobe-analytics.html) y [Audience Manager](https://www.adobe.com/es/analytics/audience-manager.html) o con [Audiencias](https://docs.adobe.com/content/help/es-ES/core-services/interface/audiences/audience-library.html).

## Requisitos de servidor

El reenvío de lado del servidor requiere el [servicio de identidad](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html). El servicio de identidad ofrece un ID universal que identifica a los visitantes del sitio en todas las soluciones de Experience Cloud. Debe implementar el servicio de ID para que el reenvío del lado del servidor funcione.

## Versiones de código

El reenvío del lado del servidor requiere la versión 1.5 (o posterior) de las bibliotecas de código abajo indicadas. Es recomendable utilizar las versiones más recientes, no las versiones mínimas que se señalan.

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### Determinación de la versión de su biblioteca de código

Cualquier herramienta que supervise las solicitudes HTTP realizadas por un navegador puede mostrar el número de versión de su código AppMeasurement y de la API de visitante. `AppMeasurement_Module_AudienceManagement.js` ni contiene ni devuelve un ID de versión. Los siguientes ejemplos muestran el aspecto del ID de versión del código de `AppMeasurement.js` y `VisitorAPI.js`.

* `AppMeasurement.js`: [Adobe Debugger](https://docs.adobe.com/content/help/es-ES/analytics/implementation/validate/debugger.html) devuelve la versión de AppMeasurement de este modo: `Version of Code | JS-1.5.1`. Otras herramientas pueden utilizar una etiqueta distinta, pero el valor siempre sigue el patrón `JS-X.X.X`, donde `X` es un número de versión.
* `VisitorAPI.js`: busque el parámetro `d_visid_ver`. Muestra el servicio ID de visitante así: `d_visid_ver: 1.5.5`. El código de la API de visitante anterior a la versión 1.5.2 no incluía número de versión. Probablemente esté utilizando una biblioteca de código antigua (y deba actualizarla) si los resultados de monitorización no devuelven un número de versión.
