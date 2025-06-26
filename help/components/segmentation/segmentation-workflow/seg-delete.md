---
description: Enumera una serie de consideraciones que debe tener en cuenta antes de eliminar segmentos.
title: Eliminar segmentos
feature: Segmentation
exl-id: 434b6fec-1dfa-4375-a9de-d47fad2c64bc
source-git-commit: 80e4a3ba4a5985563fcf02acf06997b4592261e4
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 39%

---

# Eliminar segmentos

Este artículo enumera algunas consideraciones que debe tener en cuenta antes de eliminar segmentos.

Cuando elimine un segmento:

* Los informes programados y los paneles a los que se ha aplicado este segmento siguen funcionando normalmente. Por ejemplo, el segmento o panel siguen utilizando el segmento eliminado.
* Los informes programados no se actualizan cuando edita un segmento con el mismo nombre. Este es un ejemplo: suponga que tiene dos segmentos con el mismo nombre en diferentes grupos de informes:

  | Nombre del segmento | Grupo de informes |
  |---|---|
  | Visitas provenientes de California | mainprod |
  | Visitas provenientes de California | maindev |

  Tiene un marcador que hace referencia al segmento para el grupo de informes [!UICONTROL mainprod]. A continuación, elimine ese segmento porque es un duplicado. El marcador seguirá funcionando, haciendo referencia a la definición del segmento eliminado. Si cambia la definición del segmento para el resto del segmento con el fin de incluir Isla Santa Catalina y Tijuana, el segmento aplicado al marcador no cambiará. El segmento utilizará la definición antigua. Para arreglarlo, actualice el marcador a fin de que haga referencia a la definición nueva. Si no está seguro de si un marcador, tablero o informe programado está utilizando un segmento eliminado, puede cambiar el nombre del resto del segmento para indicar si el marcador lo utiliza.
