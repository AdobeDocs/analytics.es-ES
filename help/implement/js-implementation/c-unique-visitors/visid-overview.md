---
description: Adobe usa una cookie para realizar el seguimiento de exploradores o dispositivos únicos.
keywords: Implementación de Analytics
seo-description: Adobe usa una cookie para realizar el seguimiento de exploradores o dispositivos únicos.
seo-title: Identificar visitantes únicos
solution: Analytics
subtopic: Visitantes
title: Identificar visitantes únicos
topic: Desarrollador e implementación
uuid: ed 4 dee 75-ecfb -4715-8122-461983 c 7 dd 8 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Identificar visitantes únicos

Adobe usa una cookie para realizar el seguimiento de exploradores o dispositivos únicos.

## Orden de ID de visitante de Analytics {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics proporciona varios mecanismos para identificar a los visitantes. En la siguiente tabla se muestran las diferentes maneras de identificar a un visitante en Analytics (en orden de preferencia):

| Orden utilizado | Parámetro de consulta (método de recopilación) | Presente si |
|---|---|---|
| ![](assets/step1_icon.png) | [vid (s.visitorID)](../../../implement/js-implementation/c-unique-visitors/visid-custom.md#concept_4A2000F4B6ED41E99CA6118A6D74ECE8) | Se establece s.visitorID. |
| ![](assets/step2_icon.png) | [aid (cookie s_vi)](../../../implement/js-implementation/c-unique-visitors/visid-analytics.md#concept_74F6B4B9B2FA415AB5D029A1F8F099BC) | El visitante tenía una cookie s_vi existente antes de que usted implementara el servicio de ID del visitante o ha configurado un periodo de gracia del ID del visitante. |
| ![](assets/step3_icon.png) | [mid (cookie AMCV_ establecida por el servicio de ID de visitante de Experience Cloud)](https://marketing.adobe.com/resources/help/en_US/mcvid/) | El explorador del visitante acepta cookies (de origen). |
| ![](assets/step4_icon.png) | [fid (cookie de seguridad en H.25.3 o posterior, o AppMeasurement para JavaScript)](../../../implement/js-implementation/c-unique-visitors/visid-fallback.md#concept_EBCBF9EB390E45A2BA20DB6BE931C505) | El explorador del visitante acepta cookies (de origen). |
| ![](assets/step5_icon.png) | [Dirección IP, agente de usuario y dirección IP de puerta de enlace](../../../implement/js-implementation/c-unique-visitors/visid-fallback.md#section_104819D74C594ECE879144FCC5DEF4BF) | El explorador del visitante no acepta cookies. |

En muchas situaciones, podría ver 2 o 3 ID diferentes en una llamada, pero Analytics utilizará la primera ID presente de la tabla anterior como ID de visitante oficial. Por ejemplo, si está configurando una ID de visitante personalizada (incluida en el parámetro de consulta "vid"), esa ID se utilizará antes de que otras ID pudieran estar presentes en esa misma visita.

>[!NOTE]
>
>Cada ID de visitante de Analytics está asociado con un perfil de visitante en servidores de Adobe. Los perfiles de visitante se borran tras 13 meses de inactividad, independientemente de la caducidad de cualquier cookie del ID del visitante.
