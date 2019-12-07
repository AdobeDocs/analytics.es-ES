---
description: Obtenga información sobre la variable purchaseID, que ayuda a evitar que aparezcan compras duplicadas en Adobe Analytics.
keywords: duplicate,purchase,purchaseid,s.purchaseid
subtopic: Variables
title: purchaseID
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# purchaseID

The `purchaseID` variable is used to keep an order from being counted multiple times in reporting. Whenever the purchase event is used on your site, Adobe recommends using the `purchaseID` variable.

Cuando un visitante compra un artículo en el sitio, `purchaseID` generalmente se rellena en la página "Gracias" o "Confirmación de pedido". Configure la `purchaseID` variable al mismo tiempo que se activa un evento de compra. Cuando `purchaseID` se define en un valor único, los valores de las variables de conversión solo se contabilizan para las visitas con esa ID de compra única. La definición de la página `purchaseID` es valiosa porque los visitantes suelen marcar una página de confirmación de compra para sus propios fines. Si su implementación no utiliza `purchaseID`, los datos de conversión (como los ingresos) pueden aumentar fácilmente según los visitantes que actualicen las páginas.

Además de los datos de compra, todas las variables de conversión y todos los eventos no se cuentan varias veces para las visitas con el mismo ID de compra.

## Sintaxis

La `purchaseID` variable puede contener cualquier valor alfanumérico, hasta un máximo de 20 bytes. Si establece un ID de compra de más de 20 bytes, el valor se truncará.

```js
s.purchaseID = "uniqueid";
```
