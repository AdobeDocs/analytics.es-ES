---
description: Desglose de dimensiones y elementos de dimensión en Analysis Workspace.
keywords: Analysis Workspace
title: Desglose de dimensiones
uuid: 0b888e26-f201-4405-99f9-755b3ee6cd18
feature: Workspace Basics
role: User, Admin
exl-id: 0d26c920-d0d9-4650-9cf0-b67dbc4629e1
source-git-commit: 9f0f17936de2597611728498c5ed82d36fd01d1c
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 63%

---

# Desglose de dimensiones

Desglose de dimensiones y elementos de dimensión en Analysis Workspace.

Desglose los datos ilimitadamente para sus necesidades específicas; genere consultas con métricas, dimensiones, segmentos, líneas de tiempo y otros valores de desglose de análisis relevantes.

1. [Cree un proyecto](/help/analyze/analysis-workspace/home.md) con una tabla de datos.
1. En la tabla de datos, haga clic con el botón secundario en un elemento de línea y seleccione **[!UICONTROL Desglosar]** > *`<item>`*.

   ![Resultado](assets/fa_data_table_actions.png)

   Puede desglosar métricas por elementos de dimensión o segmentos de audiencia entre periodos de tiempo seleccionados. También puede continuar desglosando hasta un nivel más granular.

   >[!NOTE]
   >
   >El número de desgloses de la tabla está limitado a 200 desgloses. Este límite aumentará para la exportación de desgloses.

## Aplicar modelos de atribución a desgloses

Cualquier desglose dentro de una tabla también puede tener aplicado cualquier modelo de atribución. Este modelo de atribución puede ser el mismo o diferente de la columna principal. Por ejemplo, puede analizar Pedidos lineales en su dimensión de Canales de marketing pero aplicar Pedidos en forma de U a los códigos de seguimiento específicos dentro de un Canal. Para editar el modelo de atribución aplicado a un desglose, simplemente sitúe el ratón encima del modelo de desglose y haga clic en **[!UICONTROL Editar]**:

![Configuración del desglose](assets/breakdown_settings.png)

Este es el comportamiento esperado al aplicar modelos de atribución a desgloses o editarlos:

* Si aplica una atribución cuando no existen otras atribuciones, la atribución se aplica a todo el árbol de columnas.

* Si agrega un desglose después de aplicar una atribución, utilizará el valor predeterminado para el desglose dado que se añadió, si esa dimensión tiene un valor predeterminado. De lo contrario, se utiliza el desglose de la columna principal. Algunas dimensiones tienen una asignación predeterminada.  Por ejemplo, [!UICONTROL Tiempo] dimensiones y [!UICONTROL Referente] use [!UICONTROL Mismo contacto]. La variable [!UICONTROL Product] usos de dimensiones [!UICONTROL Último toque]. Otras dimensiones no tienen un valor predeterminado y utilizarán la asignación de columna principal.

* Si ya hay atribuciones en el árbol de columnas, cambiar la atribución solo afecta al que esté editando.

## Vídeos

Adición de dimensiones y métricas al proyecto en Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/30606/?quality=12)

Trabajo con dimensiones en una tabla de forma libre:

>[!VIDEO](https://video.tv.adobe.com/v/40179/?quality=12)

Este es un vídeo sobre los desgloses de dimensión por posición:

>[!VIDEO](https://video.tv.adobe.com/v/24033/?quality=12)
