---
description: Pasos para completar el asistente de integración en la interfaz de Conectores de datos.
seo-description: Pasos para completar el asistente de integración en la interfaz de Conectores de datos.
seo-title: Finalización del Asistente para integración de Adobe
solution: Analytics
title: Finalización del Asistente para integración de Adobe
uuid: fb 106251-78 cf -4 a 2 a -8 ba 2-2 a 39188 ba 910
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

Pasos para completar el asistente de integración en la interfaz de Conectores de datos.

1. Vaya al área Conectores de datos (anteriormente Genesis) dentro de Adobe Marketing Cloud.
1. Inicie el asistente de integración de Responsys.
1. Elija el grupo de informes deseado y proporcione un nombre para la integración.
1. Configure los siguientes elementos:

   | Elemento | Descripción |
   |---|---|
   | La dirección de correo electrónico | La dirección de correo electrónico del contacto principal |
   | Descripción | (Opcional) Descripción de esta configuración de integración |
   | ID de cuenta | Se ha obtenido poniéndose en contacto con el equipo de asistencia de Responsys en support@responsys.com |

1. Configure the following **[!UICONTROL Variable Mappings]** items:

   | Elemento | Descripción |
   |---|---|
   | ID de mensaje | Seleccione una evar para recopilar el ID de mensaje en tiempo real. |
   | Recipient ID | Seleccione una evar para recopilar el ID de destinatario en tiempo real. |
   | Devoluciones totales | Seleccione un evento numérico para recibir devoluciones diarias de Responsys. |
   | Correo electrónico enviado | Seleccione un evento numérico para recibir los envíos diarios de Responsys. |
   | Pulsado | Seleccione un evento numérico para recibir clics totales diarios de Responsys. |
   | Abierto | Seleccione un evento numérico para recibir el total diario de Responsys. |
   | Sin suscripción | Seleccione un evento numérico para recibir las suscripciones diarias de Responsys. |
   | Entregado | Seleccione un evento numérico para recibir entregas diarias de Responsys. |

1. Habilite el acceso a los datos y configure la recopilación de datos.
   1. Cambie el nombre de las clasificaciones según sea necesario.
   1. **[!UICONTROL Los segmentos de socio]** son segmentos estándar de remercadotecnia que se incluyen en la integración.
   1. Under **[!UICONTROL Access Requests]**, check the box to allow product information to be exported to Responsys in daily remarketing segments.
   1. Configure si recopilará los ID actualizando manualmente su código de recopilación de Analytics o utilizando la solución automatizada. If you select **[!UICONTROL Automated Solution]**, you must include the parameters that are used in email links to pass ID’s.
1. Review all configuration items and click **[!UICONTROL Activate Now]**.
