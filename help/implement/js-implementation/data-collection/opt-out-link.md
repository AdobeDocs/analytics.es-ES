---
description: Especifique un enlace de exclusión y personalice la marca del enlace. Los visitantes del sitio web pueden determinar que su actividad no debe rastrearse con los productos de análisis de Adobe en la página de exclusión del dominio de recopilación de datos específico.
keywords: Implementación de Analytics
seo-description: Especifique un enlace de exclusión y personalice la marca del enlace. Los visitantes del sitio web pueden determinar que su actividad no debe rastrearse con los productos de análisis de Adobe en la página de exclusión del dominio de recopilación de datos específico.
seo-title: Agregar un vínculo de exclusión
solution: Analytics
subtopic: Resolución de problemas
title: Agregar un vínculo de exclusión
topic: Desarrollador e implementación
uuid: c 12092 be -3 be 7-4621-b 838-d 6 b 78 d 074 f 84
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Agregar un vínculo de exclusión

Especifique un enlace de exclusión y personalice la marca del enlace. Los visitantes del sitio web pueden determinar que su actividad no debe rastrearse con los productos de análisis de Adobe en la página de exclusión del dominio de recopilación de datos específico.

Si un usuario no desea que se le rastree y se establece una cookie de exclusión, el archivo JavaScript seguirá enviando datos a los servidores de Adobe, aunque estos datos ni se procesarán ni se usarán en los informes.

La sección collection_domain de la estructura de la dirección URL es el valor de trackingServer que se usa en el archivo JavaScript. El dominio de recopilación que se usa en la implementación de Adobe Analytics se encuentra en DigitalPulse Debugger, en la primera fila de la tabla de Adobe Analytics, con la etiqueta "First Party Cookies" o "Third Party Cookies", en función de la implementación. El dominio de recopilación del sitio web puede contener un dominio de 2o7.net, omtrdc.net o del sitio web (por ejemplo, métricas.ejemplo.com).

Los visitantes que desean excluirse hacen clic en el vínculo de la página de exclusión y a continuación se establece una cookie en su explorador. Si se detecta la cookie `omniture_optout` para el dominio de seguimiento aplicable, las actividades del usuario no se incluirán en los informes de Adobe Analytics. Puede asignar su propio vínculo a la cookie de exclusión o seguir los pasos siguientes para establecer esta cookie.

Adobe ofrece opciones de exclusión para todos los tipos de implementación. Usted es el responsable de su propia política de privacidad y de cumplir los términos acordados. Tenga en cuenta que el vínculo a la página de exclusión cambiará según el tipo de implementación, tal como se indica en este documento.

Si implementa productos y servicios de Adobe Analytics y establece cookies en dominios propiedad de Adobe (por ejemplo, 207.net u omtrdc.net), puede mostrar a los visitantes del sitio web el mecanismo de exclusión del [Centro de privacidad de Adobe](https://www.adobe.com/privacy/opt-out.html), válido para todos los sitios que usan cookies de Adobe para los productos y servicios de Adobe Analytics. The direct link to the Adobe opt-out mechanism is `https:// *collection_domain* /optout.html`.

More information about Adobe Analytics privacy practices can be found at [https://www.adobe.com/privacy/advertising-services.html](https://www.adobe.com/privacy/advertising-services.html).

* [Estructura de la dirección URL de la página de exclusión](../../../implement/js-implementation/data-collection/opt-out-link.md#section_E0462428D2E440E7863E24D2F6DBF748)
* [Direcciones URL de exclusión de ejemplo](../../../implement/js-implementation/data-collection/opt-out-link.md#section_258DE5226AA0483CA790D2C9C5318B2E)
* [Personalizar la marca de su URL de exclusión](../../../implement/js-implementation/data-collection/opt-out-link.md#section_674AB62E810B414AB8F1615C0E3061F8)

## Estructura de la dirección URL de la página de exclusión {#section_E0462428D2E440E7863E24D2F6DBF748}

La página de exclusión tiene la dirección URL siguiente:

```
https://collection_domain/optout.html[?optional_parameters]
```

`optional_parameters` La inclusión:

`locale=[code]`: Proporciona una versión traducida de la página de exclusión. Se admiten las configuraciones regionales siguientes:

* en_US (valor predeterminado)
* de_DE
* es_ES
* fr_FR
* jp_JP
* ko_KR
* zh_CN
* zh_TW

`popup=1`: Trata la página como si se tratara de un elemento emergente y proporciona un botón "Cerrar ventana".

## Direcciones URL de exclusión de ejemplo {#section_258DE5226AA0483CA790D2C9C5318B2E}

Una página web en inglés a ventana completa que contiene un vínculo. Si el usuario hace clic en él, no se le rastreará en metrics.example.com:

```
https://metrics.example.com/optout.html
```

Una página web en francés a ventana completa que contiene un vínculo. Si el usuario hace clic en él, no se le rastreará en example.d3.sc.omtrdc.net:

```
https://example.d3.sc.omtrdc.net/optout.html?locale=fr_FR
```

Una página web en alemán en una ventana emergente que contiene un vínculo. Si el usuario hace clic en él, no se le rastreará en example.112.2o7.net:

```
https://example.112.2o7.net/optout.html?popup=1&locale=de_DE
```

## Personalizar la marca de su URL de exclusión {#section_674AB62E810B414AB8F1615C0E3061F8}

Puede proporcionar un enlace, como el siguiente, en algún lugar de su sitio web:

```
 <a href=" https://stats.adobe.com/optout.html?optout=1&confirm_change=1">
Click Here to Opt Out! </a>
```

Donde *`stats.adobe.com`* se reemplazará con cualquier *`s.trackingServer`* variable establecida en.

Additionally, if you want like to provide a link to opt-in, use the same URL, but replace `?optout=1` with `?optin=1`, and keep the `confirm_change=1`.
