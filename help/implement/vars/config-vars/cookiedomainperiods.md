---
title: cookieDomainPeriods
description: (Obsoleto) El AppMeasurement de ayuda determina dónde almacenar las cookies cuando el dominio de nivel superior de un sitio web contiene un punto.
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: 1cdcc748e50c7eeffa98897006154aa0953ce7e3
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 18%

---

# cookieDomainPeriods

>[!IMPORTANT]
>Esta variable está obsoleta. Si utiliza cualquiera de los siguientes:
>
>* AppMeasurement v2.26.x o posterior
>* Extensión de Adobe Analytics v1.9.4 o posterior
>* Servicio de Adobe Experience Cloud ID
>
>Esta variable no hace nada, ya que la biblioteca aplicable detecta automáticamente el dominio en el que se configurarán las cookies.

La variable `cookieDomainPeriods` ayudó al AppMeasurement a determinar dónde establecer las cookies de Analytics al indicar que el dominio de nivel superior tenía un punto adicional. Esta variable permitía que el AppMeasurement acomodara el período adicional en el dominio de nivel superior y estableciera cookies en la ubicación correcta. Si el dominio de nivel superior del sitio web no incluye un periodo adicional, esta variable no es obligatoria.

* Para dominios como `example.co.uk` o `www.example.co.jp`, establezca esta variable como `"3"`.
* Para dominios como `example.nsw.gov.au`, establezca esta variable en `"4"`.
* Para dominios como `example.com` o `products.example.org`, omita establecer esta variable o establézcala en `"2"`.

>[!TIP]
>
>No tenga en cuenta los subdominios para esta variable. Por ejemplo, no configure `cookieDomainPeriods` en la URL de ejemplo `store.toys.example.com`. El AppMeasurement reconoce que las cookies se almacenan en `example.com`, incluso en direcciones URL con muchos subdominios.

Para implementaciones en el AppMeasurement v2.26.x o posterior, la cookie [`s_ac`](https://experienceleague.adobe.com/es/docs/core-services/interface/data-collection/cookies/analytics) se usa para ayudar a determinar automáticamente el dominio de cookie correcto. En primer lugar, la biblioteca intenta escribir una cookie que incluye dos puntos de dominio. Si se produce un error al configurar esta cookie, vuelve a intentarlo, incluidos más periodos de dominio hasta que se realiza correctamente. Esta cookie se elimina inmediatamente una vez configurada.

## Períodos de dominio de cookies mediante el SDK web

El SDK web determina automáticamente el dominio correcto para establecer las cookies.

## Períodos del dominio de cookies mediante la extensión de Adobe Analytics

**[!UICONTROL Períodos de dominio]** es un campo en el acordeón [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
1. Expanda el acordeón de [!UICONTROL Cookies], que muestra el campo [!UICONTROL Períodos de dominio].

Establezca este campo en `3` solo en los dominios de nivel superior que contengan un punto. De lo contrario, este campo se puede dejar en blanco.

## Puntos de dominio de cookies en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `cookieDomainPeriods` es una cadena que normalmente se establece en `"3"`, solo en los dominios de nivel superior que contienen un punto. Su valor predeterminado es `"2"`, que se adapta a la mayoría de los dominios de nivel superior como `.com` y `.org`.

```js
// Manually set cookieDomainPeriods for domains with a period in the top-level domain, such as www.example.co.uk
s.cookieDomainPeriods = "3";
```
