---
title: cookieDomain
description: La variable cookieDomain ayuda a determinar el dominio en el que se configurarán las cookies.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# cookieDomain

> [!IMPORTANT] Esta variable está retirada. Use [`trackingServer`](trackingserver.md) en su lugar.

La `cookieDomain` variable determina el dominio donde AppMeasurement establece las cookies. Puede utilizar esta variable para establecer explícitamente el dominio de la cookie en lugar de utilizar la [`cookieDomainPeriods`](cookiedomainperiods.md) variable.

Esta variable sólo debe utilizarse cuando se cumplen **ambas** condiciones:

* Si su implementación utiliza cookies de origen. Esta variable no es necesaria en implementaciones que utilizan un [`trackingServer`](trackingserver.md) valor que contiene `sc.omtrdc.net`.
* Si el dominio tiene un punto en su sufijo. Por ejemplo, `example.co.uk` podría utilizar la `cookieDomain` variable para indicar explícitamente que el dominio de la cookie es `example.co.uk` y no `co.uk`.

Solo se ha utilizado un pequeño número de implementaciones para la `cookieDomain` variable, e incluso entonces, se pueden usar variables alternativas como [`cookieDomainPeriods`](cookiedomainperiods.md) .

## Dominio de cookie en Adobe Experience Platform Launch

No hay un campo dedicado en Launch para utilizar esta variable. Utilice el editor de código personalizado, siguiendo la sintaxis de AppMeasurement.

## s.cookieDomain en AppMeasurement e inicie el editor de código personalizado

La `cookieDomain` variable es una cadena y está configurada en el dominio en el que desea almacenar las cookies.

```js
s.cookieDomain = "stats.example.com";
```
