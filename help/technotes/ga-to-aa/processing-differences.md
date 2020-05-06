---
title: Diferencias de procesamiento y arquitectura entre plataformas de Analytics
description: Descubra cómo se recopilan y muestran algunos datos de forma diferente entre plataformas como Adobe Analytics y Google Analytics.
translation-type: tm+mt
source-git-commit: 3211598c2ff43493b329a9be4fb6877ae29cf08b
workflow-type: tm+mt
source-wordcount: '494'
ht-degree: 66%

---


# Diferencias de procesamiento y arquitectura entre plataformas de Analytics

Aunque tanto Adobe Analytics como Google Analytics son herramientas de análisis, la forma de recopilar y procesar los datos entre plataformas es muy diferente. Utilice esta página para conocer algunas de las principales diferencias en la manera en que se recopilan dimensiones y métricas, y por qué podrían mostrar números diferentes en informes similares.

## [!UICONTROL Tasa de devoluciones]

[!UICONTROL La tasa de devolución es un KPI común que se utiliza para ayudar a medir la eficacia y la importancia de las páginas de aterrizaje en la mayoría de las herramientas de análisis. ] Esto se define comúnmente como las visitas que entran al sitio web pero no incluyen un clic en otra página.

* In Adobe Analytics, [!UICONTROL Bounce Rate] is calculated using the formula **Bounces divided by Entries**.
* In Google Analytics, [!UICONTROL Bounce Rate] is calculated using the formula **Single-page sessions divided by Sessions**.

En ambas plataformas, si se envían varias visitas en la misma sesión o visitas individuales, no se consideran como una devolución. En Adobe Analytics, los vínculos personalizados están disponibles y son bastante comunes, lo que puede impedir que una visita se cuente como una devolución. Google Analytics no suele enviar más de una solicitud de datos en la misma página.

To achieve better parity between reporting tools, use the [!UICONTROL Single Page Visits] metric in Adobe Analytics instead of [!UICONTROL Bounces] as part of a calculated metric. The [!UICONTROL Single Page Visits] metric includes the total number of visits that only included one-page view, or visits that enter the website but do not include a click to another page.

Consulte la métrica [Tasa de devolución](/help/components/c-variables/c-metrics/metrics-bounce-rate.md) en la Guía del usuario de componentes para obtener más información.

## [!UICONTROL Visitas y sesiones]

[!UICONTROL Las visitas] (conocidas como sesiones en Google Analytics) son un grupo de vistas de página realizadas por el mismo usuario en un corto período de tiempo. [!UICONTROL Las visitas en ambas plataformas suelen expirar tras 30 minutos de inactividad. ] Both platforms allow customization on when a [!UICONTROL Visit] expires. Existen varios escenarios que pueden causar diferencias en cada plataforma.

* **Fin de día:** Todas las sesiones de Google Analytics caducan después de las 23:59. Si el usuario sigue activo en el sitio después de las 24:00, se crea una nueva sesión. Adobe Analytics cuenta las visitas al día siguiente como parte de la misma visita individual.
* **Diferentes campañas:** Se inicia una nueva sesión en Google Analytics si cambia la fuente de campaña de un usuario. If a new [!UICONTROL Tracking Code] value is seen in Adobe Analytics, it is considered part of the same visit.
* **Anulación manual de sesión:** Se inicia una nueva sesión en Google Analytics si se utiliza `sessionControl` para iniciar o finalizar manualmente una sesión. [!UICONTROL Las visitas no se pueden finalizar manualmente en Adobe Analytics.]
* **Detección de visitas atípicas en Adobe Analytics:** Una nueva [!UICONTROL visita] en Adobe Analytics inicio automáticamente si un usuario alcanza las 12 horas de actividad continua, las 2500 visitas o las 100 visitas en un plazo de 100 segundos. Cada uno de estos criterios de detección se activa normalmente por la actividad de bots.

Consulte la métrica [Visitas](/help/components/c-variables/c-metrics/metrics-visit.md) en la Guía del usuario de componentes para obtener más información.
