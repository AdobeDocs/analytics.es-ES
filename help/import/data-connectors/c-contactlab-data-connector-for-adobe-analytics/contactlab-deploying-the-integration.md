---
description: 'null'
title: Implementación de la integración
uuid: df3f24c9-d2e3-489e-b97e-e1af0d5dd1fa
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Implementación de la integración{#deploying-the-integration}

La implementación de esta integración es un proceso sencillo que requiere las siguientes acciones:

## Completar el Asistente para integración de Adobe{#completing-the-adobe-integration-wizard}

Pasos para completar el asistente de integración en la interfaz de Conectores de datos.

1. Vaya al área Conectores de datos (anteriormente Genesis) dentro de Adobe Experience Cloud.
1. Inicie el asistente para la integración de ContactLab.
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

## Verificar la integración{#verifying-the-integration}

Ver la configuración de la integración de ContactLab en Adobe Experience Cloud

1. Vea el registro de actividades de integración.
   1. En Adobe Experience Cloud, vaya a **[!UICONTROL Asistencia]** &gt; Registro **[!UICONTROL de actividades de integración]**.

      ![](assets/integration_activity_log.png)

   1. Busque entradas como Datos **[!UICONTROL de clasificación importados correctamente]**, Datos de **[!UICONTROL métricas importados correctamente]** y Datos de **[!UICONTROL métricas exportados correctamente]**. Estas entradas deben aparecer en el plazo de 1 día desde que se realizó correctamente la implementación.
1. Vea los datos de los informes en Adobe Analytics.
   1. Vaya a Conversión **** personalizada &gt; Conversión **[!UICONTROL personalizada 1-10]** &gt; Informes **[!UICONTROL de ID de]** mensaje.

      ![](assets/reporting.png)

   1. Busque informes de ContactLab. Estos datos deben aparecer entre 24 y 48 horas después de la implementación correcta.
