---
title: cookieDomain
description: La variable cookieDomain ayuda a determinar el dominio en el que se configurarán las cookies.
translation-type: tm+mt
source-git-commit: dfe2b09b2ee287219d18099c51b6fbd7c86bab21
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 100%

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

## Cookie Domain en Adobe Experience Platform Launch

No hay un campo específico en Launch para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.cookieDomain en el editor de código personalizado de AppMeasurement y Launch

La variable `cookieDomain` es una cadena y está configurada en el dominio en el que desee almacenar las cookies.

```js
s.cookieDomain = "stats.example.com";
```
