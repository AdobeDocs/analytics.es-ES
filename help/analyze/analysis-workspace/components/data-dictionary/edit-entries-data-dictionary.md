---
description: El diccionario de datos de Analysis Workspace permite a los usuarios catalogar y seguir los distintos componentes de Analysis Workspace, incluido su uso previsto, cuáles están aprobados, cuáles son duplicados, etc.
title: Edición de entradas en el diccionario de datos
feature: Components
role: Admin
source-git-commit: 7e105b4cd22187411dedd663080703e6daec91f5
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 63%

---

# Edición de entradas de componentes en el diccionario de datos

{{release-limited-testing}}

Los administradores de Analytics pueden editar entradas de componentes en el diccionario de datos de un grupo de informes determinado. Todos los usuarios del grupo de informes pueden ver los cambios realizados.

Para editar un componente en el diccionario de datos:

1. Vaya al proyecto de Analysis Workspace que contiene el componente que desea editar.

1. Seleccione el icono del **Diccionario de datos** en el carril izquierdo de Analysis Workspace. (Las formas alternativas de acceder al diccionario de datos se describen en “Acceso al diccionario de datos” en [Información general del diccionario de datos](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md)).

   Se muestra la ventana Diccionario de datos.

   ![Vista de administrador del diccionario de datos](assets/data-dictionary-admin.png)

1. Asegúrese de que el grupo de informes correcto está seleccionado en el menú desplegable. De forma predeterminada, se muestra el grupo de informes en el que ya se encuentra.

1. (Opcional) En el campo de búsqueda, empiece a escribir el nombre del componente que desea editar.

   Los iconos se muestran junto a los nombres de los componentes para indicar el tipo de componente:

   | Icono | Significado |
   |---------|----------|
   | ![Dimension](assets/dimension-icon.png) | Indica una **dimensión**. Los Dimension son proporcionados por Adobe. Las dimensiones existentes no se pueden modificar y no se pueden crear nuevas dimensiones. |
   | ![Icono de métrica](assets/default-metric-icon.png) | Indica una **métrica estándar** (no calculado). Las métricas estándar las proporciona el Adobe y no se pueden modificar. |
   | ![Icono de Adobe](assets/default-calc-metric-icon.png) | Indica una **plantilla de métrica calculada** o **plantilla de segmento**. Estos componentes se proporcionan mediante Adobe y no se pueden modificar. |
   | ![Icono de calculadora](assets/calculated-metric-icon-created.png) | Indica una **métrica calculada** creado por un administrador de Analytics de su organización. |
   | ![Icono de Segmento](assets/segment-icon.png) | Indica una **segmento**. Pueden ser segmentos proporcionados por un Adobe o creados por un administrador de Analytics de su organización. |
   | ![Icono de intervalo de fechas](assets/date-range-icon.png) | Indica una **intervalo de fechas**. Pueden ser intervalos de fechas proporcionados por el Adobe o creados por un administrador de Analytics de su organización. |

{{dd-filter-criteria}}

1. En la lista de componentes, seleccione el componente que desea editar.

1. Seleccione el icono **Editar** ![icono Editar del diccionario de datos](assets/data-dictionary-edit-icon.png) junto al nombre del componente.

1. Edite cualquiera de la siguiente información acerca del componente:

   {{dd-component-information}}

1. Haga clic en el icono **Guardar** ![icono Guardar del diccionario de datos](assets/data-dictionary-save-icon.png) para guardar los cambios.
