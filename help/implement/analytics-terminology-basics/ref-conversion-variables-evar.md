---
description: La variable de conversión de perspectiva personalizada (o eVar) se coloca en el código de Adobe en las páginas web del sitio seleccionadas. Su principal función es segmentar las métricas de éxito de conversión en los informes de marketing personalizados.
keywords: Implementación de Analytics; Evar; conversion variable; Valor de evar; conversión; evento de éxito
seo-description: La variable de conversión de perspectiva personalizada (o eVar) se coloca en el código de Adobe en las páginas web del sitio seleccionadas. Su principal función es segmentar las métricas de éxito de conversión en los informes de marketing personalizados.
seo-title: Variables de conversión (evars)
solution: Analytics
title: Variables de conversión (evars)
topic: Desarrollador e implementación
uuid: 50071 c 1 c-be 00-4 b 3 a-a 7 ee -5 d 129 acf 498 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Variables de conversión (evars)

La variable de conversión de perspectiva personalizada (o eVar) se coloca en el código de Adobe en las páginas web del sitio seleccionadas. Su principal función es segmentar las métricas de éxito de conversión en los informes de marketing personalizados.

El mejor uso de las eVars es para medir causa y efecto, como:

* Qué campañas internas influyeron en los ingresos
* Qué anuncios de banner tuvieron como resultado final un registro
* El número de veces que se usó una búsqueda interna antes de realizar un pedido

>[!IMPORTANT]
>
>Al implementar Analytics, es importante conocer las evars que utilizará y cuántas. También debe comprender cómo se configuran esas eVars en Admin Console. Para obtener información detallada sobre las eVars, consulte [Variables de conversión (eVar)](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) en la ayuda de Analytics y en la documentación de referencia.

Una eVar puede basarse en visitas y funcionar de modo similar a las cookies. Los valores pasados a las variables eVar siguen al usuario durante un período de tiempo predeterminado.

Cuando una eVar está establecida en un valor para un visitante, Adobe recuerda automáticamente ese valor hasta que caduque. Cualquier evento exitoso que encuentra el visitante mientras la eVar está activa se cuenta hacia el valor eVar.

>[!NOTE]
>
>Solo se puede almacenar un valor único en una evar en una solicitud de imagen. Si quiere que haya varios valores en un valor eVar, le recomendamos que implemente [](/help/implement/js-implementation/c-variables/page-variables.md)Variables de lista.

Para obtener más información sobre las variables, consulte:

* [Variables para la implementación e informes de Analytics](../../implement/js-implementation/c-variables/sc-variables.md#concept_E10E43221A2740FAAF900B79CE1EC5FB) en esta ayuda
* [Variables: su uso en informes](https://marketing.adobe.com/resources/help/en_US/reference/variable_definitions.html)
* [Variables de página](/help/implement/js-implementation/c-variables/page-variables.md)
* [Variable campaign](/help/implement/js-implementation/c-variables/page-variables.md)
* [Variable products](/help/implement/js-implementation/c-variables/page-variables.md)
* [Variable products](https://marketing.adobe.com/resources/help/en_US/mobile/android/products.html) en la documentación del SDK móvil

