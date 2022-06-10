---
title: purchaseID
description: Anule la duplicación de visitas en función de un identificador de compra único.
feature: Variables
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 80%

---

# purchaseID

La variable `purchaseID` ayuda a evitar que las visitas que contienen la misma compra inflen informes. Por ejemplo: Si un visitante llega a la página de confirmación de compra, normalmente envía a Adobe datos sobre los ingresos generados por la transacción. Si el usuario actualiza esta página varias veces o marca la página para visitarla más adelante, esas visitas pueden inflar los informes. La variable `purchaseID` anula la duplicación de métricas cuando más de una visita tiene el mismo ID de compra.

Cuando Adobe reconoce una visita como una compra duplicada, todos los datos de conversión (como eVars y eventos) no se muestran en los informes. En las fuentes de datos, la columna `duplicate_purchase` se establece en `1`.

Los ID de compra se aplican a todos los visitantes y no caducan. Si un visitante establece un ID de compra determinado y un visitante diferente lo establece un año después, se anula la duplicación de la segunda compra.

## ID de compra mediante el SDK web

El ID de compra es [asignado para Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) en el campo XDM `commerce.order.purchaseID`.

## ID de compra con la extensión de Adobe Analytics

No hay un campo específico en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.purchaseID en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.purchaseID` es una cadena que contiene un identificador único para una compra. Se configura en la misma visita que un evento de compra. Utilice únicamente caracteres alfanuméricos para rellenar esta variable.

Esta variable puede almacenar un máximo de 20 bytes. Los valores superiores a 20 bytes se truncan. Si este valor truncado coincide con los valores truncados siguientes, se anularán las duplicaciones de esas visitas.

```js
s.purchaseID = "ABC123";
```

Si utiliza la `digitalData` [capa de datos](../../prepare/data-layer.md):

```js
s.purchaseID = digitalData.transaction.transactionID;
```

>[!CAUTION]
>
>No utilice una función aleatoria para generar un ID de compra.
