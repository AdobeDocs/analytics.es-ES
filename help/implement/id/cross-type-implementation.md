---
title: Seguimiento en diferentes tipos de implementación
description: Utilice diferentes tipos de implementación y realice un seguimiento de los visitantes.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 58%

---

# Seguimiento en diferentes tipos de implementación

La arquitectura principal de una implementación de Adobe Analytics es coherente en todos los tipos de implementación. El proceso implica definir variables y compilarlas en una solicitud de imagen que se envía a los servidores de recopilación de datos de Adobe. Este concepto significa que puede cambiar sin problemas entre AppMeasurement, el SDK web y sus extensiones respectivas en la recopilación de datos de Adobe Experience Platform en diferentes páginas del mismo sitio.

Adobe recomienda mantener la coherencia en la implementación de un sitio utilizando el mismo tipo de implementación en todas las páginas. Sin embargo, si algunas partes del sitio tienen requisitos diferentes, puede utilizar esta página para asegurarse de que el seguimiento de los visitantes sea coherente en todas las páginas.

Si utiliza más de un tipo de implementación (como AppMeasurement y solicitudes de imagen codificadas), asegúrese de que las siguientes variables estén configuradas correctamente y coincidan entre sí.

>[!NOTE]
>
>Todos los tipos de implementación deben utilizar el mismo tipo de identificación de visitante (ID de Analytics heredado o servicio de ID de visitante). Adobe recomienda utilizar el servicio de ID de visitante en todas las implementaciones, siempre que sea posible.

| Variable | Extensión de etiquetas del SDK web | Web SDK (aleación) | Extensión de Analytics | AppMeasurement | Solicitud de imagen codificada |
|---|---|---|---|---|---|
| ID del grupo de informes | Añada Adobe Analytics como servicio al [configurar una secuencia de datos](https://experienceleague.adobe.com/es/docs/experience-platform/datastreams/configure) | Añada Adobe Analytics como servicio al [configurar una secuencia de datos](https://experienceleague.adobe.com/es/docs/experience-platform/datastreams/configure) | [!UICONTROL Grupos de informes] en la sección [!UICONTROL Administración de biblioteca] al [configurar la extensión](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/analytics/overview) | Argumento de cadena en [`s_gi`](../vars/functions/s-gi.md) | Parte de la dirección URL `pathname` (después de `/b/ss/`) |
| Servicio Experience Cloud ID | [Incluido(a) de forma nativa](web-sdk-extension.md) | [Incluido(a) de forma nativa](alloy.md) | Usar la [extensión del servicio Experience Cloud ID](analytics-extension.md) | Implementación [`VisitorAPI.js`](appmeasurement.md) | Realice una [llamada independiente al servicio de ID](https://experienceleague.adobe.com/es/docs/id-service/using/implementation/direct-integration) para obtener el ID deseado e incluir `mid` en la cadena de consulta |
| dominio de Edge | El campo [!UICONTROL Dominio de Edge] al [Configurar la extensión](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) | La propiedad `edgeDomain` al [configurar el SDK web](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/commands/configure/overview) | [!UICONTROL Servidor de seguimiento SSL] en la sección [!UICONTROL General] al [Configurar la extensión](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/analytics/overview) | La variable [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) | El `hostname` de la URL de solicitud de imagen |

Si alguna de estas variables no es coherente en cada tipo de implementación, es probable que Adobe las considere como visitantes independientes. Si los visitantes no se rastrean sin problemas en los tipos de implementación del sitio, el motivo más común es que el servicio de ID está configurado incorrectamente. Asegúrese de que cada tipo de implementación obtiene correctamente el mismo Experience Cloud ID (`mid`) en todo el sitio.
