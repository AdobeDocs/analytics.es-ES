---
description: Las métricas calculadas y calculadas avanzadas son métricas personalizadas que se pueden crear a partir de métricas existentes.
keywords: Métricas calculadas;Métricas calculadas avanzadas
title: Métricas calculadas y métricas calculadas avanzadas
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 53%

---

# Métricas calculadas y métricas calculadas avanzadas

Las métricas calculadas y las métricas calculadas avanzadas son métricas personalizadas que se pueden crear a partir de métricas existentes.

Nuestras herramientas de métricas calculadas ofrecen una forma muy flexible de crear, administrar y ajustar métricas. Como expertos en marketing, gestores de productos y analistas, les permite plantear preguntas acerca de los datos sin tener que cambiar su implementación de [!DNL Analytics] En cada paquete de [!DNL Analytics] están disponibles las siguientes métricas personalizadas:

* Adobe [!DNL Analytics] Foundation: calculadas
* [Adobe Analytics Select](https://www.adobe.com/es/data-analytics-cloud/analytics/select.html): calculadas + calculadas avanzadas
* [Adobe Analytics Prime](https://www.adobe.com/es/data-analytics-cloud/analytics/prime.html): calculadas + calculadas avanzadas
* [Adobe Analytics Ultimate](https://www.adobe.com/es/data-analytics-cloud/analytics/ultimate.html): calculadas + calculadas avanzadas

A continuación se muestra una comparación de las métricas calculadas y las capacidades avanzadas de las métricas calculadas:

| Opciones del creador | Métricas calculadas  | Métricas calculadas avanzadas |
|---|---|---|
| [Tipos de formato (decimal, tiempo, porcentaje, moneda)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) | Sí | Sí |
| [Cambios de atribución (predeterminado, lineal, de participación, etc.)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Sí | Sí |
| [Tipos de métrica (estándar, total)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Sí | Sí |
| Operadores básicos (sumar, restar, multiplicar, dividir) | Sí | Sí |
| [Aplicar segmentos](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) | No | Sí |
| [Funciones básicas (recuento, valor absoluto, media, etc.)](/help/components/c-calcmetrics/cm-reference/cm-functions.md) | No | Sí |
| [Funciones avanzadas (regresión, si/entonces, unidad tipificada, etc.)](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) | No | Sí |

## Competencias {#section_A0A5C275B68A4D628950BBB0B1EE631F}

Puede

* Cree métricas en [!UICONTROL Analysis Workspace], [!UICONTROL Report Builder], [!UICONTROL Detección de anomalías] y [!UICONTROL Análisis de contribución].
* Crear métricas segmentadas que se derivan del tiempo de ejecución de un informe, sin tener que cambiar la implementación. Éstas pueden verse en el historial, ya que se basan en segmentos.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Métricas calculadas](https://video.tv.adobe.com/v/37936?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]

* Compartir métricas entre grupos de informes. Esto significa que todas las métricas de reciente creación se aplican a todos los grupos de informes en la misma empresa de inicio de sesión.
* (Solo métricas calculadas avanzadas) Segmentar métricas. Por ejemplo, puede crear una métrica para “Visitantes nuevos”, con un recuento de personas de las cuales sea la primera sesión.

* (Solo métricas calculadas avanzadas) Incorporar funciones estadísticas para ayudarle a describir mejor los datos. Por ejemplo, puede contar el número de elementos de un informe o agregar el número de desviaciones estándar para cada elemento.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Métricas calculadas segmentadas en segmentos](https://video.tv.adobe.com/v/37935?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Limitaciones {#section_CB878B02451541D68A68B508D4DBD19A}

Algunas funciones de [!DNL Analytics] permiten utilizar eventos, pero no métricas calculadas:

* [!UICONTROL Secuelas] en [!UICONTROL Analysis Workspace]
* [!UICONTROL Análisis de cohortes] en Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segmentos]
* [!DNL Analytics] for [!DNL Target]

## Herramientas {#section_D65E9C067E9C45E1A50DD30F50561BB2}

A continuación se ofrece una breve descripción general de las herramientas [!UICONTROL Métricas calculadas]:

| Herramienta | Competencias |
|--- |--- |
| Creador de métricas calculadas | <ul><li>Cree métricas calculadas avanzadas con modelos de asignación avanzados.</li><li>Añadir segmentos en línea a fórmulas métricas</li><li>Comparar segmentos en el mismo informe. Por ejemplo, comparar los visitantes locales con los visitantes internacionales.</li><li>Uso de funciones estadísticas</li><li>Proporcionar descripciones de métricas detalladas (mostrar qué hace, dónde utilizarla y para qué NO utilizarla)</li><li>Copiar definiciones en métricas nuevas</li><li>Proporcionar una vista previa de métricas en línea</li><li>Establecer la polaridad de una métrica, lo cual indica si es bueno o malo que un evento personalizado determinado (métrica) aumente</li><li>Etiquetar métricas</li></ul> |
| Administrador de métricas calculadas | <ul><li>Compartir métricas con otros&lt;/li><li>Aprobación y depuración de métricas</li><li>Organizar (etiquetar) sus métricas para que los demás puedan encontrarlas</li><li>Eliminar métricas</li><li>Cambiar nombre de métricas</li></ul> |
| Carril del selector de métricas | Le permite buscar y agregar o aplicar métricas en el informe. También puede cambiar el orden (las opciones son: alfabético, recomendado, más utilizados, más recientes). Además, puede filtrar Grupos de informes para mostrar solo las métricas creadas en un grupo de informes específico.  Para acceder a este Selector de métricas, haga clic en el icono Métricas que encontrará en el lateral izquierdo de un informe. |
| API para métricas calculadas | Parte del conjunto de API de Adobe Analytics 2.0. |
