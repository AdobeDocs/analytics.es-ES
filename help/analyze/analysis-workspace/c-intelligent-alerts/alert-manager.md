---
description: Crear, editar o eliminar alertas.
title: Administrador de alertas (Analysis Workspace)
feature: Alerts
role: User, Admin
exl-id: c33a9a30-f53f-443c-96b7-6a87d03573c7
source-git-commit: 58e1d3025b455de7fa07037b3b0659330c8324c7
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 5%

---


# Administración de alertas

Puede administrar las alertas existentes en el Administrador de alertas. Puede realizar varias tareas de administración en las alertas, como etiquetado, cambio de nombre, eliminación, etc.

El Administrador de alertas está estructurado de la misma manera que [Administrador de segmentos](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-manage.html?lang=es) y el [Administrador de métricas calculadas](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-manager.html?lang=es).

## Creación de alertas

Para crear alertas desde el Administrador de alertas:

1. Seleccionar **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]** para acceder al Administrador de alertas en Adobe Analytics.

   ![](assets/alert-manager.png)

1. Seleccionar [!UICONTROL **Añadir**] (o [!UICONTROL **Crear nueva alerta**] si no tiene ninguna alerta existente).

1. Seleccione el tipo de alerta que corresponde a la alerta que desea crear:

   * [!UICONTROL **Alerta de datos de Analytics**]: una alerta para notificarle cuando se producen eventos anormales en los datos.

     Si selecciona esta opción, continúe con [Creación de alertas](/help/analyze/analysis-workspace/c-intelligent-alerts/alert-builder.md) para obtener más información sobre la creación de alertas.

   * [!UICONTROL **Alerta de uso de llamadas al servidor**]: una alerta para notificarle del riesgo o la incidencia de un exceso en los datos de asignación y consumo de llamadas al servidor.

     Si selecciona esta opción, continúe con [Alertas de uso de llamadas al servidor](/help/admin/admin/c-server-call-usage/scu-alerts.md).

     >[!NOTE]
     >
     >Debe ser administrador de Analytics o usuario con el permiso Uso de llamadas al servidor para tener acceso a este.




## Administrar alertas existentes

Para administrar las alertas existentes en el Administrador de alertas:

1. Seleccionar **[!UICONTROL Componentes]** > **[!UICONTROL Alertas]** para acceder al Administrador de alertas en Adobe Analytics.

   ![](assets/alert-manager.png)

1. Seleccione una o varias alertas que desee administrar.

   ![](assets/alert-manager-tasks.png)

1. En la barra de acciones, seleccione cualquiera de las siguientes opciones:

   | Acción | Función |
   |---------|----------|
   | [!UICONTROL **Etiqueta**] | Aplicar una etiqueta a una alerta. Esto le ayuda a organizar las alertas para facilitar su uso. |
   | [!UICONTROL **Eliminar**] | Elimina la alerta. |
   | [!UICONTROL **Cambiar el nombre**] | Cambia el nombre de la alerta. |
   | [!UICONTROL **Aprobar**] | Marcar la alerta como Aprobada. |
   | [!UICONTROL **Copiar**] | Crea una copia (duplicado) de la alerta. |
   | [!UICONTROL **Deshabilitar**] | Deshabilita una alerta que está habilitada actualmente. |
   | [!UICONTROL **Activar**] | Habilita una alerta que está deshabilitada actualmente. |
   | [!UICONTROL **Renovar**] | Renueva la fecha de caducidad de la alerta. Esto amplía la fecha de caducidad a 1 año a partir del día en que seleccionó esta opción, independientemente de la fecha de caducidad original. |
   | [!UICONTROL **Exportar a CSV**] | Exporta la alerta a un archivo .CSV. |
