---
description: Pasos para completar el asistente de integración en la interfaz de Conectores de datos.
seo-description: Pasos para completar el asistente de integración en la interfaz de Conectores de datos.
seo-title: Finalización del Asistente para integración de Adobe
solution: Analytics
title: Finalización del Asistente para integración de Adobe
uuid: a8135be3-fba3-436d-8959-faed40b15088
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Finalización del Asistente para integración de Adobe{#completing-the-adobe-integration-wizard}

Pasos para completar el asistente de integración en la interfaz de Conectores de datos.

1. Vaya al área Conectores de datos (anteriormente Genesis) dentro de Adobe Experience Cloud.
1. Inicie el asistente de integración de ContactLab.
1. Elija el grupo de informes deseado y proporcione un nombre para la integración.
1. Configure los siguientes elementos:

   | Elemento | Descripción |
   |---|---|
   | La dirección de correo electrónico | La dirección de correo electrónico del contacto principal |
   | Descripción | (Opcional) Descripción de esta configuración de integración |

1. Configure los siguientes elementos de asignaciones **[!UICONTROL de variables]** :

   | Elemento | Descripción |
   |---|---|
   | ID del vínculo | Seleccione una eVar para recopilar los ID de vínculo en tiempo real. |
   | ID del mensaje | Seleccione una eVar para recopilar los ID de los mensajes en tiempo real. |
   | Recipient ID | Seleccione una eVar para recopilar los ID de los destinatarios en tiempo real. |
   | Devoluciones | Seleccione un evento numérico para recibir devoluciones diarias de ContactLab. |
   | Enviado | Seleccione un evento numérico para recibir envíos diarios desde ContactLab. |
   | Clic | Seleccione un evento numérico para recibir todos los clics diarios desde ContactLab. |
   | Abierto | Seleccione un evento numérico para recibir las aperturas totales diarias desde ContactLab. |
   | No suscrito | Seleccione un evento numérico para recibir anulaciones diarias de las suscripciones de ContactLab. |

1. Habilite el acceso a los datos y configure la recopilación de datos.
   1. Cambie el nombre de las clasificaciones según sea necesario.
   1. **[!UICONTROL Los segmentos]** asociados son segmentos de remercadotecnia estándar que se incluyen en la integración.
   1. En **[!UICONTROL Sus segmentos]**, seleccione los segmentos personalizados que desee incluir en esta integración. Puede crear segmentos personalizados adicionales en el panel de administración.
   1. En Solicitudes **[!UICONTROL de]** acceso, marque la casilla para permitir que la información del producto se exporte a ContactLab en segmentos diarios de remercadotecnia.
   1. Cambie el nombre de las métricas calculadas según sea necesario.
   1. Configure si va a recopilar ID actualizando manualmente el código de recopilación de Analytics o utilizando la solución automatizada. Si selecciona Solución **** automatizada, debe incluir los parámetros que se utilizan en los vínculos de correo electrónico para pasar ID.
1. Revise todos los elementos de configuración y haga clic en **[!UICONTROL Activar ahora]**.
