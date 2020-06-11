---
title: Visitantes con Experience Cloud ID
description: El número de visitantes únicos que utilizan el servicio de ID de Adobe Experience Cloud.
translation-type: tm+mt
source-git-commit: 0328de560185e716a3913080feda9cd078e0f206
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 19%

---


# Visitantes con Experience Cloud ID

La métrica &quot;Visitantes con Experience Cloud ID&quot; muestra el número de visitantes únicos identificados por Adobe mediante el servicio [](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html)Experience Cloud ID. Esta dimensión es útil para comparar con la métrica visitantes [](unique-visitors.md) únicos a fin de asegurarse de que la mayoría de los visitantes del sitio utiliza el servicio de ID. Si una gran parte de los visitantes no utiliza las cookies del servicio de ID, puede indicar un problema en la implementación.

>[!NOTE] Esta métrica es especialmente importante para la depuración si utiliza varios servicios de Experience Cloud, como Adobe Destinatario o Adobe Audiencia Manager. Los segmentos compartidos en los productos de Experience Cloud no incluyen visitantes sin un ID de Experience Cloud.

## Cómo se calcula esta métrica

Esta métrica se basa en la métrica visitantes [](unique-visitors.md) únicos, excepto que solo incluye personas identificadas mediante la cadena de `mid` consulta (en función de la [`s_ecid`](https://docs.adobe.com/content/help/es-ES/core-services/interface/ec-cookies/cookies-analytics.html) cookie).

## Depurar la configuración de Experience Cloud ID

La métrica &quot;Visitantes con Experience Cloud ID&quot; puede resultar útil para solucionar problemas de integraciones de Experience Cloud o identificar áreas del sitio que no tienen implementado el servicio de ID.

Arrastre los &quot;Visitantes con Experience Cloud ID&quot; en paralelo con los visitantes únicos para compararlos:

![Comparación única de visitantes](assets/metric-mcvid1.png)

En este ejemplo, observe que cada página tiene el mismo número de &quot;Visitantes únicos&quot; que &quot;Visitantes con un ID de Experience Cloud&quot;. Sin embargo, el número total de visitantes únicos es mayor que el número total de visitantes con Experience Cloud ID. Puede crear una métrica [](../c-calcmetrics/cm-overview.md) calculada para averiguar qué páginas no están configurando el servicio de ID. Puede utilizar la siguiente definición:

![Definición de métrica calculada](assets/metric-mcvid2.png)

Al añadir la métrica calculada al informe, puede ordenar el informe Páginas de manera que aparezcan las páginas con el mayor número de visitantes sin un MCID:

![Páginas sin servicio de ID](assets/metric-mcvid3.png)

Tenga en cuenta que el valor de la dimensión &quot;Vistas rápidas del producto&quot; no se implementa correctamente con Identity Service. Puede trabajar con los equipos adecuados dentro de su organización para actualizar estas páginas lo antes posible. Puede crear un informe similar con cualquier tipo de dimensión, como el tipo [de](../dimensions/browser-type.md)explorador, la sección [](../dimensions/site-section.md)del sitio o cualquier [eVar](../dimensions/evar.md).
