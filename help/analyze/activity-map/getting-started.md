---
title: Introducción a Activity Map
description: Empiece a utilizar la superposición y las dimensiones del Activity Map.
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: bfafc1f8eddf82b34fb45e3d6197213f0cee0d97
workflow-type: tm+mt
source-wordcount: '847'
ht-degree: 0%

---

# Introducción a Activity Map

Activity Map de Adobe Analytics consta de cuatro elementos principales:

* **Configuración del grupo de informes**: debe habilitar el Activity Map en la configuración del grupo de informes. Cuando se habilita, el grupo de informes crea varias variables reservadas para dimensiones y métricas de Activity Map.
* **Implementación**: recopile datos del Activity Map en su sitio web o propiedad. La personalización del modo en que se recopilan los datos puede mejorar la calidad y la experiencia de los informes.
* **Dimensiones y métricas de Workspace**: Cuando la implementación esté configurada correctamente, puede usar dimensiones y métricas de Activity Map en Analysis Workspace.
* **Superposición**: El Adobe ofrece una extensión de explorador para ver los datos del Activity Map en el contexto del sitio web.

## Habilitar la configuración de grupos de informes

Los grupos de informes deben tener habilitados los informes de Activity Map para que pueda empezar a recopilar datos. Si la implementación envía datos de Activity Map a un grupo de informes sin la creación de informes de Activity Map habilitada, los datos de Activity Map no se incluyen en la visita.

**[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > Seleccionar grupo de informes > **[!UICONTROL Editar configuración]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Informes de Activity Map]** > **[!UICONTROL Habilitar informes de Activity Map]**

Al habilitar los informes de Activity Map, se crean varias variables reservadas de back-end. Consulte [Informes de Activity Map](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/activity-map.md) en la guía de administración de Adobe Analytics para obtener más información.

## Instalación de código

La implementación debe configurarse correctamente para enviar los datos del Activity Map al Adobe.

+++Extensión de etiqueta de SDK web

La recopilación de datos de Activity Map requiere la extensión **[!UICONTROL Adobe Experience Platform Web SDK]** v2.23 o posterior. Las versiones de extensión anteriores a v2.16 tienen compatibilidad limitada. Estas versiones de extensiones anteriores envían datos de Activity Map en un evento independiente del resto de los datos. Este evento adicional aumenta el número de visitas que envía a Adobe Analytics o Adobe Experience Platform.

El parámetro de configuración **[!UICONTROL Click data collection]** administra la recopilación de datos del Activity Map y suele estar habilitado de forma predeterminada. Puede comprobar que está activado en los ajustes de configuración de la extensión:

1. Inicie sesión en [experience.adobe.com](https://experience.adobe.com)
1. Seleccione **[!UICONTROL Recopilación de datos]** en el menú de acceso rápido o el selector de productos en la parte superior derecha.
1. Seleccione **[!UICONTROL Etiquetas]** en el menú de navegación de la izquierda.
1. Seleccione la etiqueta que desee editar.
1. Seleccione **[!UICONTROL Extensiones]** en el menú de navegación de la izquierda.
1. Seleccione **[!UICONTROL Adobe Experience Platform Web SDK]** en la lista de extensiones instaladas y, a continuación, seleccione **[!UICONTROL Configure]** a la derecha.
1. Busque la sección con la etiqueta [!UICONTROL Recopilación de datos] y asegúrese de que la casilla de verificación **[!UICONTROL Habilitar la recopilación de datos con clic]** esté habilitada.
1. Seleccione **[!UICONTROL Guardar]**.
1. Si es necesario, cree los cambios en una biblioteca y publíquelos en producción.

Consulte [Configurar la extensión de etiquetas del SDK web](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration#data-collection) para obtener más información.

+++

+++Biblioteca JavaScript del SDK web (`alloy.js`)

La recopilación de datos de Activity Map requiere la biblioteca JavaScript v2.20 o posterior del SDK web. Las versiones de la biblioteca anteriores a v2.15 tienen compatibilidad limitada. Estas versiones de biblioteca anteriores envían datos de Activity Map en un evento independiente del resto de los datos. Este evento adicional aumenta el número de visitas que envía a Adobe Analytics o Adobe Experience Platform.

La variable de configuración [`clickCollectionEnabled`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) del SDK web administra la recopilación automática de datos del Activity Map. Está habilitado de forma predeterminada a menos que esté deshabilitado explícitamente.

```js
alloy("configure", {
  datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg",
  clickCollectionEnabled: true
});
```

+++

Extensión de etiqueta +++Adobe Analytics

El parámetro de configuración **[!UICONTROL Usar Activity Map]** administra la recopilación de datos del Activity Map y suele estar habilitado de forma predeterminada. Está disponible para todas las extensiones de etiquetas v1.9.0 o posteriores. Puede comprobar que está activado en los ajustes de configuración de la extensión:

1. Inicie sesión en [experience.adobe.com](https://experience.adobe.com)
1. Seleccione **[!UICONTROL Recopilación de datos]** en el menú de acceso rápido o el selector de productos en la parte superior derecha.
1. Seleccione **[!UICONTROL Etiquetas]** en el menú de navegación de la izquierda.
1. Seleccione la etiqueta que desee editar.
1. Seleccione **[!UICONTROL Extensiones]** en el menú de navegación de la izquierda.
1. Seleccione **[!UICONTROL Adobe Analytics]** en la lista de extensiones instaladas y, a continuación, seleccione **[!UICONTROL Configure]** a la derecha.
1. Asegúrese de que la casilla de verificación **[!UICONTROL Usar Activity Map]** esté habilitada.
1. Seleccione **[!UICONTROL Guardar]**.
1. Si es necesario, cree los cambios en una biblioteca y publíquelos en producción.

Consulte la [descripción general de la extensión de Adobe Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview) para obtener más información.

+++

+++Biblioteca JavaScript de Adobe Analytics (`AppMeasurement.js`)

El módulo Activity Map gestiona la recopilación de datos del Activity Map y se incluye con todas las bibliotecas de AppMeasurement v1.6 o posteriores. Puede inspeccionar el archivo `AppMeasurement.js` para asegurarse de que se incluye.

1. Vaya a la [Última versión del AppMeasurement de Adobe Analytics](https://github.com/adobe/appmeasurement/releases/latest) en GitHub.
1. Descargue el archivo de biblioteca de AppMeasurement comprimido y, a continuación, abra `AppMeasurement.js` contenido en él.
1. El módulo Activity Map se incluye cerca de la parte superior de este archivo. Asegúrese de que este módulo esté incluido en la biblioteca de AppMeasurementes que utiliza su sitio.

+++

## Dimensiones disponibles

Cuando Activity Map está habilitado tanto para el grupo de informes como para la implementación, puede empezar a utilizar las siguientes dimensiones en Analysis Workspace:

* [[!UICONTROL Vínculo de Activity Map]](/help/components/dimensions/activity-map-link.md)
* [[!UICONTROL Región Activity Map]](/help/components/dimensions/activity-map-region.md)
* [[!UICONTROL Página de Activity Map]](/help/components/dimensions/activity-map-page.md)
* [[!UICONTROL Vínculo De Activity Map Por Región]](/help/components/dimensions/activity-map-link-by-region.md)

## Descargue e instale la extensión o el complemento del explorador

Además de las dimensiones disponibles en Analysis Workspace, también puede ver los datos del Activity Map como una superposición en el sitio web. Para ver esta superposición, descargue e instale la extensión o el complemento del explorador Activity Map.

**[!UICONTROL Herramientas]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map de descarga]**

Este vínculo le lleva a la extensión compatible del explorador o al marketplace de complementos donde puede instalarlo. Una vez instalada, la extensión o el complemento aparece en la parte superior derecha del explorador, donde puede iniciar sesión y habilitar la superposición.
