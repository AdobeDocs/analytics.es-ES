---
title: ActivityMap.region
description: Personalice la forma en que Activity Map recopila la región en la que se hizo clic.
feature: Appmeasurement Implementation
role: Admin, Developer
exl-id: 9bbdb124-b865-4431-8a98-9814c3f2e65c
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 13%

---

# ActivityMap.region

La variable `ActivityMap.region` le permite invalidar la lógica que utiliza Activity Map para establecer los valores de región. Esta variable es útil en áreas donde desea tener más control del que proporciona [`ActivityMap.regionExclusions`](../config-vars/activitymap-regionexclusions.md).

>[!CAUTION]
>Esta variable anula completamente la lógica de Activity Map. La configuración de una función de anulación aquí que devuelva valores incorrectos puede causar problemas de recopilación de datos con dimensiones de Activity Map y la superposición de Activity Map.

## Omisión de los valores de región mediante Web SDK

Puede usar la llamada de retorno [`OnBeforeLinkClickSend`](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/commands/configure/onbeforelinkclicksend) para alterar la carga útil de Web SDK o anular el envío de datos.

## Anulación de región mediante la extensión de Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## ActivityMap.region en AppMeasurement y el editor de código personalizado de la extensión de Analytics

Asigne esta variable a una función que:

* Recibe el elemento HTML donde se hizo clic; y
* Devuelve un valor de cadena. Este valor de cadena es el valor final usado para la dimensión [Región de Activity Map](/help/components/dimensions/activity-map-region.md).

Si el valor devuelto es [falsy](https://developer.mozilla.org/es-ES/docs/Glossary/Falsy), todas las variables de datos de contexto de Activity Map se borran y no se realiza un seguimiento de los datos del vínculo.

## Ejemplos

Utilice un nombre de etiqueta en minúsculas como región:

```js
s.ActivityMap.region = function(clickedElement) {
  while (clickedElement && (clickedElement = clickedElement.parentNode)) {
    var regionId = clickedElement.tagName;
    if (regionId) {
      return regionId.toLowerCase();
    }
  }
}
```

Utilice nombres de clase específicos como región:

```js
s.ActivityMap.region = function(ele) {
  var className,
  classNames = {
    'header': 1,
    'navbar': 1,
    'left-content': 1,
    'main-content': 1,
    'footer': 1,
  };
  while ((ele && (ele = ele.parentNode))) {
    if ((className = ele.className)) {
      let classes = className.split(' ');
      for (let i = 0; i < classes.length; i++) {
        if (classNames[classes[i]]) {
          return classes[i];
        }
      }
    }
  }
  return "BODY";
}
```
