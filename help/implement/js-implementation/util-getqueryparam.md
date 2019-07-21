---
description: Devuelve el valor de un parámetro de cadena de consulta especificado, si se encuentra en la dirección URL de la página o en la cadena proporcionada.
keywords: Implementación de Analytics
seo-description: Devuelve el valor de un parámetro de cadena de consulta especificado, si se encuentra en la dirección URL de la página o en la cadena proporcionada.
seo-title: Util.getQueryParam
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Util.getQueryParam
topic: Desarrollador e implementación
uuid: 1 fecd 148-3 e 52-46 f 2-a 73 f -003563 f 7 a 62 c
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Util.getQueryParam

Devuelve el valor de un parámetro de cadena de consulta especificado, si se encuentra en la dirección URL de la página o en la cadena proporcionada.

Puesto que los datos importantes (por ejemplo, códigos de seguimiento de campañas, palabras clave de búsqueda interna, etc.) están disponibles en la cadena de consulta en una página,  getQueryParam ayuda a capturar los datos en variables de Analytics.

Esta utilidad reemplaza al complemento [getQueryParam](../../implement/js-implementation/plugins/getqueryparam.md#concept_E3D0FEC81E1F4987B39CC467F19FFCFF).

**Sintaxis:**

```
s.Util.getQueryParam(key, [url], [delim])
```

>[!NOTE]
>
>La sintaxis de la utilidad difiere de la sintaxis del complemento.

**Parámetros:**

| Parámetro | Descripción |
|---|---|
| key | (obligatorio) Nombre del parámetro de cadena de consulta que desea obtener. Este parámetro distingue entre mayúsculas y minúsculas. |
| url | (optional) Default url is `s.pageURL` or `window.location`. Al especificar un valor para este parámetro se anula la dirección URL desde la que se recuperó el parámetro de consulta y se utiliza la dirección especificada. |
| delim | (opcional) Delimitador de parámetros en la dirección URL. El delimitador predeterminado es "&amp;". Esto permite especificar un delimitador de cadena de consulta alternativo, por ejemplo, ";". |

**Valores devueltos:**

La función devolverá una cadena vacía "si no se proporciona ninguna clave, o si existe ninguna de las opciones de URL, o si la clave no se encuentra en la dirección URL. Si se encuentra un delimitador de fragmento en la URL, no se considera todo lo que sigue al delimitador de fragmento. Si la clave existe y se asigna a un valor, el valor es decodificado y decodificado.

**Ejemplo:**

```js
s.doPlugins = function(s) { 
  s.campaign = s.Util.getQueryParam("cid"); 
};
```

