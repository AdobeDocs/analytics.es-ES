---
title: Revisión de implementación menor (después de cada lanzamiento del sitio web)
description: Siga estos pasos para asegurarse de que la implementación no contenga errores y esté en línea con los KPI.
translation-type: tm+mt
source-git-commit: 82064e267729b6995402bd122c6f71b3d38967a3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---


# Revisión de implementación menor (después de cada lanzamiento del sitio web)

¿Por qué debería revisar la implementación después de cada lanzamiento del sitio web? Debido a que debe asegurarse de que las actualizaciones de código no tengan ramificaciones no deseadas, y debe abordar cualquier problema con la calidad de los datos mientras sean pequeños. Si realiza esta revisión menor de manera consistente después de cada lanzamiento del sitio web, verá que las [críticas](/help/implement/review/major-review.md) principales (cada 6 meses) son mucho más fáciles. También evitará que las cuestiones pequeñas se conviertan en cuestiones de grandes datos que podrían erosionar la confianza de los interesados.

## 1. ¿De qué manera impactó el lanzamiento en los datos de esa sección del sitio?

Realice pruebas exhaustivas de la unidad: Revise todo el código y las variables que corresponden a la sección del sitio que acaba de actualizar para asegurarse de que el nuevo seguimiento funcione según lo diseñado.

## 2. Actualice su documentación

Actualice el Documento de requisitos comerciales (BRD) y la Referencia de diseño de la solución (SDR) con todas las variables que haya agregado o cambiado para adaptarse al lanzamiento.

¿No tiene documentación de la implementación? Exporte una lista de variables y cree su BRD o SDR usando [esta plantilla](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/implementation/implementation-basics/creating-a-business-requirements-document.html?lang=en#implementation).

## 3. Inicio con los 5 KPI principales

Conocer los 5 indicadores de rendimiento clave (KPI) más importantes le ayudará a determinar las métricas y dimensiones asociadas que debe examinar. Si no ha actualizado los KPI en los últimos 6 meses o si su empresa aún no ha creado KPI, siga [estas instrucciones](/help/implement/review/define-kpis.md).

## 4. ¿Todas las métricas y variables de KPI siguen funcionando bien después de la versión?

Recuerde que cualquier actualización de código puede tener ramificaciones no deseadas. Desea asegurarse de que todas las métricas y dimensiones asociadas con los 5 KPI [principales](/help/implement/review/define-kpis.md) sigan funcionando correctamente. Para ello:

* **Cree paneles** para ver las vistas de tendencias horarias de estas métricas y variables críticas. También puede configurar alertas inteligentes para cada métrica) y supervisarlas durante uno o dos días después de la publicación, para asegurarse de que obtiene los datos que espera y de que los datos son correctos. Busque puntos de inflexión. Estar preparados para remediar cualquier problema crítico inmediatamente. Si encuentra alguna discrepancia que no tenga el aspecto correcto, consulte la capa de datos, las reglas del administrador de etiquetas y las reglas de procesamiento para averiguar por qué.
* **Vuelva a ejecutar el Panel** de mantenimiento de Analytics para supervisar las tendencias generales de las métricas y variables de KPI.
Para obtener más información sobre cómo asegurarse de que las métricas y variables funcionan correctamente, lea estas sugerencias de la campeona de Adobe Analytics Sarah Owen.

## 5. ¿Hay lagunas en la calidad de los datos?

Evaluar la situación y hacer un plan para remediar los datos. A continuación, realice los cambios necesarios, actualice la documentación e informe a los interesados sobre los cambios que ha realizado.

Vea este vídeo de la Campeona de Adobe Analytics Sarah Owen sobre los tiempos naturales en los que puede ajustar las revisiones de su implementación a su programa de trabajo:

>[!VIDEO](https://video.tv.adobe.com/v/328340/?quality=12&learn=on)
