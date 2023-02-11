---
title: Seguimiento en diferentes tipos de implementación
description: Utilice diferentes tipos de implementación y realice un seguimiento de los visitantes.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
source-git-commit: 90914569256cf891cb3cf693843e7cf9ede2f4ce
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 14%

---

# Seguimiento en diferentes tipos de implementación

La arquitectura principal de una implementación de Adobe Analytics es coherente en todos los tipos de implementación. El proceso implica definir variables y compilarlas en una solicitud de imagen que se envía a los servidores de recopilación de datos de Adobe. Este concepto significa que puede cambiar sin problemas entre AppMeasurement, el SDK web y sus extensiones respectivas en la recopilación de datos de Adobe Experience Platform en diferentes páginas del mismo sitio.

Adobe recomienda mantener la coherencia en la implementación de un sitio utilizando el mismo tipo de implementación en todas las páginas. Sin embargo, si algunas partes del sitio tienen requisitos diferentes, puede utilizar esta página para asegurarse de que el seguimiento de los visitantes sea coherente en todas las páginas.

Si utiliza más de un tipo de implementación (como AppMeasurement y solicitudes de imagen codificadas), asegúrese de que las siguientes variables estén correctamente configuradas y coincidan entre sí:

| Variable | AppMeasurement | Extensión de Analytics | SDK web | Extensión de SDK web | Solicitud de imagen codificada |
| --- | --- | --- | --- | --- | --- |
| ID del grupo de informes | Argumento de cadena dentro de [`s_gi`](../vars/functions/s-gi.md) | [!UICONTROL Grupos de informes] en el [!UICONTROL Administración de biblioteca] sección cuando [Configuración de la extensión](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | Añadir Adobe Analytics como servicio cuando [Configuración de un conjunto de datos](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | Añadir Adobe Analytics como servicio cuando [Configuración de un conjunto de datos](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | Parte de la dirección URL `pathname` (después de `/b/ss/`) |
| Servidor de seguimiento | La variable [`trackingServer`](../vars/config-vars/trackingserver.md) y [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) variables | [!UICONTROL Servidor de seguimiento] y [!UICONTROL Servidor de seguimiento SSL] en el [!UICONTROL General] sección cuando [Configuración de la extensión](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | La variable `edgeDomain` propiedad when [Configuración del SDK web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=es) | La variable [!UICONTROL Dominio de Edge] when [Configuración de la extensión](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=es) | La variable `hostname` de la URL de solicitud de imagen |
| Servicio Experience Cloud ID | Implementación [`VisitorAPI.js`](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=es) | Utilice la variable [Extensión de Adobe Experience Cloud ID Service](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Utilice la variable [Extensión de Adobe Experience Cloud ID Service](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Utilice la variable [Extensión de Adobe Experience Cloud ID Service](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Haga un [llamada separada a los servidores del servicio de ID](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html) para obtener el ID deseado |

{style=&quot;table-layout:auto&quot;}

Si cualquiera de estas variables no es coherente en cada tipo de implementación, Adobe las considera visitantes independientes. Si los visitantes no se rastrean sin problemas en los tipos de implementación del sitio, el motivo más común es que el servicio de ID está configurado incorrectamente. Consulte [Métodos de implementación](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-methods.html) en la guía del usuario del servicio de ID para obtener más información.
