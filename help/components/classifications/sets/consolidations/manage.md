---
title: Administrar consolidaciones de conjuntos de clasificaciones
description: Obtenga información sobre cómo consolidar uno o más conjuntos de clasificaciones en un único conjunto.
exl-id: 0be97ca4-56c3-4642-9347-924812e88e8c
feature: Classifications
source-git-commit: cfa8335008548254786e46dfe634229edad5bd54
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 3%

---

# Administrar consolidaciones de clasificación

Si tiene varios conjuntos de clasificaciones que contienen datos de clasificación similares, puede consolidarlos en uno solo. Al consolidar dos o más conjuntos de clasificaciones, Adobe genera un nuevo conjunto de clasificaciones que contiene todos los datos de clasificación de cada conjunto de clasificaciones individual. Las consolidaciones son útiles cuando se han cargado datos en muchos grupos de informes. O cuando tiene dimensiones que contienen los mismos datos de clasificación y desea combinarlas en un solo flujo de trabajo.

Debe tener acceso de administrador de productos para Adobe Analytics para ver el Administrador de consolidación de conjuntos de clasificaciones.



Para administrar consolidaciones de clasificación:

1. Seleccione **[!UICONTROL Componentes]** en la barra de menús superior de Adobe Analytics y, a continuación, seleccione **[!UICONTROL Conjuntos de clasificaciones]**.
1. En **[!UICONTROL Conjuntos de clasificaciones]**, seleccione la pestaña **[!UICONTROL Consolidaciones]**.


## Administrador de consolidaciones de clasificación

El administrador **[!UICONTROL Conjuntos de clasificaciones - Consolidaciones]** tiene los siguientes elementos de interfaz:

![Conjuntos de clasificaciones - Administrador de consolidaciones](assets/classifications-sets-consolidations.png)



### Lista de consolidaciones de clasificación

La lista ➊ muestra consolidaciones de clasificación que se han creado y validado y que podrían estar consolidándose. La lista tiene las siguientes columnas:

| Columna | Descripción |
|---|---|
| **[!UICONTROL Nombre de consolidación]** | El nombre de la consolidación de conjuntos de clasificaciones. |
| **[!UICONTROL Trabajo actual]** | El trabajo asociado a la consolidación de conjuntos de clasificaciones. |
| **[!UICONTROL Estado]** | El estado de la consolidación de conjuntos de clasificaciones. Los valores posibles son: **[!UICONTROL Creado]**, **[!UICONTROL Cancelado]**, **[!UICONTROL Cancelando]**, **[!UICONTROL Validando]**, **[!UICONTROL Error de validación]**, **[!UICONTROL Validado]**, **[!UICONTROL Comparando]**, **[!UICONTROL Error de comparación]**, **[!UICONTROL Consolidación]**, **[!UICONTROL Enviado]**, **[!UICONTROL Consolidando]**, **[!UICONTROL Error de consolidación]**, **[!UICONTROL Consolidación exitosa]**, **[!UICONTROL Esperando aprobación]**, **[!UICONTROL Finalizando]**, **[!UICONTROL Error]** o **[!UICONTROL Completada]**. |
| **[!UICONTROL Hora de creación]** | La hora de creación de la clasificación define la consolidación. |
| **[!UICONTROL Hora de finalización]** | Hora de finalización de las consolidaciones de clasificación. |


Para cambiar el tamaño de una columna en la lista de consolidación de clasificación, puede:

* Pase el ratón sobre el separador de columnas y arrástrelo hasta el ancho de columna deseado.
* Seleccione ![ChevronDown](/help/assets/icons/ChevronDown.svg) y seleccione **[!UICONTROL Cambiar tamaño de columna]**. Una línea vertical con el botón de cambio de tamaño le permite cambiar el tamaño de la columna al deseado con.

Para ordenar una columna en la lista de consolidación de clasificación

* Seleccione ![cheurón descendente](/help/assets/icons/ChevronDown.svg) y seleccione **[!UICONTROL Orden ascendente]** o **[!UICONTROL Orden descendente]**. Una flecha (↑↓) indica qué columna y cómo se ordena.

### Botones Buscar y

En el área ➋ de la parte superior de la lista de consolidaciones de clasificación, puede:

* Busque ![Buscar](/help/assets/icons/Search.svg) consolidaciones de clasificación. Los resultados se muestran en la lista de consolidaciones de clasificación. Seleccione ![CrossSize200](/help/assets/icons/CrossSize200.svg) para borrar la búsqueda.
* Elimine cualquier filtro que se aplique a la lista de consolidación de conjuntos de clasificaciones. Seleccione ![CrossSize100](/help/assets/icons/CrossSize100.svg) para quitar un filtro.
* Cree una nueva consolidación de conjuntos de clasificaciones. Seleccione ![AgregarCírculo](/help/assets/icons/AddCircle.svg) **[!UICONTROL Nuevo]** para abrir el cuadro de diálogo de consolidación de conjuntos de clasificación y definir una nueva consolidación de conjuntos de clasificación.
* Defina las columnas de la lista de consolidaciones de clasificación. Seleccione ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) y, en el cuadro de diálogo **[!UICONTROL Personalizar tabla]**, seleccione las columnas que se mostrarán debajo de **[!UICONTROL Seleccionar columnas que se mostrarán]**. Seleccione **[!UICONTROL Aplicar]** para aplicar la configuración de columna.


### Barra de acciones

Al seleccionar uno o más conjuntos de clasificaciones en la lista de conjuntos de clasificaciones, aparece una barra de acciones azul ➌. Las siguientes acciones están disponibles en la barra de acciones:

| Icono | Acción | Descripción |
|---|---|---|
| ![Editar](/help/assets/icons/Edit.svg) | **[!UICONTROL Editar]** | [Editar la consolidación de conjuntos de clasificación](process.md#edit-a-consolidation) |
| ![VerDetalles](/help/assets/icons/ViewDetail.svg) | **[!UICONTROL Ver]** | Ver detalles de la consolidación del juego de clasificaciones. Según el estado, puede [aprobar](process.md#approve) o [cancelar](process.md#cancel) la consolidación. |


### Panel Filtro

Seleccione ![Filter](/help/assets/icons/Filter.svg) para mostrar el panel de filtro ➍ que le permite filtrar la lista de consolidaciones de clasificación. Puede filtrar por:

* **[!UICONTROL Estado]**. Seleccione uno de los posibles valores para filtrar la lista de consolidaciones de clasificación según el estado. |
* **[!UICONTROL Hora de finalización]**. Seleccione uno de los posibles valores para filtrar la lista de consolidaciones de clasificación en el momento de finalización.
* **[!UICONTROL Hora de creación]**. Seleccione uno de los posibles valores para filtrar la lista de consolidaciones de clasificación en el momento de finalización.


Seleccione ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Ocultar filtros]** para ocultar el panel Filtros.

Tenga en cuenta que los filtros que se muestran en el panel Filtros reflejan las opciones de las consolidaciones de clasificación cargadas previamente.
