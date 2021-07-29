---
title: pageType
description: Determine si la página actual conduce a un error 404.
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 83%

---

# pageType

La variable `pageType` es un indicador que se utiliza para designar las páginas de error en el sitio, como los errores 404. Si esta variable contiene la cadena `errorPage`, rellena la dimensión “Páginas no encontradas”.

>[!IMPORTANT]
>
>No configure esta variable en páginas que no sean de error.

## Tipo de página con etiquetas en Adobe Experience Platform

No hay un campo dedicado en la interfaz de usuario de recopilación de datos para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## “s.pageType” en el editor de código personalizado de AppMeasurement y 

La variable `s.pageType` es una cadena donde el valor `errorPage` es el único válido. Establezca esta variable en este valor en cualquier página de error del sitio, como en páginas de error 404.

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>Utilice una eVar para recopilar el código de error y obtener más información sobre los errores específicos que los visitantes encuentran en el sitio.
