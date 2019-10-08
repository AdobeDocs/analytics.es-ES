---
description: Para el evento purchase, se usan variables de Analytics para capturar información específica sobre las compras. La variable s.purchaseID se usa para serializar (anular la duplicación) el evento.
keywords: Implementación de análisis
seo-description: Para el evento purchase, se usan variables de Analytics para capturar información específica sobre las compras. La variable s.purchaseID se usa para serializar (anular la duplicación) el evento.
seo-title: Eventos Purchase
solution: Analytics
title: Eventos Purchase
topic: Desarrollador e implementación
uuid: d90cdec7-7397-445a-84e5-31014f7ff875
translation-type: tm+mt
source-git-commit: e21bb18dd0d0eb13222c655091c3a87939a0351d

---


# Eventos Purchase

Para el evento purchase, se usan variables de Analytics para capturar información específica sobre las compras. La variable `s.purchaseID` se usa para serializar (anular la duplicación) el evento.

Si se llama a un evento de compra sin la variable `purchaseID`, automáticamente se genera una variable única basada en las variables `s.products` y `s.events`. Este ID de compra generado automáticamente se almacena localmente como un valor de cookie dentro del explorador del visitante y no se envía a Adobe. Por otro lado, los ID de compra definidos manualmente se envían a Adobe. Las últimas cinco compras realizadas por un visitante (con o sin ID de compra) se almacenan en la cookie local.

Cuando un visitante realiza cualquier compra, se realizan las siguientes comprobaciones:

* ¿El la ID de compra coincide con cualquiera de los cinco valores de cookie? En caso afirmativo, la solicitud de imagen se considera una compra duplicada. En el informe no aparece ninguna variable de conversión y tampoco el evento de compra.
* Si `s.purchaseID` se define, ¿coincide con algún valor ya recopilado en el grupo de informes? En caso afirmativo, la solicitud de imagen se considera una compra duplicada. En el informe no aparece ninguna variable de conversión y tampoco el evento de compra.

Se puede utilizar código del lado del servidor para generar el número único (valor alfanumérico) incrustado en el código fuente HTML. Con este fin normalmente se usa la ID de pedido o un valor alfanumérico similar. Este valor no debe cambiar si el usuario actualiza la página.

## Sintaxis

```js
s.purchaseID="12345678";
```

## Ejemplos

```js
s.products="Footwear;Hiking Boots;1;170.00";
s.purchaseID="12345678";
s.events="purchase";
```

## Notas adicionales

* No utilice una función de aleatorización de JavaScript para generar un número que genere números únicos cada vez que se cargue la página. Adobe recomienda utilizar una capa de datos para almacenar un ID de compra determinado.
* Los identificadores únicos son aplicables a todos los usuarios en todas las sesiones. Asegúrese de que todos los ID de compra sean verdaderamente únicos.
* Los valores válidos son valores alfanuméricos de hasta 20 caracteres de longitud.
* La variable `s.purchaseID``s.events` serializa todos los eventos que se pasan en la variable   y anula los valores de serialización de eventos. No utilice la serialización [!UICONTROL de] eventos para ningún evento si la `s.purchaseID` variable se utiliza en la página actual.
* If the `s.purchaseID` variable is left blank, each instance of the purchase event, even page reloads, is counted.
