---
title: Uso de datos XDM con Analytics
description: Información general sobre el uso de datos XDM de Experience Platform en Adobe Analytics
exl-id: 6f1282fb-8d4a-4d88-9be0-1c939c22cb92
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 87%

---

# Uso de datos perimetrales de Adobe Experience Platform Edge con Analytics

Puede utilizar el [SDK web de Adobe Experience Platform (AEP)](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) para enviar datos a Adobe Analytics. Esto funciona traduciendo el [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=es) a un formato utilizado por Analytics.

Analytics recopila datos de XDM mediante dos métodos:

* Asignación automática desde esquemas XDM
* Asignación manual a datos de contexto

## Asignación automática

La asignación automática se basa en un [esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html) predeterminado del XDM que rellena automáticamente los objetos JSON que se incluyen en la recopilación de datos típica de Analytics. Las variables de Analytics que se asignan automáticamente del XDM a los grupos de informes configurados no requieren la asistencia del desarrollador para la incorporación.

## Asignación manual

[La asignación manual de datos XDM a Analytics](xdm-manual.md) se basa en variables de [datos de contexto de Analytics](../vars/page-vars/contextdata.md). Estas variables se colocan en objetos JSON que corresponden a esquemas aplicables. Generalmente, el equipo de desarrollo agrega datos de contexto tras la implementación y, a continuación, los administradores establecen [reglas de procesamiento](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) para aplicar esos datos a los grupos de informes especificados.

## Configuración

Para configurar Analytics para recibir datos XDM:

1. Instale y [configure](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) el [SDK web de Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html).

2. Asegúrese de que los grupos de informes aplicables estén asignados a los datos que desee. Los datos de XDM pasan automáticamente al grupo de informes desde Adobe Experience Platform.
