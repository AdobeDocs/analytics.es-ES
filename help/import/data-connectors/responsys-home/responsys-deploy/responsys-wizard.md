---
description: Pasos para completar el asistente de integración en la interfaz de Conectores de datos.
seo-description: Pasos para completar el asistente de integración en la interfaz de Conectores de datos.
seo-title: Finalización del Asistente para integración de Adobe
solution: Analytics
title: Finalización del Asistente para integración de Adobe
uuid: fb106251-78cf-4a2a-8ba2-2a39188ba910
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Finalización del Asistente para integración de Adobe{#completing-the-adobe-integration-wizard}

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
