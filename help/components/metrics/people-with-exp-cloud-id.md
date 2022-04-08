---
title: Usuarios con Experience Cloud ID
description: El número de personas en el análisis entre dispositivos que tienen un Experience Cloud ID.
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: ht
source-wordcount: '130'
ht-degree: 100%

---

# Usuarios con Experience Cloud ID

Personas con Experience Cloud ID es una métrica de [Análisis entre dispositivos](../cda/overview.md) que muestra el número de [Personas](people.md) que fueron identificadas por Adobe mediante el servicio de [ID de Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es).

## Cálculo de esta métrica

Teniendo en cuenta cada [persona](people.md) (identificada o no identificada), esta métrica aumenta si la visita contiene la `mid` cadena de consulta (basada en la cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=es)).

Puede crear la métrica calculada `[People with ECID] ÷ [People]` para obtener el porcentaje de visitantes del sitio mediante el servicio de ID.

Consulte la métrica equivalente que no es de CDA [Visitantes con Experience Cloud ID](visitors-with-ecid.md) para obtener más información sobre la importancia del ID de Experience Cloud y la depuración de la configuración.
