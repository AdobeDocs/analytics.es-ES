---
description: Describe cómo definir permisos y las dimensiones que están disponibles en Analytics.
title: Informes de Activity Map en Analytics
feature: Activity Map
role: User, Admin
exl-id: 8d7be302-bdfc-4370-b8f0-ab1af1e439ca
source-git-commit: 4af73d19afd8844f814aafd45153cc638aa535d6
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 92%

---

# Informes de Activity Map en Analytics

Describe cómo definir permisos y las dimensiones que están disponibles en Analytics.

## Definir permisos {#permissions}

Para que los usuarios puedan informar sobre las dimensiones de Activity Map, es necesario que usted, como administrador, realice las acciones siguientes:

* [Añadir usuarios al perfil de producto Acceso de Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* Personalice el acceso de los usuarios a las dimensiones. Consulte la siguiente sección.

## Dimensiones de Activity Map de Analytics {#dimensions}

Puede [personalizar el acceso de los usuarios a las dimensiones](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html) en un nivel granular. A continuación se muestran las dimensiones de Activity Map disponibles en Analytics:

| Dimensión | Descripción |
|---|---|
| Activity Map Activity Map | Muestra las páginas en las que se hizo clic en un vínculo. |
| Región de Activity Map | Indica todas las regiones de los vínculos recopilados en todo el sitio web. Tenga en cuenta que si una región aparece en varias páginas, la métrica se agregará en todas sus páginas. |
| Vínculos de Activity Map | Indica todos los vínculos recopilados en todo el sitio web. |
| Vínculos y región de Activity Map | Muestra todos los vínculos recogidos y la región a la que pertenecen en todo el sitio Web. |
| Activity Map XY | Sin uso |

* Estas dimensiones deberían estar disponibles en Analysis Workspace, Reports &amp; Analytics y el Report Builder, siempre que la implementación de Analytics tenga [Activity Map activado](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* En Reports &amp; Analytics, vaya a **[!UICONTROL Ver todos los informes]** > **[!UICONTROL Activity Map]**.
* Para mirar un vínculo y una región de una página determinada, solo hay que crear un desglose desde la página de Activity Map en cuestión en Vínculos y región de Activity Map.
