---
description: Etiquetar los datos del grupo de informes significa que se asignan etiquetas de identidad, sensibilidad y administración de datos a cada variable de un grupo de informes determinado. Asegúrese de familiarizarse primero con las etiquetas y sus definiciones.
title: Etiquetado de datos de grupos de informes
uuid: a694851c-8933-496e-9118-113cc38cba8a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Etiquetado de datos de grupos de informes

Etiquetar los datos del grupo de informes significa que se asignan etiquetas de identidad, sensibilidad y administración de datos a cada variable de un grupo de informes determinado. Asegúrese de familiarizarse primero con las etiquetas y sus definiciones.

>[!NOTE] Recuerde que el etiquetado debe revisarse cada vez que se crea un nuevo grupo de informes o cuando se activa una nueva variable dentro de un grupo de informes existente. También es posible que tenga que revisar el etiquetado cuando se habiliten nuevas integraciones de soluciones, ya que pueden exponer nuevas variables que pueden requerir etiquetado. Una reimplementación de sus aplicaciones móviles o sitios web puede cambiar la forma en que se utilizan las variables existentes, lo que también puede requerir actualizaciones de las etiquetas.

## Asignación o edición de etiquetas de grupos de informes {#section_39F829F35A274EACA532E2F6FF392996}

**Ejemplo**: Usted, como responsable del tratamiento de datos, pretende recopilar direcciones de correo electrónico e ID de cookie de los interesados para tratar sus solicitudes de privacidad de datos. Estos ID de cookies se almacenan en un grupo de informes en Adobe Analytics. Para crear una etiqueta para las direcciones de correo electrónico y los ID de cookies, debe utilizar el marco de Aplicación y etiquetado del uso de datos (DULE) de la plataforma de Adobe Cloud en Analytics.

1. En Analytics, vaya a **[!UICONTROL Admin]** > **[!UICONTROL Data Governance]** > **[!UICONTROL (select report suite)]**![](assets/privacy_rs_settings.png)

1. Seleccione el grupo de variables que desea etiquetar.

   ![](assets/variables.png)

   * **Dimensiones** estándar (dimensiones integradas de Adobe Analytics)
   * **Métricas** estándar (métricas predeterminadas de Adobe Analytics)
   * **Eventos de conversión** (eventos de éxito personalizados)
   * **Dimensiones de conversión de comercialización** (eVars de comercialización)
   * **Dimensiones** de conversión (eVars sin comercialización)
   * **Dimensiones** de tráfico personalizado (props)
   * **Dimensiones y Eventos** de la solución (dimensiones/eventos relacionados con soluciones como Móvil, Vídeo, Mapa de la Actividad, etc., e integraciones con soluciones como Adobe Campaign, Adobe Experience Manager, Advertising Cloud, etc.)
   * **Dimensiones de procesamiento de datos** (las variables que no están expuestas directamente en la generación de informes mediante la interfaz de Adobe Analytics, pero están disponibles mediante las fuentes de datos o las solicitudes del Data Warehouse)

1. (Opcional) Haga clic en el icono de información (i) junto a cada variable para comprender mejor sus valores más comunes a lo largo de los últimos 90 días. (Esta funcionalidad no está disponible para las dimensiones de procesamiento de datos, ya que no están disponibles en la interfaz de usuario de Analytics).

   ![](assets/info.png)

1. Select one or more variables by clicking their checkbox, then select the **[!UICONTROL Edit]** icon (to the right) to edit one or more variable(s).

   ![](assets/edit.png)

1. El cuadro de diálogo de etiquetas de **datos de identidad** se abre automáticamente. Estas etiquetas clasifican los datos que se pueden usar por sí mismos o en combinación con otros datos para identificar a una persona o permitir ponerse en contacto de forma directa con ella. Para obtener más información sobre estas etiquetas, consulte [Etiquetas de datos de identidad (DULE).](/help/admin/c-data-governance/gdpr-labels.md#identity-data-labels)

   >[!NOTE]
   >
   >El marco de etiquetado y aplicación del uso de los datos (Data Usage Labeling &amp; Enforcement, DULE) se ha diseñado para proporcionar una manera uniforme de recopilar, comunicar y usar metadatos de los datos de soluciones, servicios y plataformas en Adobe Experience Cloud. Los metadatos ayudan a los responsables del tratamiento de datos a indicar qué datos son información personal, cuáles son datos confidenciales y qué restricciones contractuales están asociadas a los datos.

   ![](assets/identity_labels.png)

1. Abra la sección **Datos confidenciales** para establecer las etiquetas de datos confidenciales, la cual organiza por categorías los datos de geolocalización. Para obtener más información sobre estas etiquetas, consulte [Etiquetas de datos confidenciales (DULE).](/help/admin/c-data-governance/gdpr-labels.md#sensitive-data-labels)

   ![](assets/sensitive_data.png)

1. Abra la sección de datos de privacidad de datos para establecer las etiquetas de **Administración de datos**. Utilice esta sección para instruir cómo gestiona Adobe cada variable de solicitudes de eliminación y acceso de privacidad de datos, así como para la definición de qué variables deben analizarse para encontrar ID de interesados para estas solicitudes. Para obtener más información sobre estas etiquetas, consulte [Etiquetas de administración de datos (Privacidad de datos).](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels)

   ![](assets/privacy_labels.png)

1. Click **[!UICONTROL Apply]** once you have completed all labeling.

## Copia de etiquetas en grupos de informes {#section_7C6FDAFF049F4126B84F6261F72668EE}

Si desea aplicar la misma configuración de DULE/Privacidad de datos más de un grupo de informes, puede seguir estos pasos:

1. Seleccione el grupo de variables (dimensiones estándar, dimensiones de conversión, etc.) que contenga la variable que desea copiar. Tenga en cuenta que sólo puede copiar las etiquetas de un grupo de variables a la vez.
1. Seleccione algunas o todas las variables de este grupo.
1. Haga clic en **[!UICONTROL Copy Labels to Report Suite(s)]** en en la parte superior derecha del cuadro de diálogo Gobierno de datos.

   ![](assets/apply_as_template.png)

1. Either check **[!UICONTROL Select All]** to copy labels for the selected variables to all report suites or select the individual report suites that you want to copy the labels to.

   >[!IMPORTANT]
   >
   >Tenga en cuenta que todos los grupos de informes que seleccione deben estar asignados a su organización de Experience Cloud.

   Cuando copia las etiquetas de una variable o establece variables en distintos grupos de informes, la copia se dirige a la variable de la posición correspondiente en el grupo de informes de destino. En el caso de dimensiones estándar, métricas estándar, dimensiones y Eventos de solución y dimensiones de procesamiento de datos, las etiquetas se copiarán en la variable con el **mismo nombre** en el grupo de informes de destino.

   Sin embargo, para las variables de conversión (eVar), las dimensiones de conversión comerciales y las dimensiones de tráfico personalizadas (props), la copia se realizará a la variable con el **mismo número** que el grupo de informes de destino. Por ejemplo, eVar12 se copiará en eVar12 de todos los grupos de informes de destino. Los nombres de estas variables se ignorarán en la determinación del destino de la copia. Si la variable correspondiente no está habilitada en el grupo de informes de destino, la copia fallará para esa variable.

   Cuando copia las etiquetas de las clasificaciones definidas para una variable, las etiquetas se copiarán a una clasificación en la variable correspondiente en el grupo de informes de destino (como eVar7 a eVar7) cuyo nombre es idéntico al de la clasificación que se está copiando. De lo contrario, fallará la copia de las etiquetas de esa clasificación.

   Se muestra un mensaje de estado tras aplicar un conjunto de etiquetas. El mensaje de estado incluirá los nombres de todas las variables o clasificaciones de destino y los grupos de informes para los que se produjo un error en la copia.

   >[!IMPORTANT]
   >
   >Siempre debe comprobar los grupos de informes de destino para garantizar que las etiquetas se copian correctamente. Esto resulta especialmente importante en el caso de variables que tienen etiquetas de ID o DEL.

1. Haga clic en **[!UICONTROL Apply]**.

