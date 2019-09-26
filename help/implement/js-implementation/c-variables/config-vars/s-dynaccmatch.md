---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountMatch

La variable utiliza el objeto DOM para recuperar la sección de la dirección URL donde se aplican todas las reglas de 

This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' Como el valor predeterminado es [!DNL window.location.host], esta variable no es necesaria para que [!UICONTROL selección de cuentas dinámicas] funcione. For additional information, see [dynamicAccountList](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

Las reglas encontradas en `dynamicAccountList` se aplican al valor de `dynamicAccountMatch`. Si `dynamicAccountMatch` solo contiene [!DNL window.location.host] (predeterminado), las reglas en `dynamicAccountList` se aplican solo al dominio de la página.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | window.location.host |

## Sintaxis y valores posibles

La sintaxis de la variable `dynamicAccountMatch` normalmente la rellenará el consultor de Adobe que proporciona el archivo de AppMeasurement para JavaScript. Sin embargo, los valores indicados a continuación se pueden aplicar en cualquier momento.

```js
s.dynamicAccountMatch=[DOM object]
```

| Descripción | Valor |
|---|---|
| Dominio (predeterminado) | window.location.host |
| Ruta | window.location.pathname |
| Cadena de consulta | (window.location.search?window.location.search:"?") |
| Dominio y ruta | window.location.host+window.location.pathname |
| Ruta y cadena de consulta | window.location.pathname+(window.location.search?window.location.search:"?") |
| Dirección URL completa | window.location.href |

## Ejemplos

```js
s.dynamicAccountMatch=window.location.pathname
```

```js
s.dynamicAccountMatch=window.location.host+window.location.pathname
```

## Parámetros de configuración

Ninguno.

## Problemas, preguntas y consejos

* La selección de cuentas dinámicas no se admite en [AppMeasurement para JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* When pages are saved to a hard drive, [!DNL window.location.host] is empty, causing those page views to be sent to the default report suite (in `s_account`).

* Cuando se traduce una página con un motor de traducción web, como Google, la [!UICONTROL selección de cuentas dinámicas] no funciona como está previsto. Para un seguimiento más preciso, rellene el lado del servidor de la variable [!UICONTROL s_account ].
