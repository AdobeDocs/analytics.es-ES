---
title: cookieDomain
description: (Retirado) Ayuda a determinar el dominio en el que se configurarán las cookies.
feature: Appmeasurement Implementation
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
role: Admin, Developer
TQID: https://experienceleague.adobe.com/z6occeGLpxezOj7go2DrwG-j-fc9yBuGyHSmZJK9RfQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 198
ht-degree: 77%

---

# cookieDomain

>[!IMPORTANT]
>Esta variable está retirada. Utilice [`trackingServer`](trackingserver.md) en su lugar.

La variable `cookieDomain` determina el dominio donde AppMeasurement establece las cookies. Puede utilizar esta variable para establecer explícitamente el dominio de la cookie en lugar de utilizar la variable [`cookieDomainPeriods`](cookiedomainperiods.md).

Esta variable solo debe utilizarse cuando se cumplen **ambas** condiciones:

* Si su implementación utiliza cookies de origen. Esta variable no es necesaria en implementaciones que utilizan un [`trackingServer`](trackingserver.md) valor que contiene `sc.adobedc.net`.
* Si el dominio tiene un punto en su sufijo. Por ejemplo, `example.co.uk` podría utilizar la variable `cookieDomain` para indicar explícitamente que el dominio de la cookie es `example.co.uk` y no `co.uk`.

Solo se ha utilizado un pequeño número de implementaciones para la variable `cookieDomain`, e incluso entonces, se pueden usar variables alternativas como [`cookieDomainPeriods`](cookiedomainperiods.md).

## Dominio de cookies mediante Web SDK

Web SDK puede determinar el dominio de almacenamiento de cookies correcto sin esta variable.

## Dominio de cookies con la extensión Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.cookieDomain en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `cookieDomain` es una cadena y está configurada en el dominio en el que desee almacenar las cookies.

```js
s.cookieDomain = "stats.example.com";
```
