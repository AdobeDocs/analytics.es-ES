---
description: 'null'
title: Implementación de la integración
uuid: 5abf6d49-b05b-4e0f-8d9b-bb02d8f1c84a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Implementación de la integración{#deploying-the-integration}

La implementación de esta integración es un proceso sencillo que requiere las siguientes acciones:

## Finalización del Asistente para integración de Adobe{#completing-the-adobe-integration-wizard}

Pasos para completar el asistente de integración en la interfaz de Conectores de datos.

1. Vaya al área Conectores de datos (anteriormente Genesis) dentro de Adobe Experience Cloud.
1. Inicie el asistente de integración de Responsys.
1. Elija el grupo de informes deseado y proporcione un nombre para la integración.
1. Configure los siguientes elementos:

   | Elemento | Descripción |
   |---|---|
   | La dirección de correo electrónico | La dirección de correo electrónico del contacto principal |
   | Descripción | (Opcional) Descripción de esta configuración de integración |
   | ID de cuenta | Obtenido poniéndose en contacto con el equipo de asistencia de Responsys en support@responsys.com |

1. Configure los siguientes elementos de asignaciones **[!UICONTROL de variables]** :

   | Elemento | Descripción |
   |---|---|
   | ID del mensaje | Seleccione una eVar para recopilar los ID de los mensajes en tiempo real. |
   | Recipient ID | Seleccione una eVar para recopilar los ID de los destinatarios en tiempo real. |
   | Devoluciones totales | Seleccione un evento numérico para recibir devoluciones diarias de Responsys. |
   | Correo electrónico enviado | Seleccione un evento numérico para recibir envíos diarios desde Responsys. |
   | Clic | Seleccione un evento numérico para recibir todos los clics diarios de Responsys. |
   | Abierto | Seleccione un evento numérico para recibir las aperturas totales diarias desde Responsys. |
   | No suscrito | Seleccione un evento numérico para recibir las cancelaciones diarias de suscripción de Responsys. |
   | Enviado | Seleccione un evento numérico para recibir entregas diarias desde Responsys. |

1. Habilite el acceso a los datos y configure la recopilación de datos.
   1. Cambie el nombre de las clasificaciones según sea necesario.
   1. **[!UICONTROL Los segmentos]** asociados son segmentos de remercadotecnia estándar que se incluyen en la integración.
   1. En Solicitudes **[!UICONTROL de]** acceso, marque la casilla para permitir que la información del producto se exporte a Responsys en segmentos de remercadotecnia diarios.
   1. Configure si va a recopilar ID actualizando manualmente el código de recopilación de Analytics o utilizando la solución automatizada. Si selecciona Solución **** automatizada, debe incluir los parámetros que se utilizan en los vínculos de correo electrónico para pasar ID.
1. Revise todos los elementos de configuración y haga clic en **[!UICONTROL Activar ahora]**.

## Configuración dentro del sistema Responsys{#configuring-within-the-responsys-system}

La activación de la integración implica ponerse en contacto con la asistencia de Responsys.

Después de completar el asistente de integración, debe activar la integración en Responsys.

Para ello, póngase en contacto con el equipo de asistencia de Responsys en support@responsys.com.
