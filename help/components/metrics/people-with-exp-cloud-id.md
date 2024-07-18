---
title: Usuarios con Experience Cloud ID
description: El número de personas en el análisis entre dispositivos que tienen un Experience Cloud ID.
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 83%

---

# Usuarios con Experience Cloud ID

Personas con Experience Cloud ID es una métrica de [Análisis entre dispositivos](../cda/overview.md) que muestra el número de [Personas](people.md) que fueron identificadas por Adobe mediante el servicio de [ID de Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es).

## Cálculo de esta métrica

Teniendo en cuenta cada [persona](people.md) (identificada o no identificada), esta [métrica](overview.md) aumenta si la visita contiene la cadena de consulta `mid` (basada en la cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=es)).

Puede crear la métrica calculada `[People with ECID] ÷ [People]` para obtener el porcentaje de visitantes del sitio mediante el servicio de ID.

Consulte la métrica equivalente que no es de CDA [Visitantes con Experience Cloud ID](visitors-with-ecid.md) para obtener más información sobre la importancia del ID de Experience Cloud y la depuración de la configuración.
