---
title: fpcookieDomainPeriods
description: Ayudar a AppMeasurement a comprender qué dominio almacenará cookies si su dominio tiene un punto en su sufijo.
feature: Variables
exl-id: e994a188-1dab-4bf0-912b-cd2f6a1032e0
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 86%

---

# fpCookieDomainPeriods

La variable `fpCookieDomainPeriods` ayuda a AppMeasurement a determinar dónde se configuran las cookies de Analytics. Para ello, llama a que el sufijo de dominio tenga un punto adicional. Esta variable permite a AppMeasurement dar cabida al período adicional en el sufijo de dominio y configurar cookies en la ubicación correcta. Hereda el valor de [`cookieDomainPeriods`](cookiedomainperiods.md), pero sigue siendo una práctica recomendada si utiliza una implementación de cookie de origen.

* Para dominios como `example.com` o `www.example.com`, no es necesario configurar esta variable. Si es necesario, puede establecer esta variable en `"2"`.
* Para dominios como `example.co.uk` o `www.example.co.jp`, establezca esta variable como `"3"`.

>[!IMPORTANT]
>
>No tenga en cuenta los subdominios para esta variable. Por ejemplo, no configure `fpCookieDomainPeriods` en la URL de ejemplo `store.toys.example.com`. AppMeasurement reconoce de forma predeterminada que las cookies deben almacenarse en `example.com`, incluso en direcciones URL con muchos subdominios.

## Puntos de dominio de origen mediante el SDK web

El SDK web puede determinar el dominio de almacenamiento de cookies correcto sin esta variable.

## Puntos de dominio de origen mediante la extensión de Adobe Analytics

Puntos de dominio de origen es un campo en el acordeón de [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
4. Expanda el acordeón de [!UICONTROL Cookies], que muestra el campo [!UICONTROL Puntos de dominio de origen].

Establezca este campo como `3` solo en los dominios que contengan un punto en su sufijo. De lo contrario, este campo se puede dejar en blanco.

## s.fpCookieDomainPeriods en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `fpCookieDomainPeriods` es una cadena que generalmente se define como `"3"`, solo en los dominios que contienen un punto en su sufijo. Su valor predeterminado es `"2"`, que se adapta a la mayoría de los dominios.

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
