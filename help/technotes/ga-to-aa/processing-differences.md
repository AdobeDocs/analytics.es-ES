---
title: Diferencias de procesamiento y arquitectura entre plataformas de Analytics
description: Descubra cómo se recopilan y muestran algunos datos de forma diferente entre plataformas como Adobe Analytics y Google Analytics.
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Diferencias de procesamiento y arquitectura entre plataformas de Analytics

Aunque tanto Adobe Analytics como Google Analytics son herramientas de Analytics, la forma en que se recopilan y procesan los datos entre plataformas es muy diferente. Utilice esta página para comprender algunas de las diferencias clave en la manera en que se recopilan determinadas dimensiones y métricas, y por qué podrían mostrar números diferentes en informes similares.

## Tasa de devoluciones

La tasa de devoluciones es un KPI común que se utiliza para ayudar a medir la eficacia y la importancia de las páginas de aterrizaje en la mayoría de las herramientas de análisis. Esto se define comúnmente como las visitas que entran al sitio web pero no incluyen un clic en otra página.

* En Adobe Analytics, la tasa de devoluciones se calcula mediante la fórmula **Devoluciones divididas por entradas**.
* En Google Analytics, la Tasa de salida hacia otro sitio se calcula mediante la fórmula Sesiones de **una sola página divididas por Sesiones**.

En ambas plataformas, si se envían varias visitas en la misma visita o sesión, no se considera una devolución. En Adobe Analytics, los vínculos personalizados están disponibles y son bastante comunes, lo que puede impedir que una visita se cuente como una devolución. Google Analytics no suele enviar más de una solicitud de datos en la misma página.

Para lograr una mejor paridad entre las herramientas de informes, utilice la métrica Visitas a una sola página en Adobe Analytics en lugar de Devoluciones como parte de una métrica calculada. La métrica Visitas a una sola página incluye el número total de visitas que solo incluyeron una vista de una página o visitas que ingresaron al sitio web pero no incluyeron un clic en otra página.

Consulte la métrica [Tasa](/help/components/c-variables/c-metrics/metrics-bounce-rate.md) de devoluciones en la guía del usuario Componentes para obtener más información.

## Visitas y sesiones

Las visitas (conocidas como sesiones en Google Analytics) son un grupo de vistas de página realizadas por el mismo usuario en un corto período de tiempo. Las visitas en ambas plataformas suelen caducar tras 30 minutos de inactividad. Ambas plataformas permiten la personalización cuando caduca una visita. Existen varios escenarios que pueden causar diferencias en cada plataforma.

* **** Fin de día: Todas las sesiones de Google Analytics caducan después de las 11:59 de un día determinado. Si el usuario sigue activo en el sitio después de las 12:00, se crea una nueva sesión. Adobe Analytics continúa las visitas al día siguiente como parte de la misma visita.
* **** Diferentes campañas: Se inicia una nueva sesión en Google Analytics si cambia la fuente de campaña de un usuario. Si se ve un nuevo valor de código de seguimiento en Adobe Analytics, se considera parte de la misma visita.
* **** Anulación manual de sesión: Se inicia una nueva sesión en Google Analytics si se utiliza `sessionControl` para iniciar o finalizar manualmente una sesión. Las visitas no se pueden finalizar manualmente en Adobe Analytics.
* **** Detección de visitas atípicas en Adobe Analytics: Una nueva visita en Adobe Analytics se inicia automáticamente si un usuario llega a las 12 horas de actividad continua, a las 2500 visitas o a las 100 visitas en un plazo de 100 segundos. Cada uno de estos criterios de detección se activa normalmente por la actividad de bots.

Consulte la métrica [Visitas](/help/components/c-variables/c-metrics/metrics-visit.md) en la guía del usuario Componentes para obtener más información.
