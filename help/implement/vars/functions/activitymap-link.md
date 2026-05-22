---
title: ActivityMap.link
description: Personalice la forma en que Activity Map recopila el vínculo en el que se hizo clic.
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 3a31f80b-dbee-4a45-ac3c-0b8ca198c95a
TQID: 'https://experienceleague.adobe.com/5NCARDGth07l5vixudVzLrE7FVrh82PS4xNrJ61gnow'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 308
ht-degree: 10%

---

# ActivityMap.link

La variable `ActivityMap.link` le permite anular la lógica que Activity Map utiliza para establecer los valores de los vínculos. Esta variable es útil en áreas donde desea tener más control del que proporciona [`ActivityMap.linkExclusions`](../config-vars/activitymap-linkexclusions.md).

>[!CAUTION]
>Esta variable anula completamente la lógica de Activity Map. La configuración de una función de anulación aquí que devuelva valores incorrectos puede causar problemas de recopilación de datos con dimensiones de Activity Map y la superposición de Activity Map.

## Anulación de los valores de los vínculos mediante Web SDK

Puede usar la llamada de retorno [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) para alterar la carga útil de Web SDK o anular el envío de datos.

## Anulación de vínculos con la extensión de Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## ActivityMap.link en AppMeasurement y el editor de código personalizado de la extensión de Analytics

Asigne esta variable a una función que:

* Recibe el elemento HTML donde se hizo clic; y
* Devuelve un valor de cadena. Este valor de cadena es el valor final usado para la dimensión [Activity Map Link](/help/components/dimensions/activity-map-link.md).

Si el valor devuelto es [falsy](https://developer.mozilla.org/es-ES/docs/Glossary/Falsy), todas las variables de datos de contexto de Activity Map se borran y no se realiza un seguimiento de los datos del vínculo.

## Ejemplos

Usar solamente el atributo title de `<a>` etiquetas. Si el atributo del título no está presente, no se realiza el seguimiento del vínculo.

```js
s.ActivityMap.link = function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

Devuelva el nombre del vínculo establecido manualmente en `s.tl`, si existe; de lo contrario, devuelva la dirección URL del vínculo.

```js
s.ActivityMap.link = function(ele, linkName) {
  if (linkName) {
    return linkName;
  }
  if (ele && ele.tagName == 'A' && ele.href) {
    return ele.href;
  }
}
```

En lugar de reemplazar completamente la lógica de vínculo predeterminada, puede modificarla condicionalmente.

```html
<script>
  // Copy the original link function
  var originalLinkFunction = s.ActivityMap.link;
  // Return the link name from s.tl, a modified activity map value, or the original activity map value
  s.ActivityMap.link = function(element,linkName)
  {
    return linkName || customFunction(element) || originalLinkFunction(element,linkName);
  };
</script>

<button type="button" onclick="s.tl(this,'o',customFunction(this)">Add To Cart</button>
```

1. Si se pasa `linkName`, `tl()` llamó al método. Devuelve lo que `tl()` pasó como `linkName`.
2. Cuando Activity Map llama a `linkName`, nunca se pasa, así que llame a `customFunction()` con el elemento de vínculo. Puede utilizar cualquier función personalizada que desee para devolver un valor.
3. Si ninguno de los valores devueltos anteriores, utilice el nombre del vínculo que normalmente se recopila como reserva.
