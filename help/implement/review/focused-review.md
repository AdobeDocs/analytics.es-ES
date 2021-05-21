---
title: Revisión específica (después de cada lanzamiento de sitio web)
description: Siga estos pasos para asegurarse de que la implementación no contenga errores y esté alineada con los KPI.
exl-id: e38f92b6-bd6e-4835-a8e5-0f29ac962066
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '514'
ht-degree: 100%

---

# Revisión específica (después de cada lanzamiento de sitio web)

¿Por qué debería revisar la implementación cada pocos meses? Para poder abordar cualquier problema con la calidad de los datos mientras sea pequeño. Si realiza esta revisión específica de manera constante tras cada lanzamiento de sitio web, verá que sus [revisiones completas](/help/implement/review/full-review.md) bianuales le resultarán mucho más sencillas. También evitará que pequeños problemas se conviertan en grandes problemas de datos que podrían afectar negativamente a la confianza de las partes interesadas.

## 1. Comience con los 5 KPI principales

Conocer los 5 indicadores de rendimiento clave (KPI) más importantes le ayudará a determinar las métricas y dimensiones asociadas que debe examinar. Si no ha actualizado los KPI en los últimos 6 meses o si su empresa aún no ha creado ningún KPI, siga [estas instrucciones](/help/implement/review/define-kpis.md).

## 2. Asegúrese de que las métricas y las variables de KPI siguen funcionando correctamente

Recuerde que las actualizaciones de código que se realizan con el tiempo pueden tener ramificaciones no deseadas. Debe asegurarse de que todas las métricas y dimensiones asociadas con los [5 KPI principales](/help/implement/review/define-kpis.md) siguen funcionando correctamente. Idealmente, esto debería hacerse justo después de la publicación de un sitio web; si no lo ha hecho en los últimos meses, hágalo *ahora*. Para ello:

* Cree paneles para ver las vistas de tendencias por hora de estas métricas y variables esenciales (o configure [alertas inteligentes](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/intelligent-alerts/intellligent-alerts.html?lang=es#analysis-workspace) para cada métrica). A continuación, monitorícelas durante uno o dos días para asegurarse de que obtiene los datos esperados y de que los datos son correctos. Busque puntos de inflexión. Prepárese para solucionar todos los posibles problemas críticos de inmediato. Si encuentra alguna discrepancia, consulte la capa de datos, las reglas del administrador de etiquetas y las reglas de procesamiento para averiguar el motivo.
* Vuelva a ejecutar el [panel de mantenimiento de Analytics](https://assets.adobe.com/public/9549dbe7-765a-4899-77b8-85cbba1a4252) para monitorizar las tendencias generales de las métricas y variables de KPI.

*Para obtener más información sobre cómo asegurarse de que las métricas y variables funcionan correctamente, [lea estas sugerencias](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/my-five-best-tips-for-keeping-adobe-analytics-humming/td-p/388608) de la campeona de Adobe Analytics, Sarah Owen.*

## 3. Examine a fondo los datos de la sección actualizada del sitio

Asegúrese de que la versión más reciente del sitio no haya repercutido en la recopilación de datos de dicha sección del sitio: revise todo el código y las variables que corresponden a la sección para asegurarse de que el nuevo seguimiento funcione según lo diseñado.

## 4. Actualice la documentación

Si ha añadido o cambiado recientemente métricas o variables, deberá actualizar el Documento de requisitos de empresa (BRD) y la Referencia de diseño de soluciones (SDR).

Si no dispone de documentación sobre la implementación, exporte una lista de variables y cree su BRD o SDR con [esta plantilla](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=es#implementation).

## 5. Aborde inmediatamente cualquier brecha que encuentre en la calidad de los datos

Evalúe la situación y trace un plan para solucionar los problemas de los datos. A continuación, realice los cambios necesarios, actualice la documentación e informe a las partes interesadas de los cambios que ha realizado.

*Vea este vídeo de 2 minutos de la campeona de Adobe Analytics, Sarah Owen, acerca de cuándo puede encajar las revisiones de su implementación en su ocupada agenda:*

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
