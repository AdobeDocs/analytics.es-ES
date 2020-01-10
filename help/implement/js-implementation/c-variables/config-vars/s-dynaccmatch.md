---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicAccountMatch

La variable utiliza el objeto DOM para recuperar la sección de la dirección URL donde se aplican todas las reglas de

Esta variable solo es válida cuando *`dynamicAccountSelection`* está configurada en “True”. Como el valor predeterminado es [!DNL window.location.host], esta variable no es necesaria para que [!UICONTROL selección de cuentas dinámicas] funcione. Para obtener más información, consulte [dynamicAccountList](https://docs.adobe.com/content/help/es-ES/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

Las reglas encontradas en `dynamicAccountList` se aplican al valor de `dynamicAccountMatch`. Si `dynamicAccountMatch` solo contiene [!DNL window.location.host] (predeterminado), las reglas en `dynamicAccountList` se aplican solo al dominio de la página.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N/A | N/A | N/A | window.location.host |

## Sintaxis y valores posibles

La variable `dynamicAccountMatch` normalmente la rellenará el consultor de Adobe que proporcione el archivo de AppMeasurement para JavaScript. Sin embargo, los valores indicados a continuación se pueden aplicar en cualquier momento.

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

Ninguna

## Problemas, preguntas y consejos

* La selección de cuentas dinámicas no es compatible con [AppMeasurement para JavaScript](https://docs.adobe.com/content/help/es-ES/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Cuando las páginas se guardan en un disco duro, [!DNL window.location.host] está vacío, lo que provoca que las vistas de esas páginas se envíen al grupo de informes predeterminado (en `s_account`).

* Cuando se traduce una página con un motor de traducción web, como Google, la [!UICONTROL selección de cuentas dinámicas] no funciona como está previsto. Para un seguimiento más preciso, rellene el lado del servidor de la variable [!UICONTROL s_account].
