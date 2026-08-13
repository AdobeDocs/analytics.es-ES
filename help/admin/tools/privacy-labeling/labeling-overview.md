---
description: Al etiquetar los datos de los grupos de informes, se asignan etiquetas de identidad, confidencialidad y gobernanza de datos a cada variable de un grupo de informes determinado.
title: Información general sobre etiquetado de privacidad
feature: Data Governance
role: Admin
exl-id: d1bd833c-3fd4-4572-a5dc-d7bab8a79cb8
TQID: https://experienceleague.adobe.com/xEs37qiYjTVJWRDKa7HwJqfTtyBYKstA6ehq1-0qKt0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: b8734a57-d5fb-44a8-8ee1-65225cecaeaeid: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2: id: b22bc0f7-b089-4966-95a1-31e7b3b69b79id: b99602d0-836e-4dbb-979f-c0dec53f883cid: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 534
ht-degree: 98%

---

# Información general sobre etiquetado de privacidad

Al etiquetar los datos de los grupos de informes, se asignan etiquetas de identidad, confidencialidad y gobernanza de datos a cada variable de un grupo de informes determinado. Asegúrese de familiarizarse primero con las [etiquetas y sus definiciones](/help/admin/tools/privacy-labeling/labels.md).

>[!NOTE]
>
>Recuerde que el etiquetado debe revisarse cada vez que se crea un nuevo grupo de informes o cuando se habilita una nueva variable dentro de un grupo de informes existente. También es posible que necesite revisar el etiquetado cuando se habiliten nuevas integraciones de la solución, ya que pueden exponer nuevas variables que pueden requerir etiquetado. Una reimplementación de sus aplicaciones móviles o sitios web puede cambiar la forma en la que se utilizan las variables existentes, las cuales también pueden necesitar la actualización de las etiquetas.

## Asignación o edición de etiquetas de privacidad de grupos de informes {#assign-edit}

**Ejemplo**: usted, como responsable del tratamiento de datos, pretende recopilar direcciones de correo electrónico e ID de cookie de los interesados para tratar sus solicitudes de privacidad de datos. Estos ID de cookie se almacenan en un grupo de informes en Adobe Analytics.

1. En Adobe Analytics, vaya a **[!UICONTROL Administrador]** > **[!UICONTROL Todos los administradores]** > **[!UICONTROL Configuración y recopilación de datos]** > **[!UICONTROL gobernanza de datos]**.

   ![Etiquetado de privacidad](assets/privacy_rs_settings.png)

1. Seleccione un grupo de informes en el selector **[!UICONTROL Grupos de informes]** situado en la parte superior.

1. En la sección de filtro de la izquierda, seleccione qué grupos de variables desea etiquetar. Solo puede etiquetar un grupo de variables a la vez.

   * **Componentes estándar**: los componentes estándar son dimensiones y métricas de Analytics integradas que se recopilan de forma predeterminada dentro de una implementación de Analytics.
   * **Variables de conversión**: la variable de conversión de Custom Insight (o eVar) se coloca en el código de Adobe en las páginas web del sitio seleccionadas. Su principal función es segmentar las métricas de éxito de conversión en los informes de marketing personalizados. Una eVar puede basarse en visitas y funcionar de modo similar a las cookies. Los valores pasados a las variables eVar siguen al usuario durante un período de tiempo predeterminado.
   * **Variables de lista**: las variables de lista son variables personalizadas que se pueden utilizar como desee. Funcionan de manera similar a las eVars, excepto que pueden contener varios valores en la misma visita. Las variables de lista no tienen un límite de caracteres.
   * **Variables de tráfico**: las variables (o props) de tráfico de Custom Insight permiten correlacionar datos personalizados con eventos específicos relacionados con el tráfico. Las variables prop están incorporadas en el código de implementación de cada página del sitio web.
   * **Eventos de éxito**: los eventos de éxito (también conocidos como eventos de conversión o eventos personalizados) son acciones de las que se puede realizar un seguimiento. Usted determina lo que es un evento de éxito. Por ejemplo, si un visitante compra un artículo, el evento de compra podría considerarse un evento de éxito.
   * **Clasificaciones**: los desgloses de clasificación se utilizan para asignar datos de informes de Analytics a propiedades relacionadas. Las clasificaciones pueden utilizarse para distintos fines, pero el más común es la clasificación de los códigos de seguimiento de campaña (tanto internos como externos) y los ID de productos.

1. Para seleccionar una variable, haga clic en su casilla de verificación y, a continuación, haga clic en **[!UICONTROL Editar etiquetas de privacidad]** en la barra azul que aparece en la parte inferior de la pantalla.

   ![Editar](assets/edit-label.png)

   Esta pantalla muestra las etiquetas aplicadas actualmente y le permite aplicar etiquetas adicionales. Es posible que no pueda aplicar o modificar todas las etiquetas, según el componente.

   ![Etiquetas aplicadas](assets/edit-labels2.png)

1. Haga clic en **[!UICONTROL Aplicar]** una vez haya completado todo el etiquetado.

