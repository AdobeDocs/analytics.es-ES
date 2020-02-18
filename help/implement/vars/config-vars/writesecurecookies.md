---
title: writeSecureCookies
description: Permite a AppMeasurement establecer cookies con el atributo Secure.
translation-type: tm+mt
source-git-commit: 117a3c1ad411b25d8277b5678915b76eadd232a7

---


# writeSecureCookies

La `writeSecureCookies` variable permite que AppMeasurement establezca cookies [](https://en.wikipedia.org/wiki/Secure_cookie) seguras para Analytics. Esta configuración se aplica tanto a las cookies de ID de visitante configuradas por AppMeasurement como a las cookies configuradas mediante el `Util.CookieWrite` método . Requiere AppMeasurement 2.18.0 o superior.

> [!NOTE] Si habilita la `writeSecureCookies` variable, asegúrese de que todo el contenido del sitio se suministra de forma segura a través de HTTPS.

## Escribir cookies seguras en el lanzamiento de Adobe Experience Platform

No hay un campo dedicado en Launch para utilizar esta variable. Utilice el editor de código personalizado, siguiendo la sintaxis de AppMeasurement.

## s.writeSecureCookies en el editor de código personalizado AppMeasurement e Launch

La `s.writeSecureCookies` variable es un booleano que determina si AppMeasurement establece el atributo Secure al crear una cookie. Its default value is `false`. Configure esta variable en `true` si todo el contenido del sitio es seguro y desea que las cookies configuradas por AppMeasurement tengan el atributo Secure.

```js
s.writeSecureCookies = true;
```
