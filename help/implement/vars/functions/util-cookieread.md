---
title: Util.cookieRead
description: Obtiene el valor de una cookie.
feature: Appmeasurement Implementation
exl-id: b05b628c-bae6-4dba-bc1d-6a1ab56e3660
role: Admin, Developer
TQID: https://experienceleague.adobe.com/BuAe772j8DToDmAkr46Bg5kEAifNIFso0xQ423xdwxg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 184
ht-degree: 72%

---

# Util.cookieRead

Las cookies pueden almacenar y recuperar información entre páginas del mismo dominio. Utilice el método `Util.cookieRead()` para recuperar un valor de una cookie.

## Lectura de cookies mediante la extensión de Adobe Analytics y la extensión de Web SDK

Puede leer las cookies configurando los valores en los elementos de datos.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Elementos de datos] y, a continuación, haga clic en el elemento de datos deseado (o cree un elemento de datos).
4. Establezca la lista desplegable [!UICONTROL Extension] en **[!UICONTROL Core]** y el [!UICONTROL Tipo de elemento de datos] en **[!UICONTROL Cookie]**.
5. Escriba el nombre de la cookie en el campo de texto.

El valor de la cookie se almacena en el elemento de datos. A continuación, puede hacer referencia al elemento de datos en las reglas para asignar las variables deseadas.

## s.Util.cookieRead() en AppMeasurement y el editor de código personalizado de la extensión de Analytics

Llame al método `s.Util.cookieRead()` para leer un valor de cookie deseado. Su único argumento es una cadena, que es obligatoria. Este método devuelve una cadena que contiene el valor de la cookie. Si las cookies no existen, se devuelve una cadena vacía.

```js
// Reads the value set in the cookie named 'example' and assigns the value to eVar1
s.eVar1 = s.Util.cookieRead("example");
```
