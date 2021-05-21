---
title: Diferencias de procesamiento y arquitectura entre plataformas de Analytics
description: Descubra cómo se recopilan y muestran algunos datos de forma diferente entre plataformas como Adobe Analytics y Google Analytics.
exl-id: 3e457915-3c2d-49f7-9b77-df18c04d49cd
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '494'
ht-degree: 100%

---

# Diferencias de procesamiento y arquitectura entre plataformas de Analytics

Aunque tanto Adobe Analytics como Google Analytics son herramientas de análisis, la forma de recopilar y procesar los datos entre plataformas es muy diferente. Utilice esta página para conocer algunas de las principales diferencias en la manera en que se recopilan dimensiones y métricas, y por qué podrían mostrar números diferentes en informes similares.

## [!UICONTROL Tasa de devoluciones]

La [!UICONTROL tasa de devolución] es un KPI común que se utiliza para ayudar a medir la eficacia y la importancia de las páginas de aterrizaje en la mayoría de las herramientas de análisis. Esto se define comúnmente como las visitas que entran al sitio web pero no incluyen un clic en otra página.

* En Adobe Analytics, la [!UICONTROL Tasa de salida hacia otro sitio] se calcula mediante la fórmula **Devoluciones divididas por entradas**.
* En Google Analytics, la [!UICONTROL Tasa de salida hacia otro sitio] se calcula mediante la fórmula **Sesiones de una sola página divididas por sesiones**.

En ambas plataformas, si se envían varias visitas en la misma sesión o visitas individuales, no se consideran como una devolución. En Adobe Analytics, los vínculos personalizados están disponibles y son bastante comunes, lo que puede impedir que una visita se cuente como una devolución. Google Analytics no suele enviar más de una solicitud de datos en la misma página.

Para lograr una mejor paridad entre las herramientas de creación de informes, utilice la métrica [!UICONTROL Visitas a una sola página] en Adobe Analytics en lugar de [!UICONTROL Devoluciones] como parte de una métrica calculada. La métrica [!UICONTROL Visitas a una sola página] incluye el número total de visitas que solo incluyeron una vista de una página o visitas que entraron al sitio web, pero no incluyen un clic en otra página.

Consulte la métrica [Tasa de devolución](/help/components/metrics/bounce-rate.md) en la Guía del usuario de componentes para obtener más información.

## [!UICONTROL Visitas y sesiones]

Las [!UICONTROL visitas] (conocidas como sesiones en Google Analytics) son un grupo de vistas de página llevadas a cabo por el mismo usuario en un corto período de tiempo. [!UICONTROL Las visitas] en ambas plataformas suelen expirar tras 30 minutos de inactividad. Ambas plataformas permiten la personalización cuando caduca una [!UICONTROL visita]. Existen varios escenarios que pueden causar diferencias en cada plataforma.

* **Fin de día:** Todas las sesiones de Google Analytics caducan después de las 23:59. Si el usuario sigue activo en el sitio después de las 24:00, se crea una nueva sesión. Adobe Analytics cuenta las visitas al día siguiente como parte de la misma visita individual.
* **Diferentes campañas:** Se inicia una nueva sesión en Google Analytics si cambia la fuente de campaña de un usuario. Si se ve un nuevo valor de [!UICONTROL código de seguimiento] en Adobe Analytics, se considera parte de la misma visita.
* **Anulación manual de sesión:** Se inicia una nueva sesión en Google Analytics si se utiliza `sessionControl` para iniciar o finalizar manualmente una sesión. [!UICONTROL Las visitas no se pueden finalizar manualmente en Adobe Analytics.]
* **Detección de visitas atípicas en Adobe Analytics:** Una nueva [!UICONTROL Visita] se inicia automáticamente en Adobe Analytics si un usuario alcanza las 12 horas de actividad continua, las 2500 visitas o las 100 visitas en un plazo de 100 segundos. Cada uno de estos criterios de detección se activa normalmente por la actividad de bots.

Consulte la métrica [Visitas](/help/components/metrics/visits.md) en la Guía del usuario de componentes para obtener más información.
