---
title: Prácticas recomendadas para implementar canales de marketing de Adobe Analytics
description: Prácticas recomendadas actualizadas para usar los canales de marketing con Attribution y Customer Journey Analytics
feature: Marketing Channels
exl-id: a0ab818d-7165-4f34-bc43-1ed8d6215800
source-git-commit: 16fdad50b9d63bc6db07347c6ec91fb0d2df5722
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 97%

---

# Attribution con canales de marketing: prácticas recomendadas

[Los canales de marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md) son una valiosa y potente función de Adobe Analytics. Las directrices actuales relativas a la implementación del canal de marketing se formularon en un momento en que no existía ni [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) ni [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=es#cja-usecases).

Para futuras pruebas de la implementación de los canales de marketing y para garantizar que haya coherencia en la creación de informes con Attribution y Customer Journey Analytics, publicamos un conjunto de prácticas recomendadas actualizadas. Si ya está utilizando los canales de marketing, puede elegir las mejores opciones entre estas nuevas directrices. Si es nuevo en los canales de marketing, le recomendamos que se adhiera a todas las prácticas recomendadas nuevas.

Cuando se introdujeron los canales de marketing por primera vez, solo incluyeron dimensiones de primer y último contacto. Ya no se necesitan dimensiones explícitas de primer/último contacto con la versión actual de atribución. Adobe proporciona dimensiones genéricas de “Canal de marketing” y “Detalle del canal de marketing” para que pueda utilizarlas con el modelo de atribución deseado. Estas dimensiones genéricas se comportan de forma idéntica a las dimensiones del canal de último contacto, pero tienen una etiqueta diferente para evitar confusiones al usar canales de marketing con un modelo de atribución diferente.

Dado que las dimensiones del canal de marketing dependen de una definición de visita tradicional (según lo definen sus reglas de procesamiento), su definición de visita no se puede cambiar mediante grupos de informes virtuales. Estas prácticas revisadas permiten ventanas retrospectivas claras y controladas con Attribution y con Adobe Analytics.

## Práctica recomendada n.º 1: Aprovechar Attribution para el análisis controlado

Recomendamos utilizar [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) en lugar de la atribución de canal de marketing existente para ajustar el análisis de canal de marketing. Siga las otras prácticas recomendadas para garantizar la coherencia y controles sólidos de los análisis con Attribution.

![](assets/attribution.png)

* La configuración de las dimensiones de canal de marketing y detalle del canal de marketing establece puntos de contacto que se deben evaluar, correspondientes a cada instancia del canal de marketing.
* Para el análisis de métricas, su organización debe alinearse en uno o más modelos de atribución. Guarde las métricas personalizadas con este modelo para facilitar su reutilización.
* De forma predeterminada, los datos se asignan mediante el último contacto y la configuración del período de participación del visitante. Los modelos de métricas de Attribution ofrecen un buen control sobre las ventanas de retrospectiva y más variedad, incluida la [atribución algorítmica](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/algorithmic.html?lang=es#analysis-workspace).

## Práctica recomendada n.º 2: Sin definiciones de canal de actualización directa y de sesión

No se recomiendan los canales de actualización directa e interna/de sesión para su uso con modelos de atribución personalizados.

¿Qué sucede si su organización ya tiene configurada la actualización directa y de sesión? En este caso, le recomendamos que [cree una clasificación](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/classifications-mchannel.md) para el primer contacto/último contacto y deje los canales de actualización directa y de sesión sin clasificar. La dimensión clasificada arrojará los mismos resultados de Attribution que si esos canales nunca se hubieran configurado.

![](assets/direct-session-refresh.png)

## Práctica recomendada n.º 3: Habilitar el canal de último contacto de anulación para todos los canales

Los modelos de atribución personalizados utilizados con la dimensión de canal de marketing en Workspace funcionan mejor cuando esta configuración está habilitada. Si habilita esta configuración, la instancia de un canal de marketing se contabilizará cuando se encuentre un nuevo canal o detalle. Debe habilitarla para todos los canales, excepto para la actualización directa o interna/de sesión, que ya no recomendamos que se utilice con los modelos de atribución personalizados.

![](assets/override.png)

## Práctica recomendada n.º 4: Minimizar el periodo de participación del visitante

Si establece el período de participación del visitante como mínimo en 1 día, se minimiza la probabilidad de que persistan los valores. Debido a que los modelos de atribución personalizados (AIQ) permiten ventanas de retrospectiva flexibles, recomendamos configurar el valor mínimo para minimizar el impacto de esta configuración.

![](assets/expiration.png)

## Práctica recomendada n.º 5: Las reglas de procesamiento de los canales de marketing solo deben existir para los canales habilitados

Asegúrese de eliminar las reglas de procesamiento del canal de marketing de los canales desactivados. Las reglas solo deben existir para los canales de marketing que están marcados como habilitados.
