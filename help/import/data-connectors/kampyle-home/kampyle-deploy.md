---
description: 'null'
title: Implementación de la integración
uuid: ebb385ca-7bfb-4cd3-9ff6-a5f5a52db5c9
translation-type: tm+mt
source-git-commit: 61df62a6f7089ce7d0308e3b62664176b76e520e

---


# Implementación de la integración {#deploying-the-integration}

La implementación de esta integración consiste en completar el Asistente para integración de Adobe, implementar el código de complemento (JavaScript) y verificar la integración.

## Completar el asistente de integración de Adobe {#complete-the-adobe-integration-wizard}

Para activar la integración, complete el asistente de configuración en la interfaz de Conectores de datos.

1. Inicie sesión en Adobe Experience Cloud.
1. Vaya a **[!UICONTROL Data Connectors]**.
1. Inicie el asistente de integración de Kampyle.
1. Seleccione el grupo de informes deseado y proporcione un nombre para la integración.
1. Configure las opciones siguientes:
   1. **[!UICONTROL Email address]**: La dirección de correo electrónico del contacto principal.
   1. **[!UICONTROL Description]** (opcional): Descripción de esta configuración de integración.
   1. **[!UICONTROL Kampyle Key]**:: Busque esta clave en la aplicación Kampyle en **[!UICONTROL Feedback Form]** > **[!UICONTROL Feedback Form Customization]**.
   1. **[!UICONTROL Tracking Server]**:: Valor del servidor de seguimiento que se utiliza para realizar el seguimiento de los datos de Adobe Analytics.
   1. **[!UICONTROL Tracking Server Secure]**:: Si el servidor de seguimiento es diferente para el tráfico seguro/https, proporcione esta configuración aquí.
1. Configure the following **[!UICONTROL Variable Mappings]** items:
   1. **[!UICONTROL Kampyle Feedback ID]**: Elija una variable eVar disponible en el grupo de informes
   1. **[!UICONTROL Feedback Grade]**:: Seleccione un evento de éxito disponible (escriba &quot;contador&quot;) en el grupo de informes.
   1. **[!UICONTROL Feedback Items]**:: Seleccione un evento de éxito disponible (escriba &quot;contador&quot;) en el grupo de informes.
   1. **[!UICONTROL Feedback with Grade]**:: Seleccione un evento de éxito disponible (escriba &quot;contador&quot;) en el grupo de informes.
1. Marque la casilla para que el Panel de integración de Kampyle se cree automáticamente (recomendado).
1. Review all configuration items and click **[!UICONTROL Activate Now]**.

## Implementar el objeto de configuración de integración {#deploy-the-integration-configuration-object}

Después de completar el asistente de integración, implemente el objeto de configuración de integración en la propiedad web. En muchos casos, la forma más sencilla de implementar el objeto de configuración de integración es incluirlo en el código de implementación de Adobe Analytics.

> [!NOTE] Si utiliza Adobe Experience Platform Launch, puede añadir fácilmente el objeto de configuración de integración a través de esa herramienta.

1. Navigate to the **[!UICONTROL Resources]** > **[!UICONTROL Support]** tab of the integration.
1. Descargue y guarde el **[!UICONTROL Kampyle Integration Code (JS)]** recurso. El código tiene un aspecto similar al siguiente:

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. Implemente el código mediante uno de los siguientes métodos:

   * Utilice Adobe Experience Platform Launch.
   * Envíe el código al recurso de organización que mantiene la implementación de Adobe Analytics.

## Verificar la integración {#verify-the-integration}

Valide que la integración transfiera datos correctamente completando un par de comprobaciones.

### Registro de actividades de integración {#section-0472df9180db4f218db5f6040cab07af}

View your Kampyle integration setup within the Adobe Experience Cloud by navigating to **[!UICONTROL Support]** > **[!UICONTROL Integration Activity Log]**. Under the **[!UICONTROL Data In]** tab, you should see entries stating that classification data was successfully imported.

> [!NOTE] Las entradas de registro suelen aparecer en las 24 horas siguientes a la implementación correcta.

![Registro de actividad de integración](assets/integration_activity_log.png)

### Datos de informes de Adobe {#section-1ae9f0a5e6bc40988478ff55aefd56ac}

Vea sus informes de comentarios de Kampyle con Adobe Analytics navegando hasta los informes de Kampyle dentro de la estructura de menú adecuada.

> [!NOTE] Los datos de los informes deberían aparecer en un plazo de 24 a 48 horas después de la implementación, suponiendo que los formularios de comentarios integrados reciban los envíos de manera activa.

![Datos de Adobe sistema de informes](assets/adobe_reporting_data.png)
