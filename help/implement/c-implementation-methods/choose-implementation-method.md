---
description: Existen varias formas de implementar Adobe Analytics.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;javascript
title: Elegir un método de implementación
topic: Developer and implementation
uuid: 20d3317f-7c63-4421-93e0-fff60dbd9f87
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Elegir un método de implementación

Existen varias formas de implementar Adobe Analytics.

* [!UICONTROL Adobe Experience Platform Launch] (recomendado)
* [!UICONTROL Dynamic Tag Management]
* JavaScript

## [!UICONTROL Adobe Experience Platform Launch] {#section_AEEA6AFE2C8D4182BC778F08EA171DC8}

[!UICONTROL Experience Platform Launch] es la nueva generación de funcionalidades de administración de etiquetas de sitios web y SDK móvil de Adobe. [!UICONTROL Experience Platform Launch] le ofrece una alternativa sencilla para implementar y gestionar todas las integraciones de análisis, marketing y publicidad necesarias para ofrecer al cliente experiencias más relevantes.

[!UICONTROL Experience Platform Launch] ofrece a los usuarios las herramientas necesarias para crear y mantener sus propias integraciones con [!DNL Experience Platform Launch], que se denominan Extensiones. Estas extensiones están disponibles para los clientes web y móviles de [!UICONTROL Launch] en las tiendas de aplicaciones de modo que puedan instalar, configurar e implementar rápidamente sus integraciones.

For more information, see [Getting Started with Experience Platform Launch](https://docs.adobelaunch.com/getting-started).

## [!UICONTROL Dynamic Tag Management] {#section_22E3F3F928894A6A8D77E6953E6CA51C}

[!UICONTROL Dynamic Tag Management] automatiza buena parte del trabajo detallado necesario para implementar [!DNL Analytics]. Introduzca la información necesaria en una interfaz basada en formularios y [!DNL Dynamic Tag Management] generará el código que tiene que añadir a sus páginas.
Es importante familiarizarse con JavaScript y comprender la terminología básica de Analytics, como:

* Qué es una [eVar](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) y cómo funciona
* Cuándo utilizar un [evento personalizado](/help/implement/analytics-terminology-basics/c-props-evars/event-custom.md)

Para obtener información sobre el acceso, puesta en marcha y ejecución de Dynamic Tag Management, consulte [Introducción](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html) en Documentación del producto de Dynamic Tag Management.

Para obtener más información, consulte [Implementación de Analytics con DTM](/help/implement/c-implement-with-dtm/dtm-implementation-overview.md).

## JavaScript {#section_55429940D5094B9BB513E526F224D1B4}

El método de implementación con JavaScript requiere que configure manualmente los códigos JavaScript de sus páginas. Gran parte de este esfuerzo se puede simplificar si utiliza los métodos de implementación de Experience Platform Launch o DTM. Sin embargo, es posible que algunos usuarios deban utilizar el método de JavaScript.

La implementación con JavaScript requiere lo siguiente:

* Buenos conocimientos de JavaScript
* Una buena comprensión de los conceptos y la terminología de Analytics

Para obtener más información, consulte [Implementación de Analytics con JavaScript](/help/implement/js-implementation/javascript-implementation-overview.md).
