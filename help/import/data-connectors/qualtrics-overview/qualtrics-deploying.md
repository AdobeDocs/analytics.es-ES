---
description: Implementar esta integración es un proceso sencillo que requiere las siguientes acciones.
solution: Analytics
subtopic: Qualtrics
title: Implementación de la integración
topic: Data connectors
uuid: 9bdc233d-63f6-456d-8c26-b5736dfdef09
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Implementación de la integración{#deploying-the-integration}

Implementar esta integración es un proceso sencillo que requiere las siguientes acciones.

## Finalización del Asistente para integración de Adobe{#completing-the-adobe-integration-wizard}

Para activar la integración, debe completar el asistente para la integración de Qualtrics en la interfaz de Data Connectors

1. Vaya a los conectores de datos e inicie el asistente para la integración de Qualtrics.
1. Seleccione el grupo de informes que desee utilizar para esta integración y proporcione un nombre.

   Complete el asistente de integración, proporcionando la información descrita en los pasos siguientes. 1. Paso 1 **del Asistente**

   | Email Address | La dirección de correo electrónico del contacto principal. |
   |---|---|
   | Descripción | (Opcional) Descripción de esta configuración de integración. |
   | ID de organización de Qualtrics | [Búsqueda de la ID de organización de Qualtrics](../qualtrics-overview/qualtrics-org-id.md) |
   | Token de Adobe SiteCatalyst | [Generación del token de Qualtrics de Adobe Analytics](../qualtrics-overview/qualtrics-token.md) |

1. **Paso 2 del Asistente: Asignaciones** de variables| Lista de respuestas de Qualtrics| Seleccione una variable de lista disponible en el grupo de informes. (Es posible que necesite habilitar una nueva listVar dentro del Administrador de grupos de informes).  ||—|—|| ID de respuesta de Qualtrics| Seleccione una eVar o prop disponible en el grupo de informes. (Es posible que necesite habilitar una nueva listVar dentro del Administrador de grupos de informes).  || Servidor de seguimiento|Proporcione la configuración del servidor de seguimiento (dominio) que utiliza para realizar el seguimiento de los datos de Adobe Analytics. Utilice el servidor de `trackingServerSecure` seguimiento si difiere de la configuración estándar del servidor de seguimiento.  || Envíos de Encuesta de Qualtrics| Seleccione un evento disponible en su grupo de informes (es posible que necesite habilitar un nuevo evento desde el Administrador de grupos de informes).  |

1. **Paso 3** del asistente: No se necesita nada, solo información.

   Resultado (1). **Paso 4 del Asistente: Exportar configuración**

   | eVar | Seleccione hasta cinco de las eVars que desee exhibir para exportar a Qualtrics |
   |---|---|
   | Eventos | Seleccione hasta cinco de los eventos personalizados que desee exponer para exportarlos a Qualtrics |
   | Propriétés | Seleccione hasta cinco de las Props que desee exponer para exportar a Qualtrics |
   | Solicitudes de acceso | Marque la casilla de cualquiera de las métricas y dimensiones estándar que desee exportar a Qualtrics. Se `visitor_id` requiere para permitir que la exportación funcione correctamente. |

1. **Paso 5** del asistente: Revise la configuración y haga clic en **[!UICONTROL Activar ahora]**.

## Activación de la integración en Qualtrics Research Suite{#enabling-the-integration-in-qualtrics-research-suite}

Después de completar el asistente de integración, debe activar la integración para cada estudio de Qualtrics que desee conectar.

1. Inicie sesión en Qualtrics Research Suite.
1. En la ficha **[!UICONTROL Mis estudios]** , haga clic en el botón **[!UICONTROL Editar]** del estudio que desee integrar.
1. Haga clic en el menú Opciones **** avanzadas y seleccione **[!UICONTROL Adobe Analytics]**. (si no ve esta opción, pregunte al administrador si desea obtener los permisos necesarios).

   ![](assets/advanced_options.png)

1. Seleccione la Configuración de Adobe Analytics y, a continuación, haga clic en **[!UICONTROL Guardar]**. Si no hay configuraciones disponibles, es probable que aún no haya completado el Asistente para integración de Adobe.
   1. La casilla de verificación **[!UICONTROL Incluir respuestas]** parciales se puede utilizar para indicar que desea capturar datos en Adobe Analytics después de completar cada pantalla parcial del estudio. Si no se selecciona, los datos se transfieren únicamente para los estudios completados.
   1. La casilla de verificación **[!UICONTROL Enviar marca de hora con señalización]** solo se debe utilizar cuando se integre con un grupo de informes configurado para recibir datos con marca de hora (algo poco común).
   ![](assets/integration_config.png)

## Verificación de la integración{#verifying-the-integration}

Una vez completados todos los pasos de implementación, puede validar que la integración esté transfiriendo datos correctamente.

1. **Registro** de actividades de integración: En la interfaz de usuario de Conectores de datos, vea la ficha **[!UICONTROL Asistencia]** en la integración de Qualtrics. Debajo del encabezado Registro **[!UICONTROL de actividades de]** integración debe ver las entradas que indican los datos de clasificación correctos importados.

   >[!NOTE]
   >
   >Estas entradas deben aparecer en el plazo de 1 hora desde que se realizó correctamente la implementación.

   ![](assets/verify-1.png)

1. **Datos** de informes: Vea los informes de los estudios de Qualtrics con la interfaz de usuario de informes y análisis de marketing navegando por los informes de los estudios de Qualtrics (en Variables **[!UICONTROL de lista]**).

   >[!NOTE]
   >
   >Estos datos deben aparecer en un plazo de 24 a 48 horas tras la implementación correcta, suponiendo que el estudio integrado reciba respuestas de forma activa.

   ![](assets/verify-2.png) ![](assets/verify-3.png)


