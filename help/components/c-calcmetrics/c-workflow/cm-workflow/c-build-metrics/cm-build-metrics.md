---
description: El Creador de métricas calculadas proporciona un lienzo en el que arrastrar y soltar dimensiones, métricas, segmentos y funciones para crear métricas personalizadas basadas en lógica de jerarquía de contenedor, reglas y operadores. Esta herramienta de desarrollo integrada le permite crear y guardar métricas calculadas simples o métricas calculadas avanzadas complejas.
title: Generar métricas
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
source-git-commit: f8541ac8f82e63f1664b06ed788d307c5d224ca9
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 40%

---

# Generar métricas

Adobe Analytics proporciona un lienzo en el que arrastrar y soltar dimensiones, métricas, segmentos y funciones para crear métricas personalizadas basadas en lógica, reglas y operadores de jerarquía de contenedor. Esta herramienta de desarrollo integrada le permite crear y guardar métricas calculadas simples o complejas.

## Comenzar a crear una métrica calculada

Puede usar el creador de métricas calculadas para crear métricas calculadas. Cuando se crean de esta manera, las métricas calculadas están disponibles en la lista de componentes y, a continuación, se pueden utilizar en proyectos de toda la organización. También puede crear una métrica calculada rápida, tal como se describe en [Crear métricas calculadas para un solo proyecto](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) en [Métricas](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

Acceda al creador de métricas calculadas para empezar a crear una métrica calculada que esté disponible en la lista de componentes.

1. Acceda al creador de métricas calculadas de cualquiera de las siguientes maneras:

   * En Analysis Workspace, abra un proyecto y seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Crear métrica]**.
   * En Analysis Workspace, abra un proyecto y, a continuación, seleccione el icono **Más** junto a la sección [!UICONTROL **Métricas**] en el carril izquierdo.
   * En [!DNL Customer Journey Analytics], vaya a **[!UICONTROL Componentes]** > **[!UICONTROL Métricas calculadas]** y, a continuación, seleccione **[!UICONTROL + Agregar]** en la parte superior de la página Métricas calculadas.

1. Continuar con [Áreas del generador de métricas calculadas](#areas-of-the-calculated-metrics-builder).

## Áreas del Creador de métricas calculadas

La siguiente imagen y la tabla adjunta explican algunas de las áreas y características principales del Creador de métricas calculadas.

![](assets/cm_builder_ui.png)

| Ubicación en la imagen | Nombre y función |
|---|---|
| 1 | **Título:** Es obligatorio nombrar la métrica. No puede guardar la métrica a menos que tenga un nombre. |
| 2 | **Descripción:** Proporciónele una descripción descriptiva para mostrar para qué se utiliza y para distinguirla de características similares. <p>La descripción también aparece en el informe. Se recomienda NO añadir la fórmula en la descripción; en su lugar, describa para qué se debe o no utilizar la métrica. (La fórmula se genera a medida que crea la métrica, debajo del encabezado del Resumen. Como resultado, no hay necesidad de agregar la fórmula a la descripción). </p> |
| 3 | **Formato:** Las opciones incluyen Decimal, Hora, Porcentaje y Moneda. |
| 4 | **Lugares decimales:** Muestra cuántos lugares decimales se mostrarán en el informe. El número máximo de lugares decimales que puede especificar es 10. |
| 5 | **Mostrar tendencia ascendente como:** Esta configuración de polaridad de métrica muestra si Analytics debe considerar una tendencia ascendente en la métrica como buena (verde) o mala (rojo). Como resultado, el gráfico del informe se mostrará en rojo o en verde cuando vaya hacia arriba. |
| 6 | **Etiquetas:** El etiquetado es una buena manera de organizar las métricas. Todos los usuarios pueden crear etiquetas y aplicar una o más a una métrica. Sin embargo, solo verá las etiquetas de los segmentos que sean suyos o que se hayan compartido con usted. ¿Qué tipo de etiquetas debería crear? A continuación encontrará una serie de sugerencias para crear etiquetas útiles:<ul><li>**Nombres de equipos**, como Marketing social o Marketing móvil.</li><li>**Proyectos** (etiquetas de análisis), como análisis de páginas de entrada.</li><li>**Categorías**, como Women&#39;s; Geography.</li><li>**Flujos de trabajo**, como Por aprobar; Revisado para (una unidad empresarial específica)</li></ul> |
| 7 | **Resumen:** <p>La fórmula de Resumen se actualiza cada vez que realice cambios en la definición de la métrica. Esta fórmula también se muestra en el carril de métrica a la izquierda, al pasar el ratón por encima de una métrica y hacer clic en Icono <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" />. </p> |
| 8 | **Definición:** Aquí es donde arrastra las métricas/métricas calculadas, segmentos o funciones para crear la métrica calculada. <ul><li>Si arrastra una métrica calculada, ampliará su definición de métrica automáticamente. </li> <li>Puede anidar definiciones en contenedores. Sin embargo, a diferencia de los contenedores de segmento, estos contenedores funcionan como una expresión matemática y determinan el orden de las operaciones. </li> </ul> |
| 9 | **Operador:** dividido por ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) es el operador predeterminado, además de los operadores +, - y x. |
| 10 | **Vista previa:** Proporciona una lectura rápida de los posibles errores. La vista previa abarca los últimos 90 días. Esta es una forma de calibrar inicialmente si ha seleccionado los componentes adecuados para su métrica. Un resultado inesperado significaría que debe volver a revisar la definición de la métrica. |
| 11 | **Compatibilidad del producto:** La compatibilidad del producto le muestra si la métrica es compatible con <a href="https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html?lang=es"  > Datos actuales </a>, con Datos completamente procesados o solo con los informes de Canal de marketing (asignación de primer contacto). <p>Nota: Datos actuales no es compatible con todas las métricas. Las métricas que contienen segmentos o funciones no son compatibles con los datos actuales. <a href="/help/components/c-calcmetrics/cm-compatibility.md"  > Más... </a> </p> </p> |
| 12 | **Agregar:** Para todos los tipos de métricas calculadas, puede agregar contenedores y números estáticos a la definición. Para obtener métricas calculadas avanzadas, también puede añadir segmentos y funciones. <ul><li>Los contenedores funcionan como una expresión matemática y determinan el orden de las operaciones. Así, cualquier cosa que se encuentre en un contenedor se procesará antes de la operación siguiente.</li><li>Al arrastrar un segmento a un contenedor, se segmenta todo lo que se encuentra en dicho contenedor (solo métricas calculadas avanzadas).</li><li>Puede apilar múltiples segmentos en un contenedor.</li></ul> |
| 13 | **Icono de engranaje (Tipo de métrica, Atribución):** Si selecciona el icono de engranaje junto a una métrica, podrá especificar el tipo de métrica <a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md"  > y los modelos de atribución </a>. |
| 14 | **Nuevo:** Le permite crear un componente nuevo, como un segmento nuevo (que lo lleva al Generador de segmentos <a href="/help/components/segmentation/segmentation-workflow/seg-build.md"  > </a>). |
| 15 | **Componentes de búsqueda:** Esta barra de búsqueda le permite buscar dimensiones, métricas, segmentos (solo métricas calculadas avanzadas) y funciones (solo métricas calculadas avanzadas). |
| 16 | **Lista de Dimension:** En lugar de salir del Creador de métricas calculadas para generar un segmento simple (en el Generador de segmentos), por ejemplo, &quot;Página = Página principal&quot;, puede arrastrar Página y seleccionar Página principal directamente en el Creador de métricas calculadas.<p>Esto conlleva un flujo de trabajo mucho más simplificado en lo relativo a la creación de métricas calculadas segmentadas.</p> |
| 17 | **Lista de métricas:** Las métricas se dividen en 3 categorías: <ul> <li>Métricas estándar (<img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li><li>Métricas calculadas ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li><li id="li_8735E76637ED4C3F983731A66E04C93E">Plantillas de métricas ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg" id="image_D236601511CC4DD3828F223431E27E88" />), al final de la lista. </li> </ul> <p>Cuando pasa el ratón por encima de una métrica, puede ver el icono de información a su derecha: <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" width="15px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />. Si hace clic en este icono, le proporcionará la siguiente información: </p><ul> <li>La fórmula de cómo se calcula. </li><li>Una vista previa de la tendencia de la métrica. </li><li>Un icono de edición (lápiz) <img placement="break" align="center"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg" width="15px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> en la parte superior derecha, que le llevará al Creador de métricas calculadas, donde puede editar esta métrica calculada. </li></ul> |
| 18 | **Lista de segmentos:** (solo métricas calculadas avanzadas) Como administrador, en esta lista se muestran todos los segmentos creados en su compañía de inicio de sesión. Si es un usuario no administrador, en esta lista se muestran los segmentos que le pertenecen y los que han compartido con usted. <a href="https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-rights.html?lang=es"  > Más... </a> |
| 19 | **Lista de funciones:** (solo métricas calculadas avanzadas) Las funciones se dividen en dos listas: <a href="/help/components/c-calcmetrics/cm-reference/cm-functions.md"  > Básicas </a> (utilizadas con más frecuencia) y <a href="/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md"  > Avanzadas </a>. |
| 20 | **Selector de grupo de informes:** Le permite cambiar a un grupo de informes diferente. |

{style="table-layout:auto"}
