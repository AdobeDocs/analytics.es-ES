---
title: Uso de segmentos en Report Builder en Adobe Analytics
description: Describe cómo utilizar segmentos en Report Builder para Adobe Analytics
role: User
feature: Report Builder
type: Documentation
solution: Analytics
exl-id: 2691fde0-59c6-45a7-80a5-8e5e221adce2
source-git-commit: 2cb8f72a37699aa45135c9d26686f93ee20f20d7
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 4%

---

# Trabajo con segmentos en el Report Builder

Puede aplicar segmentos cuando cree un nuevo bloque de datos o cuando seleccione la opción **Editar bloque de datos** en el panel COMANDOS.

## Aplicación de segmentos a un bloque de datos

Para aplicar un segmento a todo el bloque de datos, haga doble clic en un segmento o arrastre y suelte los filtros de la lista de componentes en la sección Segmentos de la tabla.

## Aplicación de segmentos a métricas individuales

Para aplicar segmentos a métricas individuales, arrastre y suelte un segmento en una métrica de la tabla. También puede hacer clic en el icono **...** a la derecha de una métrica en el panel Tabla y, a continuación, seleccionar **[!UICONTROL Métrica del segmento]**. Para ver los segmentos aplicados, pase el ratón sobre una métrica o selecciónela en el panel Tabla. Las métricas con segmentos aplicados muestran un icono de filtro.

![La pestaña Segmentos muestra las métricas.](./assets/filter_by.png)

## Edición rápida de segmentos

Puede utilizar el panel de edición rápida para añadir, quitar o reemplazar segmentos para bloques de datos existentes.

Cuando se selecciona un rango de celdas en la hoja de cálculo, el vínculo **[!UICONTROL Segmentos]** del panel Edición rápida muestra una lista resumida de los segmentos utilizados por los bloques de datos de esa selección.

Para editar segmentos con el panel Edición rápida

1. Seleccione un rango de celdas de uno o varios bloques de datos.

   ![Panel de segmentos de edición rápida que muestra las opciones de segmentos para los grupos de informes, el intervalo de fechas y los segmentos.](./assets/select_multiple_dbs.png)

1. Haga clic en el vínculo debajo de **[!UICONTROL Segmentos]** para iniciar el panel Edición rápida - Filtros.

   ![el panel Segmentos muestra el campo Agregar segmentos y las listas de Segmentos aplicados.](./assets/quick_edit_filters.png)

### Agregar o quitar un segmento

Puede añadir o quitar segmentos mediante las opciones Añadir/Quitar.

1. Seleccione la ficha **[!UICONTROL Agregar/Quitar]** en el panel Edición rápida - Segmentos.

   Todos los segmentos aplicados a los bloques de datos seleccionados se enumeran en el panel Edición rápida - Segmentos. Los segmentos aplicados a todos los bloques de datos de la selección se enumeran en el encabezado **[!UICONTROL Aplicado a todos los bloques de datos seleccionados]**. Los segmentos aplicados a algunos bloques de datos, pero no a todos, se enumeran en el encabezado **[!UICONTROL Aplicado a uno o más bloques de datos seleccionados]**.

   Cuando hay varios segmentos presentes en los bloques de datos seleccionados, puede buscar segmentos específicos mediante el campo de búsqueda **[!UICONTROL Agregar filtro]**.

   ![Campo Agregar segmentos.](./assets/add_filter.png)

1. Para agregar segmentos, selecciónelos en el menú desplegable **[!UICONTROL Agregar segmento]**.

   La lista de segmentos en los que se puede buscar incluye todos los segmentos accesibles para los grupos de informes que están presentes en uno o más de los bloques de datos seleccionados, así como todos los segmentos disponibles globalmente en la organización.

   Al añadir un segmento, se aplica el segmento a todos los bloques de datos de la selección.

1. Para quitar segmentos, haga clic en el icono de eliminación **x** a la derecha de los segmentos en la lista **[!UICONTROL Segmentos aplicados]**.

1. Haga clic en **[!UICONTROL Aplicar]** para guardar los cambios y volver al panel central.

   El Report Builder muestra un mensaje para confirmar los cambios aplicados en el segmento.

### Reemplazo de segmentos

Puede reemplazar un segmento existente por otro para cambiar la forma en que se segmentan los datos.

1. Seleccione la ficha **[!UICONTROL Reemplazar]** en el panel Edición rápida - Segmento.

   ![Seleccione la ficha Reemplazar.](./assets/replace_filter.png)

1. Utilice el campo de búsqueda **[!UICONTROL Lista de búsqueda]** para localizar segmentos específicos.

1. Elija uno o varios segmentos que desee reemplazar.

1. Busque uno o más segmentos en el campo Reemplazar con.

   Al seleccionar un filtro, se añade a la lista **[!UICONTROL Reemplazar con]**...

1. Haga clic en **[!UICONTROL Aplicar]**.

   El Report Builder actualiza la lista de segmentos para reflejar el reemplazo.

### Definir segmentos de bloque de datos de la celda

Los bloques de datos pueden hacer referencia a segmentos desde una celda. Varios bloques de datos pueden hacer referencia a la misma celda para segmentos, lo que le permite cambiar fácilmente los segmentos para varios bloques de datos a la vez.

Para aplicar segmentos desde una celda

1. Vaya al paso 2 en el proceso de creación o edición del bloque de datos. Ver [Crear un bloque de datos](./create-a-data-block.md).
1. Haga clic en la ficha **[!UICONTROL Segmentos]** para definir los filtros.
1. Haga clic en **[!UICONTROL Crear segmento desde celda]**.

   ![Crear segmento a partir del icono de celda.](./assets/create-filter-from-cell.png)

1. Seleccione la celda desde la que desea que los bloques de datos hagan referencia a un segmento.

1. Agregue la opción de segmento que desee agregar a la celda haciendo doble clic en el segmento o arrastrándola y soltándola en la sección **[!UICONTROL Segmentos incluidos]**.

   Nota: Solo se puede seleccionar una opción para la celda determinada al mismo tiempo.

   ![El segmento Agregar de la ventana de celda que muestra los filtros incluidos.](./assets/select-filters.png)

1. Haga clic en **[!UICONTROL Aplicar]** para crear la celda de referencia.

1. En la pestaña **[!UICONTROL Segmentos]**, agregue los segmentos de celda de referencia recién creados al bloque de datos.

   ![Ficha Segmentos que muestra el segmento Hoja1!J1(Todos los datos) agregado a la tabla.](./assets/reference-cell-filter.png)

1. Haga clic en **[!UICONTROL Finalizar]**.

   Ahora otros bloques de datos pueden hacer referencia a esta celda en sus segmentos. Para aplicar la celda de referencia como un segmento a otros bloques de datos, simplemente añada la referencia de celda a sus segmentos desde la pestaña Segments.

#### Utilice la celda de referencia para cambiar los segmentos del bloque de datos

1. Seleccione la celda de referencia en la hoja de cálculo.

1. Haga clic en el vínculo bajo **[!UICONTROL Segmentos de celda]** en el menú Edición rápida.

   ![Segmentos del vínculo de celda que muestra Sheet1!J1 (Todos los datos)](./assets/filters-from-cell-link.png)

1. Seleccione el segmento en el menú desplegable.

   ![Menú desplegable de segmentos](./assets/filter-drop-down.png)

1. Haga clic en **[!UICONTROL Aplicar]**.
