---
description: Describe cómo definir permisos y las dimensiones que están disponibles en Analytics.
seo-description: Describe cómo definir permisos y las dimensiones que están disponibles en Analytics.
seo-title: Informes de [!DNL Activity Map] en Analytics
solution: Analytics
title: Informes de [!DNL Activity Map] en Analytics
topic: Activity Map
uuid: 057c6ab2-aa06-4779-ac16-f9b367d9ea43
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# [!DNL Activity Map] informes en Analytics

Describe cómo definir permisos y las dimensiones que están disponibles en Analytics.

## Set permissions {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

Before users can report on [!DNL Activity Map] dimensions, you as the Admin need to

* [Agregue usuarios al grupo](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md)de acceso [!DNL Activity Map].
* Agregar los grupos de informes que desea que tengan acceso a este grupo. Navigate to **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** &gt; **[!UICONTROL Groups]** &gt; **[!UICONTROL [!DNL Activity Map]Access]** &gt; **[!UICONTROL Edit]**.
* Personalice el acceso de los usuarios a las dimensiones. Consulte la siguiente sección.

## Dimensiones de Analytics [!DNL Activity Map]{#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

Puede [personalizar el acceso de los usuarios a las dimensiones](https://marketing.adobe.com/resources/help/en_US/reference/groups-dimensions.html) en un nivel granular. Here are the [!DNL Activity Map] dimensions available in Analytics:

| Dimensión | Descripción |
|---|---|
| [!DNL Activity Map]Activity Map | Muestra las páginas en las que se hizo clic en un vínculo. |
| [!DNL Activity Map] Región | Indica todas las regiones de los vínculos recopilados en todo el sitio web. Tenga en cuenta que si una región aparece en varias páginas, la métrica se agregará en todas sus páginas. |
| [!DNL Activity Map] Vínculos | Indica todos los vínculos recopilados en todo el sitio web. |
| [!DNL Activity Map] Vínculos y región | Indica todos los vínculos recopilados con la región correspondiente en todo el sitio web. |
| [!DNL Activity Map] XY | Sin uso |

* Estas dimensiones deberían estar disponibles en Analysis Workspace, Reports &amp; Analytics y el Report Builder, siempre que la implementación de Analytics tenga [enabled for [!DNL Activity Map]](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* In Reports &amp; Analytics, navigate to **[!UICONTROL View All Reports]** &gt; **[!UICONTROL [!DNL Activity Map]]**.

* To look at a link and region for a specific page, all you need to do is create a breakdown from the desired [!DNL Activity Map] page into the [!DNL Activity Map] Links &amp; Region.

