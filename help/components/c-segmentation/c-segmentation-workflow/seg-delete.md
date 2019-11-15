---
description: Enumera una serie de consideraciones que debe tener en cuenta antes de eliminar segmentos.
solution: Analytics
title: Eliminar segmentos
topic: Segments
uuid: cb6db6ad-f400-4633-900a-8a02dcfccf2c
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Eliminar segmentos

Enumera una serie de consideraciones que debe tener en cuenta antes de eliminar segmentos.

Cuando elimina un segmento:

* Los informes programados y los paneles a los que se ha aplicado dicho segmento siguen funcionando normalmente, es decir, el informe o panel siguen utilizando el segmento eliminado.
* Los informes programados no se actualizan cuando edita un segmento con el mismo nombre. Por ejemplo, suponga que tiene dos segmentos con el mismo nombre en diferentes grupos de informes:

   ![](assets/duplicate_seg_names.png)

   Tiene un marcador que hace referencia al segmento para el grupo de informes mainprod. Luego elimina ese segmento porque es un duplicado. El marcador seguirá funcionando, haciendo referencia a la definición del segmento eliminado. Si cambia la definición del segmento para el resto del segmento con el fin de incluir Isla Santa Catalina y Tijuana, el segmento aplicado al marcador no cambiará. Utilizará la definición antigua. Para arreglarlo, actualice el marcador a fin de que haga referencia a la definición nueva. Si no está seguro de si un marcador, tablero o informe programado está usando un segmento eliminado, puede cambiar el nombre del segmento restante para que quede más claro si el marcador está usando el segmento restante.

## Edit Embedded Deleted Segments in Ad Hoc Analysis {#section_976D601DBD2244E38B0A0222E31D2610}

Ahora, Análisis específicos le permite editar segmentos eliminados incrustados dentro del [Creador de métricas calculadas](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/) y realizar la operación "Guardar como" en el segmento.

Sin embargo, cualquier otro segmento eliminado que haga referencia al segmento eliminado permanecerá sin cambios.
