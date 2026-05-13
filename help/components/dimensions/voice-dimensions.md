---
title: Dimensiones de análisis de voz
description: Dimensiones de análisis de voz
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
TQID: https://experienceleague.adobe.com/OZ-lQkbS8hsv8ywUUa2BQoH40nfklRkJNd9SlEVkmEI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 133
ht-degree: 16%

---

# Dimensiones de análisis de voz

Al habilitar [!UICONTROL Voice and Chatbots] en [[!UICONTROL Informes de aplicaciones]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md), se crean las siguientes dimensiones (y [métricas](../metrics/voice-metrics.md)). Puede usar [Variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md) para establecerlas en el valor de cadena deseado. Cuando se habilita en la configuración del grupo de informes, se crean automáticamente [reglas de procesamiento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) que asignan dimensiones de análisis de voz a su variable de datos de contexto asociada.

| Nombre de la dimensión | Descripción | Variable de datos de contexto |
| --- | --- | --- |
| Tipo de error de voz | Tipo de error encontrado. | `a.voiceerrortype` |
| Idioma de la voz | El idioma en el que el usuario interactúa con la aplicación de voz. | `a.voicelanguage` |
| Propósito de la voz | El comando que el usuario pretende ejecutar. | `a.voiceintent` |
| Respuesta de la aplicación de voz | La respuesta que la aplicación de voz devolvió al usuario. | `a.voiceappresponse` |
| Autenticación de voz | El estado autenticado del usuario al interactuar con la aplicación de voz. | `a.voiceauthentication` |
| ID del punto de interés | El ID del punto de interés. | `a.loc.poi.id` |

{style="table-layout:auto"}
