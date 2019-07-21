---
description: 'null'
seo-description: 'null'
seo-title: Información general de paneles
title: Información general de paneles
uuid: 480700 e 6-332 e -44 f 2-a 486-e 3 d 1852 cddbc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Información general de paneles

Un panel es una colección de tablas y visualizaciones. Puede acceder a los paneles desde el icono que hay en la parte superior izquierda de Workspace. Los paneles son útiles si desea organizar sus proyectos por periodos de tiempo, unidades de negocio, geografía, etcétera. En Analysis Workspace dispone de estos cuatro tipos de panel: panel en blanco, panel atribución, panel improvisado y panel de comparación de segmentos.

Los paneles en blanco e improvisado son puntos de inicio del análisis, mientras que los de Attribution IQ y comparación de segmentos se prestan a análisis más avanzados. También hemos agregado un botón de panel “+” para que pueda añadir paneles en blanco en cualquier momento.

El panel inicial predeterminado es el improvisado, pero también puede convertir el [panel en blanco](../../../analyze/analysis-workspace/c-panels/blank-panel.md#concept_B0AD924A792F4166B13448AC253CE7E2) en el panel predeterminado.

## Filtros desplegables en los paneles {#section_D2828EEDD52944528E87F470EAB581CF}

La zona de colocación del panel tiene capacidades de filtrado desplegables. Estos filtros le permiten interactuar con los datos del proyecto de manera controlada, de modo que pueda realizar análisis en profundidad, simplificar los proyectos y compartir perspectivas con otros.

Aquí tiene un ejemplo de proyecto simplificado: suponga que existen varias versiones de un proyecto/panel para proporcionar informes de un país en concreto. Ahora puede contraer estos proyectos/paneles en un solo panel y agregar una lista desplegable de países en vez de filtrar por distintos conjuntos de datos.

![](assets/dropdowns.png)

Recuerde:

* Puede incluir múltiples componentes (o elementos de dimensión) y después cambiar entre ellos mediante un menú desplegable para filtrar el contenido del panel.
* También puede crear varias listas desplegables en un mismo panel.
* Puede personalizar el título de la lista desplegable haciendo clic en él y modificándolo, o bien puede eliminarlo haciendo clic en la X que hay al lado.
* Puede crear filtros desplegables utilizando cualquier tipo de componente: dimensiones, intervalos de fechas, segmentos y métricas. Tenga en cuenta que los intervalos de fechas desplegables siempre anulan los intervalos de fechas del panel.
* Se mantienen los colores de los componentes del carril izquierdo: amarillo para los desplegables de elementos de dimensión, verde para las métricas, azul para los segmentos y morado para los intervalos de fechas.
* La zona de colocación seguirá creando segmentos en el nivel de visita para los elementos arrastrados como segmentos. Puede modificarlos del modo habitual: haga clic en el icono de información (i) junto al segmento, haga clic en el icono de edición con forma de lápiz y, por último, modifique el segmento en el Generador de segmentos.

**Para crear y utilizar filtros desplegables:**

1. Select any items from the left rail and, **while holding down the  key**, drop them into the panel drop zone.

   ![](assets/create_dropdown.png)

   De este modo, los componentes se convierten en una lista desplegable, no en un segmento. (También puede agregar segmentos sin mantener pulsada la tecla).

   ![](assets/dropdown.png)

1. Seleccione una de las opciones desplegables para cambiar los datos en el panel de abajo. (You can also choose to not filter any of the panel data by selecting **[!UICONTROL No filter]**.)
1. Por ejemplo, si también quisiera dividir los datos por canal de marketing, podría agregar otra lista desplegable llamada “Canal de marketing”:

   ![](assets/mc_dropdown.png)

