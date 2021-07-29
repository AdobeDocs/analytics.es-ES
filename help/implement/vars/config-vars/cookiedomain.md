---
title: cookieDomain
description: La variable cookieDomain ayuda a determinar el dominio en el que se configurarán las cookies.
exl-id: 7e8c26b8-d1a7-49f7-9c12-45fb1633c9d7
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 87%

---

# cookieDomain

>[!IMPORTANT]
>
>Esta variable está retirada. Utilice [`trackingServer`](trackingserver.md) en su lugar.

La variable `cookieDomain` determina el dominio donde AppMeasurement establece las cookies. Puede utilizar esta variable para establecer explícitamente el dominio de la cookie en lugar de utilizar la variable [`cookieDomainPeriods`](cookiedomainperiods.md).

Esta variable solo debe utilizarse cuando se cumplen **ambas** condiciones:

* Si su implementación utiliza cookies de origen. Esta variable no es necesaria en implementaciones que utilizan un [`trackingServer`](trackingserver.md) valor que contiene `sc.adobedc.net`.
* Si el dominio tiene un punto en su sufijo. Por ejemplo, `example.co.uk` podría utilizar la variable `cookieDomain` para indicar explícitamente que el dominio de la cookie es `example.co.uk` y no `co.uk`.

Solo se ha utilizado un pequeño número de implementaciones para la variable `cookieDomain`, e incluso entonces, se pueden usar variables alternativas como [`cookieDomainPeriods`](cookiedomainperiods.md).

## Dominio de cookies que utiliza etiquetas en Adobe Experience Platform

No hay un campo dedicado en la interfaz de usuario de recopilación de datos para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.cookieDomain en el editor de código personalizado de AppMeasurement y 

La variable `cookieDomain` es una cadena y está configurada en el dominio en el que desee almacenar las cookies.

```js
s.cookieDomain = "stats.example.com";
```
