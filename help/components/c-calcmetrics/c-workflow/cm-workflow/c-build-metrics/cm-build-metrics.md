---
description: El Creador de métricas calculadas proporciona un lienzo en el que arrastrar y soltar dimensiones, métricas, segmentos y funciones para crear métricas personalizadas basadas en lógica de jerarquía de contenedor, reglas y operadores. Esta herramienta de desarrollo integrada le permite crear y guardar métricas calculadas simples o métricas calculadas avanzadas complejas.
title: Crear métricas
feature: Calculated Metrics
exl-id: 12bb3734-e25d-4c67-8c62-e1226d9aef94
source-git-commit: a6b7622562ced9d28229e094f027c8d0ee79532b
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 49%

---

# Crear métricas

Adobe Analytics proporciona un lienzo en el que arrastrar y soltar dimensiones, métricas, segmentos y funciones para crear métricas personalizadas basadas en lógica, reglas y operadores de jerarquía de contenedor. Esta herramienta de desarrollo integrada le permite crear y guardar métricas calculadas simples o complejas.

## Comenzar a crear una métrica calculada

Puede empezar a crear una métrica calculada de cualquiera de las siguientes maneras:

* En Analysis Workspace, abra un proyecto y seleccione **[!UICONTROL Componentes]** > **[!UICONTROL Crear métrica]**.
* En Analysis Workspace, abra un proyecto y, a continuación, seleccione **Plus** junto al icono [!UICONTROL **Métricas**] en el carril izquierdo.
* Entrada [!DNL Analytics], vaya a **[!UICONTROL Componentes]** > **[!UICONTROL Métricas calculadas]**, luego seleccione **[!UICONTROL + Agregar]** en la parte superior de la página Métricas calculadas.

## Áreas del Creador de métricas calculadas

En la siguiente imagen y en la tabla adjunta se explican algunas de las áreas y características principales del Administrador de métricas calculadas.

![](assets/cm_builder_ui.png)

| Ubicación en la imagen | Nombre y función |
|---|---|
| 1 | **Título:** Es obligatorio nombrar la métrica. No puede guardar la métrica a menos que tenga un nombre. |
| 2 | **Descripción:** Proporciónele una descripción descriptiva que indique para qué se utiliza y para distinguirla de componentes similares. <p>La descripción también aparece en el informe. Se recomienda NO añadir la fórmula en la descripción; en su lugar, describa para qué se debe o no utilizar la métrica. (La fórmula se genera a medida que crea la métrica, debajo del encabezado del Resumen. Como resultado, no hay necesidad de agregar la fórmula a la descripción). </p> |
| 3 | **Formato:** Las opciones incluyen Decimal, Hora, Porcentaje y Moneda. |
| 4 | **Lugares decimales:** Muestra cuántos lugares decimales se mostrarán en el informe. El número máximo de lugares decimales que puede especificar es 10. |
| 5 | **Mostrar tendencia ascendente como:** Esta configuración de polaridad de métrica muestra si Analytics debe considerar una tendencia ascendente en la métrica como buena (verde) o mala (rojo). Como resultado, el gráfico del informe se mostrará en rojo o en verde cuando vaya hacia arriba. |
| 6 | **Etiquetas:** El etiquetado es una buena manera de organizar las métricas. Todos los usuarios pueden crear etiquetas y aplicar una o más a una métrica. Sin embargo, solo verá las etiquetas de los segmentos que sean suyos o que se hayan compartido con usted. ¿Qué tipo de etiquetas debería crear? A continuación encontrará una serie de sugerencias para crear etiquetas útiles:<ul><li>**Nombres del equipo**, como Marketing social o Marketing móvil.</li><li>**Proyectos** (etiquetas de análisis), como análisis de Páginas de entrada.</li><li>**Categorías**, como Mujeres; Geografía.</li><li>**Flujos de trabajo**, como Por aprobar; Revisado para (una unidad comercial específica)</li></ul> |
| 7 | **Resumen:** <p>La fórmula de Resumen se actualiza cada vez que realice cambios en la definición de la métrica. Esta fórmula también se muestra en el carril de métrica a la izquierda, al pasar el ratón por encima de una métrica y hacer clic en <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> icono. </p> |
| 8 | **Definición:** Aquí es donde arrastra las métricas/métricas calculadas, segmentos o funciones para crear la métrica calculada. <ul><li>Si arrastra una métrica calculada, ampliará su definición de métrica automáticamente. </li> <li>Puede anidar definiciones en contenedores. Sin embargo, a diferencia de los contenedores de segmento, estos contenedores funcionan como una expresión matemática y determinan el orden de las operaciones. </li> </ul> |
| 9 | **Operador:** Dividido entre ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) es el operador predeterminado, además de los operadores +, - y x. |
| 10 | **Vista previa:** Proporciona una lectura rápida de cualquier posible error. La vista previa abarca los últimos 90 días. Esta es una forma de calibrar inicialmente si ha seleccionado los componentes adecuados para su métrica. Un resultado inesperado significaría que debe volver a revisar la definición de la métrica. |
| 11 | **Compatibilidad del producto:** <p>La compatibilidad del producto le muestra si la métrica es compatible con los <a href="https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/current-data.html?lang=es"  >Datos actuales</a>, con los Datos completamente procesados o solo con los informes del Canal de marketing (asignación de primer contacto). <p>Nota: Datos actuales no es compatible con todas las métricas. Las métricas que contienen segmentos o funciones no son compatibles con los datos actuales. <a href="/help/components/c-calcmetrics/cm-compatibility.md"  > Más... </a> </p> </p> |
| 12 | **Agregar:** Para todos los tipos de métricas calculadas, puede agregar contenedores y números estáticos a la definición. Para obtener métricas calculadas avanzadas, también puede añadir segmentos y funciones. <ul><li>Los contenedores funcionan como una expresión matemática y determinan el orden de las operaciones. Así, cualquier cosa que se encuentre en un contenedor se procesará antes de la operación siguiente.</li><li>Al arrastrar un segmento a un contenedor, se segmenta todo lo que se encuentra en dicho contenedor (solo métricas calculadas avanzadas).</li><li>Puede apilar múltiples segmentos en un contenedor.</li></ul> |
| 13 | **Icono de engranaje (Tipo de métrica, Atribución):** Si selecciona el icono de engranaje junto a una métrica, puede especificar la variable <a href="/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md"  > tipo de métrica y modelos de atribución </a>. |
| 14 | **Nuevo:** Permite crear un nuevo componente, como un nuevo segmento (que le dirige a la variable <a href="/help/components/segmentation/segmentation-workflow/seg-build.md"  > Generador de segmentos </a>.) |
| 15 | **Componentes de búsqueda:** Esta barra de búsqueda le permite buscar dimensiones, métricas, segmentos (solo métricas calculadas avanzadas) y funciones (solo métricas calculadas avanzadas). |
| 16 | **Lista de Dimension:** En lugar de salir del Creador de métricas calculadas para generar un segmento simple (en el Generador de segmentos), como &quot;Página = Página principal&quot;, puede arrastrar Página y seleccionar Página principal directamente en el Creador de métricas calculadas.<p>Esto conlleva un flujo de trabajo mucho más simplificado en lo relativo a la creación de métricas calculadas segmentadas.</p> |
| 17 | **Lista de métricas:** Las métricas se dividen en 3 categorías: <ul> <li>Métricas estándar (<img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg" id="image_65A80F54D73443E78542FE0B31CC3F20" />) </li><li>Métricas calculadas ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg" id="image_C5674AB9B9EB4DA9A56782D15822C319" />) </li><li id="li_8735E76637ED4C3F983731A66E04C93E">Plantillas de métricas ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Folder_18_N.svg" id="image_D236601511CC4DD3828F223431E27E88" />), al final de la lista. </li> </ul> <p>Cuando pasa el ratón por encima de una métrica, puede ver el icono de información a su derecha: <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" width="15px" id="image_5A65E772A68A4B94ACAD6552CCF21F5F" />. Si hace clic en este icono, le proporcionará la siguiente información: </p><ul> <li>La fórmula de cómo se calcula. </li><li>Una vista previa de la tendencia de la métrica. </li><li>Un icono de edición (lápiz) <img placement="break" align="center"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg" width="15px" id="image_7D5B2F026A034118BE4DA81B9215A883" /> en la parte superior derecha, que le llevará al Creador de métricas calculadas, donde puede editar esta métrica calculada. </li></ul> |
| 18 | **Lista de segmentos:** (Solo métricas calculadas avanzadas) Como administrador, en esta lista se muestran todos los segmentos creados en su empresa de inicio de sesión. Si es un usuario no administrador, en esta lista se muestran los segmentos que le pertenecen y los que han compartido con usted. <a href="https://experienceleague.adobe.com/docs/analytics/components/segmentation/segment-reference/seg-rights.html?lang=es"  > Más... </a> |
| 19 | **Lista de funciones:** (Solo métricas calculadas avanzadas) Las funciones se dividen en dos listas: <a href="/help/components/c-calcmetrics/cm-reference/cm-functions.md"  > Básico </a> (se usa con más frecuencia) y <a href="/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md"  > Avanzadas </a>. |
| 20 | **Selector de grupo de informes:** Le permite cambiar a otro grupo de informes. |

{style="table-layout:auto"}
