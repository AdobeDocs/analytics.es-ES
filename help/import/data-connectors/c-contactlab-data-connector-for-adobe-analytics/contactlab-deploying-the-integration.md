---
description: 'null'
seo-description: 'null'
seo-title: Implementación de la integración
solution: Analytics
title: Implementación de la integración
uuid: df3f24c9-d2e3-489e-b97e-e1af0d5dd1fa
translation-type: tm+mt
source-git-commit: 56d27762320a752dff6ab4d9d763bbbf6e0deff5

---


# Implementación de la integración{#deploying-the-integration}

La implementación de esta integración es un proceso sencillo que requiere las siguientes acciones:

## Complete el Asistente para integración de Adobe{#completing-the-adobe-integration-wizard}

Pasos para completar el asistente de integración en la interfaz de Conectores de datos.

1. Vaya al área Conectores de datos (anteriormente Genesis) dentro de Adobe Experience Cloud.
1. Inicie el asistente de integración de ContactLab.
1. Elija el grupo de informes deseado y proporcione un nombre para la integración.
1. Configure the following items:

   | Elemento | Descripción |
   |---|---|
   | La dirección de correo electrónico | La dirección de correo electrónico del contacto principal |
   | Descripción | (Opcional) Descripción de esta configuración de integración |

1. Configure los siguientes elementos de asignaciones **[!UICONTROL de variables]** :

   | Elemento | Descripción |
   |---|---|
   | ID del vínculo | Seleccione una eVar para recopilar los ID de vínculo en tiempo real. |
   | Message ID | Seleccione una eVar para recopilar los ID de los mensajes en tiempo real. |
   | Recipient ID | Seleccione una eVar para recopilar los ID de los destinatarios en tiempo real. |
   | Devoluciones | Seleccione un evento numérico para recibir devoluciones diarias de ContactLab. |
   | Enviado | Seleccione un evento numérico para recibir envíos diarios desde ContactLab. |
   | Clic | Seleccione un evento numérico para recibir todos los clics diarios desde ContactLab. |
   | Abierto | Seleccione un evento numérico para recibir las aperturas totales diarias desde ContactLab. |
   | No suscrito | Seleccione un evento numérico para recibir anulaciones diarias de las suscripciones de ContactLab. |

1. Habilite el acceso a los datos y configure la recopilación de datos.
   1. Cambie el nombre de las clasificaciones según sea necesario.
   1. **[!UICONTROL Partner segments are standard remarketing segments that are included in your integration.]**
   1. Under **[!UICONTROL Your Segments]**, select any custom segments that you would like to include in this integration. You can create additional custom segments under the admin panel.
   1. Under Access Requests, check the box to allow product information to be exported to ContactLab in daily remarketing segments.****
   1. Cambie el nombre de las métricas calculadas según sea necesario.
   1. Configure si va a recopilar ID actualizando manualmente el código de recopilación de Analytics o utilizando la solución automatizada. Si selecciona Solución **** automatizada, debe incluir los parámetros que se utilizan en los vínculos de correo electrónico para pasar ID.
1. Revise todos los elementos de configuración y haga clic en **[!UICONTROL Activar ahora]**.

## Verificar la integración{#verifying-the-integration}

View your ContactLab integration setup within the Adobe Experience Cloud

1. View the integration activity log.
   1. In the Adobe Experience Cloud, navigate to Support &gt; Integration Activity Log.********

      ![](assets/integration_activity_log.png)

   1. Look for entries like Classification Data imported successfully, Metrics Data imported successfully, and Metric Data exported successfully. ************ These entries should appear within 1 day of successful deployment.
1. View your reporting data within Adobe Analytics.
   1. Vaya a Conversión **** personalizada &gt; Conversión **[!UICONTROL personalizada 1-10]** &gt; Informes **[!UICONTROL de ID de]** mensaje.

      ![](assets/reporting.png)

   1. Look for ContactLab reporting. This data should appear within 24-48 hours of successful deployment.