---
description: Prueba de reglas no publicadas desde la consola con el uso del alojamiento de Akamai.
keywords: Dynamic Tag Management;rule;switcher plugin;akamai;test akamai;unpublished rules;test unpublished rules;debug rule
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Prueba de reglas no publicadas para el alojamiento de Akamai
uuid: 979e3d74-8d96-47d0-b581-cf5371248434
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Prueba de reglas no publicadas para el alojamiento de Akamai

Prueba de reglas no publicadas desde la consola con el uso del alojamiento de Akamai.

El complemento de cambio suele ser la forma más sencilla de realizar pruebas. Consulte [Complementos de Search Discovery](https://marketing.adobe.com/resources/help/es_ES/dtm/search_discovery_plugins.html) en la documentación del producto de Dynamic Tag Management para obtener más información.

Los pasos siguientes muestran cómo realizar pruebas sin utilizar el complemento de cambio:

1. Acceda a la consola web de su sitio y escriba `localStorage.setItem('sdsat_stagingLibrary', true)`.
1. Pulse **[!UICONTROL Intro]**.
1. Escriba `_satellite.setDebug(true)`, luego pulse **[!UICONTROL Intro]**.
1. Actualice la página.

   Esta acción carga la biblioteca de ensayos y configura el depurador para que pueda ver los detalles de todas las reglas (publicadas y no publicadas) disponibles que se activan en la página.
1. Cuando termine, ejecute `localStorage.setItem('sdsat_stagingLibrary', false)` y, a continuación, pulse **[!UICONTROL Intro]**.

   Resultado de los pasos
