---
title: Util.cookieRead
description: Obtiene el valor de una cookie.
feature: Variables
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '171'
ht-degree: 100%

---

# Util.cookieRead

Las cookies pueden almacenar y recuperar información entre páginas del mismo dominio. Utilice el método `Util.cookieRead()` para recuperar un valor de una cookie.

## Lectura de cookies mediante etiquetas en Adobe Experience Platform

Puede leer las cookies configurando los valores en los elementos de datos.

1. Inicie sesión en la [IU de recopilación de datos](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Elementos de datos] y, a continuación, haga clic en el elemento de datos deseado (o cree un elemento de datos).
4. Defina el menú desplegable [!UICONTROL Extensión] como [!UICONTROL Principal] y el [!UICONTROL Tipo de elemento de datos] como [!UICONTROL Cookie].
5. Escriba el nombre de la cookie en el campo de texto.

El valor de la cookie se almacena en el elemento de datos. A continuación, puede hacer referencia al elemento de datos en las reglas para asignar variables de Analytics.

## s.Util.cookieRead() en el editor de código personalizado de AppMeasurement y 

Llame al método `s.Util.cookieRead()` para leer un valor de cookie deseado. Su único argumento es una cadena, que es obligatoria. Este método devuelve una cadena que contiene el valor de la cookie. Si las cookies no existen, se devuelve una cadena vacía.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
