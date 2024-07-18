---
title: Visitantes únicos
description: Número de ID de visitante único.
feature: Metrics
exl-id: 56e7bad4-4802-49ac-a0f1-ae77441fc016
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 100%

---

# Visitantes únicos

La [métrica](overview.md) &quot;Visitantes únicos&quot; muestra el número de ID de visitante para el elemento de dimensión. Es una de las métricas más comunes utilizadas para determinar el tráfico, ya que proporciona una visión general de alto nivel de la popularidad de un elemento de dimensión. Por ejemplo: un visitante puede llegar a su sitio todos los días durante un mes, pero contará como un visitante único.

Si utiliza [Análisis entre dispositivos](../cda/overview.md), esta métrica se sustituye por la métrica [Dispositivos únicos](unique-devices.md).

## Visitantes únicos diarios, semanales, mensuales, trimestrales y anuales

Analysis Workspace trata los visitantes únicos en función de la granularidad del informe. Por ejemplo, si utiliza la dimensión [Día](../dimensions/day.md), verá visitantes únicos diarios para cada elemento de dimensión. Sin embargo, de cara al total del informe, se anula la duplicación de visitantes únicos para el intervalo de fechas de la tabla de forma libre.

## Cálculo de esta métrica

Esta métrica cuenta el número de ID del visitante único para un elemento de dimensión determinado. Utiliza varios mecanismos avanzados para identificar visitantes únicos, ya que existen diferentes maneras de identificarlos. En el siguiente cuadro se enumera las formas en las que se identifica a un visitante, junto a su prioridad. Algunas visitas pueden tener varios métodos de identificación; en estos casos se utiliza el método de mayor prioridad.

| Pedido utilizado | Parámetro de consulta (método de recopilación) | Presente cuando |
| --- | --- | --- |
| 1 | `vid` | Se establece la variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md). |
| 2 | `aid` | El visitante tiene una cookie de [`s_vi`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=es). Se configura en implementaciones sin implementar el servicio de ID de visitante o antes de hacerlo. |
| 3 | `mid` | El visitante tiene una cookie de [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=es). Se configura en implementaciones que utilizan el [Servicio de identidad de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es). |
| 4 | `fid` | El visitante tiene una cookie [`s_fid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=es), o si `aid` y `mid` no se pueden configurar por algún motivo. |
| 5 | Dirección IP, agente de usuario y dirección IP de puerta de enlace | El último recurso para identificar un visitante único si el explorador del visitante no acepta cookies. |

>[!NOTE]
>
>Cada ID de visitante de Analytics está vinculado a un perfil en los servidores de Adobe. Estos perfiles de visitante se eliminan después de 13 meses de inactividad, sin importar las expiraciones de las cookies de ID de visitantes.

## Comportamiento que afecta a la cantidad de visitantes únicos

Los identificadores de visitante únicos generalmente se almacenan en una cookie de explorador. Se cuenta un nuevo visitante único si realiza cualquiera de las siguientes acciones:

* Borra su caché en cualquier momento
* Abre un explorador diferente en el mismo equipo. Se cuenta un visitante único por explorador.
* La misma persona que explora el sitio en diferentes dispositivos. Se cuenta un visitante único por dispositivo. Puede utilizar el [análisis entre dispositivos](../cda/overview.md) para combinar visitantes mediante la métrica [Personas](people.md).
* Abre una sesión de navegación privada (como una pestaña de incógnito de Chrome).

Un nuevo visitante único *no se cuenta*, siempre y cuando se mantenga el identificador de la cookie:

* Cierra el explorador durante un periodo prolongado
* Actualiza el explorador a la versión más reciente
