---
title: ¿Qué es el ánálisis de cohortes y cómo funciona?
description: Explore en detalle los datos de su audiencia y desglóselos en grupos relacionados mediante el análisis de cohortes. Obtenga información sobre el análisis de cohorte en Analysis Workspace.
feature: Cohort Analysis
role: User, Admin
exl-id: 6a46e76f-671e-4b1b-933a-6c2776c72d09
source-git-commit: d4ad8b988ebcc177c76777b20a54cc20e8241d4d
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 86%

---

# Configuración de la tabla de cohortes {#cohort-table-overview}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="Tabla de cohortes"
>abstract="Cree una visualización de cohorte para agrupar usuarios en función de la finalización de un evento y analice la participación en curso y las cancelaciones a lo largo del tiempo."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="Tabla de cohortes"
>abstract="Agrupe a los usuarios en función de la finalización de un evento y, a continuación, analice su participación actual y las cancelaciones a lo largo del tiempo.<br/><br/>**Parámetros **<br/>**Criterios de inclusión**: los componentes utilizados para definir las cohortes de visitantes iniciales.<br/>**Criterios de retorno**: los componentes utilizados para determinar si un visitante ha regresado."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*Este artículo documenta la tabla de cohorte en **Adobe Analytics**.<br/>Consulte [Tabla de cohortes](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/cohort-table/cohort-analysis) para la versión de **Customer Journey Analytics**de este artículo.*

>[!ENDSHADEBOX]

Una *`cohort`* es un grupo de personas que comparten características en común durante un periodo especificado. El [!UICONTROL análisis de cohorte] es útil, por ejemplo, cuando desea saber cómo se involucra una cohorte con una marca. Puede identificar fácilmente los cambios en tendencias y responder en consecuencia. (Las explicaciones de [!UICONTROL análisis de cohorte] se encuentran disponibles en la web, como en la [Guía básica de análisis de cohorte](https://es.wikipedia.org/wiki/Cohort_analysis)).

Después de crear un informe de cohorte, puede depurar sus componentes (dimensiones, métricas y segmentos específicos), y luego compartir el informe de cohorte con quien desee. Consulte [Depurar y compartir](/help/analyze/analysis-workspace/curate-share/curate.md).

Ejemplos de lo que puede hacer con el [!UICONTROL análisis de cohorte]:

* Iniciar campañas diseñadas para generar una acción deseada.
* Modificar el presupuesto de marketing en el momento justo del ciclo de vida del cliente.
* Reconocer cuándo finalizar una prueba o una oferta, para maximizar el valor.
* Obtener ideas para pruebas A/B en áreas como precios, ruta de actualización, etc.

El [!UICONTROL análisis de cohorte] está disponible para todos los clientes de Adobe Analytics con derechos de acceso a [!UICONTROL Analysis Workspace].

Vídeo sobre tablas de cohorte en Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/25965/?quality=12)

>[!IMPORTANT]
>
>[!UICONTROL Análisis de cohorte] no admite métricas no segmentables (incluidas las métricas calculadas), métricas no enteras (como Ingresos) u Ocurrencias.
>
>Solo se pueden usar las métricas de los segmentos en [!UICONTROL Análisis de cohorte] y solo se pueden incrementar en >1 a la vez.

## Capacidades del análisis de cohorte

Las secciones siguientes describen las funciones de análisis de cohorte que permiten un control preciso de las cohortes que está creando.

Para obtener información más detallada sobre cómo crear una cohorte y ejecutar un informe de [!UICONTROL Análisis de cohorte], consulte [Configurar un informe de análisis de cohorte](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).

### Tabla de [!UICONTROL retención]

Un informe de cohorte de [!UICONTROL retención] devuelve la información de visitantes: cada celda de datos muestra el número sin procesar y el porcentaje de visitantes en la cohorte que realizó la acción durante ese periodo de tiempo. Se pueden incluir hasta 3 métricas y hasta 10 segmentos.

![](assets/retention-report.png)

Este es un vídeo sobre el cálculo de la retención móvil:

>[!VIDEO](https://video.tv.adobe.com/v/25962/?quality=12)

### [!UICONTROL Tabla de pérdida]

Una cohorte de [!UICONTROL pérdida] es la inversa de una tabla de retención y muestra a los visitantes que abandonaron o que no llegaron a satisfacer los criterios de regreso de su cohorte a lo largo del tiempo. Se pueden incluir hasta 3 métricas y hasta 10 segmentos.

![](assets/churn-report.png)

Aquí hay un vídeo sobre el análisis de pérdida:

>[!VIDEO](https://video.tv.adobe.com/v/25966/?quality=12)

### [!UICONTROL Cálculo móvil]

Permite calcular la retención o la pérdida en función de la columna previa, no de la columna incluida.

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL Tabla de latencia]

Mide el tiempo transcurrido antes y después de ocurrir el evento de inclusión. Es una excelente herramienta para el análisis previo/posterior. La columna **[!UICONTROL Incluido]** está en el centro de la tabla y a ambos lados se muestran los periodos de tiempo antes y después del evento de inclusión.

![](assets/cohort-latency.png)

### Cohorte de [!UICONTROL dimensión personalizada]

Cree cohortes basadas en una dimensión seleccionada y no en el tiempo, que es el comportamiento predeterminado. Utilice dimensiones como [!UICONTROL canal de marketing], [!UICONTROL campaña], [!UICONTROL producto], [!UICONTROL página], [!UICONTROL región] o cualquier otra dimensión de Adobe Analytics para mostrar cómo cambia la retención en función de los distintos valores que adoptan.

![](assets/cohort-customizable-cohort-row.png)
