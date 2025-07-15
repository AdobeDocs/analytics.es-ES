---
title: Métricas de análisis de voz
description: Métricas de análisis de voz
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
source-git-commit: c2adf6d2e328378332cc290ba2dfd75ee6587ef6
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 21%

---

# Métricas de análisis de voz

Al habilitar [!UICONTROL Voice and Chatbots] en [[!UICONTROL Informes de aplicaciones]](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md), se crean las siguientes métricas (y [dimensiones](../dimensions/voice-dimensions.md)). Puede usar [Variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md) para establecerlas en un valor de `1` (o más, si corresponde). Cuando se habilita en la configuración del grupo de informes, se crean automáticamente [reglas de procesamiento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md) que asignan métricas de análisis de voz a la variable de datos de contexto asociada.

| Nombre de la métrica | Descripción | Variable de datos de contexto |
| --- | --- | --- |
| Emisiones de voz | Déclencheur cuando se emite un comando a un asistente de voz. | `a.voiceutterances` |
| Sesión de finalización de voz | Déclencheur cuando la aplicación de voz está cerrada. | `a.voiceendsession` |
| Error de voz | Déclencheur cuando la aplicación de voz encuentra un error. | `a.voiceerror` |

{style="table-layout:auto"}
