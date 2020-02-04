---
title: Util.cookieRead
description: Obtiene el valor de una cookie.
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# Util.cookieRead

Las cookies pueden almacenar y recuperar información entre páginas del mismo dominio. Utilice el `Util.cookieRead` método para recuperar un valor de una cookie.

## Leer cookies en Adobe Experience Platform Launch

Puede leer las cookies configurando los valores en los elementos de datos.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha Elementos [!UICONTROL de] datos y, a continuación, haga clic en el elemento de datos deseado (o cree un elemento de datos).
4. Defina el menú desplegable [!UICONTROL Extensión] como [!UICONTROL Principal]y el Tipo [!UICONTROL de elemento] de datos como [!UICONTROL Cookie].
5. Escriba el nombre de la cookie en el campo de texto.

El valor de la cookie se almacena en el elemento de datos. A continuación, puede hacer referencia al elemento de datos en las reglas para asignar variables de Analytics.

## s.Util.cookieRead() en el editor de código personalizado AppMeasurement e Launch

Llame al `s.Util.cookieRead()` método para leer un valor de cookie deseado. Su único argumento es una cadena, que es obligatoria. Este método devuelve una cadena que contiene el valor de la cookie. Si las cookies no existen, se devuelve una cadena vacía.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
