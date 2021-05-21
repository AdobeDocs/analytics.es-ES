---
title: cookieDomainPeriods
description: Ayudar a AppMeasurement a comprender qué dominio almacenará cookies si su dominio tiene un punto en su sufijo.
exl-id: e994a188-1dab-4bf0-912b-cd2f6a1032e0
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '262'
ht-degree: 100%

---

# fpCookieDomainPeriods

La variable `fpCookieDomainPeriods` ayuda a AppMeasurement a determinar dónde se configuran las cookies de Analytics. Para ello, llama a que el sufijo de dominio tenga un punto adicional. Esta variable permite a AppMeasurement dar cabida al período adicional en el sufijo de dominio y configurar cookies en la ubicación correcta. Hereda el valor de [`cookieDomainPeriods`](cookiedomainperiods.md), pero sigue siendo una práctica recomendada si utiliza una implementación de cookie de origen.

* Para dominios como `example.com` o `www.example.com`, no es necesario configurar esta variable. Si es necesario, puede establecer esta variable en `"2"`.
* Para dominios como `example.co.uk` o `www.example.co.jp`, establezca esta variable como `"3"`.

>[!IMPORTANT]
>
>No tenga en cuenta los subdominios para esta variable. Por ejemplo, no configure `fpCookieDomainPeriods` en la URL de ejemplo `store.toys.example.com`. AppMeasurement reconoce de forma predeterminada que las cookies deben almacenarse en `example.com`, incluso en direcciones URL con muchos subdominios.

## Puntos de dominio de origen en Adobe Experience Platform Launch

Puntos de dominio de origen es un campo en el acordeón de [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón de [!UICONTROL Cookies], que muestra el campo [!UICONTROL Puntos de dominio de origen].

Establezca este campo como `3` solo en los dominios que contengan un punto en su sufijo. De lo contrario, este campo se puede dejar en blanco.

## s.fpCookieDomainPeriods en el editor de código personalizado de AppMeasurement y Launch

La variable `fpCookieDomainPeriods` es una cadena que generalmente se define como `"3"`, solo en los dominios que contienen un punto en su sufijo. Su valor predeterminado es `"2"`, que se adapta a la mayoría de los dominios.

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
