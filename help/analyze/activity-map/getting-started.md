---
title: Introducción a Activity Map
description: Introducción a la superposición y las dimensiones de Activity Map.
feature: Activity Map
role: User, Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
source-git-commit: a7670fcda3e8e6af0c036c8b263746e142278255
workflow-type: ht
source-wordcount: '872'
ht-degree: 100%

---

# Introducción a Activity Map

Activity Map en Adobe Analytics consta de cuatro elementos principales:

* **Configuración del grupo de informes**: debe habilitar Activity Map en la configuración del grupo de informes. Cuando se habilita, el grupo de informes crea varias variables reservadas para dimensiones y métricas de Activity Map.
* **Implementación**: Recopile datos de Activity Map en su sitio web o propiedad. La personalización del modo en que se recopilan los datos puede mejorar la calidad y la experiencia de los informes.
* **Dimensiones y métricas de Workspace**: Cuando la implementación esté configurada correctamente, puede usar dimensiones y métricas de Activity Map en Analysis Workspace.
* **Superposición**: Adobe ofrece una extensión para el explorador para ver los datos de Activity Map en el contexto del sitio web. Esta función no está disponible para implementaciones de SDK web.

## Habilite la configuración del grupo de informes

Los grupos de informes deben tener habilitados los informes de Activity Map para que pueda empezar a recopilar datos. Si la implementación envía datos de Activity Map a un grupo de informes sin la creación de informes de Activity Map habilitada, los datos de Activity Map no se incluyen en la visita.

**[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > Seleccionar grupo de informes > **[!UICONTROL Editar configuración]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Informes de Activity Map]** > **[!UICONTROL Habilitar informes de Activity Map]**

Al habilitar los informes de Activity Map, se crean varias variables reservadas del servidor. Consulte [Creación de informes de Activity Map](/help/admin/tools/manage-rs/edit-settings/activity-map.md) en la guía del administrador de Adobe Analytics para obtener más información.

## Instalación de código

Su implementación debe estar configurada correctamente para enviar datos de Activity Map a Adobe. La extensión del explorador de superposiciones no está disponible cuando Adobe Analytics se implementa con SDK web.

+++Extensión de etiquetas del SDK web

La recopilación de datos de Activity Map requiere la extensión **[!UICONTROL Adobe Experience Platform SDK web]** v2.23 o posterior. Las versiones de extensión anteriores a v2.16 tienen compatibilidad limitada. Estas versiones de extensiones anteriores envían datos de Activity Map en un evento independiente del resto de los datos. Este evento adicional aumenta el número de visitas que envía a Adobe Analytics o Adobe Experience Platform.

El parámetro de configuración **[!UICONTROL Recopilación de datos de clics]** administra la recopilación de datos de Activity Map y suele estar habilitado de manera predeterminada. Puede comprobar que está activado en los ajustes de configuración de la extensión:

1. Inicie sesión en [experience.adobe.com](https://experience.adobe.com)
1. Seleccione **[!UICONTROL Recopilación de datos]** en el menú de acceso rápido o el selector de productos en la parte superior derecha.
1. Seleccione **[!UICONTROL Etiquetas]** en el menú de navegación izquierdo.
1. Seleccione la etiqueta que desee editar.
1. Seleccione **[!UICONTROL Extensiones]** en el menú de navegación izquierdo.
1. Seleccione **[!UICONTROL Adobe Experience Platform SDK web]** en la lista de extensiones instaladas y, a continuación, seleccione **[!UICONTROL Configurar]** en la parte derecha.
1. Busque la sección con la etiqueta [!UICONTROL Recopilación de datos] y asegúrese de que la casilla de verificación **[!UICONTROL Habilitar la recopilación de datos de clics]** esté habilitada.
1. Seleccione **[!UICONTROL Guardar]**.
1. Si es necesario, cree los cambios en una biblioteca y publíquelos en producción.

Consulte [Configurar la extensión de etiquetas SDK web](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration#data-collection) para obtener más información.

+++

+++Biblioteca JavaScript SDK web (`alloy.js`)

La recopilación de datos de Activity Map requiere la biblioteca de JavaScript SDK web v2.20 o posterior. Las versiones de la biblioteca anteriores a v2.15 tienen compatibilidad limitada. Estas versiones de bibliotecas anteriores envían datos de Activity Map en un evento independiente del resto de los datos. Este evento adicional aumenta el número de visitas que envía a Adobe Analytics o Adobe Experience Platform.

La variable de configuración SDK web [`clickCollectionEnabled`](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/commands/configure/clickcollectionenabled) administra la recopilación automática de datos de Activity Map. Está habilitado de forma predeterminada a menos que se haya deshabilitado expresamente.

```js
alloy("configure", {
  datastreamId: "ebebf826-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg",
  clickCollectionEnabled: true
});
```

+++

+++Extensión de etiquetas de Adobe Analytics

La opción de configuración **[!UICONTROL Usar Activity Map]** administra la recopilación de datos de Activity Map y suele estar habilitada de forma predeterminada. Está disponible para todas las extensiones de etiquetas v1.9.0 o posteriores. Puede comprobar que está activado en los ajustes de configuración de la extensión:

1. Inicie sesión en [experience.adobe.com](https://experience.adobe.com)
1. Seleccione **[!UICONTROL Recopilación de datos]** en el menú de acceso rápido o el selector de productos en la parte superior derecha.
1. Seleccione **[!UICONTROL Etiquetas]** en el menú de navegación izquierdo.
1. Seleccione la etiqueta que desee editar.
1. Seleccione **[!UICONTROL Extensiones]** en el menú de navegación izquierdo.
1. Seleccione **[!UICONTROL Adobe Analytics]** en la lista de extensiones instaladas y, a continuación, seleccione **[!UICONTROL Configurar]** en la parte derecha.
1. Asegúrese de que la casilla de verificación **[!UICONTROL Usar Activity Map]** esté habilitada.
1. Seleccione **[!UICONTROL Guardar]**.
1. Si es necesario, cree los cambios en una biblioteca y publíquelos en producción.

Consulte la [Información general de la extensión de Adobe Analytics](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/analytics/overview) para obtener más información.

+++

+++Biblioteca JavaScript de Adobe Analytics (`AppMeasurement.js`)

El módulo Activity Map administra la recopilación de datos de Activity Map y se incluye con todas las bibliotecas de AppMeasurement versión 1.6 o posteriores. Puede inspeccionar el archivo `AppMeasurement.js` para asegurarse de que esté incluido.

1. Vaya a la [Última versión de Adobe Analytics AppMeasurement](https://github.com/adobe/appmeasurement/releases/latest) en GitHub.
1. Descargue el archivo de la biblioteca comprimido AppMeasurement y, a continuación, abra el archivo `AppMeasurement.js` que contiene.
1. El módulo Activity Map está incluido cerca de la parte superior de este archivo. Asegúrese de que este módulo esté incluido en la biblioteca de AppMeasurement que utiliza su sitio.

+++

## Dimensiones disponibles

Cuando Activity Map está habilitado tanto para el grupo de informes como para la implementación, puede empezar a utilizar las siguientes dimensiones en Analysis Workspace:

* [[!UICONTROL Vínculo de Activity Map]](/help/components/dimensions/activity-map-link.md)
* [[!UICONTROL Región de Activity Map]](/help/components/dimensions/activity-map-region.md)
* [[!UICONTROL Página de Activity Map]](/help/components/dimensions/activity-map-page.md)
* [[!UICONTROL Vínculo de Activity Map por región]](/help/components/dimensions/activity-map-link-by-region.md)

## Descargue e instale la extensión o el complemento del explorador

Además de las dimensiones disponibles en Analysis Workspace, también puede ver los datos de Activity Map como una superposición en el sitio web. Para ver esta superposición, descargue e instale la extensión o el complemento del explorador Activity Map.

**[!UICONTROL Herramientas]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Descargar Activity Map]**

Este vínculo le redirige a la extensión compatible del explorador o al marketplace de complementos donde puede instalarlo. Una vez instalada, la extensión o complemento aparecerá en la parte superior derecha del explorador, donde podrá iniciar sesión y habilitar la superposición.
