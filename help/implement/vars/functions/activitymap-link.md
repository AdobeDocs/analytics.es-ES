---
title: ActivityMap.link
description: Personalice la forma en que Activity Map recopila el vínculo en el que se hizo clic.
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 3a31f80b-dbee-4a45-ac3c-0b8ca198c95a
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 9%

---

# ActivityMap.link

La variable `ActivityMap.link` le permite anular la lógica que Activity Map utiliza para establecer los valores de los vínculos. Esta variable es útil en áreas donde desea tener más control del que proporciona [`ActivityMap.linkExclusions`](../config-vars/activitymap-linkexclusions.md).

>[!CAUTION]
>Esta variable anula completamente la lógica de Activity Map. La configuración de una función de anulación aquí que devuelva valores incorrectos puede causar problemas de recopilación de datos con dimensiones de Activity Map y la superposición de Activity Map.

## Anulación de los valores de los vínculos mediante Web SDK

Puede usar la llamada de retorno [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) para alterar la carga útil de Web SDK o anular el envío de datos.

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
