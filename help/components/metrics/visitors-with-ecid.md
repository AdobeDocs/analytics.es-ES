---
title: Visitantes con Experience Cloud ID
description: El número de visitantes únicos que utilizan un ECID.
feature: Metrics
exl-id: 16c170d0-3546-4e0a-8f3c-c141b8a0e4fe
TQID: https://experienceleague.adobe.com/CCk7FDZhZ3mFYXtAggcxnAjvJoJp5zMf0NNk5w0tVY8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: e6c28e30-8689-4bf4-8fa8-561343d308a9
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 384
ht-degree: 25%

---

# Visitantes con Experience Cloud ID

La [métrica](overview.md) de &#39;[!UICONTROL Visitantes con Experience Cloud ID]&#39; muestra el número de visitantes únicos identificados por Adobe con un ECID (mediante el [Servicio de ID de visitante](https://experienceleague.adobe.com/es/docs/id-service/using/home) o el [Servicio de identidad de Experience Platform](https://experienceleague.adobe.com/es/docs/experience-platform/identity/home)). Esta métrica es útil para compararla con la métrica [Visitantes únicos](unique-visitors.md) a fin de asegurarse de que la mayoría de los visitantes del sitio use un ECID. Si una gran parte de los visitantes no utiliza este identificador, puede indicar un problema en la implementación.

>[!NOTE]
>
>Esta métrica es especialmente importante para la depuración si utiliza varios servicios empresariales de CX, como Adobe Target o Adobe Audience Manager. Los segmentos compartidos entre productos de CX Enterprise no incluyen visitantes sin un ECID.

## Cálculo de esta métrica

Esta métrica se basa en la métrica [visitantes únicos](unique-visitors.md), excepto que solo incluye personas identificadas mediante la `mid`cadena de consulta (basada en la cookie [`s_ecid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics)).

## Depurar la configuración de ECID

La métrica &quot;[!UICONTROL Visitantes con Experience Cloud ID]&quot; puede resultar útil para solucionar problemas de integraciones empresariales de CX o identificar áreas del sitio que no tienen implementado el servicio de ID de visitante o el servicio de identidad de Experience Platform.

Arrastre los &#39;[!UICONTROL visitantes con Experience Cloud ID]&#39; en paralelo con los visitantes únicos para compararlos:

![Comparación de visitantes únicos](assets/metric-mcvid1.png)

En este ejemplo, observe que cada página tiene el mismo número de &#39;[!UICONTROL visitantes únicos]&#39; que &#39;[!UICONTROL visitantes con Experience Cloud ID]&#39;. Sin embargo, el número total de &#39;[!UICONTROL visitantes únicos]&#39; es mayor que el número total de &#39;[!UICONTROL visitantes con Experience Cloud ID]&#39;. Puede crear una [métrica calculada](../calculated-metrics/cm-overview.md) para averiguar qué páginas no están usando un ECID con la siguiente definición:

![Definición de métrica calculada](assets/metric-mcvid2.png)

Al agregar la métrica calculada al informe, puede ordenar el informe Páginas de modo que aparezcan las páginas con el mayor número de visitantes sin un ECID:

![Páginas sin ECID](assets/metric-mcvid3.png)

Tenga en cuenta que el elemento de dimensión &quot;Vistas rápidas del producto&quot; no se implementa correctamente con un ECID. Puede trabajar con los equipos adecuados dentro de su organización para actualizar estas páginas lo antes posible. Puede crear un informe similar con cualquier tipo de dimensión, como el [tipo de explorador](../dimensions/browser-type.md), la [sección del sitio](../dimensions/site-section.md) o cualquier [eVar](../dimensions/evar.md).
