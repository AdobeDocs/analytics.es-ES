---
description: Las métricas de participación asignan todo el crédito de los eventos de éxito a todos los valores de una eVar que se pasaron durante una visita. Las métricas de participación son útiles para determinar qué páginas, campañas u otros valores de variables personalizadas contribuyen en mayor medida al éxito del sitio. La participación se basa en visitas. Todos los valores de eVar de una visita anterior a la visita y que la incluye cuando se produce un evento reciben crédito de participación independientemente de la configuración de caducidad.
title: Participación
topic: Metrics
uuid: a7fa791d-0a77-429e-808e-4f97bb9ae5fc
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Participación

Las métricas de participación asignan todo el crédito de los eventos de éxito a todos los valores de una eVar que se pasaron durante una visita. Las métricas de participación son útiles para determinar qué páginas, campañas u otros valores de variables personalizadas contribuyen en mayor medida al éxito del sitio. La participación se basa en visitas. Todos los valores de eVar de una visita anterior a la visita y que la incluye cuando se produce un evento reciben crédito de participación independientemente de la configuración de caducidad.

Consulte [Participación de visitantes: Ad Hoc Analysis](/help/components/c-variables/c-metrics/metrics-visitor-participation.md) para obtener más información sobre cómo utilizan la participación los Ad Hoc Analysis.

Las métricas de participación tienen dos configuraciones por evento de conversión:

* **Deshabilitado**: Estado predeterminado de cada evento de conversión. Los datos de participación no se recopilarán para este evento.
* **Habilitado**: Los datos de participación se recopilan para este evento.

>[!NOTE] Puede habilitar la participación hasta un máximo de 100 eventos personalizados. Una vez superada esa cifra, puede crear métricas de participación en el creador [Métricas calculadas](https://marketing.adobe.com/resources/help/es_ES/analytics/calcmetrics/participation_metric.html).

Una vez habilitadas, las métricas de participación estarán disponibles automáticamente en todos los informes de conversión. Sin embargo, las métricas de participación también se pueden ver en informes de tráfico específicos a petición suya. Opcionalmente, puede solicitar que las métricas de participación estén disponibles en ciertos informes de tráfico personalizados.

## Ejemplo de participación de ingresos  {#section_DAB6C348201B454BB4ED01313AA777AF}

Suponga la siguiente secuencia:

1. Un usuario navega a su sitio y busca &quot;zapatos&quot;.
1. A continuación, el usuario busca &quot;zapatillas de tenis&quot;.
1. El usuario hace clic en un vínculo a la página del producto, agrega el artículo al carro y realiza una compra de $120.

Al mostrar los ingresos en el informe Términos de búsqueda interna, verá lo siguiente en función de la asignación seleccionada:

* **Primero**: &quot;zapatos&quot; recibiría crédito por los $120. &quot;zapatillas de tenis&quot; recibiría $0.
* **Último**: &quot;zapatillas de tenis&quot; recibiría crédito por los 120 dólares. &quot;zapatos&quot; recibiría $0.
* **Lineal**: Cada campaña obtendría un crédito de 60 dólares.

   La participación es similar a la asignación lineal, excepto que se concede crédito total a todos los valores. Si usa Ingresos (participación) como métrica, la asignación no se tiene en cuenta. Los ingresos (participación) de este ejemplo indicarían 120 $ para ambos términos de búsqueda.

>[!MORELIKETHIS]
>
>* [Cálculos de métricas](/help/components/c-variables/c-metrics/metrics-calculations.md)

