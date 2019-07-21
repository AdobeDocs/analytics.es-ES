---
description: La herramienta Comparación de segmentos (IQ de segmento) detecta las diferencias más significativas estadísticamente entre un número ilimitado de segmentos a través de un análisis automatizado de cada métrica y dimensión a las que tenga acceso. De forma automática, muestra las características clave de los segmentos de audiencia que dirigen el KPI de su empresa y le permite observar cuánto se superponen los segmentos.
keywords: Analysis Workspace; IQ de segmento
seo-description: La herramienta Comparación de segmentos (IQ de segmento) detecta las diferencias más significativas estadísticamente entre un número ilimitado de segmentos a través de un análisis automatizado de cada métrica y dimensión a las que tenga acceso. De forma automática, muestra las características clave de los segmentos de audiencia que dirigen el KPI de su empresa y le permite observar cuánto se superponen los segmentos.
seo-title: Descripción general de IQ de segmento
solution: Analytics
title: Descripción general de IQ de segmento
topic: Reports and Analytics
uuid: 80 b 8343 a -8 e 09-4234-9510-1 eecce 18567 f
translation-type: tm+mt
source-git-commit: f5f5b294f503911108e1693b7c6cd128bee659c6

---


# Descripción general de IQ de segmento

La herramienta Comparación de segmentos (IQ de segmento) detecta las diferencias más significativas estadísticamente entre un número ilimitado de segmentos a través de un análisis automatizado de cada métrica y dimensión a las que tenga acceso. De forma automática, muestra las características clave de los segmentos de audiencia que dirigen el KPI de su empresa y le permite observar cuánto se superponen los segmentos.

Los analistas pueden tardar muchas horas o incluso días para buscar las diferencias relevantes entre segmentos a través de grandes franjas de métricas y dimensiones de su empresa. Este análisis no solo es tedioso y consume mucho tiempo, sino que nunca estará seguro de si se ha perdido alguna diferencia clave sobre un segmento que hubiera tenido un gran impacto en sus esfuerzos de marketing de destino.

[Comparación de segmentos en YouTube](https://www.youtube.com/watch?v=fO3PNB93U_w&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&index=38) (4:46)

A continuación le mostramos algunas novedades sobre conceptos, visualizaciones y tablas que son clave y que se introducen con la herramienta Comparación de segmentos:

## “Everyone else” segment {#section_30AEE8181E5D46D9AB27F7CA3815D0CD}

Para mayor comodidad, hemos añadido el segmento «todos los demás» para que no tenga que crearlo manualmente. Por ejemplo, tome la audiencia Compradores. No tiene que crear un segmento de No compradores, ya que ya está incluido en el segmento «todos los demás» y se puede eliminar rápidamente si prefiere agregar un segmento diferente para compararlo.

## Size and overlap {#section_885A71EE458C43189A77B8F552CA346A}

La visualización Tamaño y superposición ilustra los tamaños comparativos de cada segmento seleccionado y cuánto se superponen entre sí. Puede situarse sobre la imagen para ver cuántos visitantes estaban en cada sección superpuesta o no superpuesta. También puede hacer clic en la superposición para crear un segmento totalmente nuevo si desea hacer un análisis en mayor profundidad. Si dos segmentos no se superponen (por ejemplo, si se usa el segmento «todos los demás»), también se verá reflejado en esta visual.

![](assets/size-overlap.png)

## Population summaries {#section_21F2B66C60184A71B89E2982A6FB945D}

A la derecha de la imagen Tamaño y cruce, la herramienta Comparación de segmentos muestra el número total de visitantes únicos en cada segmento y la población de la superposición.

![](assets/population_summaries.png)

## Top metrics {#section_E4A38516424949B79A559DC8793071F2}

>[!NOTE]
>
>Los elementos de fila que se aplican después de la comparación de segmentos no reciben una Puntuación de diferencia; la tabla cargará solamente los datos de métricas de los dos segmentos que se comparan

La tabla de métricas principales muestra las métricas más diferenciadoras estadísticamente entre los dos segmentos que ha seleccionado. Cada fila de dicha tabla representa una métrica diferenciadora, ordenada según lo diferente que sea de cada segmento. Las métricas también se muestran para cada visitante, lo que significa que si en la tabla aparece “Visitas”, los números correspondientes de la tabla representan el número medio de visitas por visitante en cada segmento. También se proporciona una puntuación de diferencia que indica cómo de diferente es esta métrica con respecto a estos dos segmentos. Una puntuación de 1 representa una diferencia estadística grande, mientras que una puntuación de 0 representa ninguna diferencia estadística.

Para obtener más información sobre cómo se calculan las puntuaciones de diferencias de cada tabla, consulte [Pruebas estadísticas utilizadas en la comparación de segmentos](../../../../analyze/analysis-workspace/c-panels/c-segment-comparison/statistical-test.md#concept_0B6AC754EAED460283D4626983F838F4).

La tabla de métricas principales es similar a cualquier otra métrica utilizada en Analysis Workspace. Puede arrastrar cualquier métrica que le interese hasta la tabla y le mostraremos cómo se compara.

Puede personalizar la tabla como desee. También se ha añadido un icono “crear imagen” para cada fila de la tabla. Al hacer clic en el botón se crea una tabla completamente nueva y una imagen sobre la herramienta Comparación de segmentos, por si no desea abarrotar la tabla de métricas principales y preferiría continuar con un análisis más profundo en una nueva tabla. Si dicha métrica no es relevante, puede hacer clic en “X” para eliminarla a la vez de la tabla. Finalmente, al igual que con cualquier otra tabla improvisada, puede pasar las páginas a través de la lista de las métricas mostradas o mostrar las primeras 10, 20, 50, etc. si desea ver más de los cinco elementos de la línea que se muestran por defecto.

![](assets/top-metrics.png)

A la derecha de la tabla de métricas se encuentra la visualización vinculada. Por defecto, la herramienta Comparación de Segmentos mostrará la tendencia de la métrica principal en la tabla sobre los últimos 30 días para cada segmento. Si desea visualizar otra métrica de la tabla de métricas principales, solo tiene que seleccionarla haciendo clic y la visualización de la derecha se actualizará para mostrarle la métrica seleccionada.

![](assets/linked-viz.png)

## Top dimension items {#section_439C1782B153427CB4FB85E177146EC0}

>[!NOTE]
>
>Los elementos de fila que se aplican después de la comparación de segmentos no reciben una Puntuación de diferencia; la tabla cargará solamente los datos de métricas de los dos segmentos que se comparan

Al igual que la tabla de métricas principales, la herramienta Comparación de segmentos ofrece la tabla de elementos de dimensión principales, que ilustra los elementos de dimensión más diferenciadores de todas las dimensiones. Cada fila muestra el porcentaje de cada segmento con este elemento de dimensión.

Por ejemplo, si compara el “Segmento A” con el “Segmento B”, es posible que la tabla de elementos de dimensión principales indique que el 100 % de los visitantes del “Segmento A” tenían el elemento de dimensión Tipo de explorador: Google, mientras que solo el 19,6 % del “Segmento B” tenía dicho elemento de dimensión.

![](assets/top-dimension-item1.png)

A la derecha de la tabla de elementos de dimensión principales, la herramienta Comparación de segmentos resalta el elemento de dimensión principal seleccionado, junto con otros elementos de dimensión principales de esa dimensión para compararlos:

![](assets/top-dimension-item.png)

## Top segments table {#section_6A0C39F930564240AF7A157005C7A80B}

>[!NOTE]
>
>Los elementos de fila que se aplican después de la comparación de segmentos no reciben una Puntuación de diferencia; la tabla cargará solamente los datos de métricas de los dos segmentos que se comparan

La tabla de segmentos principales es una tabla útil que muestra qué elementos (que no sean los dos elementos seleccionados para la comparación) se superponen de forma muy diferente a los dos segmentos seleccionados. Por ejemplo, si se compara el Segmento A con el Segmento B, es posible que la tabla de segmentos principales muestre que un tercer segmento, “Visitantes repetidos”, se superpone con el segmento A pero no con el Segmento B.

![](assets/top-segments.png)

Además, el principal segmento adicional diferenciador se muestra en una imagen de superposición a la derecha de la tabla:

![](assets/segment-overlap.png)

La imagen de superposición indica de forma gráfica la diferencia de superposición entre los tres segmentos y, al igual que el resto de imágenes vinculadas, al hacer clic en cada segmento adicional de la tabla, la imagen se actualiza para coincidir con el segmento seleccionado.

Haga clic aquí para obtener más información acerca de  [las pruebas estadísticas](../../../../analyze/analysis-workspace/c-panels/c-segment-comparison/statistical-test.md#concept_0B6AC754EAED460283D4626983F838F4) utilizadas en la comparación de segmentos.
