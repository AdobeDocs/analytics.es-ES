---
description: Existen varias formas de implementar Adobe Analytics.
keywords: Implementación de Analytics; método de implementación; administración dinámica de etiquetas; dtm; javascript
seo-description: Existen varias formas de implementar Adobe Analytics.
seo-title: Elegir un método de implementación
solution: Analytics
title: Elegir un método de implementación
topic: Desarrollador e implementación
uuid: 20 d 3317 f -7 c 63-4421-93 e 0-fff 60 dbd 9 f 87
translation-type: tm+mt
source-git-commit: b1e69abd65f171b804e7f56031e594890bbd27bb

---


# Elegir un método de implementación

Existen varias formas de implementar Adobe Analytics.

* [!UICONTROL Lanzamiento de Plataforma de Adobe Experience] (recomendado)
* [!UICONTROL Dynamic Tag Management]
* JavaScript

## [!UICONTROL Lanzamiento de Plataforma de Adobe Experience]{#section_AEEA6AFE2C8D4182BC778F08EA171DC8}

[!UICONTROL Experience Platform Launch] es la próxima generación de funciones de administración de SDK y etiquetas de sitios web de Adobe. [!UICONTROL Experience Platform Launch] le proporciona una forma sencilla de implementar y administrar todas las integraciones de análisis, marketing y publicidad necesarias para potenciar experiencias de cliente relevantes.

[!UICONTROL Launch Platform Launch] permite a cualquier persona crear y mantener sus propias integraciones con [!DNL Experience Platform Launch], llamadas Extensiones. These extensions are available to web and mobile [!UICONTROL Experience Platform Launch] customers in an app-store experience, so customers can quickly install, configure, and deploy their integrations.

For more information, see [Getting Started with Experience Platform Launch](https://docs.adobelaunch.com/getting-started).

## [!UICONTROL Dynamic Tag Management] {#section_22E3F3F928894A6A8D77E6953E6CA51C}

[!UICONTROL La administración dinámica de etiquetas] automatiza gran parte del trabajo detallado que se requiere para implementar [!DNL Analytics]. Introduzca la información necesaria en una interfaz basada en formularios y [!DNL Dynamic Tag Management] generará el código que tiene que añadir a sus páginas.
Es útil familiarizarse con JavaScript y comprender la terminología básica de Analytics, como

* Qué es una [eVar](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) y cómo funciona
* Cuándo se utiliza un [evento personalizado](../../implement/analytics-terminology-basics/c-props-evars/event-custom.md#concept_CDA3C98C85B24A71B4B5C71F24BF918F)

Para obtener información sobre el acceso, puesta en marcha y ejecución de Dynamic Tag Management, consulte [Introducción](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html) en Documentación del producto de Dynamic Tag Management.

Para obtener más información, consulte [Implementación de Analytics con administración dinámica de etiquetas](../../implement/c-implement-with-dtm/dtm-implementation-overview.md).

## JavaScript {#section_55429940D5094B9BB513E526F224D1B4}

El método de implementación con JavaScript requiere que configure manualmente los códigos JavaScript de sus páginas. Gran parte de este esfuerzo se puede simplificar si utiliza los métodos de implementación de la plataforma Expereience o la administración dinámica de etiquetas. Sin embargo, es posible que algunos usuarios deban utilizar el método de JavaScript.

La implementación con JavaScript requiere lo siguiente:

* Buenos conocimientos de JavaScript
* Una buena comprensión de los conceptos y la terminología de Analytics

Para obtener más información, consulte [Implementación de Analytics con JavaScript](../../implement/js-implementation/javascript-implementation-overview.md).
