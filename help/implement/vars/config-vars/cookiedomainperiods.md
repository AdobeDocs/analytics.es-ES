---
title: cookieDomainPeriods
description: Ayudar a AppMeasurement a comprender qué dominio almacenará cookies si su dominio tiene un punto en su sufijo.
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 88%

---


# cookieDomainPeriods

AppMeasurement determina la ubicación de la cookie mirando el sufijo de dominio y el dominio. Para dominios como `example.com`, AppMeasurement establece cookies en la ubicación correcta. Sin embargo, para otros dominios como `example.co.uk`, AppMeasurement puede establecer cookies por error en `co.uk`. La mayoría de los exploradores rechaza las cookies configuradas en este dominio inválido, lo que provoca problemas con la identificación del visitante.

La variable `cookieDomainPeriods` ayuda a AppMeasurement a determinar dónde se configuran las cookies de Analytics. Para ello, llama a que el sufijo de dominio tenga un punto adicional. Esta variable permite a AppMeasurement dar cabida al período adicional en el sufijo de dominio y configurar cookies en la ubicación correcta.

* Para dominios como `example.com` o `www.example.com`, no es necesario configurar esta variable. Si es necesario, puede establecer esta variable en `"2"`.
* Para dominios como `example.co.uk` o `www.example.co.jp`, establezca esta variable como `"3"`.

>[!IMPORTANT]
>
>No tenga en cuenta los subdominios para esta variable. Por ejemplo, no configure `cookieDomainPeriods` en la URL de ejemplo `store.toys.example.com`. AppMeasurement reconoce de forma predeterminada que las cookies deben almacenarse en `example.com`, incluso en direcciones URL con muchos subdominios.

## Períodos de dominio mediante el SDK web

El SDK web puede determinar el dominio de almacenamiento de cookies correcto sin esta variable.

## Períodos de dominio con la extensión Adobe Analytics

Períodos de dominio es un campo en el acordeón de [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
1. Expanda el acordeón de [!UICONTROL Cookies], que muestra el campo [!UICONTROL Períodos de dominio].

Establezca este campo como `3` solo en los dominios que contengan un punto en su sufijo. De lo contrario, este campo se puede dejar en blanco.

## s.cookieDomainPeriods en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `cookieDomainPeriods` es una cadena que generalmente se define como `"3"`, solo en los dominios que contienen un punto en su sufijo. Su valor predeterminado es `"2"`, que se adapta a la mayoría de los dominios.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
