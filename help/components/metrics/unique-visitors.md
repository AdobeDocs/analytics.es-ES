---
title: Visitantes únicos
description: Número de personas únicas (o dispositivos).
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '563'
ht-degree: 100%

---


# Visitantes únicos

La métrica “visitantes únicos” muestra el número de ID de visitante para el elemento de dimensión. Es una de las métricas más comunes utilizadas para determinar el tráfico, ya que proporciona una visión general de alto nivel de la popularidad de un elemento de dimensión. Por ejemplo: un visitante puede llegar a su sitio todos los días durante un mes, pero contará como un único visitante.

Si utiliza [análisis entre dispositivos](../cda/overview.md), se cambiará el nombre de esta métrica a “Dispositivos únicos”.

## Visitantes únicos diarios, semanales, mensuales, trimestrales y anuales

Reports &amp; Analytics proporciona opciones para visitantes únicos diarios, semanales, mensuales, trimestrales y anuales. En lugar de contar un solo visitante único para todo el periodo de tiempo, los visitantes únicos se contabilizan en función de la métrica seleccionada. Por ejemplo, desea ver los visitantes únicos diarios del sitio. Si un visitante llega a su sitio por la mañana y de nuevo por la noche, se cuenta como un único visitante diario. Si un visitante llega a su sitio el lunes y nuevamente el martes, se cuenta como dos visitantes únicos diarios.

Analysis Workspace trata los visitantes únicos en función de la granularidad del informe. Por ejemplo, si utiliza la dimensión [Día](../dimensions/day.md), verá visitantes únicos diarios para cada elemento de dimensión. Sin embargo, de cara al total del informe, se anula la duplicación de visitantes únicos para el intervalo de fechas de la tabla de forma libre.

## Cálculo de esta métrica

Esta métrica cuenta el número de ID del visitante único para un elemento de dimensión determinado. Utiliza varios mecanismos avanzados para identificar visitantes únicos, ya que existen diferentes maneras de identificarlos. En el siguiente cuadro se enumera las formas en las que se identifica a un visitante, junto a su prioridad. Algunas visitas pueden tener varios métodos de identificación; en estos casos se utiliza el método de mayor prioridad.

| Pedido utilizado | Parámetro de consulta (método de recopilación) | Presente cuando |
| --- | --- | --- |
| 1 | `vid` | Se establece la variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md). |
| 2 | `aid` | El visitante tiene una cookie de [`s_vi`](https://docs.adobe.com/content/help/es-ES/core-services/interface/ec-cookies/cookies-analytics.html). Se configura en implementaciones sin implementar el servicio de ID de visitante o antes de hacerlo. |
| 3 | `mid` | El visitante tiene una cookie de [`s_ecid`](https://docs.adobe.com/content/help/es-ES/core-services/interface/ec-cookies/cookies-analytics.html). Se configura en implementaciones que utilizan el [Servicio de identidad de Adobe Experience Cloud](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html). |
| 4 | `fid` | El visitante tiene una cookie [`s_fid`](https://docs.adobe.com/content/help/es-ES/core-services/interface/ec-cookies/cookies-analytics.html), o si `aid` y `mid` no se pueden configurar por algún motivo. |
| 5 | Dirección IP, agente de usuario y dirección IP de puerta de enlace | El último recurso para identificar un visitante único si el explorador del visitante no acepta cookies. |

>[!NOTE]
>
>Cada ID de visitante de Analytics está vinculado a un perfil en los servidores de Adobe. Estos perfiles de visitante se eliminan después de 13 meses de inactividad, sin importar las expiraciones de las cookies de ID de visitantes.

## Comportamiento que afecta al recuento de visitantes único

Los identificadores de visitante únicos generalmente se almacenan en una cookie de explorador. Se cuenta un nuevo visitante único si realiza cualquiera de las siguientes acciones:

* Borra su caché en cualquier momento
* Abre un explorador diferente en el mismo equipo. Se cuenta un visitante único por explorador.
* La misma persona que explora el sitio en diferentes dispositivos. Se cuenta un visitante único por dispositivo. Puede utilizar el [análisis entre dispositivos](../cda/overview.md) para combinar visitantes mediante la métrica [Personas](people.md).
* Abre una sesión de navegación privada (como una pestaña de incógnito de Chrome).

Un nuevo visitante único *no se cuenta*, siempre y cuando se mantenga el identificador de la cookie:

* Cierra el explorador durante un periodo prolongado
* Actualiza el explorador a la versión más reciente
