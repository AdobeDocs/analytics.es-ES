---
description: Implemente el conector de datos de Responsys para utilizarlo en Adobe Analytics.
title: Implementación de la integración
uuid: 5abf6d49-b05b-4e0f-8d9b-bb02d8f1c84a
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 96%

---


# Implementación de la integración {#deploying-the-integration}

Implementar esta integración es un proceso sencillo que requiere las siguientes acciones:

## Finalización del asistente de integración de Adobe {#completing-the-adobe-integration-wizard}

Pasos para completar el asistente de integración en la interfaz de Data Connectors.

1. Vaya al área de Data Connectors (anteriormente Genesis) dentro de Adobe Experience Cloud.
1. Inicie el asistente de integración de Responsys.
1. Elija el grupo de informes deseado y proporcione un nombre para la integración.
1. Configure las opciones siguientes:

   | Elemento | Descripción |
   |---|---|
   | Correo electrónico Dirección | La dirección de correo electrónico del contacto principal |
   | Descripción | (Opcional) Descripción de esta configuración de integración |
   | ID de cuenta | Se obtiene poniéndose en contacto con el equipo de asistencia de Responsys en support@responsys.com. |

1. Configure las siguientes opciones de **[!UICONTROL Asignaciones de variables]**:

   | Elemento | Descripción |
   |---|---|
   | ID de mensaje | Seleccione una eVar para recopilar los ID de mensaje en tiempo real. |
   | Recipient ID (ID de destinatario) | Seleccione una eVar para recopilar los ID de destinatario en tiempo real. |
   | Devoluciones totales | Seleccione un evento numérico para recibir devoluciones diarias de Responsys. |
   | Correo electrónico enviado | Seleccione un evento numérico para recibir envíos diarios desde Responsys. |
   | Clics | Seleccione un evento numérico para recibir todos los clics diarios de Responsys. |
   | Aperturas | Seleccione un evento numérico para recibir las aperturas totales diarias desde Responsys. |
   | Cancelación de suscripción | Seleccione un evento numérico para recibir las cancelaciones de suscripción diarias de Responsys. |
   | Entregas | Seleccione un evento numérico para recibir entregas diarias desde Responsys. |

1. Habilite el acceso a los datos y configure la recopilación de datos.
   1. Cambie los nombres de las clasificaciones si fuera necesario.
   1. **[!UICONTROL Los segmentos asociados]** son segmentos de remarketing estándar que se incluyen en la integración.
   1. En **[!UICONTROL Solicitudes de acceso]**, marque la casilla para permitir que la información del producto se exporte a Responsys en segmentos de remarketing diarios.
   1. Configure si va a recopilar los ID actualizando manualmente el código de recopilación de Analytics o utilizando la solución automatizada. Si selecciona **[!UICONTROL Solución automatizada]**, debe incluir los parámetros que se utilizan en los vínculos de correo electrónico para pasar los ID.
1. Revise todas las opciones de configuración y haga clic en **[!UICONTROL Activar ahora]**.

## Configuración dentro del sistema de Responsys {#configuring-within-the-responsys-system}

La activación de la integración implica ponerse en contacto con la asistencia de Responsys.

Después de finalizar el asistente de integración, debe activar la integración en Responsys.

Para ello, póngase en contacto con el equipo de asistencia de Responsys en support@responsys.com.
