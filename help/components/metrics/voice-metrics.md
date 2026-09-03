---
title: Métricas de análisis de voz
description: Métricas de análisis de voz
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
TQID: https://experienceleague.adobe.com/snDtqM3TiX--cjPjKj8cGkaFxMIxRprvD4ia9OnBXJk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 102
ht-degree: 21%

---

# Métricas de análisis de voz

Al habilitar [!UICONTROL Voice and Chatbots] en [[!UICONTROL Informes de aplicaciones]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md), se crean las siguientes métricas (y [dimensiones](../dimensions/voice-dimensions.md)). Puede usar [Variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md) para establecerlas en un valor de `1` (o más, si corresponde). Cuando se habilita en la configuración del grupo de informes, se crean automáticamente [reglas de procesamiento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) que asignan métricas de análisis de voz a la variable de datos de contexto asociada.

| Nombre de la métrica | Descripción | Variable de datos de contexto |
| --- | --- | --- |
| Emisiones de voz | Déclencheur cuando se emite un comando a un asistente de voz. | `a.voiceutterances` |
| Sesión de finalización de voz | Déclencheur cuando la aplicación de voz está cerrada. | `a.voiceendsession` |
| Error de voz | Déclencheur cuando la aplicación de voz encuentra un error. | `a.voiceerror` |

{style="table-layout:auto"}
