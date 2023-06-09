---
title: Administrador de consolidación de conjuntos de clasificación
description: Consolide uno o varios conjuntos de clasificaciones en uno solo.
source-git-commit: d0e3b28590b24d630a192ee857a7d84c115dc8c1
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 5%

---

# Administrador de consolidaciones de conjuntos de clasificaciones

Si tiene varios conjuntos de clasificaciones que contienen datos similares, puede consolidarlos en uno solo. Cuando se consolidan dos o más conjuntos de clasificaciones, Adobe genera un nuevo conjunto de clasificaciones que contiene todos los datos de clasificación de cada uno de ellos. Las consolidaciones son útiles cuando se han cargado datos en muchos grupos de informes o dimensiones que contienen los mismos datos de clasificación y se desea combinarlos en un solo flujo de trabajo.

**[!UICONTROL Componentes]** > **[!UICONTROL Conjuntos de clasificaciones]** > **[!UICONTROL Consolidación]**

Una vez que se ejecuta una consolidación, se eliminan los conjuntos de clasificaciones originales, sustituyendo al conjunto de clasificaciones consolidado. Clic **[!UICONTROL Añadir]** hasta [Creación de una consolidación](process.md).

## Filtrar conjuntos de clasificaciones

La parte izquierda del Administrador de consolidación de conjuntos de clasificaciones proporciona una configuración de filtro para localizar la consolidación deseada. Al hacer clic en el icono de filtro, se alterna la visibilidad de la configuración del filtro. Puede filtrar las consolidaciones por **[!UICONTROL Estado]**, **[!UICONTROL Hora de finalización]**, o **[!UICONTROL Hora de creación]**.

![Filtros de consolidación del conjunto de clasificaciones](../../assets/classification-set-consolidation-filters.png)

Hay opciones de filtro adicionales disponibles encima de las columnas del Administrador de consolidación de conjuntos de clasificaciones:

* **[!UICONTROL Buscar por título]**: busque consolidaciones por nombre.
* **Mostrar/ocultar columnas**: alternar visibilidad para cualquier columna aparte de [!UICONTROL Nombre].

## Columnas del Administrador de consolidación de conjuntos de clasificaciones

Las siguientes columnas están disponibles en el Administrador de consolidación de conjuntos de clasificaciones:

* **[!UICONTROL Nombre]**: nombre de la consolidación.
* **[!UICONTROL Trabajo actual]**: el trabajo actual. <!-- todo: better description -->
* **[!UICONTROL Estado]**: el estado de la consolidación. <!-- todo: get list of possible statuses -->
* **[!UICONTROL Fecha de creación]**: la fecha y la hora en que se creó la consolidación.
* **[!UICONTROL Fecha de finalización]**: la fecha y la hora en que se completó la consolidación (o falló).
