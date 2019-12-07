---
description: La variable de conversión de perspectiva personalizada (o eVar) se coloca en el código de Adobe en las páginas web del sitio seleccionadas. Su principal función es segmentar las métricas de éxito de conversión en los informes de marketing personalizados.
keywords: Analytics Implementation;eVar;conversion variable;eVar value;conversion;success event
title: Variables de conversión (eVars)
topic: Developer and implementation
uuid: 50071c1c-be00-4b3a-a7ee-5d129acf498b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Variables de conversión (eVars)

La variable de conversión de perspectiva personalizada (o eVar) se coloca en el código de Adobe en las páginas web del sitio seleccionadas. Su principal función es segmentar las métricas de éxito de conversión en los informes de marketing personalizados.

El mejor uso de las eVars es para medir causa y efecto, como:

* Qué campañas internas influyeron en los ingresos
* Qué anuncios de banner tuvieron como resultado final un registro
* El número de veces que se usó una búsqueda interna antes de realizar un pedido

>[!IMPORTANT]
>
>Al implementar Analytics, es importante saber cuántas eVars se van a utilizar y cuáles son. También debe comprender cómo se configuran esas eVars en Admin Console. Para obtener información detallada sobre las eVars, consulte [Variables de conversión (eVar)](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) en la ayuda de Analytics y en la documentación de referencia.

Una eVar puede basarse en visitas y funcionar de modo similar a las cookies. Los valores pasados a las variables eVar siguen al usuario durante un período de tiempo predeterminado.

Cuando una eVar está establecida en un valor para un visitante, Adobe recuerda automáticamente ese valor hasta que caduque. Cualquier evento de éxito que encuentra el visitante mientras la eVar está activa se cuenta hacia el valor eVar.

> [!NOTE] Se puede guardar un solo valor único en una eVar de una solicitud de imagen. Si quiere que haya varios valores en un valor eVar, le recomendamos que implemente [Variables de lista](/help/implement/js-implementation/page-variables/listvariable.md).

Para obtener más información sobre las variables, consulte:

* [Variables para implementación y creación de informes de Analytics](/help/implement/js-implementation/c-variables/sc-variables.md) en esta página de ayuda
* [Variables: su uso en informes](https://marketing.adobe.com/resources/help/en_US/reference/variable_definitions.html)
* [Variables de página](/help/implement/js-implementation/page-variables/page-variables.md)
* [Variable Campaign](/help/implement/js-implementation/page-variables/campaign.md)
* [Variable products](/help/implement/js-implementation/page-variables/products.md)
* [Variable products](https://marketing.adobe.com/resources/help/en_US/mobile/android/products.html) en la documentación del SDK móvil

