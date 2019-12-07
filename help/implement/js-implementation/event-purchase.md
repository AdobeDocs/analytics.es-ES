---
description: Para el evento purchase, se usan variables de Analytics para capturar información específica sobre las compras. La variable s.purchaseID se usa para serializar (anular la duplicación) el evento.
keywords: Analytics Implementation
title: Eventos Purchase
topic: Developer and implementation
uuid: d90cdec7-7397-445a-84e5-31014f7ff875
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Eventos Purchase

Para el evento purchase, se usan variables de Analytics para capturar información específica sobre las compras. La variable `s.purchaseID` se usa para serializar (anular la duplicación) el evento.

Si se pasa una visita con un evento de compra sin un ID de compra, Adobe Analytics utiliza la información de la visita (s.purchase y s.events) para crear un "ID de compra temporal". Esta ID de compra temporal solo se aplica al visitante de la visita. Los 5 ID de compra temporales anteriores se almacenan para cada ID de visitante (por grupo de informes).

Cuando un visitante realiza cualquier compra, se realizan las siguientes comprobaciones:

* ¿El el ID de compra temporal coincide con cualquiera de los últimos cinco ID de compra temporal almacenados? En caso afirmativo, la solicitud de imagen se considera una compra duplicada. En el informe no aparece ninguna variable de conversión y tampoco el evento de compra.
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
