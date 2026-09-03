---
title: Seguimiento en diferentes tipos de implementación
description: Utilice diferentes tipos de implementación y realice un seguimiento de los visitantes.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/FM6c33rpXxzy1huu8KE0VBkfe4FGIySczmVMrprFEUY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 612
ht-degree: 47%

---

# Seguimiento en diferentes tipos de implementación

La arquitectura principal de una implementación de Adobe Analytics es coherente en todos los tipos de implementación. El proceso implica definir variables y compilarlas en una solicitud de imagen que se envía a los servidores de recopilación de datos de Adobe. Este concepto significa que puede cambiar sin problemas entre AppMeasurement, el SDK web y sus extensiones respectivas en la recopilación de datos de Adobe Experience Platform en diferentes páginas del mismo sitio.

Adobe recomienda mantener la coherencia en la implementación de un sitio utilizando el mismo tipo de implementación en todas las páginas. Sin embargo, si algunas partes del sitio tienen requisitos diferentes, puede utilizar esta página para asegurarse de que el seguimiento de los visitantes sea coherente en todas las páginas.

Si utiliza más de un tipo de implementación (como AppMeasurement y solicitudes de imagen codificadas), asegúrese de que las siguientes variables estén configuradas correctamente y coincidan entre sí.

>[!NOTE]
>
>Todos los tipos de implementación deben utilizar el mismo tipo de identificación de visitante (ID de Analytics heredado, servicio de ID de visitante o servicio de Experience Platform ID). Adobe recomienda utilizar un ECID en todas las implementaciones siempre que sea posible.

| Variable | Extensión de etiquetas del SDK web | Web SDK (aleación) | Extensión de Analytics | AppMeasurement | Solicitud de imagen codificada |
|---|---|---|---|---|---|
| ID del grupo de informes | Añada Adobe Analytics como servicio al [configurar una secuencia de datos](https://experienceleague.adobe.com/es/docs/experience-platform/datastreams/configure) | Añada Adobe Analytics como servicio al [configurar una secuencia de datos](https://experienceleague.adobe.com/es/docs/experience-platform/datastreams/configure) | [!UICONTROL Grupos de informes] en la sección [!UICONTROL Administración de biblioteca] al [configurar la extensión](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/analytics/overview) | Argumento de cadena en [`s_gi`](../vars/functions/s-gi.md) | Parte de la dirección URL `pathname` (después de `/b/ss/`) |
| Servicio de ID de visitante | Incluye de forma nativa el [servicio de identidad de Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/identity/home); requiere que [`idMigrationEnabled`](https://experienceleague.adobe.com/es/docs/experience-platform/collection/js/commands/configure/idmigrationenabled) lea las cookies del servicio de identificación del visitante | Incluye de forma nativa el [servicio de identidad de Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/identity/home); requiere [[!UICONTROL migrar el ECID de VisitorAPI a Web SDK]](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/web-sdk/configure/identity) para leer las cookies del servicio de identificación del visitante | Utilice la extensión de etiqueta [&#39;[!UICONTROL Servicio Experience Cloud ID]&#39;](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/id-service/overview), que implementa [Servicio de ID de visitante](https://experienceleague.adobe.com/es/docs/id-service/using/home) | Implementar el [servicio de identificación de visitante](https://experienceleague.adobe.com/es/docs/id-service/using/home) (`VisitorAPI.js`) | Realice una [llamada independiente al servicio de ID de visitante](https://experienceleague.adobe.com/es/docs/id-service/using/implementation/direct-integration) para obtener el ID deseado e incluir `mid` en la cadena de consulta |
| dominio de Edge | El campo [!UICONTROL Dominio de Edge] al [Configurar la extensión](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) | La propiedad `edgeDomain` al [configurar el SDK web](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/commands/configure/overview) | [!UICONTROL Servidor de seguimiento SSL] en la sección [!UICONTROL General] al [Configurar la extensión](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/analytics/overview) | La variable [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) | El `hostname` de la URL de solicitud de imagen |

>[!NOTE]
>
>Las implementaciones basadas en AppMeasurement (incluida la extensión de etiquetas de Analytics) no son compatibles con el [servicio de identidad de Experience Platform](https://experienceleague.adobe.com/es/docs/id-service/using/home). Debe usar el denominador común más bajo de identificación de visitantes para sincronizar entre tipos de implementación, que suele ser el [Servicio de ID de visitante](https://experienceleague.adobe.com/es/docs/id-service/using/home) (`VisitorAPI.js`).

Si alguna de estas variables no es coherente en cada tipo de implementación, es probable que Adobe las considere como visitantes independientes. Si los visitantes no se rastrean fácilmente entre los tipos de implementación del sitio, el motivo más común es que la identificación del visitante está configurada incorrectamente. Asegúrese de que cada tipo de implementación obtiene correctamente el mismo ECID (`mid` [cadena de consulta](/help/implement/validate/query-parameters.md)) en el sitio.
