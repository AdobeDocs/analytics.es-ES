---
title: Identificación de visitantes en Adobe Analytics
description: Obtenga información sobre cómo identificar visitantes en Adobe Analytics mediante las prácticas recomendadas más recientes.
exl-id: 8d26a556-84fe-4fb5-98d6-a16b69423e5b
TQID: https://experienceleague.adobe.com/uwEv9cl3234uiWhZEZLqgAVo42b-9L-9YEIGD97Pw-Q
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 617
ht-degree: 12%

---

# Identificación de visitantes en Adobe Analytics

La identificación del visitante es fundamental para el valor que proporciona Adobe Analytics para comprender el comportamiento del usuario en línea. Implica vincular visitas a la misma persona a lo largo del tiempo mediante un identificador común. La identificación precisa de los visitantes garantiza métricas fiables y admite una estrategia de implementación adecuada. Adobe recomienda que las organizaciones prioricen los servicios de identidad modernos para mantener la coherencia y la integridad de los datos en todas las plataformas.

La identificación de visitantes en Adobe Analytics consta de los siguientes componentes:

* Identificador del lado del cliente: generalmente se almacena en una cookie de origen. Las implementaciones que dependen de cookies de terceros son menos coherentes con la identificación del visitante debido a los estándares modernos de privacidad del explorador.
* Identificador del lado del servidor: Cada ID de visitante de Analytics está vinculado a un perfil en los servidores de Adobe. Estos perfiles de visitante permiten persistencia en variables como [eVars](/help/components/dimensions/evar.md). Los perfiles se eliminan tras 13 meses de inactividad, sin importar las expiraciones de las cookies de ID de visitantes.

## Orden de identificación de las operaciones de Adobe Analytics

Cuando Adobe recibe una visita, se realizan las siguientes comprobaciones en orden. Si una propiedad determinada está presente, Adobe utiliza ese identificador para la visita. Si hay varios identificadores presentes en una visita, solo se utiliza el primer método. Tenga en cuenta que el orden de las operaciones no refleja el orden en que Adobe recomienda identificar a los visitantes.

| Pedido utilizado | Parámetros de consulta | Presente cuando |
|---|---|---|
| **1<sup>st</sup>** | `vid` | Se establece la variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md). |
| **2<sup>nd</sup>** | `aid` | El visitante ya tiene una cookie [`s_vi`](https://experienceleague.adobe.com/es/docs/core-services/interface/data-collection/cookies/analytics). Se configura en implementaciones sin implementar el servicio de ID de visitante o antes de hacerlo. |
| **3<sup>rd</sup>** | `mid` | El visitante ya tiene una cookie [`s_ecid`](https://experienceleague.adobe.com/es/docs/core-services/interface/data-collection/cookies/analytics). Configurado en implementaciones que utilizan el [servicio de identidad de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es). Adobe recomienda utilizar el servicio de ID en todas las implementaciones, siempre que sea posible. |
| **4<sup>th</sup>** | `fid` | El visitante ya tiene una cookie [`s_fid`](https://experienceleague.adobe.com/es/docs/core-services/interface/data-collection/cookies/analytics). AppMeasurement genera automáticamente un identificador de reserva si `aid` y `mid` no se pueden establecer por algún motivo. |
| **5<sup>th</sup>** | Dirección IP + agente de usuario | Se utiliza como último recurso para identificar un visitante único si el explorador del visitante no acepta cookies. Se ha generado un ID de visitante con hash antes de la [confusión de IP](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md). Si la dirección IP no está disponible, se utilizarán otros detalles de IP (como la IP de la puerta de enlace). |

A continuación, el ID de visitante seleccionado tiene un hash y se convierte en su identificador del lado del servidor. Este identificador de servidor está disponible como `visid_high` + `visid_low` en [Fuentes de datos](/help/export/analytics-data-feed/data-feed-overview.md).

## Comportamiento que afecta a la cantidad de visitantes únicos

Los identificadores de visitante únicos generalmente se almacenan en una cookie de explorador. Se cuenta un nuevo visitante único si un visitante realiza cualquiera de las siguientes acciones:

* Borra sus cookies en cualquier momento. Cada vez que se borra la caché, se cuenta un visitante único para una visita.
* Las cookies de ID de visitante caducan debido a la configuración de privacidad de su explorador. Algunos exploradores incluyen métodos de prevención de seguimiento que limitan la duración de las cookies.
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
