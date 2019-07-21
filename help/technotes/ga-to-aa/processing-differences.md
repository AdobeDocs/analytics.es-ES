---
title: Diferencias de procesamiento y arquitectura entre plataformas de Analytics
description: Obtenga información sobre cómo se recopilan y se muestran algunos datos de forma diferente entre plataformas como Adobe Analytics y Google Analytics.
translation-type: tm+mt
source-git-commit: a5f612ba5e8446a56bc2bd252a8781e8ab1de403

---


# Diferencias de procesamiento y arquitectura entre plataformas de Analytics

Aunque Adobe Analytics y Google Analytics son ambas herramientas de Analytics, la manera en que se recopilan y procesan los datos entre plataformas es muy diferente. Utilice esta página para comprender algunas de las diferencias clave en la forma en que se recopilan determinadas dimensiones y métricas y por qué pueden mostrar números diferentes en informes similares.

## Tasa de salida hacia otro sitio

La tasa de devoluciones es un KPI común que se utiliza para medir la eficacia y la importancia de las páginas de aterrizaje en la mayoría de las herramientas de análisis. Esto se suele definir como visitas que ingresan al sitio Web pero no incluyen un clic para otra página.

* In Adobe Analytics, Bounce Rate is calculated using the formula **Bounces divided by Entries**.
* In Google Analytics, Bounce Rate is calculated using the formula **Single-page sessions divided by Sessions**.

En ambas plataformas, si se envían varias visitas en la misma visita o sesión, no se considera una devolución. En Adobe Analytics, los vínculos personalizados están disponibles y son bastante comunes, lo que puede evitar que una visita se contabilice como una devolución. Google Analytics generalmente no envía más de una solicitud de datos en la misma página.

Para lograr una mejor paridad entre las herramientas de informes, utilice la métrica Visitas a una sola página en Adobe Analytics, en lugar de Devoluciones como parte de una métrica calculada. La métrica Visitas a una sola página incluye el número total de visitas que sólo incluyen vista de una página o visitas que ingresan al sitio pero no incluyen un clic para otra página.

See the [Bounce Rate](../../components/c-variables/c-metrics/metrics-bounce-rate.md) metric in the Components user guide for more information.

## Visitas y sesiones

Las visitas (conocidas como sesiones en Google Analytics) son un grupo de vistas de páginas realizadas por el mismo usuario en poco tiempo. Las visitas en ambas plataformas suelen caducar después de 30 minutos de inactividad. Ambas plataformas permiten la personalización cuando caduca una visita. Existen varios escenarios que pueden causar diferencias en cada plataforma.

* **Final del día:** Todas las sesiones de Google Analytics caducan a las 11:59 PM en un día determinado. Si el usuario aún está activo en el sitio después de 12 AM, se crea una nueva sesión. Adobe Analytics continúa las visitas al día siguiente como parte de la misma visita.
* **Diferentes campañas:** Se inicia una nueva sesión en Google Analytics si cambia la fuente de campaña de un usuario. Si se ve un nuevo valor de código de seguimiento en Adobe Analytics, se considera parte de la misma visita.
* **Anulación de sesión manual:** Se inicia una nueva sesión en Google Analytics si se utiliza `sessionControl` para iniciar o finalizar manualmente una sesión. Las visitas no se pueden finalizar manualmente en Adobe Analytics.
* **Detección de visitas de Outlier en Adobe Analytics:** Una nueva visita de Adobe Analytics se inicia automáticamente si un usuario alcanza 12 horas de actividad continua, 2500 visitas o 100 visitas en 100 segundos. Cada uno de estos criterios de detección suele desencadenarse por actividad bot.

See the [Visits](../../components/c-variables/c-metrics/metrics-visit.md) metric in the Components user guide for more information.
