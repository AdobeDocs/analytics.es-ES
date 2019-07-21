---
description: Prueba de reglas no publicadas desde la consola con el uso del alojamiento de Akamai.
keywords: Administración dinámica de etiquetas; rule; switcher plugin; akamai; probar akamai; reglas no publicadas; probar reglas no publicadas; depurar regla
seo-description: Prueba de reglas no publicadas desde la consola con el uso del alojamiento de Akamai.
seo-title: Prueba de reglas no publicadas para el alojamiento de Akamai
solution: Marketing Cloud, Analytics, Target, Administración dinámica de etiquetas
title: Prueba de reglas no publicadas para el alojamiento de Akamai
uuid: 979 e 3 d 74-8 d 96-47 d 0-b 581-cf 5371248434
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Prueba de reglas no publicadas para el alojamiento de Akamai

Prueba de reglas no publicadas desde la consola con el uso del alojamiento de Akamai.

El complemento de cambio suele ser la forma más sencilla de realizar pruebas. Consulte [Complementos de Search Discovery](https://marketing.adobe.com/resources/help/en_US/dtm/search_discovery_plugins.html) en la documentación del producto de Dynamic Tag Management para obtener más información.

Los pasos siguientes muestran cómo realizar pruebas sin utilizar el complemento de cambio:

1. Acceda a la consola web de su sitio y escriba `localStorage.setItem('sdsat_stagingLibrary', true)`.
1. Press **[!UICONTROL Enter]**.
1. Type `_satellite.setDebug(true)`, then press **[!UICONTROL Enter]**.
1. Actualice la página.

   Esta acción carga la biblioteca de ensayos y configura el depurador para que pueda ver los detalles de todas las reglas (publicadas y no publicadas) disponibles que se activan en la página.
1. When finished, run `localStorage.setItem('sdsat_stagingLibrary', false)`, then press **[!UICONTROL Enter]**.

   Resultado de los pasos