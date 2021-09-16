---
title: Usuarios con Experience Cloud ID
description: El número de personas en el análisis entre dispositivos que tienen un ID de Experience Cloud.
source-git-commit: eaf0c3b751a5fbdc70ad6bef501dbf9e8400339c
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 21%

---

# Usuarios con Experience Cloud ID

&#39;Personas con ID de Experience Cloud&#39; es una métrica de [Análisis entre dispositivos](../cda/overview.md) que muestra el número de [Personas](people.md) que fueron identificadas por Adobe mediante el servicio [ID de Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es).

## Cálculo de esta métrica

Teniendo en cuenta cada [People](people.md) (identificado o no identificado), esta métrica aumenta si la visita contiene la cadena de consulta `mid` (basada en la cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=es)).

Puede crear la métrica calculada `[People with ECID] ÷ [People]` para obtener el porcentaje de visitantes del sitio mediante el servicio de ID.

Consulte la métrica equivalente que no es de CDA [Visitantes con ID de Experience Cloud](visitors-with-ecid.md) para obtener más información sobre la importancia del ID de Experience Cloud y la depuración de la configuración.
