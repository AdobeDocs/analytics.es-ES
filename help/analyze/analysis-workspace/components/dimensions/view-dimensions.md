---
description: 'null'
title: Vista preliminar de dimensiones
uuid: dd1f87de-2d83-4c6b-b8cd-ce81c741d7a3
translation-type: tm+mt
source-git-commit: b36505c9fd7bf1d2da4d076d6b49298f01ad1cfc

---


# Vista preliminar de dimensiones

Pase el ratón sobre el icono de información (i) situado junto a una dimensión. Muestra los 5 valores principales para dimensiones que no son de tiempo (y 15 para dimensiones de tiempo). Solíamos mantener estos valores estáticos (es decir, los 5 valores elegidos nunca cambiaron).

![](assets/dimension-preview.png)

Ahora, de forma predeterminada, mostramos valores dinámicos en lugar de estáticos, con la opción de convertirlos en valores estáticos. Otras cosas a tener en cuenta:

* A medida que se actualizan los datos, las columnas de dimensiones dinámicas se actualizarán para mostrar los elementos de dimensión 5/15 actuales.
* Una columna de dimensión dinámica que se copia o mueve se convertirá en estática.
* Al pasar el ratón por encima de una columna de dimensión estática verá un icono de bloqueo que indica que la dimensión es estática.

![](assets/dimension_static.png)

## Mostrar los elementos de la dimensión

Al pasar el ratón sobre una dimensión y hacer clic en la flecha derecha gris situada junto a ella, aparece una lista de los elementos de dimensión. Cualquier lista de elementos de dimensión generalmente muestra los elementos principales de los últimos 30 días.

Si se desplaza hacia abajo hasta la parte inferior de la lista, verá un **[!UICONTROL Show Top Items From Last 6 Months]**. Haga clic en esta opción para ver los elementos principales de la dimensión durante los últimos 180 días.
