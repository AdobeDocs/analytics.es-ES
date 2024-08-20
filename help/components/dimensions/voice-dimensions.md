---
title: Dimensiones de análisis de voz
description: Dimensiones de análisis de voz
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
source-git-commit: 6a229439c455389b88d5fe96a0366b8888809c02
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 4%

---

# Dimensiones de análisis de voz

Al habilitar [!UICONTROL Voice and Chatbots] en [[!UICONTROL Informes de aplicaciones]](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md), se crean las siguientes dimensiones (y [métricas](../metrics/voice-metrics.md)). Puede usar [Variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md) para establecerlas en el valor de cadena deseado. Cuando se habilita en la configuración del grupo de informes, se crean automáticamente [reglas de procesamiento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) que asignan dimensiones de análisis de voz a su variable de datos de contexto asociada.

| Nombre de la dimensión | Descripción | Variable de datos de contexto |
| --- | --- | --- |
| Tipo de error de voz | Tipo de error encontrado. | `a.voiceerrortype` |
| Idioma de voz | El idioma en el que el usuario interactúa con la aplicación de voz. | `a.voicelanguage` |
| Intención de voz | El comando que el usuario pretende ejecutar. | `a.voiceintent` |
| Respuesta de aplicación de voz | La respuesta que la aplicación de voz devolvió al usuario. | `a.voiceappresponse` |
| Autenticación de voz | El estado autenticado del usuario al interactuar con la aplicación de voz. | `a.voiceauthentication` |
| ID del punto de interés | El ID del punto de interés. | `a.loc.poi.id` |

{style="table-layout:auto"}
