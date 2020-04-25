---
description: Puede crear segmentos a partir de un punto de contacto, añadir segmentos como punto de contacto y comparar flujos de trabajo clave entre diversos segmentos en Analysis Workspace.
keywords: fallout and segmentation;segments in fallout analysis;compare segments in fallout
title: Aplicación de segmentos en el análisis de abandonos
uuid: e87a33df-160e-4943-8d02-4d6609ae3bb1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Aplicación de segmentos en el análisis de abandonos

Puede crear segmentos a partir de un punto de contacto, añadir segmentos como punto de contacto y comparar flujos de trabajo clave entre diversos segmentos en Analysis Workspace.

>[!IMPORTANT] Los segmentos utilizados como puntos de comprobación de abandonos deben utilizar un contenedor que esté en un nivel inferior al contexto general de la visualización de abandonos. Con los abandonos respectivos a los visitantes, los segmentos utilizados como puntos de comprobación deben ser segmentos basados en visitas o visitas individuales. Con los abandonos respectivos a visitas, los segmentos utilizados como puntos de comprobación deben ser segmentos basados en visitas individuales. Si utiliza una combinación no válida, el resultado de abandonos será del 100%. Se ha añadido una advertencia a la visualización de abandonos que se mostrará cuando añada un segmento incompatible como punto de contacto. Determinadas combinaciones de contenedores de segmentos no válidas producirán diagramas de abandonos no válidos, como:

* Cuando se usa un segmento basado en visitantes como punto de contacto dentro de una visualización de abandonos de visitantes.
* Cuando se usa un segmento basado en visitantes como punto de contacto dentro de una visualización de abandonos de visitas.
* Cuando se usa un segmento basado en visitas como punto de contacto dentro de una visualización de abandonos de visitas.

## Creación de segmentos a partir de un punto de contacto {#section_915E8FBF35CD4F34828F860C1CCC2272}

1. Cree un segmento a partir de un punto de contacto específico en el que esté especialmente interesado y que pueda ser útil para su aplicación en otros informes. Para ello, haga clic con el botón derecho en el punto de contacto y seleccione **[!UICONTROL Create segment from touchpoint]**.

   ![](assets/segment-from-touchpoint.png)

   Cuando el Generador de segmentos se abre, ya contiene el segmento secuencial creado previamente que concuerda con el punto de contacto seleccionado:

   ![](assets/segment-builder.png)

1. Ponga un título y una descripción al segmento y guárdelo.

   Ahora puede utilizar este segmento en cualquier informe que desee.

## Añadir un segmento como punto de contacto {#section_17611C1A07444BE891DC21EE8FC03EFC}

Si desea ver, por ejemplo, la tendencia de los usuarios de Estados Unidos y cómo afectan a las visitas en el orden previsto, solo tiene que arrastrar el segmento correspondiente a la visita en el orden previsto:

![](assets/segment-touchpoint.png)

O puede crear un punto de contacto AND arrastrando el segmento de usuarios de Estados Unidos a otro punto de comprobación.

## Comparar segmentos en abandonos {#section_E0B761A69B1545908B52E05379277B56}

Puede comparar una cantidad ilimitada de segmentos en la visualización de visitas en el orden previsto.

1. Select the segments you want to compare from the [!UICONTROL Segments] rail on the left. En nuestro ejemplo, hemos seleccionado 2 segmentos: usuarios de EE. UU. y usuarios fuera de EE. UU.
1. Arrástrelos a la zona de colocación de Segmento en la parte superior.

   ![](assets/segment-drop.png)

1. Opcional: puede mantener “Todas las visitas” como el contenedor predeterminado o eliminarlo.

   ![](assets/seg-compare.png)

1. Ahora puede comparar las visitas en el orden previsto de los dos segmentos como, por ejemplo, cuando un segmento supera a otro u otra información.
