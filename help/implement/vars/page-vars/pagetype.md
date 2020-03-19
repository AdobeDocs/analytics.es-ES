---
title: pageType
description: Determine si la página actual conduce a un error 404.
translation-type: ht
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# pageType

La variable `pageType` es un indicador que se utiliza para designar las páginas de error en el sitio, como los errores 404. Si esta variable contiene la cadena `errorPage`, rellena la dimensión “Páginas no encontradas”.

> [!IMPORTANT] No configure esta variable en páginas que no sean de error.

## Tipo de página en Adobe Experience Platform Launch

No hay un campo específico en Launch para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## “s.pageType” en el editor de código personalizado de AppMeasurement y Launch

La variable `s.pageType` es una cadena donde el valor `errorPage` es el único válido. Establezca esta variable en este valor en cualquier página de error del sitio, como en páginas de error 404.

```js
s.pageType = "errorPage";
```

> [!TIP] Utilice una eVar para recopilar el código de error y obtener más información sobre los errores específicos que los visitantes encuentran en el sitio.
