---
description: Para el evento purchase, se usan variables de Analytics para capturar información específica sobre las compras. La variable s.purchaseID se usa para serializar (anular la duplicación) el evento.
keywords: Implementación de Analytics
seo-description: Para el evento purchase, se usan variables de Analytics para capturar información específica sobre las compras. La variable s.purchaseID se usa para serializar (anular la duplicación) el evento.
seo-title: Eventos de compra
solution: Analytics
title: Eventos de compra
topic: Desarrollador e implementación
uuid: d 90 cdec 7-7397-445 a -84 e 5-31014 f 7 ff 875
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Eventos de compra

Para el evento purchase, se usan variables de Analytics para capturar información específica sobre las compras. La variable s.purchaseID se usa para serializar (anular la duplicación) el evento.

The *`purchaseID`* is limited to 20 characters. La variable *`purchaseID`* serializa todos los eventos que se pasan en la variable [!UICONTROL s.events] y anula los valores de serialización de eventos. If *`purchaseID`* is left blank, each instance of the purchase event, even page reloads, is counted.

Si se llama a un evento de compra sin la variable *`purchaseID`*, automáticamente se genera una variable única basada en las variables *`s.products`* y *`s.events`.* La variable *`purchaseID`generada de forma automática se almacena localmente en el explorador del visitante como un valor de cookie y no se envía a ninguna tabla de grupo de informes.* Manually defined *`purchaseID`*s on the other hand are sent to a back-end table within the report suite. The last five purchases made by a visitor (with or without *`purchaseID`*) are stored in the local cookie.

Cuando un visitante realiza cualquier compra, se realizan las siguientes comprobaciones:

* ¿El *`purchaseID`* coincide con alguno de los cinco valores de cookies? En caso afirmativo, la solicitud de imagen se considera una compra duplicada. En el informe no aparece ninguna variable de conversión y tampoco el evento de compra.
* If *`purchaseID`* is defined, does it match any value in the report suite's back-end table? En caso afirmativo, la solicitud de imagen se considera una compra duplicada. En el informe no aparece ninguna variable de conversión y tampoco el evento de compra.
* Si la variable *`purchaseID`* es única tanto para los últimos 5 valores almacenados en la cookie como para la tabla *`purchaseID`del grupo de informes, la solicitud de imagen también se considera única y se incluye en el informe.* Por ejemplo, si las cinco compras ya se han incluido en la cookie local, se sobrescribe la más antigua.

Se puede utilizar código del lado del servidor para generar el número único (valor alfanumérico) incrustado en el código fuente HTML. Con este fin normalmente se usa la ID de pedido o un valor alfanumérico similar. Este valor no debe cambiar si el usuario actualiza la página. El siguiente es un ejemplo breve (observe el código *`purchaseID`* en negrita):

## Sintaxis {#section_4FBF138093BD41F59885D2ACC429FF5B}

```js
s.products="Category;ProductName;Qty;total_price [,Category2;ProductName2;Qty;total_price]" 
s.state="XX" 
s.zip="00000" 
 
<b>s.purchaseID="<%=getPurchaseID()%>"</b> 
s.events="purchase" 
```

## Ejemplos {#section_2CBA9B6386A146C0BEF375E1B55687BC}

```js
s.products="Footwear;Hiking Boots (1234);1;170.00" 
s.state="UT" 
s.zip="84097" 
s.purchaseID="12341234" 
s.events="purchase"
```

## Notas adicionales {#section_5A0590B8FD4F40DC89776F55ED9DE668}

* Asegúrese de utilizar código del lado del servidor para generar el identificador único para el evento. No utilice una función de aleatorización JavaScript para generar un número, que genera número cada vez que se carga la página (se contabiliza cada [!UICONTROL instancia]/[!UICONTROL vista de página]).

* Los identificadores únicos son aplicables a todos los usuarios en todas las sesiones. Por lo tanto, asegúrese de que el identificador sea único entre usuarios y sesiones. Por ejemplo, si la ID de pedido se repite después de 30 días, anexe la fecha del pedido para que la [!UICONTROL ID de pedido] sea suficientemente única.
* El valor de serialización puede ser alfanumérico con una longitud de hasta 20 caracteres. Estas limitaciones son idénticas a las de [!UICONTROL s.purchaseID] (reemplace s. por s_ para el código G).
* La variable [!UICONTROL s.purchaseID] serializa todos los eventos que se pasan en la variable [!UICONTROL s.events] y anula los valores de serialización de eventos. No use la [!UICONTROL serialización de eventos] para ningún evento si se usa la variable [!UICONTROL s.purchaseID] en la página actual (reemplace s. por s_ para el código G).

