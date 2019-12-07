---
description: Adobe usa una cookie para realizar el seguimiento de exploradores o dispositivos únicos.
keywords: Analytics Implementation
subtopic: Visitors
title: Identificar visitantes únicos
topic: Developer and implementation
uuid: ed4dee75-ecfb-4715-8122-461983c7dd8f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Identificar visitantes únicos

Adobe usa una cookie para realizar el seguimiento de exploradores o dispositivos únicos.

## Orden de ID de visitante de Analytics {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics proporciona varios mecanismos para identificar a los visitantes. En la siguiente tabla se muestran las diferentes maneras de identificar a un visitante en Analytics (en orden de preferencia):

| Orden utilizado | Parámetro de consulta (método de recopilación) | Presente si |
|---|---|---|
| ![](assets/step1_icon.png) | [vid (s.visitorID)](/help/implement/js-implementation/c-unique-visitors/visid-custom.md) | Se establece s.visitorID. |
| ![](assets/step2_icon.png) | [aid (cookie s_vi)](/help/implement/js-implementation/c-unique-visitors/visid-analytics.md) | El visitante tenía una cookie s_vi existente antes de que usted implementara el servicio de ID del visitante o ha configurado un periodo de gracia del ID del visitante. |
| ![](assets/step3_icon.png) | [mid (cookie AMCV_ establecida por el servicio de ID de visitante de Experience Cloud)](https://marketing.adobe.com/resources/help/en_US/mcvid/) | El explorador del visitante acepta cookies (de origen). |
| ![](assets/step4_icon.png) | [fid (cookie de seguridad en H.25.3 o posterior, o AppMeasurement para JavaScript)](/help/implement/js-implementation/c-unique-visitors/visid-fallback.md) | El explorador del visitante acepta cookies (de origen). |
| ![](assets/step5_icon.png) | [Dirección IP, agente de usuario y dirección IP de puerta de enlace](/help/implement/js-implementation/c-unique-visitors/visid-fallback.md#section_104819D74C594ECE879144FCC5DEF4BF) | El explorador del visitante no acepta cookies. |

En muchas situaciones, podría ver 2 o 3 ID diferentes en una llamada, pero Analytics utilizará la primera ID presente de la tabla anterior como ID de visitante oficial. Por ejemplo, si está configurando una ID de visitante personalizada (incluida en el parámetro de consulta "vid"), esa ID se utilizará antes de que otras ID pudieran estar presentes en esa misma visita.

> [!NOTE] Cada ID de visitante de Analytics está asociado con un perfil del visitante en los servidores de Adobe. Los perfiles de visitante se borran tras 13 meses de inactividad, independientemente de la caducidad de cualquier cookie del ID del visitante.
