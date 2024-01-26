---
title: writeSecureCookies
description: Permite a AppMeasurement establecer cookies con el atributo Secure.
feature: Variables
exl-id: 0e03d621-5770-4c25-981d-e4af1431ec69
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 76%

---

# writeSecureCookies

La variable `writeSecureCookies` permite que AppMeasurement establezca [cookies seguras](https://en.wikipedia.org/wiki/Secure_cookie) para Analytics. Esta configuración se aplica tanto a las cookies de ID de visitante configuradas por AppMeasurement como a las cookies configuradas mediante el método `Util.CookieWrite()`. Requiere AppMeasurement 2.18.0 o superior.

`writeSecureCookies` solo se aplica a las cookies configuradas por el JavaScript de AppMeasurement (`s_fid`, `s_cc` y `s_sq`). Las cookies configuradas por la respuesta `https` (`s_vi` y `s_ecid`) se pueden configurar como “seguras” poniéndose en contacto con el Servicio de atención al cliente de Adobe.

Obtenga más información acerca de las cookies de Analytics [aquí](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html?lang=es).

>[!WARNING]
>
>Si habilita la variable `writeSecureCookies`, asegúrese de que todo el contenido del sitio se suministre de forma segura a través de HTTPS. La recopilación de datos no funciona correctamente si esta variable está habilitada y tiene contenido no seguro en la página.

## Uso de cookies seguras con el SDK web

Si su sitio utiliza el protocolo HTTPS, el atributo Secure se establece para todas las cookies que establece el SDK web.

## Escribir cookies seguras mediante la extensión de Adobe Analytics

[!UICONTROL Escribir cookies seguras] es una casilla de verificación situada debajo del elemento de acordeón [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL Cookies], que muestra la casilla [!UICONTROL Escribir cookies seguras].

## s.writeSecureCookies en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.writeSecureCookies` es un booleano que determina si AppMeasurement establece el atributo Secure al crear una cookie. Su valor predeterminado es `false`. Configure esta variable en `true` si todo el contenido del sitio es seguro y desea que las cookies configuradas por AppMeasurement tengan el atributo Secure.

```js
s.writeSecureCookies = true;
```
