---
description: Explica cómo extraer activos publicados en Report Builder a Power BI Desktop
title: Extraer activos publicados a Power BI Desktop
feature: Report Builder
role: User, Admin
exl-id: ce6020df-caf4-4cd2-8086-4357309e5bbb
TQID: https://experienceleague.adobe.com/fS1xnUciNh8LdPw2ENYMJTDGLqo3C8u4lu39X-GYuZE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 222
ht-degree: 69%

---

# Extraer activos publicados a Power BI Desktop

{{legacy-arb}}

Explica cómo extraer activos publicados en Report Builder a Power BI Desktop

## Requisitos previos {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* Debe tener instalada la última versión de Power BI Desktop (versión de abril de 2017)
* Este proceso supone que ya ha publicado en el Servicio de Power BI tablas o solicitudes con el formato de Report Builder.

## Proceso {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

En la actualización de abril de 2017 de Power BI Desktop, Microsoft lanzó la capacidad de conectarse a conjuntos de datos en el servicio de Power BI. Esta función le permite crear nuevos informes de conjuntos de datos existentes que ya ha publicado en la nube. Puede aprovechar esta función para colaborar mejor y reducir los esfuerzos de duplicado en todo el equipo.

1. En Power BI Desktop, vaya a **[!UICONTROL Archivo]** > **[!UICONTROL Opciones y configuración]** > **[!UICONTROL Opciones]** > **[!UICONTROL Características de vista previa.]**
1. Habilite **[!UICONTROL Conexión dinámica al Servicio de Power BI]** y haga clic en **[!UICONTROL Aceptar]**. ![Haga clic en Conexión dinámica al Servicio de Power BI y a continuación haga clic en Aceptar.](assets/bi-preview-features.png)

1. Reinicie Power BI Desktop.
1. Una vez que haya reiniciado el escritorio, vaya a **[!UICONTROL Inicio]** > **[!UICONTROL Obtener datos]** > **[!UICONTROL Más...]**.
1. Busque y seleccione **[!UICONTROL Servicio de Power BI]**.
1. En **[!UICONTROL Servicio de Microsoft Power BI]** > **[!UICONTROL Mi espacio de trabajo]**, seleccione el conjunto de datos que había publicado previamente desde Report Builder.

Para obtener más información, consulte la [publicación de blog de Microsoft](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/).
