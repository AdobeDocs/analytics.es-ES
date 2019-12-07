---
description: Devuelve el valor de un parámetro de cadena de consulta especificado, si se encuentra en la dirección URL de la página o en la cadena proporcionada.
keywords: Analytics Implementation
subtopic: JavaScript AppMeasurement
title: Util.getQueryParam
topic: Developer and implementation
uuid: 1fecd148-3e52-46f2-a73f-003563f7a62c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Util.getQueryParam

Devuelve el valor de un parámetro de cadena de consulta especificado, si se encuentra en la dirección URL de la página o en la cadena proporcionada.

Puesto que los datos importantes (por ejemplo, códigos de seguimiento de campañas, palabras clave de búsqueda interna, etc.) están disponibles en la cadena de consulta en una página, getQueryParam ayuda a capturar los datos en variables de Analytics.

Esta utilidad reemplaza al complemento [getQueryParam](/help/implement/js-implementation/plugins/getqueryparam.md).

**Sintaxis:**

```
s.Util.getQueryParam(key, [url], [delim])
```

> [!NOTE] La sintaxis de la utilidad difiere de la sintaxis del complemento.

**Parámetros:**

| Parámetro | Descripción |
|---|---|
| key | (obligatorio) Nombre del parámetro de cadena de consulta que desea obtener. Este parámetro distingue entre mayúsculas y minúsculas. |
| URL | (opcional) La dirección URL predeterminada es `s.pageURL` o `window.location`. Al especificar un valor para este parámetro se anula la dirección URL desde la que se recuperó el parámetro de consulta y se utiliza la dirección especificada. |
| delim | (opcional) Delimitador de parámetros en la dirección URL. El delimitador predeterminado es "&amp;". Esto permite especificar un delimitador de cadena de consulta alternativo, por ejemplo, ";". |

**Devuelve:**

La función devolverá una cadena vacía “” si no se proporciona ninguna clave, si no existe ninguna de las opciones de URL o si la clave no se encuentra en la dirección URL. Si se encuentra un # delimitador de fragmento en la dirección URL, no se tiene en cuenta todo lo que sigue al delimitador de fragmento. Si la clave existe y se asigna a un valor, el valor recibe una URL descodificada y se devuelve.

**Ejemplo:**

```js
s.doPlugins = function(s) { 
  s.campaign = s.Util.getQueryParam("cid"); 
};
```

