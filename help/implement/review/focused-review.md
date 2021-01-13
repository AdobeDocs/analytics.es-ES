---
title: Revisión centrada (después de cada lanzamiento de sitio web)
description: Siga estos pasos para asegurarse de que la implementación no contenga errores y esté en línea con los KPI.
translation-type: tm+mt
source-git-commit: 8c4ea92523f5e969b9ffe462ea6fb4c21c176141
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# Revisión centrada (después de cada lanzamiento de sitio web)

¿Por qué debería revisar la implementación cada pocos meses? Así que puede abordar cualquier problema con la calidad de los datos mientras son pequeños. Si realiza esta revisión centrada de manera consistente después de cada lanzamiento de sitio web, verá que sus [revisiones completas](/help/implement/review/full-review.md) bianuales son mucho más fáciles. También evitará que las cuestiones pequeñas se conviertan en cuestiones de grandes datos que podrían erosionar la confianza de los interesados.

## 1. Inicio con los 5 KPI principales.

Conocer los 5 indicadores de rendimiento clave (KPI) más importantes le ayudará a determinar las métricas y dimensiones asociadas que debe examinar. Si no ha actualizado los KPI en los últimos 6 meses o si su empresa aún no ha creado KPI, siga [estas instrucciones](/help/implement/review/define-kpis.md).

## 2. Asegúrese de que las métricas y variables de KPI siguen funcionando correctamente.

Recuerde que las actualizaciones de código a lo largo del tiempo pueden tener ramificaciones no deseadas. Desea asegurarse de que todas las métricas y dimensiones asociadas con los [5 KPI principales](/help/implement/review/define-kpis.md) sigan funcionando correctamente. Idealmente, esto debería hacerse justo después de la publicación de un sitio web; si no lo ha hecho en los últimos meses, hágalo *ahora*. Para ello:

* Cree paneles para ver las vistas de tendencias por hora de estas métricas y variables críticas (o configure [alertas inteligentes](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html#analysis-workspace) para cada métrica). A continuación, supervise durante uno o dos días para asegurarse de que obtiene los datos esperados y de que los datos son correctos. Busque puntos de inflexión. Estar preparados para remediar cualquier problema crítico inmediatamente. Si encuentra alguna discrepancia, consulte la capa de datos, las reglas del administrador de etiquetas y las reglas de procesamiento para averiguar por qué.
* Vuelva a ejecutar el [Panel de mantenimiento de Analytics](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252) para supervisar las tendencias generales de las métricas y variables de KPI.

*Para obtener más información sobre cómo asegurarse de que las métricas y variables funcionan correctamente,  [lea estos ](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608) consejos de la campeona de Adobe Analytics Sarah Owen.*

## 3. Examine a fondo los datos de la sección actualizada del sitio.

Asegúrese de que la versión más reciente del sitio no tenga un impacto adverso en la recopilación de datos de esa sección del sitio: revise todo el código y las variables que corresponden a esa sección para asegurarse de que el nuevo seguimiento funcione según lo diseñado.

## 4. Actualice la documentación.

Si ha agregado o cambiado recientemente métricas o variables, debe actualizar el Documento de requisitos comerciales (BRD) y la Referencia de diseño de soluciones (SDR).

Si no dispone de documentación sobre la implementación, exporte una lista de variables y cree su BRD o SDR con [esta plantilla](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation).

## 5. Abordar inmediatamente cualquier brecha que encuentre en la calidad de los datos.

Evaluar la situación y hacer un plan para remediar los datos. A continuación, realice los cambios necesarios, actualice la documentación e informe a los interesados sobre los cambios que ha realizado.

*Vea este vídeo de 2 minutos de la campeona de Adobe Analytics Sarah Owen sobre los tiempos naturales en los que puede ajustar las reseñas de su implementación a su apretada programación:*

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
