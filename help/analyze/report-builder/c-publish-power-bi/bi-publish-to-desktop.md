---
description: Explica cómo extraer activos publicados en el Creador de informes a Power BI Desktop
title: Extraer activos publicados a Power BI Desktop
uuid: ef47d5c7-31e0-44fc-a792-bc9d12bb089e
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Extraer activos publicados a Power BI Desktop

Explica cómo extraer activos publicados en el Creador de informes a Power BI Desktop

## Requisitos previos {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* Debe tener instalada la versión más reciente de Power BI Desktop (versión de abril de 2017)
* Este proceso supone que ya ha publicado en el Servicio de Power BI tablas o solicitudes con el formato del Creador de informes.

## Proceso {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

En la actualización de abril de 2017 de Power BI Desktop, Microsoft incluyó la capacidad de conectar con conjuntos de datos en el Servicio de Power BI. Esta función le permite crear nuevos informes a partir de conjuntos de datos existentes que ya haya publicado en la nube. Puede aprovechar esta función para mejorar la colaboración y reducir los casos de esfuerzos duplicados en el equipo.

1. In Power BI Desktop, go to **[!UICONTROL File]** &gt; **[!UICONTROL Options and settings]** &gt; **[!UICONTROL Options]** &gt; **[!UICONTROL Preview features.]**
1. Habilite **[!UICONTROL Conexión dinámica al Servicio de Power BI]** y haga clic en **[!UICONTROL Aceptar]**. ![](assets/bi-preview-features.png)

1. Reinicie Power BI Desktop.
1. **[!UICONTROL Una vez que haya reiniciado el escritorio, vaya a]** Inicio **[!UICONTROL &gt;]** Obtener datos **[!UICONTROL &gt;]** Más....
1. Busque y seleccione **[!UICONTROL Servicio de Power BI]**.
1. Under **[!UICONTROL Microsoft Power BI service]** &gt; **[!UICONTROL My Workspace]**, select the dataset that you had previously published from Report Builder.

Para obtener más información, consulte esta [publicación en el blog de Microsoft](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/).
