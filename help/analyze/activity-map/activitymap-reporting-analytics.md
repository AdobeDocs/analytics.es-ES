---
description: Describe cómo definir permisos y las dimensiones que están disponibles en Analytics.
title: Informes de Activity Map en Analytics
feature: Activity Map
role: User, Admin
exl-id: 8d7be302-bdfc-4370-b8f0-ab1af1e439ca
source-git-commit: a979fc8787fa96f8fa8317996ac66341a6f54354
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 78%

---

# Informes de Activity Map en Analytics

Describe cómo definir permisos y las dimensiones que están disponibles en Analytics.

## Definición de permisos {#permissions}

Para que los usuarios puedan informar sobre las dimensiones de Activity Map, es necesario que usted, como administrador, realice las acciones siguientes:

* [Añadir usuarios al perfil de producto Acceso de Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* Personalice el acceso de los usuarios a las dimensiones. Consulte la siguiente sección.

## Dimensiones del Activity Map de Analytics {#dimensions}

Puede [personalizar el acceso de los usuarios a las dimensiones](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html) en un nivel granular. A continuación se muestran las dimensiones de Activity Map disponibles en Analytics:

| Dimensión | Descripción |
|---|---|
| Página del Activity Map | Muestra las páginas en las que se hizo clic en un vínculo. |
| Región de Activity Map | Indica todas las regiones de los vínculos recopilados en todo el sitio web. Tenga en cuenta que si una región aparece en varias páginas, la métrica se agregará en todas sus páginas. |
| Vínculos de Activity Map | Indica todos los vínculos recopilados en todo el sitio web. |
| Vínculos y región de Activity Map | Muestra todos los vínculos recogidos y la región a la que pertenecen en todo el sitio Web. |
| Activity Map XY | Sin uso |

* Estas dimensiones deben estar disponibles en Analysis Workspace y Report Builder, siempre que la implementación de Analytics tenga [habilitado para Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* En Analysis Workspace, extraiga las dimensiones relacionadas con Activity Map en un informe.
* Para mirar un vínculo y una región de una página determinada, solo hay que crear un desglose desde la página de Activity Map en cuestión en Vínculos y región de Activity Map.
