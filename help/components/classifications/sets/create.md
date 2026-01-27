---
title: Crear conjuntos de clasificaciones
description: Obtenga información sobre los campos disponibles y las descripciones al crear un conjunto de clasificaciones.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
source-git-commit: d5e1432569516d13d2de30a2cb30cebb067ab783
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 3%

---

# Creación y edición de conjuntos de clasificaciones

Usted [crea](#create-a-classification-set) y [edita](#edit-a-classification-set) conjuntos de clasificaciones desde el administrador de conjuntos de clasificaciones.

## Crear un conjunto de clasificación

Para crear un conjunto de clasificaciones:

1. Seleccione **[!UICONTROL Componentes]** en la barra de menús superior de Adobe Analytics y, a continuación, seleccione **[!UICONTROL Conjuntos de clasificaciones]**.
1. En **[!UICONTROL Conjuntos de clasificaciones]**, seleccione la pestaña **[!UICONTROL Conjuntos de clasificaciones]**.
1. Seleccione ![AgregarCírculo](/help/assets/icons/AddCircle.svg) **[!UICONTROL Nuevo]**.
1. En el diálogo **[!UICONTROL Agregar nuevo conjunto de clasificaciones]**:

   ![Conjuntos de clasificaciones: agregar nuevo conjunto de clasificaciones](assets/classifications-sets-new.png)

   1. Escriba un **[!UICONTROL Nombre]**. Por ejemplo: `Classification Set Example`.
   1. Escriba una **[!UICONTROL descripción (opcional)]**. Por ejemplo, `Example classification set`.
   1. Escriba una o más direcciones de correo electrónico (separadas por comas) en **[!UICONTROL Notificar problemas]**. Se envían notificaciones por correo electrónico a estos usuarios sobre problemas.
   1. Seleccione el **[!UICONTROL tipo]** del conjunto de clasificaciones. Los tipos posibles son:
      * **[!UICONTROL Principal]**. Un conjunto de clasificaciones principal se aplica a las dimensiones recopiladas en Adobe Analytics. Las clasificaciones principales permiten agrupar (clasificar) los valores de dimensión granulares en niveles de datos más significativos. Por ejemplo, es posible que desee agrupar palabras clave de búsqueda interna en categorías de búsqueda interna para comprender los temas de los datos de búsqueda. O bien, clasifique los SKU de productos por color o categoría.
         * Escriba una o más **[!UICONTROL Suscripciones]**.  Puede definir varias combinaciones de **[!UICONTROL Grupo de informes]** y **[!UICONTROL Dimension]** en un conjunto de clasificaciones.

         * Seleccione ![CrossSize400](/help/assets/icons/CrossSize400.svg) para eliminar una combinación de **[!UICONTROL Grupo de informes]** y **[!UICONTROL Dimension clave]**.

        Si agrega una combinación de **[!UICONTROL Grupo de informes]** y **[!UICONTROL Dimension de claves]** que ya existe en otro conjunto de clasificaciones, se mostrará un mensaje de color rojo.
Puedes realizar lo siguiente:
         * Seleccione **[!UICONTROL Agregar a]** existente para abrir el otro conjunto de clasificaciones y [agregar clasificaciones al esquema](manage/schema.md) para ese otro conjunto de clasificaciones.
         * Cambie **[!UICONTROL Report Suite]** y **[!UICONTROL Key Dimension]** por una combinación que ya no esté suscrita a otro conjunto de clasificaciones.
      * **[!UICONTROL Búsqueda]**. Normalmente denominada tabla de consulta como secundaria o subclasificaciones, es la clasificación de una clasificación principal. Una búsqueda es un metadato sobre un valor de clasificación, en lugar de la dimensión original. Por ejemplo, una dimensión *Product* puede tener una clasificación principal de *Código de color*. Se podría adjuntar una tabla de búsqueda de *Nombre de color* al *Código de color* para explicar cada código de color.
1. Seleccione **[!UICONTROL Guardar]** para guardar el conjunto de clasificaciones. Seleccione **[!UICONTROL Cancelar]** para cancelar la definición.
1. Para definir el esquema del conjunto de clasificaciones, seleccione el conjunto de clasificaciones recién creado del administrador de **[!UICONTROL Conjuntos de clasificaciones]** para [editar el conjunto de clasificaciones](#edit-a-classification-set).


## Editar un conjunto de clasificaciones

Para editar un conjunto de clasificaciones:

1. Seleccione **[!UICONTROL Componentes]** en la barra de menús superior de Adobe Analytics y, a continuación, seleccione **[!UICONTROL Conjuntos de clasificaciones]**.
1. En **[!UICONTROL Conjuntos de clasificaciones]**, seleccione la pestaña **[!UICONTROL Conjuntos de clasificaciones]**.
1. Seleccione el nombre del conjunto de clasificaciones.
1. En el cuadro de diálogo **[!UICONTROL Conjunto de clasificaciones: _nombre del conjunto de clasificaciones_]**, puede definir la [configuración](manage/settings.md) y el [esquema](manage/schema.md) para el conjunto de clasificaciones.
1. Una vez finalizado, selecciona **[!UICONTROL Guardar]** para guardar los cambios. Seleccione **[!UICONTROL Cancelar]** para cancelar.


<!--


### Schema

In the Schema tab 





You can use the Classification set manager to create a classification set.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > **[!UICONTROL Add]**

When creating a classification set, the following fields are available.

* **[!UICONTROL Name]**: A text field used to identify the classification set. This field cannot be edited upon creation, but can be renamed later.
* **[!UICONTROL Column Name]**: The name of the first classification dimension that you want to create. This field is the dimension name used in Analysis Workspace, and the column name when exporting classification data. You can add more column names after the classification set is created.
* **[!UICONTROL Type]**: Radio buttons that indicate the type of classification.
  * **[!UICONTROL Primary]**: Apply to dimensions collected in Analytics. They are a way to group (classify) granular dimension values into more meaningful levels of data. For example, you might want to group internal search keywords into internal search categories, to better understand themes in your search data.
  * **[!UICONTROL Lookup]**: Commonly referred to as child or subclassifications, a lookup table is a classification of a primary classification. It is metadata about a classification value, rather than the original dimension. For example, the Product variable might have a primary classification of 'Color code'. A lookup table of 'Color name' could then be attached to 'Color code' to further explain what each code means.
* **[!UICONTROL Subscriptions]** The report suites and dimensions that this classification set applies to. You can add multiple report suite and dimension combinations to a classification set.

![Create a Classification set](../../assets/classification-set-create.png)

If a classification set exists for a given report suite + variable, the classification is added to the schema instead. A given report suite + variable combination cannot belong to multiple classification sets.

-->