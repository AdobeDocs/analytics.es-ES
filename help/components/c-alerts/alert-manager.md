---
description: Administrar alertas.
title: Información general sobre el Administrador de alertas
feature: Alerts
exl-id: 3408c79f-3d85-44b9-8fca-ce956853dfa4
source-git-commit: 86580b3c149c0feb1d70d9ba197cf0810e472586
workflow-type: ht
source-wordcount: '638'
ht-degree: 100%

---

# Administrador de alertas

Puede administrar las alertas existentes en el Administrador de alertas. Puede realizar varias tareas de administración de las alertas, como etiquetado, cambio de nombre, eliminación, etc.

El Administrador de alertas tiene una estructura muy similar al [Administrador de segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=es) y al [Administrador de métricas calculadas](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=es).

![](assets/alert-manager.png)

## Creación de alertas

Para crear alertas desde el Administrador de alertas:

1. Seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]** para acceder al Administrador de alertas en Adobe Analytics.

   ![](assets/alert-manager.png)

1. Seleccione [!UICONTROL **Añadir**] (o [!UICONTROL **Crear nueva alerta**] si no tiene ninguna alerta existente).

1. Seleccione el tipo de alerta que corresponde a la alerta que desea crear:

   * [!UICONTROL **Alerta de datos de Analytics**]: una alerta para avisarle cuando se produzcan eventos anómalos en sus datos.

     Si selecciona esta opción, continúa con [Crear alertas](/help/components/c-alerts/alert-builder.md) para obtener más detalles acerca de la creación de alertas.

   * [!UICONTROL **Alerta de uso de llamadas al servidor**]: una alerta para notificarle el riesgo o la incidencia de un exceso en los datos de asignación y consumo de llamadas al servidor.

     Si selecciona esta opción, continúe con [Alertas de uso de llamadas al servidor](/help/admin/admin/c-server-call-usage/scu-alerts.md).

     >[!NOTE]
     >
     >Debe ser administrador de Analytics o usuario con el permiso Uso de llamadas al servidor para tener acceso a este.

## Administrar alertas existentes

Puede realizar varias acciones en las alertas existentes, como etiquetado, cambio de nombre, eliminación, etc.

Para administrar las alertas existentes en el Administrador de alertas:

1. Seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]** para acceder al Administrador de alertas en Adobe Analytics.

   ![](assets/alert-manager.png)

1. Seleccione una o varias alertas que desee administrar.

   ![](assets/alert-manager-tasks.png)

1. En la barra de acciones, seleccione cualquiera de las siguientes opciones:

   | Acción | Función |
   |---------|----------|
   | [!UICONTROL **Etiqueta**] | Aplicar una etiqueta a una alerta. Esto permite organizarlas para facilitar su uso. |
   | [!UICONTROL **Eliminar**] | Elimina la alerta. |
   | [!UICONTROL **Cambiar el nombre**] | Cambia el nombre de la alerta. |
   | [!UICONTROL **Aprobar**] | Marcar la alerta como Aprobada. |
   | [!UICONTROL **Copiar**] | Crea una copia (duplicado) de la alerta. |
   | [!UICONTROL **Deshabilitar**] | Deshabilita una alerta que está habilitada actualmente. |
   | [!UICONTROL **Activar**] | Habilita una alerta que está deshabilitada actualmente. |
   | [!UICONTROL **Renovar**] | Renueva la fecha de caducidad de la alerta. Esto amplía la fecha de vencimiento a 1 año a partir del día en que seleccionó esta opción, independientemente de la fecha de vencimiento original. |
   | [!UICONTROL **Exportar a CSV**] | Exportar una alerta a un archivo .CSV. |

## Editar una alerta

Para editar una alerta existente:

1. Seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]** para acceder al Administrador de alertas en Adobe Analytics.

   ![](assets/alert-manager.png)

1. Seleccione el nombre de la alerta en la columna [!UICONTROL **Título y descripción**].

1. Edite la alerta como desee.

   A continuación se indican algunas de las acciones que puede realizar al editar una alerta:

   * Añadir alertas a otros grupos de informes
   * Añadir o modificar la descripción
   * Modificar la granularidad temporal
   * Modificación de los destinatarios
   * Modificación de la fecha de vencimiento
   * Modificación de métricas y filtros

1. Seleccione [!UICONTROL **Guardar**].

## Configuración de columnas

Puede configurar la información mostrada para cada alerta en el Administrador de alertas configurando las columnas que se muestran.

Para configurar las columnas visibles en el Administrador de alertas:

1. En Adobe Analytics, seleccione la pestaña **[!UICONTROL Componentes]** y, a continuación, **[!UICONTROL Alertas]**.

1. En el Administrador de alertas, seleccione el icono **Personalizar columnas** ![Personalizar icono de columnas](assets/customize-columns-icon.png) y, a continuación, seleccione las columnas que desea que se muestren en el Administrador de alertas.

   Las columnas disponibles son las siguientes:

   | Título de columna | Descripción |
   |---|---|
   | Título y descripción | Estos valores se proporcionan en el Generador de alertas. Para editar el título y la descripción, seleccione el vínculo del título para abrir el generador de alertas. |
   | Favoritos | Muestra iconos de estrella junto a cada alerta, lo que permite marcar las alertas como favoritas. <!-- For more information, see [Mark calculated metrics as favorites](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). --> |
   | Tipo | Muestra si la alerta es una alerta de datos de Analytics o una alerta de uso de llamadas al servidor. |
   | Habilitado | Muestra si la alerta está habilitada o deshabilitada actualmente. |
   | Grupo de informes | Indica en qué grupo de informes se guardó la alerta por última vez. |
   | Propietario | Indica a quién pertenece la alerta. Como no administrador, solo puede ver las alertas que le pertenecen o las que se compartieron con usted. |
   | Etiquetas | Muestra las etiquetas que se aplicaron a la alerta, tanto por su parte como por parte de las personas que compartieron la alerta con usted. |
   | Fecha de caducidad | Muestra la fecha y la hora en que la alerta está configurada para vencer. |
   | Fecha de modificación | Indica la fecha en la que se modificó la alerta por última vez. |

   {style="table-layout:auto"}

   <!-- When "Last used" column is added, add this information as the description: Shows the date when the alert was last used. <p>This information can help you determine whether a component is valuable to users in your organization, where it is used, and if it needs to be deleted or modified.</p><p>Consider the following when viewing this column:</p><ul><li>This information does not include usage from the API, Report Builder, or Data Warehouse.</li><li>For some components, this column might not contain data if the component was last used prior to September 2023.</li></ul> -->


