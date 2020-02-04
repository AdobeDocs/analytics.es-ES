---
title: cookieDomainPeriods
description: Ayuda a AppMeasurement a comprender qué dominio almacenar cookies si su dominio tiene un punto en su sufijo.
translation-type: tm+mt
source-git-commit: 04b97e93a95691132680d4da197dc62eb2b9fdd1

---


# cookieDomainPeriods

AppMeasurement determina la ubicación de la cookie mirando el sufijo de dominio y dominio. Para dominios como `example.com`, AppMeasurement establece cookies en la ubicación correcta. Sin embargo, para otros dominios como `example.co.uk`, AppMeasurement puede establecer cookies por error en `co.uk`. La mayoría de los exploradores rechaza las cookies configuradas en este dominio no válido, lo que provoca problemas con la identificación del visitante.

La `cookieDomainPeriods` variable ayuda a AppMeasurement a determinar dónde se configuran las cookies de Analytics. Para ello, llama a que el sufijo de dominio tenga un período adicional. Esta variable permite a AppMeasurement dar cabida al período adicional en el sufijo de dominio y configurar cookies en la ubicación correcta.

* Para dominios como `example.com` o `www.example.com`, no es necesario configurar esta variable. Si es necesario, puede establecer esta variable en `"2"`.
* Para dominios como `example.co.uk` o `www.example.co.jp`, establezca esta variable en `"3"`.

> [!IMPORTANT] No tenga en cuenta los subdominios para esta variable. Por ejemplo, no configure `cookieDomainPeriods` en la URL de ejemplo `store.toys.example.com`. AppMeasurement reconoce de forma predeterminada que las cookies deben almacenarse en `example.com`, incluso en direcciones URL con muchos subdominios.

## Períodos de dominio en el lanzamiento de la plataforma de experiencias de Adobe

Períodos de dominio es un campo en el acordeón [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón [!UICONTROL Cookies] , que muestra el campo Períodos  de dominio.

Establezca este campo en `3` solo los dominios que contengan un punto en su sufijo. De lo contrario, este campo se puede dejar en blanco.

## s.cookieDomainPeriods en AppMeasurement e inicie el editor de código personalizado

La `cookieDomainPeriods` variable es una cadena que generalmente se define como `"3"`, sólo en los dominios que contienen un punto en su sufijo. Su valor predeterminado es `"2"`, que acomoda a la mayoría de los dominios.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
