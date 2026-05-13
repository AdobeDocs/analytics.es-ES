---
title: cookieDomainPeriods
description: (Obsoleto) Ayude a AppMeasurement a determinar dónde almacenar las cookies cuando el dominio de nivel superior de un sitio web contiene un punto.
feature: Appmeasurement Implementation
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
TQID: https://experienceleague.adobe.com/bsJTIAuqcWoXWWus0oPME9LEwEMaiCGjd1ChmCuSjKY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 394
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

La variable `cookieDomainPeriods` ayudó a AppMeasurement a determinar dónde establecer las cookies de Analytics al indicar que el dominio de nivel superior tenía un punto adicional. Esta variable permitía a AppMeasurement dar cabida al período adicional en el dominio de nivel superior y establecer cookies en la ubicación correcta. Si el dominio de nivel superior del sitio web no incluye un periodo adicional, esta variable no es obligatoria.

* Para dominios como `example.co.uk` o `www.example.co.jp`, establezca esta variable como `"3"`.
* Para dominios como `example.nsw.gov.au`, establezca esta variable en `"4"`.
* Para dominios como `example.com` o `products.example.org`, omita establecer esta variable o establézcala en `"2"`.

>[!TIP]
>
>No tenga en cuenta los subdominios para esta variable. Por ejemplo, no configure `cookieDomainPeriods` en la URL de ejemplo `store.toys.example.com`. AppMeasurement reconoce que las cookies se almacenan en `example.com`, incluso en direcciones URL con muchos subdominios.

En implementaciones de AppMeasurement v2.26.x o posterior, la cookie [`s_ac`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics) se usa para ayudar a determinar automáticamente el dominio de cookie correcto. En primer lugar, la biblioteca intenta escribir una cookie que incluye dos puntos de dominio. Si se produce un error al configurar esta cookie, vuelve a intentarlo, incluidos más periodos de dominio hasta que se realiza correctamente. Esta cookie se elimina inmediatamente una vez configurada.

## Períodos del dominio de cookies mediante Web SDK

Web SDK determina automáticamente el dominio correcto en el que se configurarán las cookies.

## Períodos del dominio de cookies mediante la extensión de Adobe Analytics

**[!UICONTROL Períodos de dominio]** es un campo en el acordeón [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
1. Expanda el acordeón de [!UICONTROL Cookies], que muestra el campo [!UICONTROL Períodos de dominio].

Establezca este campo en `3` solo en los dominios de nivel superior que contengan un punto. De lo contrario, este campo se puede dejar en blanco.

## Puntos de dominio de cookies en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `cookieDomainPeriods` es una cadena que normalmente se establece en `"3"`, solo en los dominios de nivel superior que contienen un punto. Su valor predeterminado es `"2"`, que se adapta a la mayoría de los dominios de nivel superior como `.com` y `.org`.

```js
// Manually set cookieDomainPeriods for domains with a period in the top-level domain, such as www.example.co.uk
s.cookieDomainPeriods = "3";
```
