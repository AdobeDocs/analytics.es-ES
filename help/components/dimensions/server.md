---
title: Servidor
description: El nombre del servidor.
feature: Dimensions
exl-id: c2454c0d-497e-46f8-8569-7d0517097cab
TQID: 'https://experienceleague.adobe.com/BDVwwy3jCtHrcWLy2nOHVnDRbFiAoR-EeOzp-35XjBs'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 61%
---
# Servidor

La [dimensión](overview.md) del &quot;servidor&quot; generalmente indica el nombre de host del sitio. Para los grupos de informes que combinan varios dominios o subdominios, esta dimensión es valiosa para ver qué dominios o subdominios funcionan mejor.

Esta dimensión está relacionada con las dimensiones de la sección [Página](page.md) y [Sección del sitio](site-section.md). La página es más granular, el servidor es menos granular y la sección del sitio está entre los dos.

## Rellene esta dimensión con datos

AppMeasurement recopila estos datos mediante la variable [`server`](/help/implement/vars/page-vars/server.md), que es funcionalmente idéntica a una prop.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | [`server`](/help/implement/vars/page-vars/server.md) |
| **Campo Web SDK / XDM** | [`web.webPageDetails.server`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **Parámetro de consulta** | [`server`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **etiqueta XML** | [`<server>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Límite de bytes** | 100 bytes |
| **Persistencia** | Hit |

## Elementos de dimensión

Los elementos de dimensión incluyen los servidores del sitio. Su organización determina qué elementos de dimensión específicos desea utilizar. Algunas organizaciones utilizan `window.location.hostname`, mientras que otras formulan valores personalizados. Sea cual sea el método que utilice, asegúrese de que sea coherente y de que lo grabe en un [documento de diseño de solución](/help/implement/prepare/solution-design.md).
