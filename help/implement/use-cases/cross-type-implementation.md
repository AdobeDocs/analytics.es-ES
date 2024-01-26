---
title: Seguimiento en diferentes tipos de implementación
description: Utilice diferentes tipos de implementación y realice un seguimiento de los visitantes.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 100%

---

# Seguimiento en diferentes tipos de implementación

La arquitectura principal de una implementación de Adobe Analytics es coherente en todos los tipos de implementación. El proceso implica definir variables y compilarlas en una solicitud de imagen que se envía a los servidores de recopilación de datos de Adobe. Este concepto significa que puede cambiar sin problemas entre AppMeasurement, el SDK web y sus extensiones respectivas en la recopilación de datos de Adobe Experience Platform en diferentes páginas del mismo sitio.

Adobe recomienda mantener la coherencia en la implementación de un sitio utilizando el mismo tipo de implementación en todas las páginas. Sin embargo, si algunas partes del sitio tienen requisitos diferentes, puede utilizar esta página para asegurarse de que el seguimiento de los visitantes sea coherente en todas las páginas.

Si usa más de un tipo de implementación (como AppMeasurement y solicitudes de imagen codificadas), asegúrese de que las siguientes variables estén correctamente configuradas y coincidan entre sí:

| Variable | AppMeasurement | Extensión de Analytics | SDK web | Extensión del SDK web | Solicitud de imagen codificada |
| --- | --- | --- | --- | --- | --- |
| ID del grupo de informes | Argumento de cadena dentro de [`s_gi`](../vars/functions/s-gi.md) | [!UICONTROL Grupos de informes] en la sección [!UICONTROL Administración de biblioteca] al [configurar la extensión](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=es) | Añada Adobe Analytics como servicio al [configurar una secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=es) | Añada Adobe Analytics como servicio al [configurar una secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=es) | Parte de la dirección URL `pathname` (después de `/b/ss/`) |
| Servidor de seguimiento | Las variables [`trackingServer`](../vars/config-vars/trackingserver.md) y [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) | [!UICONTROL Servidor de seguimiento] y [!UICONTROL Servidor de seguimiento SSL] en la sección [!UICONTROL General] al [configurar la extensión](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=es) | La propiedad `edgeDomain` al [configurar el SDK web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=es) | El [!UICONTROL dominio Edge] al [configurar la extensión](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=es) | El `hostname` de la URL de solicitud de imagen |
| Servicio Experience Cloud ID | Implementación [`VisitorAPI.js`](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=es) | Utilice la [Extensión del servicio de ID de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html?lang=es) | Utilice la [Extensión del servicio de ID de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html?lang=es) | Utilice la [Extensión del servicio de ID de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html?lang=es) | Haga una [llamada separada a los servidores del servicio de ID](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html?lang=es) para obtener el ID deseado |

{style="table-layout:auto"}

Si cualquiera de estas variables no es coherente en cada tipo de implementación, Adobe las considera visitantes independientes. Si los visitantes no se rastrean sin problemas en los tipos de implementación del sitio, el motivo más común es que el servicio de ID está configurado incorrectamente. Consulte [Métodos de implementación](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-methods.html?lang=es) en la guía del usuario del servicio de ID para obtener más información.
