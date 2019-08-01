---
description: La siguiente figura muestra cómo funciona la recopilación de datos.
keywords: DFA
seo-description: La siguiente figura muestra cómo funciona la recopilación de datos.
seo-title: Integración de Adobe Integration en tiempo real
solution: Analytics
title: Integración de Adobe Integration en tiempo real
topic: Data Connectors
uuid: 5 dce 319 c -7 d 4 b -4475-8 e 6 d-dc 5 c 972 a 82 e 9
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Integración de Adobe: recopilación de datos en tiempo real{#adobe-integration-real-time-data-collection}

La siguiente figura muestra cómo funciona la recopilación de datos.

![](assets/DFA_data_collection.png)

La parte de recopilación de datos de la integración de Adobe comienza cuando el visitante llega a la página de aterrizaje (1). El código de recopilación de datos de Adobe que se ejecuta en la página de aterrizaje no conoce el historial que el visitante ha tenido con los anuncios publicados. El equipo de DFA de Google ha coordinado un servicio que se ejecuta en el Servidor de Floodlight DFA para permitir que el código de Adobe realice una consulta a la información de anuncio sobre el visitante que se encuentra en el sitio (2). Para obtener estos datos, demora temporalmente la señalización de imagen de Adobe y solicita los datos del Servidor de Floodlight.

Cuando llegan los datos, o si tardan demasiado tiempo, activa la visita a los servidores de seguimiento de Adobe (3).

El módulo Integrate es un módulo principal y especial de JavaScript de Adobe que hace que se demore la señalización de imagen de Adobe, esperando la solicitud de un tercero durante un período de tiempo específico ( *`s.maxDelay`*). *`s.maxDelay`* define cuánto tiempo el módulo Integrate esperará datos del Servidor de Floodlight DFA antes de activar la etiqueta de imagen en el explorador del visitante. Este comportamiento es importante para que los datos básicos del visitante se sigan recopilando, incluso cuando los Servidores de Floodlight DFA no están en funcionamiento o bien tienen una carga intensiva. Si los datos de Floodlight llegan antes de que *`s.maxDelay`* hayan caducado, los datos de seguimiento de Adobe aún se activarán de forma inmediata, y contendrán los datos de DFA adicionales.

Cuando se agota el tiempo de espera, el código de la página puede especificar un Evento de Informes y análisis de Adobe para utilizarse como Evento de tiempo de espera. Este evento resulta útil a la hora de diagnosticar problemas con la integración, o a la hora de ajustar *`s.maxDelay`*. En casos donde existen tiempos de espera excesivos, incremente *`s.maxDelay`*. *`s.maxDelay`* puede establecerse demasiado alto, en cuyo caso los visitantes pueden tener la posibilidad de abandonar el sitio antes de que caduque el *`s.maxDelay`* temporizador. For more discussion on this topic, see [Tuning s.maxDelay](../dfa-data-connector-analytics/dfa-integration/dfa-tuning-s-maxlelay.md#concept-6deb28eee18e414db220d6009d449f0d).

Algunas veces el Servidor de Floodlight responde con errores acerca del visitante. Esto generalmente sucede cuando el Servidor de Floodlight no conoce nada sobre el visitante, ya que el visitante aún no ha visto anuncios o no tiene una cookie de visitante DFA. El código de la página puede especificar una variable (eVar) de Conversión personalizada que recopilará estos errores, y puede ayudar en la resolución de problemas de implementación o destacar problemas con la transacción de Google. Los errores más comunes son Sin historial, Sin cookie, Error de consulta y No optó, tal como se describe en la siguiente tabla:

| Error | Nombre | Descripción |
|---|---|---|
| nh | Sin historial | El visitante no ha visto ni hecho clic en anuncios. |
| nc | Sin cookie | El visitante no tiene un código de visitante DFA. |
| qe | Error de consulta | Hubo un error al consultar los datos del Servidor de Floodlight. |
| oo | No optó | El visitante no optó por el rastreo de clics o la impresión de Google. |

