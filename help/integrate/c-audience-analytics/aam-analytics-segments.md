---
description: Tanto Analytics como Audience Manager emplean segmentos. Sin embargo, los segmentos de Analytics no son exactamente iguales a los de Audience Manager. Estas diferencias contribuyen, en parte, a las discrepancias que se pueden apreciar entre los informes de Analytics y de Audience Manager. Por tanto, es importante y útil comprender estas diferencias al comenzar a trabajar con segmentos en ambas soluciones.
title: Explicación de los segmentos en Analytics y Audience Manager
uuid: 13f7d1d7-6a3f-42f1-822e-8d3523999efa
exl-id: 2bc662e7-7552-41e1-9d4a-bc7aa81b8c1d
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 97%

---

# Explicación de los segmentos en Analytics y Audience Manager

Tanto Analytics como Audience Manager emplean segmentos. Sin embargo, los segmentos de Analytics no son exactamente iguales a los de Audience Manager. Estas diferencias contribuyen, en parte, a las discrepancias que se pueden apreciar entre los informes de Analytics y de Audience Manager. Por tanto, es importante y útil comprender estas diferencias al comenzar a trabajar con segmentos en ambas soluciones.

## Segmentos de Audience Manager {#section_417DC4B5648547778A27E42CE1D09900}

Un segmento de Audience Manager es un grupo de visitantes (ID de usuario) que cumplen un conjunto de características definidas y conectadas mediante reglas lógicas. Existen cuatro criterios para determinar si un visitante (ID de usuario) es parte de un segmento en Audience Manager:

* Reglas establecidas en los propios segmentos y las características que componen cada segmento. Estas reglas definen las condiciones que un ID de usuario debe cumplir o mostrar para poder pertenecer a un segmento.
* Modelado algorítmico. Los usuarios que cumplen los criterios de un segmento particular pueden pertenecer a otros en función del modelado y el análisis algorítmico.
* Intervalos de tiempo de vida (TTL). La pertenencia a un segmento puede caducar pasado un tiempo establecido o continuar indefinidamente.
* Momento de actualización y frecuencia. Definir cuándo y con qué frecuencia los usuarios tienen una interacción (realización de características) puede ayudar a crear segmentos basados en el nivel de interés real (o percibido) en un sitio, una sección o un creativo particular.

La pertenencia a segmentos es fluida en Audience Manager. Los usuarios pueden entrar o salir de un segmento dependiendo de si cumplen o no los criterios del mismo en un momento dado. Esto significa que la población de un segmento de Audience Manager puede aumentar o reducirse con el tiempo.

Un segmento de Audience Manager aparece como una audiencia en Analytics.

Para obtener más información, consulte [Datos de población de características y segmentos en el Generador de segmentos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html) y [Señales, características y segmentos](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html).

## Segmentos de Analytics {#section_62EC584BB7134E10923BCBA7F9BD89A8}

Un segmento de Analytics es un mecanismo de filtrado para los datos de sus informes. El filtrado puede producirse en el nivel del visitante o de la visita, y no solo estrictamente en el nivel del visitante, como sucede en Audience Manager. Hay varios factores importantes a considerar al comparar un segmento de Analytics con uno de Audience Manager:

* Los segmentos de Analytics operan sobre un conjunto de datos distinto de los de Audience Manager. Durante la recopilación de datos, Analytics aplica a estos muchos pasos de posprocesado que no están disponibles en Audience Manager. Estos pasos pueden incluir la persistencia de eVar, reglas de procesamiento, búsquedas (geolocalización, dispositivo móvil), VISTA y muchos otros. Audience Manager recibe los datos preprocesados mediante reenvío de lado del servidor (o DIL).

   Se producen discrepancias de datos comunes al comparar segmentos basados en dimensiones que nunca caducan en Analytics con la misma dimensión en Audience Manager. Por ejemplo, listVars o eVars de comercialización que nunca caducan.

   Por ejemplo, si eVar = azul y está establecido para que nunca caduque en Analytics, cualquier segmento de Analytics con el criterio “eVar = azul” siempre incluirá a este visitante. Por su parte, en Audience Manager, este visitante podría quedar fuera de un segmento definido de forma similar pasado un tiempo establecido.

* Los segmentos de Analytics tienen más capacidades que los de AAM. Los segmentos de Audience Manager siempre se evalúan en el nivel del visitante. Los segmentos de Analytics pueden definirse en el nivel del visitante o de la visita (o una combinación de estos). Además, Analytics admite capacidades de segmentación avanzada que Audience Manager no admite, como la segmentación secuencial.
* Como se ha mencionado antes, los usuarios pueden entrar o salir de un segmento dependiendo de si cumplen o no los criterios del mismo en un momento dado.

   Por el contrario, en Analytics, los visitantes se incluyen o excluyen de un segmento en función del intervalo de fechas de los informes. Por ejemplo, un solo visitante hizo una compra el mes pasado. En AAM, a este visitante se le incluiría en un segmento “comprador”, independientemente del intervalo de fechas. En Analytics, un informe basado en este mes no incluiría al visitante en el segmento. Sí lo incluiría, sin embargo, un informe basado en este mes y en el mes pasado.

Si desea obtener más información, consulte la [Guía de segmentación de Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html).
