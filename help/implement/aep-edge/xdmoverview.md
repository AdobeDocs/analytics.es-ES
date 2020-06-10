---
title: Uso de datos XDM con Analytics
description: 'Información general sobre el uso de datos XDM de la plataforma de experiencia en Adobe Analytics '
translation-type: tm+mt
source-git-commit: a28a05047e95d12343fd94f7b11e5cabf7fac070
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 4%

---


# Uso de datos perimetrales de Adobe Experience Platform con Analytics

Puede utilizar el SDK [web de](https://docs.adobe.com/content/help/es-ES/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html) Adobe Experience Platform (AEP) para enviar datos a Adobe Analytics. Esto funciona traduciendo el modelo de datos de [experiencia (XDM)](https://docs.adobe.com/content/help/en/experience-platform/xdm/home.html) a un formato utilizado por Analytics.

Analytics recopila datos XDM mediante dos métodos:

* Asignación automática desde esquemas XDM
* Asignación manual a datos de contexto

## Asignación automática

[La asignación](xdm-manual.md) automática depende de un [esquema](https://docs.adobe.com/content/help/en/experience-platform/xdm/schema/composition.html) predeterminado del XDM que rellena automáticamente los objetos JSON que se incluyen en la recopilación de datos típica de Analytics. Las variables de Analytics que se asignan automáticamente desde el XDM a los grupos de informes configurados no requieren que el desarrollador las incorpore.

## Asignación manual

La asignación manual de datos XDM a Analytics se basa en variables de datos [de contexto de](../vars/page-vars/contextdata.md) Analytics. Estas variables se colocan en objetos JSON que corresponden a esquemas aplicables. Generalmente, el equipo de desarrollo agrega datos de contexto tras la implementación y, a continuación, los administradores establecen reglas [de](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md) procesamiento para aplicar esos datos a los grupos de informes especificados.

## Configuración

Para configurar Analytics para recibir datos XDM:

1. Instale y [configure](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/configuring-the-sdk.html) el SDK [web de](https://docs.adobe.com/content/help/en/experience-platform/edge/fundamentals/installing-the-sdk.html)Adobe Experience Platform.

2. Asegúrese de que los grupos de informes aplicables estén asignados a los datos que desee. Los datos XDM pasan automáticamente al grupo de informes desde la plataforma Adobe Experience.
