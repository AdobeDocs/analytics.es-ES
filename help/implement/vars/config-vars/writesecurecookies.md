---
title: writeSecureCookies
description: Permite a AppMeasurement establecer cookies con el atributo Secure.
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# writeSecureCookies

La variable `writeSecureCookies` permite que AppMeasurement establezca [cookies seguras](https://en.wikipedia.org/wiki/Secure_cookie) para Analytics. Esta configuración se aplica tanto a las cookies de ID de visitante configuradas por AppMeasurement como a las cookies configuradas mediante el método `Util.CookieWrite()`. Requiere AppMeasurement 2.18.0 o superior.

>[!IMPORTANT] Si habilita la variable `writeSecureCookies`, asegúrese de que todo el contenido del sitio se suministre de forma segura a través de HTTPS. AppMeasurement no funciona si esta variable está habilitada y tiene contenido no seguro en la página.

## Escribir cookies seguras en Adobe Experience Platform Launch

No hay un campo específico en Launch para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.writeSecureCookies en el editor de código personalizado de AppMeasurement y Launch

La variable `s.writeSecureCookies` es un booleano que determina si AppMeasurement establece el atributo Secure al crear una cookie. Su valor predeterminado es `false`. Configure esta variable en `true` si todo el contenido del sitio es seguro y desea que las cookies configuradas por AppMeasurement tengan el atributo Secure.

```js
s.writeSecureCookies = true;
```
