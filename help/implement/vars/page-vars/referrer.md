---
title: referente
description: Omitir el referente recopilado automáticamente para una visita.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# referente

La `referrer` variable anula el referente recopilado automáticamente en los informes. Esta variable es útil en situaciones en las que el referente podría perderse, como por ejemplo durante redirecciones o reenviando temporalmente al visitante a un procesador de pagos. Esta variable ayuda a rellenar las dimensiones &#39;Referente&#39; y &#39;Dominio de referencia&#39;.

## Referente en Adobe Experience Platform Launch

Puede establecer el referente al configurar la extensión de Analytics (variables globales) o en reglas.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics - Establecer variables] o haga clic en el icono &#39;+&#39;.
5. Defina el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el tipo [!UICONTROL de] acción en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Referente] .

Puede establecer el referente en cualquier valor de cadena, incluidos los elementos de datos.

## s.referrer en el editor de código personalizado AppMeasurement e Launch

La `s.referrer` variable es una cadena que contiene la dirección URL de la página anterior. Esta variable puede almacenar un máximo de 255 bytes; los valores mayores a 255 bytes se truncan. AppMeasurement establece automáticamente esta variable en `document.referrer`; no es necesario configurar esta variable a menos que desee anular el valor recopilado automáticamente.

```js
s.referrer = "https://example.com";
```

Evite establecer esta variable en valores que no sean URL.

## Ejemplo

Muchas organizaciones se ocupan de las implementaciones en torno a las redirecciones. Puede utilizar la [`getQueryParam`](../functions/util-getqueryparam.md) utilidad para obtener el referente de la dirección URL si el sitio lo aloja. Asegúrese de que la dirección URL codifique los valores incluidos en la cadena de consulta.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
