---
description: 'null'
seo-description: 'null'
seo-title: Implementación de la integración
solution: Analytics
title: Implementación de la integración
uuid: ebb385ca-7bfb-4cd3-9ff6-a5f5a52db5c9
translation-type: tm+mt
source-git-commit: f326b29bb73fd6e8630957c43dfd89f47b711986

---


# Implementación de la integración{#deploying-the-integration}

Implementar esta integración es un proceso sencillo que consiste en completar el Asistente para integración de Adobe, implementar el código de complemento (javascript) y verificar la integración.

## Complete el Asistente para integración de Adobe{#complete-the-adobe-integration-wizard}

Para activar la integración, debe completar el asistente de configuración en la interfaz de Conectores de datos.

1. Inicie sesión en Adobe Experience Cloud.
1. Vaya a Conectores **[!UICONTROL de datos]** (anteriormente Genesis).
1. Inicie el asistente de integración de Kampyle.
1. Seleccione el grupo de informes deseado y proporcione un nombre para la integración.
1. Configure los siguientes elementos:
   1. **[!UICONTROL Dirección]** de correo electrónico: la dirección de correo electrónico del contacto principal.
   1. **[!UICONTROL Descripción]** : descripción (opcional) de esta configuración de integración.
   1. **[!UICONTROL Clave]** de Kampyle: busque esta clave en la aplicación Kampyle en Formulario **[!UICONTROL de]** comentarios &gt; Personalización del formulario de **[!UICONTROL comentarios]**.
   1. **[!UICONTROL Servidor]** de seguimiento: la configuración del servidor de seguimiento (dominio) que se utiliza para rastrear datos de Adobe Analytics.
   1. **[!UICONTROL Servidor de seguimiento seguro]** : si el servidor de seguimiento es diferente para el tráfico seguro/https, proporcione esta configuración aquí.
1. Configure los siguientes elementos de asignaciones **[!UICONTROL de variables]** :
   1. **[!UICONTROL ID]** de comentarios de Kampyle: seleccione una variable eVar disponible en el grupo de informes
   1. **[!UICONTROL Grado]** de comentarios: seleccione un evento de éxito disponible (escriba "contador") en el grupo de informes.
   1. **[!UICONTROL Elementos]** de comentarios: seleccione un evento de éxito disponible (escriba "contador") en el grupo de informes.
   1. **[!UICONTROL Comentarios con categoría]** : seleccione un evento de éxito disponible (escriba "contador") en el grupo de informes.
1. Marque la casilla para que el tablero de Integración de Kampyle se cree automáticamente (recomendado).
1. Revise todos los elementos de configuración y haga clic en **[!UICONTROL Activar ahora]**.

## Implementar el objeto de configuración de integración{#deploy-the-integration-configuration-object}

Después de completar el asistente de integración, debe implementar el objeto de configuración de integración en la propiedad web.

En muchos casos, la forma más sencilla de implementar el objeto de configuración de integración es incluirlo en el código de implementación de Adobe Analytics.

> [!NOTE] Si utiliza Adobe TagManager o la administración dinámica de etiquetas para implementar Adobe Analytics, puede añadir fácilmente el objeto de configuración de integración mediante esa herramienta.

1. Vaya a la ficha **[!UICONTROL Recursos]** &gt; **[!UICONTROL Asistencia]** de la integración.
1. Descargue y guarde el recurso **[!UICONTROL Kampyle Integration Code (JS)]** . The code looks similar to this:

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. Implemente el código mediante uno de los siguientes métodos:
| **Utiliza Adobe TagManager o la administración dinámica de etiquetas.** | Utilice la interfaz de administración de etiquetas para agregar el código. |
|---|---|
| In all other cases | Deliver the code to the organizational resource that is responsible for updating your Adobe Analytics deployment code.  |****

## Verify the Integration{#verify-the-integration}

Validate that the integration is successfully transferring data by completing a couple of checks.

### Registro de actividades de integración {#section-0472df9180db4f218db5f6040cab07af}

View your Kampyle integration setup within the Adobe Experience Cloud by navigating to Support &gt; Integration Activity Log. ******** Under the Data In tab, you should see entries stating that classification data was successfully imported.****

> [!NOTE] Log entries should appear within 24 hours of successful deployment.

![](assets/integration_activity_log.png)

### Adobe Reporting Data {#section-1ae9f0a5e6bc40988478ff55aefd56ac}

View your Kampyle feedback reports with Adobe Analytics by navigating to the Kampyle reporting within the appropriate menu structure.

> [!NOTE] Reporting data should appear within 24-48 hours of successful deployment, assuming that the integrated feedback form(s) is actively receiving submissions.

![](assets/adobe_reporting_data.png)

