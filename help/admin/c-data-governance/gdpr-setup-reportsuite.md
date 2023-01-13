---
description: Al etiquetar los datos de los grupos de informes, se asignan etiquetas de identidad, confidencialidad y control de datos a cada variable de un grupo de informes determinado.
title: Etiquetado de datos de grupos de informes
feature: Data Governance
exl-id: d1bd833c-3fd4-4572-a5dc-d7bab8a79cb8
source-git-commit: bb5204584ebcd5be3254f34b0954f53e6fb11ea4
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 50%

---

# Etiquetado de datos de grupos de informes

>[!NOTE]
>
>Esta interfaz de usuario actualizada se encuentra actualmente en prueba limitada.

Al etiquetar los datos de los grupos de informes, se asignan etiquetas de identidad, confidencialidad y control de datos a cada variable de un grupo de informes determinado. Asegúrese de familiarizarse primero con el [etiquetas y sus definiciones](/help/admin/c-data-governance/gdpr-labels.md).

>[!NOTE]
>
>Recuerde que el etiquetado debe revisarse cada vez que se crea un nuevo grupo de informes o cuando se activa una nueva variable dentro de un grupo de informes existente. También es posible que necesite revisar el etiquetado cuando se activen nuevas integraciones de la solución, ya que pueden exponer nuevas variables que pueden requerir etiquetado. Una reimplementación de sus aplicaciones móviles o sitios web puede cambiar la forma en la que se utilizan las variables existentes, las cuales también pueden necesitar la actualización de las etiquetas.

## Asignación o edición de etiquetas de privacidad de grupos de informes {#assign-edit}

**Ejemplo**: Usted, como responsable del tratamiento de datos, pretende recopilar direcciones de correo electrónico e ID de cookie de los interesados para tratar sus solicitudes de privacidad de datos. Estos ID de cookie se almacenan en un grupo de informes en Adobe Analytics. Para crear una etiqueta para direcciones de correo electrónico e ID de cookie, debe utilizar el marco de etiquetado y aplicación del uso de los datos (DULE) de la plataforma de Adobe Experience Cloud en Analytics.

1. En Adobe Analytics, vaya a **[!UICONTROL Administrador]** > **[!UICONTROL Todos los administradores]** > **[!UICONTROL Configuración y recopilación de datos]** > **[!UICONTROL Administración de datos]**.

   ![Etiquetado de privacidad](assets/privacy_rs_settings.png)

1. Seleccione un grupo de informes en la **[!UICONTROL Grupos de informes]** en la parte superior.

1. En la sección de filtro de la izquierda, seleccione qué grupos de variables desea etiquetar. Solo puede etiquetar un grupo de variables a la vez.

   * **Componentes estándar** : Los componentes estándar son dimensiones y métricas de Analytics integradas que se recopilan de forma predeterminada dentro de una implementación de Analytics.
   * **Variables de conversión** - La variable de conversión de Custom Insight (o eVar) se coloca en el código de Adobe de las páginas web seleccionadas del sitio. Su principal función es segmentar las métricas de éxito de conversión en los informes de marketing personalizados. Un eVar puede basarse en visitas y funcionar de manera similar a las cookies. Los valores pasados a las variables eVar siguen al usuario durante un período de tiempo predeterminado.
   * **Variables de lista** - Las variables de lista son variables personalizadas que se pueden utilizar como desee. Funcionan de manera similar a las eVars, excepto que pueden contener varios valores en la misma visita. Las variables de lista no tienen un límite de caracteres.
   * **Variables de tráfico** - Las variables de tráfico de Custom Insight (o props) permiten correlacionar datos personalizados con eventos específicos relacionados con el tráfico. Las variables prop están incorporadas en el código de implementación de cada página del sitio web.
   * **Eventos de éxito** : los eventos de éxito (también conocidos como eventos de conversión o eventos personalizados) son acciones de las que se puede realizar un seguimiento. Usted determina lo que es un evento de éxito. Por ejemplo, si un visitante compra un artículo, el evento de compra puede considerarse un evento de éxito..
   * **Clasificaciones** : los desgloses de clasificación se utilizan para asignar datos de informes de Analytics a propiedades relacionadas. Las clasificaciones se pueden usar para diversos fines, pero la mayoría de ellas se usan para clasificar códigos de seguimiento de campaña (tanto internos como externos) e ID de producto.

1. Para seleccionar una variable, haga clic en su casilla de verificación y, a continuación, haga clic en **[!UICONTROL Editar etiquetas de privacidad]** en la barra azul que aparece en la parte inferior de la pantalla.

   ![Editar](assets/edit-label.png)

   Esta pantalla muestra las etiquetas aplicadas actualmente y le permite aplicar etiquetas adicionales. Es posible que no pueda aplicar o modificar todas las etiquetas, según el componente.

   ![Etiquetas aplicadas](assets/edit-labels2.png)

   >[!NOTE]
   >
   >El marco de etiquetado y aplicación del uso de los datos (Data Usage Labeling &amp; Enforcement, DULE) se ha diseñado para proporcionar una manera uniforme de recopilar, comunicar y usar metadatos de los datos de soluciones, servicios y plataformas en Adobe Experience Cloud. Los metadatos ayudan a los responsables del tratamiento de datos a indicar qué datos son información personal, cuáles son datos confidenciales y qué restricciones contractuales están asociadas a los datos.

1. Haga clic en **[!UICONTROL Aplicar]** una vez haya completado todo el etiquetado.

