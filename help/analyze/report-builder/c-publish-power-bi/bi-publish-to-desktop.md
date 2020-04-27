---
description: Explica cómo extraer activos publicados en Report Builder a Power BI Desktop
title: Extraer activos publicados a Power BI Desktop
uuid: ef47d5c7-31e0-44fc-a792-bc9d12bb089e
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Extraer activos publicados a Power BI Desktop

Explica cómo extraer activos publicados en Report Builder a Power BI Desktop

## Requisitos previos {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* Debe tener instalada la versión más reciente de Power BI Desktop (versión de abril de 2017)
* Este proceso supone que ya ha publicado en el Servicio de Power BI tablas o solicitudes con el formato de Report Builder.

## Proceso {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

En la actualización de abril de 2017 de Power BI Desktop, Microsoft incluyó la capacidad de conectar con conjuntos de datos en el Servicio de Power BI. Esta función le permite crear nuevos informes a partir de conjuntos de datos existentes que ya haya publicado en la nube. Puede aprovechar esta función para mejorar la colaboración y reducir los casos de esfuerzos duplicados en el equipo.

1. En Power BI Desktop, vaya a **[!UICONTROL File]** > **[!UICONTROL Options and settings]** > **[!UICONTROL Options]** > **[!UICONTROL Preview features.]**
1. Habilite **[!UICONTROL Power BI Service Live Connection]** y haga clic en **[!UICONTROL OK]**. ![](assets/bi-preview-features.png)

1. Reinicie Power BI Desktop.
1. Una vez que haya reiniciado el escritorio, vaya a **[!UICONTROL Home]** > **[!UICONTROL Get Data]** > **[!UICONTROL More...]**.
1. Busque y seleccione **[!UICONTROL Power BI service]**.
1. En **[!UICONTROL Microsoft Power BI service]** > **[!UICONTROL My Workspace]**, seleccione el conjunto de datos que ha publicado anteriormente desde el Creador de informes.

Para obtener más información, consulte esta [publicación en el blog de Microsoft](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/).
