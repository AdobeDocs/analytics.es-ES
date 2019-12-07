---
description: 'null'
title: Implementación de la integración
uuid: 1a0770a7-c61b-4eec-a9b3-983def842ad8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Implementación de la integración{#deploying-the-integration}

La implementación de esta integración es un proceso sencillo que consiste en completar el Asistente para integración de Adobe y verificar la integración.

## Finalización del Asistente para integración de Adobe{#completing-the-adobe-integration-wizard}

Pasos para completar el asistente de integración en la interfaz de Conectores de datos.

1. Vaya al área Conectores de datos (anteriormente Genesis) dentro de Adobe Experience Cloud.
1. Inicie el asistente para la integración de señales dinámicas.
1. Elija el grupo de informes deseado y proporcione un nombre para la integración.
1. Configure los siguientes elementos:

   | Elemento | Descripción |
   |---|---|
   | La dirección de correo electrónico | La dirección de correo electrónico del contacto principal. |
   | Descripción | (Opcional) Descripción de esta configuración de integración. |
   | ID de comunidad | Puede obtener este ID en su representante de señales dinámicas. |

1. Configure los siguientes elementos de asignaciones **[!UICONTROL de variables]** :

   | Elemento | Descripción |
   |---|---|
   | Código de seguimiento | Seleccione una variable eVar disponible en el grupo de informes. |

1. Revise las clasificaciones que se crearán para esta integración.
1. Marque la casilla para crear el tablero de integración de señal dinámica (opcional, pero muy recomendable).
1. Revise todos los elementos de configuración y haga clic en **[!UICONTROL Activar ahora]**.
1. **Importante**: Una vez que haya completado el asistente, debe notificar al representante de señales dinámicas para que pueda activar la integración en la plataforma VoiceStorm.

## Verificación de la integración{#verifying-the-integration}

Pasos para ver la configuración de la integración de Dynamic Signal VoiceStorm en Adobe Experience Cloud

1. Vea la configuración de la integración de Dynamic Signal en el registro de actividades de integración.
   1. En Adobe Experience Cloud, vaya a **[!UICONTROL Asistencia]** &gt; Registro **[!UICONTROL de actividades de integración]** .

      ![](assets/integration_activity_log.png)

   1. Busque entradas como Datos **[!UICONTROL de clasificación importados correctamente]**. Estas entradas deben aparecer en las 24 horas siguientes a la implementación correcta.
1. Revise los informes de señales dinámicas en Adobe Analytics mediante el panel creado automáticamente con el asistente de integración de Adobe (paso 7). Como alternativa, puede navegar a los informes de señales dinámicas dentro de la estructura de menú de Adobe Analytics; consulte las siguientes capturas de pantalla.

   **Nota**:Estos datos deben aparecer entre 24 y 48 horas después de la implementación correcta.

   ![](assets/reporting.png)

   ![](assets/reporting2.png)
