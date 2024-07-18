---
title: purchaseID
description: Anule la duplicación de visitas en función de un identificador de compra único.
feature: Variables
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
role: Admin, Developer
source-git-commit: 4bd46fd5a9b98bcca67a66c87c9bca67fa00061a
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 73%

---

# purchaseID

La variable `purchaseID` ayuda a evitar que las visitas que contienen la misma compra inflen informes. Por ejemplo: Si un visitante llega a la página de confirmación de compra, normalmente envía a Adobe datos sobre los ingresos generados por la transacción. Si el usuario actualiza esta página varias veces o marca la página para visitarla más adelante, esas visitas pueden inflar los informes. La variable `purchaseID` anula la duplicación de métricas cuando más de una visita tiene el mismo ID de compra.

Cuando Adobe reconoce una visita como una compra duplicada, todos los datos de conversión (como eVars y eventos) no se muestran en los informes. En las fuentes de datos, la columna `duplicate_purchase` se establece en `1`.

Los ID de compra se aplican a todos los visitantes y caducan pasados 37 meses. Si un visitante establece un ID de compra determinado y un visitante diferente lo establece un año después, se anula la duplicación de la segunda compra.

## ID de compra mediante el SDK web

El ID de compra está asignado a las siguientes variables:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.commerce.order.purchaseID`
* [Objeto de datos](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.purchaseID`

## ID de compra con la extensión Adobe Analytics

Puede establecer el ID de compra al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca la lista desplegable [!UICONTROL Extension] en Adobe Analytics y [!UICONTROL Action Type] en [!UICONTROL Set Variables].
6. Busque la sección [!UICONTROL ID de compra].

Puede establecer el ID de compra en un valor o elemento de datos. También puede copiar el valor de otra variable de Analytics.

## &quot;s.purchaseID&quot; en el AppMeasurement y el editor de código personalizado de la extensión de Analytics

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
