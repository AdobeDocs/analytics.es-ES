---
description: Las clasificaciones sirven para clasificar los valores en grupos e informar a nivel del grupo. Por ejemplo, puede clasificar todas las campañas de búsqueda pagada en una categoría como términos de música pop e informar sobre el éxito de esa categoría en relación a métricas como Instancias (pulsaciones) y la conversión a eventos de éxito.
title: Clasificaciones de conversión
translation-type: tm+mt
source-git-commit: ec93137d0b5334e312fe0ec42953457243117d4a
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Clasificaciones de conversión

Las clasificaciones sirven para clasificar los valores en grupos e informar a nivel del grupo. Por ejemplo, puede clasificar todas las campañas de búsqueda pagada en una categoría como *términos de música pop* e informar sobre el éxito de esa categoría en relación a métricas como Instancias (pulsaciones) y la conversión a eventos de éxito.

Las clasificaciones de conversión permiten clasificar variables de conversión. Una vez clasificado, cualquier informe que se pueda generar con los datos clave también se puede generar con las propiedades de datos asociadas.

Después de activar las clasificaciones, utilice el [Importador de clasificaciones](/help/components/classifications/importer/c-working-with-saint.md) para asignar valores determinados a la clasificación adecuada.

>[!WARNING]
>
>Cambiar el nombre de una clasificación puede causar problemas con las reglas existentes creadas en el creador [de reglas](/help/components/classifications/crb/classification-rule-builder.md)de clasificación. Si cambia el nombre de una clasificación que tiene reglas de clasificación, asegúrese de corregir cada regla para que señale a la clasificación con el nombre cambiado.

## Descripciones de clasificaciones de conversión

| Elemento | Descripción |
| --- | --- |
| Nombre | Nombre de la clasificación |
| Habilitada por fecha (de texto solamente) | Indica si la clasificación de texto es un intervalo de fechas para las variables de campaña. |
| Opciones (de texto solamente) | Crea una lista de valores de clasificación disponibles para esta clasificación. Utilice Opciones con variables de campaña para proporcionar a los usuarios una lista de los valores admitidos para la clasificación en el Administrador de campañas. |
| Tipo de número (numérica solamente) | Especifica el tipo de número en la clasificación numérica. Las opciones son Numérica, Porcentaje y Moneda. |

## Agregar clasificaciones de conversión

Instrucciones que describen cómo se agregan clasificaciones de conversión en Administración.

1. Haga clic en **[!UICONTROL Admin]** > **[!UICONTROL Grupos de informes]**.
1. Selección de un grupo de informes.
1. Haga clic en **[!UICONTROL Editar configuración]** > **[!UICONTROL Conversión]** > **[!UICONTROL Clasificaciones de conversión]**.
1. En la lista desplegable **[!UICONTROL Seleccionar tipo de clasificación]**, seleccione la variable donde desee agregar una clasificación.

   ![Información sobre los pasos](../assets/sub_class_create.png)

1. Pase el cursor sobre el icono **[!UICONTROL Editar clasificación]**, a continuación seleccione **[!UICONTROL Añadir clasificación]**.
1. En el campo **[!UICONTROL Seleccionar tipo]**, seleccione el tipo de clasificación que desee agregar a la variable.

   Las opciones son **[!UICONTROL Texto]** y **[!UICONTROL Numérica]**. Para obtener más información acerca de los tipos de clasificaciones, consulte [esta página de ayuda](/help/components/classifications/c-classifications.md).
1. En el cuadro de diálogo **[!UICONTROL Clasificaciones de texto]**, configure la clasificación como desee:

1. En el cuadro de diálogo **[!UICONTROL Lista desplegable]**, agregue o elimine opciones.

   Al agregar opciones, se crea una lista de valores de clasificación disponibles para esta clasificación. Puede utilizarse esta opción con las variables de Campaña para proporcionar a los usuarios una lista de los valores admitidos para la clasificación en el Administrador de campañas. Utilice esto para dimensiones de clasificación donde tiene un número pequeño de valores permitidos que cambian pocas veces o nunca. Por ejemplo, podría ejecutar diferentes campañas dirigidas a diferentes niveles de lealtad de clientes: Plata, Oro y Platino. Luego podría utilizar una lista desplegable para asegurarse de que solo los valores aceptados sean aquellos que coincidan con sus tres niveles. Si alguien intenta utilizar un valor diferente, se descarta.

1. Haga clic en **[!UICONTROL Guardar]**.

## Eliminar una clasificación de conversión

Elimine una clasificación de conversión cuando ya no la necesite.

1. Abra el Administrador de grupos de informes haciendo clic en **[!UICONTROL Admin]** > **[!UICONTROL Grupos de informes]**, en el encabezado de Suite.
1. Selección de un grupo de informes.
1. Haga clic en **[!UICONTROL Editar configuración]** > **[!UICONTROL Conversión]** > **[!UICONTROL Clasificaciones de conversión]**.
1. En la lista desplegable **[!UICONTROL Seleccionar tipo de clasificación]**, seleccione la variable donde desee eliminar una clasificación.
1. Pase el cursor sobre **[!UICONTROL Editar clasificación]** y, a continuación, seleccione **[!UICONTROL Eliminar clasificación]**.
1. En el cuadro de diálogo Eliminar clasificación, haga clic en **[!UICONTROL Eliminar]**.
