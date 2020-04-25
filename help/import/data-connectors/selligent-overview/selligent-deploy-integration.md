---
description: Implementar esta integración es un proceso sencillo de tres pasos.
title: Implementación de la integración
uuid: c578bf26-34c2-44ea-8e60-2990273f8659
translation-type: tm+mt
source-git-commit: a02fb674ea71a05e085c8e9b2dc4460f62f2cd51

---


# Implementación de la integración {#deploying-the-integration}

Implementar esta integración es un proceso sencillo de tres pasos.

## Finalización del asistente de integración {#completing-the-integration-wizard}

Para activar la integración, debe completar el asistente de integración de Selligent en la interfaz de Data Connectors.

1. Vaya al área de Data Connectors de Adobe Experience Cloud.

   ![](assets/selligent-data_connectors.png)

1. En **[!UICONTROL Añadir integraciones]**, arrastre y suelte el complemento de Selligent en Adobe Experience Cloud.

   ![](assets/selligent-add_integration.png)

   Esto abrirá la integración de Data Connectors de Selligent.

1. **Configuración de integración**: elija el grupo de informes deseado y proporcione un nombre para la integración en **[!UICONTROL Configuración de la integración]**.

1. En **[!UICONTROL Valores personalizados]**, rellene toda la información relacionada con su cuenta de Selligent.

   ![](assets/selligent-general_settings.png)

1. **Asignación de variables**: elija las eVars y los eventos reservados correspondientes en los menús desplegables:

   ![](assets/selligent-variables.png)

1. **Configuración de datos**: puede elegir sus propios segmentos en **[!UICONTROL Sus segmentos]**, excepto los 3 segmentos de **[!UICONTROL socio]** automatizados.

1. Esta integración puede requerir la descarga de algunos puntos de datos en su cuenta de Selligent. Puede optar por permitir el acceso a esto en **[!UICONTROL Solicitud de acceso]**.
1. En **[!UICONTROL Recopilación de datos]**, elija una solución automática o manual (complemento de JavaScript) para recopilar parámetros de cadena de consulta de la dirección URL de la página de aterrizaje. Si elige una solución automatizada, introduzca el parámetro de cadena de consulta para el ID de mensaje y ID de destinatario, que son MID y RID respectivamente. Para obtener un complemento de JavaScript, póngase en contacto con su consultor de Adobe.
1. **Configuración de informes**: en **[!UICONTROL Generación de paneles]**, marque la casilla para que el panel de Selligent se genere automáticamente.

   ![](assets/selligent-report_settings.png)

1. Revise el resumen de la integración y haga clic en **[!UICONTROL Activar]**.

## Configuración dentro de Selligent {#configuration-within-selligent}

Tan pronto como la integración está habilitada dentro de Adobe Analytics, se activa una configuración automática en Selligent.

Se ha creado un rastreador que hace un seguimiento de cada correo electrónico. Si desea limitarlo a un dominio determinado, actualice la configuración del rastreador.

Se recomienda encarecidamente mover al principio el parámetro de seguimiento de Adobe Analytics en la dirección URL. Así se garantiza que las reglas de procesamiento de Adobe recogen los parámetros de la dirección URL de la página de aterrizaje. Habilite el seguimiento marcando la casilla de verificación como se muestra a continuación.

![](assets/selligent-tracker.png)

## Verificación de la integración {#verifying-the-integration}

Una vez completados todos los pasos de la implementación, puede validar que la integración transfiera datos correctamente.

El intercambio de datos tarda unos días en comenzar. Asegúrese de ponerse en contacto con Selligent después de activar la integración.

### Registro de actividades de integración {#section-927e270495db479fba9578915d9ae9c9}

Navegue hasta la integración de Selligent en Data Connectors. En la pestaña **[!UICONTROL Asistencia]**, debería ver eventos como Datos de métricas importados o Datos de clasificación importados correctamente:

![](assets/selligent-verifying.png)

### Datos de informes {#section-ebd481a162324e66bd6dc8cb4b8d2424}

Revise los informes de mensajes de Selligent con las métricas apropiadas.

1. Vaya a Reports &amp; Analytics en Adobe Experience Cloud.
1. Seleccione el grupo de informes correspondiente.
1. En **[!UICONTROL Conversión personalizada]**, seleccione los **[!UICONTROL informes de ID de mensaje]** y elija **[!UICONTROL ID o nombre de mensaje]**.
