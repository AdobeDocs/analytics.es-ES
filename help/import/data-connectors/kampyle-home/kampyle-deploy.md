---
description: 'null'
title: Implementación de la integración
uuid: ebb385ca-7bfb-4cd3-9ff6-a5f5a52db5c9
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Implementación de la integración{#deploying-the-integration}

Implementar esta integración es un proceso sencillo que consiste en completar el Asistente para integración de Adobe, implementar el código de complemento (javascript) y verificar la integración.

## Completar el Asistente para integración de Adobe{#complete-the-adobe-integration-wizard}

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

> [!NOTE] Si utiliza Adobe TagManager o la administración dinámica de etiquetas para implementar Adobe Analytics, puede añadir fácilmente el objeto de configuración de integración a través de esa herramienta.

1. Vaya a la ficha **[!UICONTROL Recursos]** &gt; **[!UICONTROL Asistencia]** de la integración.
1. Descargue y guarde el recurso **[!UICONTROL Kampyle Integration Code (JS)]** . El código tiene un aspecto similar al siguiente:

   ```
   /* Kampyle:  Integration configuration settings */
     window.k_sc_param = { "version":1.1 }
   ```

1. Implemente el código mediante uno de los siguientes métodos:
| **Utiliza Adobe TagManager o la administración dinámica de etiquetas.** | Utilice la interfaz de administración de etiquetas para agregar el código. ||—|—|| **En todos los demás casos** | Envíe el código al recurso de organización responsable de actualizar el código de implementación de Adobe Analytics.  |

## Verificar la integración{#verify-the-integration}

Valide que la integración esté transfiriendo datos correctamente mediante la realización de un par de comprobaciones.

### Registro de actividades de integración {#section-0472df9180db4f218db5f6040cab07af}

Para ver la configuración de la integración de Kampyle en Adobe Experience Cloud, vaya a **[!UICONTROL Asistencia]** &gt; Registro **[!UICONTROL de actividades]** de integración. En la ficha **[!UICONTROL Datos en]** , debe ver las entradas que indican que los datos de clasificación se importaron correctamente.

> [!NOTE] Las entradas de registro deben aparecer en las 24 horas siguientes a la implementación correcta.

![](assets/integration_activity_log.png)

### Datos de informes de Adobe {#section-1ae9f0a5e6bc40988478ff55aefd56ac}

Vea sus informes de comentarios de Kampyle con Adobe Analytics navegando hasta los informes de Kampyle dentro de la estructura de menú adecuada.

> [!NOTE] Los datos de los informes deberían aparecer en un plazo de 24 a 48 horas a partir de la implementación correcta, suponiendo que los formularios integrados de comentarios estén recibiendo envíos activamente.

![](assets/adobe_reporting_data.png)

