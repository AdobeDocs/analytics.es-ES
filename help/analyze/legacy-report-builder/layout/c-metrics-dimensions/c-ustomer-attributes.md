---
description: Los atributos del cliente se almacenan en un nuevo tipo de elemento denominado VisAttr, que puede configurarse como dimensión o como métrica.
title: Atributos del cliente
feature: Report Builder
role: User, Admin
exl-id: b5855ce0-6d17-4690-a2c2-366b66ab8e83
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 83%

---

# Atributos del cliente

{{legacy-arb}}

Los atributos del cliente se almacenan en un nuevo tipo de elemento denominado VisAttr, que puede configurarse como dimensión o como métrica.

Para obtener más información sobre cómo cargar atributos de cliente, consulte la [ayuda de Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=es).

* Si está configurado como métrica, VisAttr se expone como métrica y como &quot;dimensión&quot;.

  ![Captura de pantalla que muestra atributos del cliente de métricas y dimensiones.](assets/ca_metrics.png) ![](assets/ca_dimension.png)

* Es compatible con el mismo desglose que un eVar (todo se puede desglosar).
* VisAttr es compatible con todas las métricas eVar.
* VisAttr como métrica es compatible con la clasificación por categorías o “bucketization”, (como el Tiempo transcurrido en el sitio: 0 a 30, 31 a 60, etc.).
* VisAttr está disponible como una dimensión de segmentación.
