---
description: Las métricas calculadas y las calculadas avanzadas se pueden personalizar a partir de las métricas existentes.
keywords: Métricas calculadas; métricas calculadas avanzadas
title: Métricas calculadas y calculadas avanzadas
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: ht
source-wordcount: '552'
ht-degree: 100%

---

# Métricas calculadas y calculadas avanzadas

Las métricas calculadas y las calculadas avanzadas se pueden personalizar a partir de las métricas existentes.

Nuestras herramientas de métricas calculadas ofrecen una forma muy flexible de crear, administrar y ajustar métricas. Como expertos en marketing, gestores de productos y analistas, les permite plantear preguntas acerca de los datos sin tener que cambiar su implementación de [!DNL Analytics] En cada paquete de [!DNL Analytics] están disponibles las siguientes métricas personalizadas:

* Adobe [!DNL Analytics] Foundation: calculadas
* [Adobe Analytics Select](https://www.adobe.com/es/data-analytics-cloud/analytics/select.html): calculadas + calculadas avanzadas
* [Adobe Analytics Prime](https://www.adobe.com/es/data-analytics-cloud/analytics/prime.html): calculadas + calculadas avanzadas
* [Adobe Analytics Ultimate](https://www.adobe.com/es/data-analytics-cloud/analytics/ultimate.html): calculadas + calculadas avanzadas

A continuación se muestra una comparación entre las competencias de las métricas calculadas y las métricas calculadas avanzadas:

| Opciones de Builder | Métricas calculadas  | Métricas calculadas avanzadas |
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

* Cree métricas entre [!UICONTROL Analysis Workspace], [!UICONTROL Report Builder], [!UICONTROL Detección de anomalías] y [!UICONTROL Análisis de contribución].
* Crear métricas segmentadas que deriven del tiempo de ejecución de un informe, sin tener que cambiar la implementación. Ya que se basan en segmentos, pueden encontrarse en el historial.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut ](/help/assets/icons/VideoCheckedOut.svg) [Métricas calculadas](https://video.tv.adobe.com/v/37936?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]

* Compartir métricas entre grupos de informes. Esto significa que todas las métricas de reciente creación se aplican a todos los grupos de informes en la misma empresa de inicio de sesión.
* (Solo métricas calculadas avanzadas) Segmente por métricas. Por ejemplo, puede crear la métrica “Visitantes nuevos” para contar las primeras sesiones de una persona.

* (Solo métricas calculadas avanzadas) Incorpore funciones estadísticas que le ayuden a describir mejor los datos. Por ejemplo, haga recuentos del número de elementos de un informe o agregue el número de desviaciones estándar para cada elemento.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut ](/help/assets/icons/VideoCheckedOut.svg) [Métricas calculadas segmentadas en segmentos](https://video.tv.adobe.com/v/37935?quality=12&learn=on&captions=spa){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Limitaciones {#section_CB878B02451541D68A68B508D4DBD19A}

Algunas de las funciones de [!DNL Analytics] permiten utilizar los eventos, pero no las métricas calculadas:

* [!UICONTROL Secuelas] en [!UICONTROL Analysis Workspace]
* [!UICONTROL Análisis de cohortes] en Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segmentos]
* [!DNL Analytics] para [!DNL Target]

## Herramientas {#section_D65E9C067E9C45E1A50DD30F50561BB2}

A continuación se describen brevemente las herramientas de [!UICONTROL Métricas calculadas]:

| Herramienta | Competencias |
|--- |--- |
| Creador de métricas calculadas | <ul><li>Cree métricas calculadas avanzadas con modelos de asignación avanzados.</li><li>Añadir segmentos en línea a fórmulas de métricas</li><li>Comparar segmentos en el mismo informe. Por ejemplo, comparar los visitantes locales con los visitantes internacionales.</li><li>Utilizar funciones estadísticas</li><li>Proporcionar descripciones detalladas de las métricas (mostrar qué hacen, dónde utilizarlas y dónde NO se deben utilizar).</li><li>Copiar definiciones en métricas nuevas</li><li>Proporcionar una vista previa de métricas en línea</li><li>Establecer la polaridad de una métrica, lo cual indica si es bueno o malo que un evento personalizado determinado (métrica) vaya al alza.</li><li>Etiquetar métricas</li></ul> |
| Administrador de métricas calculadas | <ul><li>Compartir métricas con otros&lt;/li<li>Aprobar y depurar métricas</li><li>Organizar (etiquetar) sus métricas para que los demás puedan encontrarlas</li><li>Eliminar métricas</li><li>Cambiar el nombre de las métricas</li></ul> |
| Carril del selector de métricas | Le permite buscar y añadir o aplicar métricas al informe. También puede cambiar el orden de clasificación con las opciones Alfabético, Recomendado, Más usados y Usado recientemente. Además, le permite filtrar por grupos de informes para mostrar solo las métricas creadas en un grupo de informes específico. Para acceder a este Selector de métricas, haga clic en el icono Métricas a la izquierda de un informe.  |
| API para métricas calculadas | Parte del conjunto de API de Adobe Analytics 2.0. |
