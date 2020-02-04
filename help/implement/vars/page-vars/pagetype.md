---
title: pageType
description: Determine si la página actual es un error 404.
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# pageType

La `pageType` variable es un indicador que se utiliza para designar las páginas de error en el sitio, como los errores 404. Si esta variable contiene la cadena `errorPage`, rellena la dimensión &#39;Páginas no encontradas&#39;.

> [!IMPORTANT] No configure esta variable en páginas que no sean de error.

## Tipo de página en Adobe Experience Platform Launch

No hay un campo dedicado en Launch para utilizar esta variable. Utilice el editor de código personalizado, siguiendo la sintaxis de AppMeasurement.

## s.pageType en el editor de código personalizado AppMeasurement e Launch

La `s.pageType` variable es una cadena donde el valor `errorPage` es su único valor válido. Establezca esta variable en este valor en cualquier página de error del sitio, como en 404 páginas.

```js
s.pageType = "errorPage";
```

> [!TIP] Utilice una eVar para recopilar el código de error y obtener más información sobre los errores específicos que los visitantes encuentran en el sitio.
