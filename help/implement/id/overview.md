---
title: Identificación de visitantes en Adobe Analytics
description: Obtenga información sobre cómo identificar visitantes en Adobe Analytics mediante las prácticas recomendadas más recientes.
source-git-commit: 5bd1914dc52c664348f30793761f0fc347343156
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 17%

---

# Identificación de visitantes en Adobe Analytics

La identificación del visitante es fundamental para el valor que proporciona Adobe Analytics para comprender el comportamiento del usuario en línea. Implica vincular visitas a la misma persona a lo largo del tiempo mediante un identificador común. La identificación precisa de los visitantes garantiza métricas fiables y admite una estrategia de implementación adecuada. Adobe recomienda que las organizaciones prioricen los servicios de identidad modernos para mantener la coherencia y la integridad de los datos en todas las plataformas.

La identificación de visitantes en Adobe Analytics consta de los siguientes componentes:

* Identificador del lado del cliente: generalmente se almacena en una cookie de origen. Las implementaciones que dependen de cookies de terceros son menos coherentes con la identificación del visitante debido a los estándares modernos de privacidad del explorador.
* Identificador del lado del servidor: Cada ID de visitante de Analytics está vinculado a un perfil en los servidores de Adobe. Estos perfiles de visitante se eliminan después de 13 meses de inactividad, sin importar las caducidades de las cookies de ID de visitantes.

## Orden de identificación de las operaciones de Adobe Analytics

Cuando Adobe recibe una visita, se realizan las siguientes comprobaciones en orden. Si una propiedad determinada está presente, Adobe utiliza ese identificador para la visita. Si hay varios identificadores presentes en una visita, solo se utiliza el primer método.

| Pedido utilizado | Parámetros de consulta | Presente cuando |
|---|---|---|
| **1<sup>st</sup>** | `vid` | Se establece la variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md). |
| **2<sup>nd</sup>** | `aid` | El visitante ya tiene una cookie [`s_vi`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=es). Se configura en implementaciones sin implementar el servicio de ID de visitante o antes de hacerlo. |
| **3<sup>rd</sup>** | `mid` | El visitante ya tiene una cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=es). Configurado en implementaciones que utilizan el [servicio de identidad de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es). Adobe recomienda utilizar el servicio de ID en todas las implementaciones, siempre que sea posible. |
| **4<sup>th</sup>** | `fid` | El visitante tiene una cookie [`s_fid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=es) existente, o si `aid` y `mid` no se pudieron establecer por algún motivo. |
| **5<sup>th</sup>** | Dirección IP, agente de usuario y dirección IP de puerta de enlace | Se utiliza como último recurso para identificar un visitante único si el explorador del visitante no acepta cookies. |

## Comportamiento que afecta a la cantidad de visitantes únicos

Los identificadores de visitante únicos generalmente se almacenan en una cookie de explorador. Se cuenta un nuevo visitante único si se produce alguna de las siguientes situaciones:

* Borra sus cookies en cualquier momento. Cada vez que se borra la caché, se cuenta un visitante único para una visita.
* Las cookies de ID de visitante caducan debido a la configuración de privacidad de su explorador. Muchos exploradores modernos incluyen una forma de prevención del seguimiento.
* Abre un explorador diferente en el mismo equipo. Se cuenta un visitante único por explorador.
* Abre una sesión de navegación privada (como una pestaña de incógnito de Chrome). Se cuenta un visitante único por sesión de navegación después de cerrar todas las pestañas.
* Visita el sitio en diferentes dispositivos. Se cuenta un visitante único por dispositivo.
* Visita el sitio después de más de 13 meses de inactividad.

Considere la posibilidad de usar [costura](https://experienceleague.adobe.com/es/docs/analytics-platform/using/stitching/overview) en Customer Journey Analytics para identificar a la misma persona mediante varios navegadores o dispositivos.

## Comportamiento que no afecta a la cantidad de visitantes únicos

Se cuenta un nuevo visitante único *no*, siempre y cuando se mantenga el identificador del visitante:

* Cierra el explorador (durante menos de 13 meses)
* Actualiza el explorador a la versión más reciente
* Reinicia el equipo
