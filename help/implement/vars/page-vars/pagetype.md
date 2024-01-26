---
title: pageType
description: Determine si la página actual conduce a un error 404.
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 100%

---

# pageType

La variable `pageType` es un indicador que se utiliza para designar las páginas de error en el sitio, como los errores 404. Si esta variable contiene la cadena `errorPage`, rellena la [dimensión](/help/components/dimensions/pages-not-found.md) y la [métrica](/help/components/metrics/pages-not-found.md) “Páginas no encontradas”.

>[!IMPORTANT]
>
>No configure esta variable en páginas que no sean de error.

## Tipo de página que utiliza el SDK web

El tipo de página está [asignado para Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=es) en el campo XDM `web.webPageDetails.isErrorPage`. Este campo XDM es booleano; configúrelo como `true` para marcarla como página de error, o `false` si no es una página de error. Adobe traduce automáticamente el booleano al valor de cadena `errorPage` cuando se envía a un grupo de informes de Analytics.

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
