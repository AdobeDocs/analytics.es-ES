---
title: Crear Y Editar Conjuntos De Clasificaciones
description: Obtenga información sobre cómo crear y editar conjuntos de clasificaciones en Adobe Analytics, incluidos tipos de clasificaciones principales y de búsqueda, suscripciones y notificaciones de trabajos.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
TQID: https://experienceleague.adobe.com/b-q3Dk14UUhBEzfhXvkPF1Zh56GrmpXh6N4Mtkiyl-c
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 502
ht-degree: 2%

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
   1. Seleccione el **[!UICONTROL tipo]** del conjunto de clasificaciones. Los tipos posibles son:
      * **[!UICONTROL Principal]**. Un conjunto de clasificaciones principal se aplica a las dimensiones recopiladas en Adobe Analytics. Las clasificaciones principales permiten agrupar (clasificar) los valores de dimensión granulares en niveles de datos más significativos. Por ejemplo, es posible que desee agrupar palabras clave de búsqueda interna en categorías de búsqueda interna para comprender los temas de los datos de búsqueda. O bien, clasifique los SKU de productos por color o categoría.
      * **[!UICONTROL Búsqueda]**. Normalmente denominada tabla de consulta como secundaria o subclasificaciones, es la clasificación de una clasificación principal. Una búsqueda es un metadato sobre un valor de clasificación, en lugar de la dimensión original. Por ejemplo, una dimensión *Product* puede tener una clasificación principal de *Código de color*. Se podría adjuntar una tabla de búsqueda de *Nombre de color* al *Código de color* para explicar cada código de color.
1. En la sección **[!UICONTROL Notificaciones de trabajo]**, seleccione a quién desea notificar en caso de error o éxito de los trabajos del conjunto de clasificación.
   * Para notificar un error a los usuarios:
      1. Habilitar **[!UICONTROL Notificar si se produce un error]**.
      1. Especifique una o más direcciones de correo electrónico separadas por comas en **[!UICONTROL Destinatarios de correo electrónico con errores]**.
   * Para notificar a los usuarios que se ha realizado correctamente:
      1. Habilitar **[!UICONTROL Notificar si se realiza correctamente]**.
      1. Especifique una o más direcciones de correo electrónico separadas por comas en **[!UICONTROL Destinatarios de correo electrónico de éxito]**.
1. En la sección **[!UICONTROL Suscripciones]**, en caso de que haya seleccionado **[!UICONTROL Principal]**, escriba una o más **[!UICONTROL Suscripciones]**.  Puede definir varias combinaciones de **[!UICONTROL Grupo de informes]** y **[!UICONTROL Dimension]** en un conjunto de clasificaciones.

   * Seleccione ![CrossSize400](/help/assets/icons/CrossSize400.svg) para eliminar una combinación de **[!UICONTROL Grupo de informes]** y **[!UICONTROL Dimension clave]**.

   Si agrega una combinación de **[!UICONTROL Grupo de informes]** y **[!UICONTROL Dimension de claves]** que ya existe en otro conjunto de clasificaciones, se mostrará un mensaje de color rojo.
Puedes realizar lo siguiente:
   * Seleccione **[!UICONTROL Agregar a]** existente para abrir el otro conjunto de clasificaciones y [agregar clasificaciones al esquema](manage/schema.md) para ese otro conjunto de clasificaciones.
   * Cambie **[!UICONTROL Report Suite]** y **[!UICONTROL Key Dimension]** por una combinación que ya no esté suscrita a otro conjunto de clasificaciones.
1. Seleccione **[!UICONTROL Guardar]** para guardar el conjunto de clasificaciones. Seleccione **[!UICONTROL Cancelar]** para cancelar la definición.

Para definir el esquema del conjunto de clasificaciones, seleccione el conjunto de clasificaciones recién creado del administrador de **[!UICONTROL Conjuntos de clasificaciones]** para [editar el conjunto de clasificaciones](#edit-a-classification-set).


## Editar un conjunto de clasificaciones

Para editar un conjunto de clasificaciones:

1. Seleccione **[!UICONTROL Componentes]** en la barra de menús superior de Adobe Analytics y, a continuación, seleccione **[!UICONTROL Conjuntos de clasificaciones]**.
1. En **[!UICONTROL Conjuntos de clasificaciones]**, seleccione la pestaña **[!UICONTROL Conjuntos de clasificaciones]**.
1. Seleccione el nombre del conjunto de clasificaciones.
1. En el cuadro de diálogo **[!UICONTROL Conjunto de clasificaciones: _nombre del conjunto de clasificaciones_]**, puede definir la [configuración](manage/settings.md) y el [esquema](manage/schema.md) para el conjunto de clasificaciones.
1. Una vez finalizado, selecciona **[!UICONTROL Guardar]** para guardar los cambios. Seleccione **[!UICONTROL Cancelar]** para cancelar.
