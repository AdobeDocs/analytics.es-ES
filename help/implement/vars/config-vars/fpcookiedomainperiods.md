---
title: cookieDomainPeriods
description: Ayuda a AppMeasurement a comprender qué dominio almacenar cookies si su dominio tiene un punto en su sufijo.
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# fpCookieDomainPeriods

La `fpCookieDomainPeriods` variable ayuda a AppMeasurement a determinar dónde se configuran las cookies de Analytics. Para ello, llama a que el sufijo de dominio tenga un período adicional. Esta variable permite a AppMeasurement dar cabida al período adicional en el sufijo de dominio y configurar cookies en la ubicación correcta. Hereda el valor de `cookieDomainPeriods`, pero sigue siendo una práctica recomendada si utiliza una implementación de cookie de origen.

* Para dominios como `example.com` o `www.example.com`, no es necesario configurar esta variable. Si es necesario, puede establecer esta variable en `"2"`.
* Para dominios como `example.co.uk` o `www.example.co.jp`, establezca esta variable en `"3"`.

> [!IMPORTANT] No tenga en cuenta los subdominios para esta variable. Por ejemplo, no configure `fpCookieDomainPeriods` en la URL de ejemplo `store.toys.example.com`. AppMeasurement reconoce de forma predeterminada que las cookies deben almacenarse en `example.com`, incluso en direcciones URL con muchos subdominios.

## Períodos de dominio de origen en el lanzamiento de la plataforma de experiencia de Adobe

Períodos de dominio de origen es un campo en el acordeón [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL Cookies] , que muestra el campo Períodos [!UICONTROL de dominio de] origen.

Establezca este campo en `3` solo los dominios que contengan un punto en su sufijo. De lo contrario, este campo se puede dejar en blanco.

## s.fpCookieDomainPeriods en AppMeasurement e inicie el editor de código personalizado

La `fpCookieDomainPeriods` variable es una cadena que generalmente se define como `"3"`, sólo en los dominios que contienen un punto en su sufijo. Su valor predeterminado es `"2"`, que acomoda a la mayoría de los dominios.

```js
// Manually set fpCookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.fpCookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.fpCookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.fpCookieDomainPeriods = "3" : s.fpCookieDomainPeriods = "2";
```
