---
description: Las métricas de participación otorgan crédito total de eventos de éxito a todos los valores de un eVar transferidos durante una visita. Las métricas de participación son útiles para determinar qué páginas, campañas u otros valores de variables personalizadas contribuyen más al éxito del sitio. La participación se basa en visitas. Todos los valores de eVar de una visita anterior y que incluyan la visita cuando se produce un evento reciben crédito de participación, independientemente del valor de caducidad.
title: Participación
topic: Metrics
uuid: a7fa791d-0a77-429e-808e-4f97bb9ae5fc
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Participación

Las métricas de participación otorgan crédito total de eventos de éxito a todos los valores de un eVar transferidos durante una visita. Las métricas de participación son útiles para determinar qué páginas, campañas u otros valores de variables personalizadas contribuyen más al éxito del sitio. La participación se basa en visitas. Todos los valores de eVar de una visita anterior y que incluyan la visita cuando se produce un evento reciben crédito de participación, independientemente del valor de caducidad.

Consulte [Participación de visitantes: Ad Hoc Analysis](/help/components/c-variables/c-metrics/metrics-visitor-participation.md) para obtener más información sobre cómo utilizan la participación los Ad Hoc Analysis.

Las métricas de participación tienen dos configuraciones por evento de conversión:

* **Deshabilitado**: estado predeterminado de cada evento de conversión. La participación no se recopilará para este evento.
* **Habilitado**: los datos de participación se recopilan para este evento.

> [!NOTE] Puede habilitar la participación hasta un máximo de 100 eventos personalizados. Una vez superada esa cifra, puede crear métricas de participación en el creador [Métricas calculadas](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/participation_metric.html).

Una vez habilitadas, las métricas de participación estarán disponibles automáticamente en todos los informes de conversión. No obstante, las métricas de participación también se pueden ver en informes de tráfico específicos si así se solicita. Opcionalmente, se puede solicitar que las métricas de participación estén disponibles en determinados informes de tráfico.

## Ejemplo de participación de ingresos  {#section_DAB6C348201B454BB4ED01313AA777AF}

Imagine la secuencia siguiente:

1. Un usuario accede a su sitio y busca "zapatillas".
1. A continuación, el mismo usuario busca "zapatillas de tenis".
1. El usuario hace clic en vínculos a páginas de productos, los añade al carro de compras y realiza una compra de 120 €.

Al mostrar los ingresos en el Informe de términos de búsqueda internos, verá lo siguiente según la asignación seleccionada:

* **Primero**: "zapatillas" recibiría el crédito de los 120 €. "zapatillas de tenis" recibiría 0 €.
* **Por último**: "zapatillas de tenis" recibiría el crédito de los 120 €. "zapatillas" recibiría 0 €.
* **Lineal**: cada campaña obtendría un crédito de 60 dólares.

   La participación es similar a la asignación lineal, con la excepción de que se otorga crédito total a todos los valores. Si usa Ingresos (participación) como la métrica, se ignorará la asignación. Ingresos (participación) en este ejemplo asignaría 120 € a los dos términos de búsqueda.

>[!MORELIKETHIS]
>
>* [Cálculos de métricas](/help/components/c-variables/c-metrics/metrics-calculations.md)

