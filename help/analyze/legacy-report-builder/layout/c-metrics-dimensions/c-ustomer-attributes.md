---
description: Los atributos del cliente se almacenan en un nuevo tipo de elemento denominado VisAttr, que puede configurarse como dimensión o como métrica.
title: Atributos del cliente
feature: Report Builder
role: User, Admin
exl-id: b5855ce0-6d17-4690-a2c2-366b66ab8e83
TQID: https://experienceleague.adobe.com/J-KoYBPg-bECW1utOk2L0YLtBWd9-jHT6gwAEm54fs4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 135
ht-degree: 80%

---

# Atributos del cliente

{{legacy-arb}}

Los atributos del cliente se almacenan en un nuevo tipo de elemento denominado VisAttr, que puede configurarse como dimensión o como métrica.

Para obtener más información sobre cómo cargar atributos de cliente, consulte la [ayuda de Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=es).

* Si está configurado como métrica, VisAttr se expone como métrica y como &quot;dimensión&quot;.

  ![Captura de pantalla que muestra atributos del cliente de métricas y dimensiones.](assets/ca_metrics.png) ![](assets/ca_dimension.png)

* Es compatible con el mismo desglose que un eVar (todo se puede desglosar).
* VisAttr es compatible con todas las métricas de eVar.
* VisAttr como métrica es compatible con la clasificación por categorías o “bucketization”, (como el Tiempo transcurrido en el sitio: 0 a 30, 31 a 60, etc.).
* VisAttr está disponible como una dimensión de segmentación.
