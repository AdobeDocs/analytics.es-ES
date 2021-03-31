---
description: Describe cómo definir permisos y las dimensiones que están disponibles en Analytics.
title: Informes de Activity Map en Analytics
uuid: 057c6ab2-aa06-4779-ac16-f9b367d9ea43
feature: Activity Map
role: Profesional empresarial, administrador
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 98%

---


# Informes de Activity Map en Analytics

Describe cómo definir permisos y las dimensiones que están disponibles en Analytics.

## Definir permisos {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

Para que los usuarios puedan informar sobre las dimensiones de Activity Map, es necesario que usted, como administrador, realice las acciones siguientes:

* [Agregar usuarios al grupo de acceso de Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* Agregar los grupos de informes que desea que tengan acceso a este grupo. Vaya a **[!UICONTROL Administración]** > **[!UICONTROL Administración de usuarios]** > **[!UICONTROL Grupos]** > **[!UICONTROL Acceso a Activity Map]** > **[!UICONTROL Editar]**.
* Personalice el acceso de los usuarios a las dimensiones. Consulte la siguiente sección.

## Dimensiones de Activity Map de Analytics {#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

Puede [personalizar el acceso de los usuarios a las dimensiones](https://docs.adobe.com/content/help/es-ES/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html) en un nivel granular. A continuación se muestran las dimensiones de Activity Map disponibles en Analytics:

| Dimensión | Descripción |
|---|---|
| Página de Activity Map | Muestra las páginas en las que se hizo clic en un vínculo. |
| Región de Activity Map | Indica todas las regiones de los vínculos recopilados en todo el sitio web. Tenga en cuenta que si una región aparece en varias páginas, la métrica se agregará en todas sus páginas. |
| Vínculos de Activity Map | Indica todos los vínculos recopilados en todo el sitio web. |
| Vínculos y región de Activity Map | Muestra todos los vínculos recogidos y la región a la que pertenecen en todo el sitio Web. |
| Activity Map XY | Sin uso |

* Estas dimensiones deberían estar disponibles en Analysis Workspace, Reports &amp; Analytics y el Report Builder, siempre que la implementación de Analytics tenga [Activity Map activado](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* En Reports &amp; Analytics, vaya a **[!UICONTROL Ver todos los informes]** > **[!UICONTROL Activity Map]**.

* Para mirar un vínculo y una región de una página determinada, solo hay que crear un desglose desde la página de Activity Map en cuestión en Vínculos y región de Activity Map.

