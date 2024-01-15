---
description: Las clasificaciones sirven para clasificar los valores en grupos e informar a nivel del grupo. Por ejemplo, puede clasificar todas las campañas de búsqueda pagada en una categoría como términos de música pop e informar sobre el éxito de esa categoría en relación a métricas como Instancias (pulsaciones) y la conversión a eventos de éxito.
title: Clasificaciones de conversión
feature: Classifications
role: Admin
exl-id: b4855000-adf3-4e3b-af36-f4803383126d
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '566'
ht-degree: 93%

---

# Clasificaciones de conversión

Las clasificaciones sirven para clasificar los valores en grupos e informar a nivel del grupo. Por ejemplo, puede clasificar todas las campañas de [!UICONTROL Búsqueda de pago] en una categoría como *términos de música pop* e informar sobre el éxito de esa categoría en relación con métricas como instancias (clics) y conversión a eventos de éxito. Puede añadir hasta 255 clasificaciones a una variable.

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL Conversión]** > **[!UICONTROL Clasificaciones de conversión]**

Las clasificaciones de conversión permiten clasificar variables de conversión. Una vez clasificado, cualquier informe que se pueda generar con los datos clave también se puede generar con las propiedades de datos asociadas.

Después de activar las clasificaciones, utilice el [Importador de clasificaciones](/help/components/classifications/importer/c-working-with-saint.md) para asignar valores específicos a la clasificación adecuada.

>[!WARNING]
>
>Cambiar el nombre de una clasificación puede causar problemas con las reglas existentes creadas en el [Generador de reglas de clasificación](/help/components/classifications/crb/classification-rule-builder.md). Si cambia el nombre de una clasificación que tiene reglas de clasificación, asegúrese de corregir cada regla para que señale a la clasificación con el nombre cambiado.

## Descripciones de clasificaciones de conversión

| Elemento | Descripción |
| --- | --- |
| Nombre | Nombre de la clasificación |
| Habilitada por fecha (de texto solamente) | Indica si la clasificación de texto es un intervalo de fechas para las variables de campaña. |
| Opciones (de texto solamente) | Crea una lista de valores de clasificación disponibles para esta clasificación. Utilice Opciones con variables de campaña para proporcionar a los usuarios una lista de los valores admitidos para la clasificación en el Administrador de campañas. |
| Tipo de número (numérica solamente) | Especifica el tipo de número en la clasificación numérica. Las opciones son Numérica, Porcentaje y Moneda. |

## Agregar clasificaciones de conversión

Para agregar clasificaciones de conversión en Administración:

1. Haga clic en **[!UICONTROL Admin]** > **[!UICONTROL Grupos de informes]**.
1. Selección de un grupo de informes.
1. Haga clic en **[!UICONTROL Editar configuración]** > **[!UICONTROL Conversión]** > **[!UICONTROL Clasificaciones de conversión]**.
1. En la lista desplegable **[!UICONTROL Seleccionar tipo de clasificación]**, seleccione la variable donde desee agregar una clasificación.

   ![Información sobre los pasos](/help/admin/admin/assets/sub_class_create.png)

1. Pase el cursor sobre el icono **[!UICONTROL Editar clasificación]**, a continuación seleccione **[!UICONTROL Añadir clasificación]**.
1. En el campo **[!UICONTROL Seleccionar tipo]**, seleccione el tipo de clasificación que desee agregar a la variable.

   Las opciones son **[!UICONTROL Texto]** y **[!UICONTROL Numérica]**. Para obtener más información acerca de los tipos de clasificaciones, consulte [esta página de ayuda](/help/components/classifications/c-classifications.md).
1. En el cuadro de diálogo **[!UICONTROL Clasificaciones de texto]**, configure la clasificación como desee:

1. Agregar o quitar opciones del cuadro de diálogo de la lista desplegable.

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
