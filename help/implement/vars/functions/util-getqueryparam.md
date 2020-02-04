---
title: Util.getQueryParam
description: Devuelve el valor de un parámetro de cadena de consulta.
translation-type: tm+mt
source-git-commit: dfe8409b13fcf67eae6a0c404f83c1209f89ae12

---


# Util.getQueryParam

Los parámetros de cadena de consulta de una URL de navegador contienen con frecuencia datos importantes para Analytics. Utilice el `Util.getQueryParam` método para recuperar datos de la cadena de consulta.

## Obtener datos de parámetros de cadena de consulta en Adobe Experience Platform Launch

Puede obtener datos de parámetros de cadena de consulta estableciendo valores en los elementos de datos.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha Elementos [!UICONTROL de] datos y, a continuación, haga clic en el elemento de datos deseado (o cree un elemento de datos).
4. Defina el menú desplegable [!UICONTROL Extensión] como [!UICONTROL Principal]y el Tipo [!UICONTROL de elemento] de datos como Parámetro [!UICONTROL de cadena]de consulta.
5. Introduzca el parámetro de cadena de consulta en el campo de texto.

El valor del parámetro de cadena de consulta se almacena en el elemento de datos. A continuación, puede hacer referencia al elemento de datos en las reglas para asignar variables de Analytics.

## s.Util.getQueryParam() en el editor de código personalizado AppMeasurement e Launch

Llame al `s.Util.getQueryParam()` método para recuperar un valor de cadena de consulta de la dirección URL del explorador. Se requiere el argumento de cadena que contiene un parámetro de cadena de consulta. Este método devuelve una cadena que puede asignar a variables de Analytics:

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

Un segundo argumento opcional permite especificar la cadena que se va a comprobar para buscar parámetros de cadena de consulta. De forma predeterminada, la utilidad observa la dirección URL del explorador.

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

Un tercer argumento opcional permite personalizar el delimitador de cadena de consulta. Its default value is `&`. Puede cambiar este valor si la cadena de consulta utiliza un delimitador diferente.

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

> [!NOTE] Las versiones anteriores de AppMeasurement tenían un complemento denominado `s.getQueryParam` . Este complemento ya no es necesario, ya que ahora se incluye en AppMeasurement de forma predeterminada.
