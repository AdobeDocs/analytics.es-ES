---
title: pageType
description: Determine si la página actual conduce a un error 404.
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 75%

---

# pageType

La variable `pageType` es un indicador que se utiliza para designar las páginas de error en el sitio, como los errores 404. Si esta variable contiene la cadena `errorPage`, rellena la [dimensión](/help/components/dimensions/pages-not-found.md) y la [métrica](/help/components/metrics/pages-not-found.md) “Páginas no encontradas”.

>[!IMPORTANT]
>
>No configure esta variable en páginas que no sean de error.

## Tipo de página que utiliza el SDK web

El canal está asignado a las siguientes variables:

* [Objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.isErrorPage`: este campo XDM es booleano; establézcalo en `true` para marcarlo como página de error o `false` si no es una página de error.
* [Objeto de datos](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageType` - este campo de objeto de datos es una cadena; establézcalo en `"errorPage"` para marcarlo como tal.

## Tipo de página con la extensión de Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.pageType en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.pageType` es una cadena donde el valor `errorPage` es el único válido. Establezca esta variable en este valor en cualquier página de error del sitio, como en páginas de error 404.

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>Utilice una eVar para recopilar el código de error y obtener más información sobre los errores específicos que los visitantes encuentran en el sitio.
