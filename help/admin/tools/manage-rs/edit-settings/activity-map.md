---
description: Habilite dimensiones para que Activity Map pueda recopilar datos.
title: Informar sobre Activity Map
feature: Admin Tools
exl-id: 9300c12e-3ade-4850-8a22-cba61b35ca67
TQID: https://experienceleague.adobe.com/GiBhdUMAX5P9zxxDAVUZPcaeKpnezKvDn3MB0g95DH0
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 170
ht-degree: 31%

---

# Informar sobre Activity Map

Permite habilitar dimensiones para usarlas con [Activity Map](/help/analyze/activity-map/overview.md).

**[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > Seleccionar grupo de informes > **[!UICONTROL Editar configuración]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Informes de Activity Map]**

Esta sección de la documentación de se centra en la activación de dimensiones que utiliza Activity Map. Consulte [Información general de Activity Map](/help/analyze/activity-map/overview.md) para obtener más información sobre la superposición, las variables de implementación y las dimensiones.

Al seleccionar el botón **[!UICONTROL Habilitar informes de Activity Map]**, se crean las siguientes dimensiones:

* [[!UICONTROL Vínculo de Activity Map]](/help/components/dimensions/activity-map-link.md): El nombre del vínculo donde se hizo clic.
* [[!UICONTROL Región de Activity Map]](/help/components/dimensions/activity-map-region.md): El nombre de la región donde se hizo clic.
* [[!UICONTROL Página de Activity Map]](/help/components/dimensions/activity-map-page.md): El nombre de la página en el momento en que se hizo clic en el vínculo.
* [[!UICONTROL Vínculo de Activity Map por región]](/help/components/dimensions/activity-map-link-by-region.md): Un valor concatenado de vínculo de Activity Map y la región de Activity Map.

Una vez habilitada, la implementación puede empezar a enviar datos a estas dimensiones para usarlos en [Analysis Workspace](/help/analyze/analysis-workspace/home.md) y en la [superposición de la extensión del explorador](/help/analyze/activity-map/overlay/overview.md).

>[!NOTE]
>
>Al habilitar Activity Map para un grupo de informes, se habilita de forma permanente sin ninguna forma de deshabilitarlo en el futuro.
