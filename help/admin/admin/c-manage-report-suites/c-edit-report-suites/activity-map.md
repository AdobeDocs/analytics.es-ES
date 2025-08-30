---
description: Habilite dimensiones para que Activity Map pueda recopilar datos.
title: Informes del Activity Map
feature: Admin Tools
exl-id: 9300c12e-3ade-4850-8a22-cba61b35ca67
source-git-commit: 24101efe2b860734c9d176ba8be8f17e26429442
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 3%

---

# Informes del Activity Map

Permite habilitar dimensiones para usarlas con [Activity Map](/help/analyze/activity-map/overview.md).

**[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > Seleccionar grupo de informes > **[!UICONTROL Editar configuración]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Informes de Activity Map]**

Esta sección de la documentación de se centra en la activación de dimensiones que utiliza Activity Map. Consulte [Información general de Activity Map](/help/analyze/activity-map/overview.md) para obtener más información sobre la superposición, las variables de implementación y las dimensiones.

Al seleccionar el botón **[!UICONTROL Habilitar informes de Activity Map]**, se crean las siguientes dimensiones:

* [[!UICONTROL Vínculo de Activity Map]](/help/components/dimensions/activity-map-link.md): El nombre del vínculo donde se hizo clic.
* [[!UICONTROL Región de Activity Map]](/help/components/dimensions/activity-map-region.md): El nombre de región donde se hizo clic.
* [[!UICONTROL Página de Activity Map]](/help/components/dimensions/activity-map-page.md): El nombre de la página en el momento en que se hizo clic en el vínculo.
* [[!UICONTROL Vínculo de Activity Map por región]](/help/components/dimensions/activity-map-link-by-region.md): Un valor concatenado de Vínculo de Activity Map y Región de Activity Map.

Una vez habilitada, la implementación puede empezar a enviar datos a estas dimensiones para usarlos en [Analysis Workspace](/help/analyze/analysis-workspace/home.md) y en la [superposición de la extensión del explorador](/help/analyze/activity-map/overlay/overview.md).

>[!NOTE]
>
>Al habilitar Activity Map para un grupo de informes, se habilita de forma permanente sin ninguna forma de deshabilitarlo en el futuro.
