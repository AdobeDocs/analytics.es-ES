---
title: Visitantes únicos
description: Número de individuos (o dispositivos) únicos.
translation-type: tm+mt
source-git-commit: 9704267cd3ebf480facd68f6cca44167b1d9686d
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 10%

---


# Visitantes únicos

La métrica &quot;visitantes únicos&quot; muestra el número de ID de visitante para el valor de dimensión. Es una de las métricas más comunes utilizadas al determinar el tráfico, ya que proporciona una visión general de alto nivel de la popularidad de un valor de dimensión. Por ejemplo: un visitante puede llegar a su sitio todos los días durante un mes, pero todavía cuenta como un único visitante.

Si utiliza análisis [](../cda/overview.md)entre dispositivos, se cambiará el nombre de esta métrica a &quot;Dispositivos únicos&quot;.

## visitantes únicos diarios, semanales, mensuales, trimestrales y anuales

Informes y Analytics proporciona opciones para visitantes únicos diarios, semanales, mensuales, trimestrales y anuales. En lugar de contar un solo visitante único para todo el período de tiempo, los visitantes únicos se contabilizan en función de la métrica seleccionada. Por ejemplo: desea ver los visitantes únicos diarios del sitio. Si un visitante llega a su sitio por la mañana y de nuevo por la noche, se cuenta como un único visitante diario único. Si un visitante llega a su sitio el lunes y nuevamente el martes, se cuenta como dos visitantes únicos diarios.

El Analysis Workspace trata los visitantes únicos en función de la granularidad del informe. Por ejemplo, si utiliza la dimensión [Día](../dimensions/day.md) , verá visitantes únicos diarios para cada valor de dimensión. Sin embargo, para el total del informe, se anula la duplicación de visitantes únicos para el intervalo de fechas de la tabla improvisada.

## Cómo se calcula esta métrica

Esta métrica cuenta el número de ID de visitante únicos para un valor de dimensión determinado. Utiliza múltiples mecanismos avanzados para identificar visitantes únicos, ya que existen varias maneras de identificarlos. En el siguiente cuadro se lista la manera en que se identifica un visitante, junto con su prioridad. Algunas visitas pueden tener varios métodos de identificación de visitantes; en estos casos se utiliza el método de mayor prioridad.

| Pedido utilizado | Parámetro de consulta (método de recopilación) | Presente cuando |
| --- | --- | --- |
| 1 | `vid` | Se establece la [`visitorID`](/help/implement/vars/config-vars/visitorid.md) variable. |
| 2 | `aid` | Visitante tiene una [`s_vi`](https://docs.adobe.com/content/help/es-ES/core-services/interface/ec-cookies/cookies-analytics.html) cookie existente. Se configura en implementaciones sin o antes de implementar el servicio de ID de Visitante. |
| 3 | `mid` | Visitante tiene una [`s_ecid`](https://docs.adobe.com/content/help/es-ES/core-services/interface/ec-cookies/cookies-analytics.html) cookie existente. Se configura en implementaciones que utilizan el servicio [de identidad de](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html)Adobe Experience Cloud. |
| 4 | `fid` | Visitante tiene una [`s_fid`](https://docs.adobe.com/content/help/es-ES/core-services/interface/ec-cookies/cookies-analytics.html) cookie existente, o si `aid` y `mid` no se pudo configurar por ningún motivo. |
| 5 | Dirección IP, agente de usuario y dirección IP de puerta de enlace | Último recurso para identificar un visitante único si el explorador del visitante no acepta cookies. |

>[!NOTE]
>
>Cada ID de visitante de Analytics está vinculado a un perfil en los servidores de Adobe. Estos perfiles de visitante se eliminan después de al menos 13 meses de inactividad, independientemente de la caducidad de cualquier cookie de ID de visitante.

## Comportamiento que afecta al recuento de visitantes único

Los identificadores de visitante únicos generalmente se almacenan en una cookie de explorador. Se cuenta un nuevo visitante único si realiza cualquiera de las siguientes acciones:

* Borra su caché en cualquier momento
* Abre un explorador diferente en el mismo equipo. Se cuenta un visitante único por explorador.
* La misma persona que explora el sitio en diferentes dispositivos. Se cuenta un visitante único por dispositivo. Puede utilizar el análisis [entre](../cda/overview.md) dispositivos para combinar visitantes mediante la métrica [Personas](people.md) .
* Abre una sesión de navegación privada (como la ficha Incognito de Chrome).

Un nuevo visitante único *no se cuenta* , siempre y cuando se mantenga el identificador de cookie:

* Cierra el explorador durante un período prolongado
* Actualiza el explorador a la versión más reciente
