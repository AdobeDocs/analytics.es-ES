---
description: Debe satisfacer los siguientes requisitos de solución, servicio y código de Experience Cloud para implementar el reenvío de lado del servidor. Estos requisitos también incluyen instrucciones para comprobar versiones del código y obtener las bibliotecas de código más actualizadas.
solution: Analytics
title: Requisitos para el reenvío del lado del servidor
feature: Report Suite Settings
exl-id: af0cf85a-381e-46d2-a4fd-9a5b073c8a8d
role: Admin
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 100%

---

# Requisitos para el reenvío del lado del servidor

Debe satisfacer los siguientes requisitos de solución, servicio y código de Experience Cloud para implementar el reenvío de lado del servidor. Estos requisitos también incluyen instrucciones para comprobar versiones del código y obtener las bibliotecas de código más actualizadas.

## Requisitos de solución

El reenvío del lado del servidor funciona con [Analytics](https://www.adobe.com/es/analytics/adobe-analytics.html) y [Audience Manager](https://www.adobe.com/es/analytics/audience-manager.html) o con [Audiencias](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=es).

## Requisitos de servidor

El reenvío de lado del servidor requiere el [servicio de identidad](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es). El servicio de identidad ofrece un ID universal que identifica a los visitantes del sitio en todas las soluciones de Experience Cloud. Debe implementar el servicio de ID para que el reenvío del lado del servidor funcione.

## Versiones de código

El reenvío del lado del servidor requiere la versión 1.5 (o posterior) de las bibliotecas de código abajo indicadas. Es recomendable utilizar las versiones más recientes, no las versiones mínimas que se señalan.

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### Determinación de la versión de su biblioteca de código

Cualquier herramienta que supervise las solicitudes HTTP realizadas por un navegador puede mostrar el número de versión de su código AppMeasurement y de la API de visitante. `AppMeasurement_Module_AudienceManagement.js` ni contiene ni devuelve un ID de versión. Los siguientes ejemplos muestran el aspecto del ID de versión del código de `AppMeasurement.js` y `VisitorAPI.js`.

* `AppMeasurement.js`: [Adobe Debugger](https://experienceleague.adobe.com/docs/analytics/implementation/validate/debugger.html?lang=es) devuelve la versión de AppMeasurement de este modo: `Version of Code | JS-1.5.1`. Otras herramientas pueden utilizar una etiqueta distinta, pero el valor siempre sigue el patrón `JS-X.X.X`, donde `X` es un número de versión.
* `VisitorAPI.js`: busque el parámetro `d_visid_ver`. Muestra el servicio ID de visitante así: `d_visid_ver: 1.5.5`. El código de la API de visitante anterior a la versión 1.5.2 no incluía número de versión. Probablemente esté utilizando una biblioteca de código antigua (y deba actualizarla) si los resultados de monitorización no devuelven un número de versión.
