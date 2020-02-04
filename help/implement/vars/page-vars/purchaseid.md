---
title: purchaseID
description: Anule la duplicación de visitas en función de un identificador de compra único.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# purchaseID

La `purchaseID` variable ayuda a evitar que las visitas que contienen la misma compra inflen informes. Por ejemplo: si un visitante llega a la página de confirmación de compra, normalmente envía a Adobe datos sobre los ingresos generados por la transacción. Si el usuario actualiza esta página varias veces o marca la página para visitarla más adelante, esas visitas pueden inflar los informes. La `purchaseID` variable anula la duplicación de métricas cuando más de una visita tiene la misma ID de compra.

Cuando Adobe reconoce una visita como una compra duplicada, todos los datos de conversión (como eVars y eventos) no se muestran en los informes. En las fuentes de datos, la `duplicate_purchase` columna se establece en `1`.

Las ID de compra se aplican a todos los visitantes y no caducan. Si un visitante establece un ID de compra determinado y un visitante diferente lo establece un año después, se anula la duplicación de la segunda compra.

## ID de compra en Adobe Experience Platform Launch

No hay un campo dedicado en Launch para utilizar esta variable. Utilice el editor de código personalizado, siguiendo la sintaxis de AppMeasurement.

## s.purchaseID en el editor de código personalizado AppMeasurement e Launch

La `s.purchaseID` variable es una cadena que contiene un identificador único para una compra. Se configura en la misma visita que un evento de compra. Utilice únicamente caracteres alfanuméricos para rellenar esta variable.

Esta variable puede almacenar un máximo de 20 bytes; los valores superiores a 20 bytes se truncan. Si este valor truncado coincide con los valores truncados subsiguientes, se anularán las duplicaciones de esas visitas subsiguientes.

```js
s.purchaseID = "ABC123";
```

> [!NOTE] No utilice una función de aleatorización para generar un ID de compra. Adobe recommends using a [data layer](../../prepare/data-layer.md) to store a given purchase ID.
