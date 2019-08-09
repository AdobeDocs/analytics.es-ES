---
description: 'Existen varias maneras en que esta integración obtiene datos sobre el visitante que llega por anuncio. La primera manera es haciendo clic en un anuncio y llegar en una página de aterrizaje etiquetada, también denominada pulsación '
keywords: DFA
seo-description: 'Existen varias maneras en que esta integración obtiene datos sobre el visitante que llega por anuncio. La primera manera es haciendo clic en un anuncio y llegar en una página de aterrizaje etiquetada, también denominada pulsación '
seo-title: Información general sobre la integración del servicio de publicidad
solution: Analytics
title: Información general sobre la integración del servicio de publicidad
topic: Data Connectors
uuid: e 286 f 61 e -4 b 09-48 b 5-b 1 e 9-3 c 07 b 6 face 24
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Información general sobre la integración del servicio de publicidad{#ad-serving-integration-overview}

Existen varias maneras en que esta integración obtiene datos sobre el visitante que llega por anuncio. La primera manera es haciendo clic en un anuncio y llegar en una página de aterrizaje etiquetada, también denominada pulsación:

![](assets/Diagram1.png)

El visitante llega en un sitio del publicador, que aloja el anuncio. Este anuncio tiene un identificador único, denominado ID de anuncio. Los anuncios comprenden una ubicación más un creativo, que describen dónde se encuentra el anuncio en el sitio del publicador y qué contenido se mostró al visitante. Cuando el visitante obtiene este anuncio, ubicación o creativo desde los servidores de contenido DFA, rastrea una impresión en los Servidores de Floodlight DFA para este visitante (1).

Si el visitante hace clic en el anuncio (2), se realiza una consulta al Servidor de Floodlight que cuenta un clic, 302 redirecciona (3) al visitante a la página de aterrizaje. Se denomina una pulsación cuando el visitante ha llegado en la página de aterrizaje. Esta página contiene código de seguimiento de Adobe que realiza una consulta de datos desde el Servidor de Floodlight DFA. 

No se denomina una pulsación cuando el visitante no llega realmente a la página de aterrizaje después de que el Servidor de Floodlight haya rastreado un clic. Puede que algunos anuncios e implementaciones realmente no hagan que el explorador del visitante obedezca el redireccionamiento 302. Para obtener más información sobre este tema, consulte [Reconciliación de discrepancias de métricas](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-reconciling-metric-discrepancies.md#concept-8c31ebe761ca4b3fab1e3a18ef5d098f).

La siguiente métrica capturada por esta integración ocurre cuando el visitante recibe la impresión de anuncio, no hace clic, pero en algún momento próximo inminente llega a la página de aterrizaje por otro medio.

![](assets/Viewthrough.png)

Este escenario se denomina visualización. La diferencia en este escenario con el escenario de pulsación es que el visitante no hace clic en el anuncio, sino que en cambio continúa con otras actividades antes de llegar a la página de aterrizaje (2). En el caso más simple, el visitante escribe la dirección URL de la página de aterrizaje en el explorador. En otros casos, el visitante continúa explorando pero luego usa un motor de búsqueda, que lleva al visitante a la página de aterrizaje. En cualquier caso, el usuario llega a la página de aterrizaje.
