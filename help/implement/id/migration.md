---
title: Consideraciones sobre la migración del servicio de ID de visitante para Adobe Analytics
description: Una visión general de cómo Adobe Analytics interactúa con el servicio de ID de visitante.
source-git-commit: 3055a76f797438be71e82ea8f73800dc82ff4805
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 0%

---

# Consideraciones sobre la migración del servicio de ID de visitante para Adobe Analytics

Si su organización planea pasar al servicio de ID de visitante con una implementación de Analytics existente, hay que tener en cuenta algunos temas importantes. Estas consideraciones son importantes para conservar la integridad de identificación del visitante y comprender cómo funciona el servicio de ID en presencia de una implementación de Analytics existente.

## Interacción del servicio de ID de visitante con cookies de visitante de Analytics heredadas

Dado que AppMeasurement tiene su propio método para identificar a los visitantes, es posible que algunos visitantes tengan cookies de Analytics heredadas cuando una organización implemente el servicio de ID de visitante. En la lista siguiente se describe cómo se identifica a un visitante en distintas circunstancias.

* **No hay cookies de visitante**: El servicio de ID asigna un Experience Cloud ID (`mid`).
* **Existe una cookie `s_vi`**: El servicio de identidad escribe el identificador de Analytics heredado existente (`aid`) en la cookie `AMCV`, además de un identificador de Experience Cloud (`mid`). Dado que `aid` es mayor en el [orden de operaciones](overview.md), el ID de Analytics heredado es el identificador de visitante hasta que la cookie `AMCV` caduque o se borre. Cuando se habilita un período de gracia, el servicio de ID incluye `mid` y `aid` en su respuesta.
* **Existe una cookie de reserva**: El servicio de identidad no escribe la cookie de reserva (`fid`) en la cookie `AMCV`. En su lugar, los visitantes reciben un Experience Cloud ID (`mid`) como si fueran un visitante nuevo.

## Período de gracia del servicio de ID de visitante

Si tiene varias implementaciones que envían datos al mismo grupo de informes y solo puede implementar el servicio de ID de visitante en algunas implementaciones, Adobe recomienda configurar un periodo de gracia. Por ejemplo: Si la sección de asistencia técnica de su sitio se administra mediante una solución de etiquetado independiente, es posible que tenga el servicio de ID de visitante implementado en el resto del sitio antes de la sección de asistencia técnica. Sin un período de gracia, los nuevos visitantes que vean la sección de asistencia reciben un ID de visitante de Analytics heredado, lo que provoca que se cuenten dos visitantes independientes. Con un período de gracia, el servicio de ID de visitante emite un Experience Cloud ID (`mid`) y un ID de visitante de Analytics heredado (`aid`) para que las áreas del sitio sin el servicio de ID sigan identificando a los visitantes de forma coherente.

Si coordina la implementación del servicio de ID de visitante en todas las áreas del sitio, no necesita ningún periodo de gracia. Para configurar un período de gracia, comuníquese con el [Servicio de atención al cliente de Adobe](https://helpx.adobe.com/es/marketing-cloud/contact-support.html).

## Seguimiento entre dominios

Algunas implementaciones de ID de visitante de Analytics heredadas pueden utilizar &quot;cookies de terceros descriptivas&quot;, en las que dos dominios comparten la misma cookie de visitante en un dominio común como `data.example.com`. Dado que las cookies de terceros sencillas siguen siendo cookies de terceros, la mayoría de los exploradores modernos las rechazan, lo que provoca que Analytics dependa de un ID de reserva (`fid`) para la identificación del visitante. El traslado al servicio de ID permite a todos los dominios establecer la cookie `AMCV` en un contexto de origen, lo que aumenta su viabilidad para conservar un ID de visitante.

Aunque el servicio de ID de visitante intenta establecer una cookie de terceros para el seguimiento entre dominios (la cookie [`demdex` &#x200B;](https://experienceleague.adobe.com/en/docs/id-service/using/intro/cookies)), la mayoría de los exploradores modernos la suelen rechazar. Considere utilizar el método [`appendVisitorIDsTo`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/appendvisitorid) para pasar los Experience Cloud ID entre sus dominios.

## Seguimiento del lado del servidor

Puede llamar a [`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid) para obtener el Experience Cloud ID (`mid`) y a [`getAnalyticsVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getanalyticsvisitorid) para obtener el ID de Analytics heredado (`aid`). Adobe recomienda comprobar ambos para conservar la lógica de identificación del visitante.
