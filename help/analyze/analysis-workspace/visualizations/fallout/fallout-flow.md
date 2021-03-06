---
description: Utilice la visualización de visitas en orden previsto de un proyecto de Workspace.
title: Resumen de abandonos
feature: Visualizations
role: User, Admin
exl-id: 85d0c88e-d159-4870-aaf6-51899d87ff77
source-git-commit: 10ae8213b8745439ab5968853f655a1176b8c38a
workflow-type: ht
source-wordcount: '496'
ht-degree: 100%

---

# Resumen de abandonos

Las visualizaciones de visitas en el orden previsto ofrecen más opciones para crear sus informes de visitas en el orden previsto. Los informes de visitas en el orden previsto muestran dónde abandonaron los visitantes y continuaron en una secuencia de páginas predefinidas.

A continuación, se muestra un vídeo sobre la visualización Visita en orden previsto:

>[!VIDEO](https://video.tv.adobe.com/v/24042/?quality=12)

Las visualizaciones de visitas en el orden previsto le permiten:

* Realizar comparaciones paralelas de dos segmentos distintos en el mismo informe
* Arrastrar, soltar y reorganizar pasos de embudo (puntos de contacto).
* Mezclar valores de distintas dimensiones y métricas
* Crear un informe de visitas en el orden previsto multidimensional
* Identificar a qué lugar van los clientes inmediatamente tras la visita en el orden previsto

Las visitas en el orden previsto muestran la conversión y las tasas de visitas en el orden previsto entre cada paso o punto de contacto en una secuencia.

Por ejemplo, se puede hacer un seguimiento de dónde los visitantes abandonan la secuencia prevista a lo largo del proceso de compra. Para ello, basta con seleccionar un punto de contacto inicial y otro de conclusión, y luego añadir puntos de contacto intermedios para crear una ruta de navegación por el sitio web. Pero también puede crear visitas en el orden previsto multidimensionales.

La visualización de visitas en el orden previsto es útil para analizar:

* Las tasas de conversión a través de procesos específicos en el sitio (tales como un proceso de registro o de compra).
* Flujos de tráfico generales, con un alcance más amplio: entre las personas que visitaron la página principal, este flujo muestra cuántas fueron de allí a realizar una búsqueda y cuántas continuaron para ver un elemento específico.
* Correlaciones entre los eventos del sitio. Las correlaciones muestran el porcentaje de personas que leyeron la política de privacidad y procedieron a realizar la compra de un producto.

## La segmentación como base para Flujo y Abandonos {#section_654F37A398C24DDDB1552A543EE29AA9}

Los segmentos aplicados a los paneles de Workspace funcionan de un modo ligeramente distinto a los aplicados a los informes de visitas en orden previsto y flujo en Reports &amp; Analytics. La mayoría de las veces ofrecen los mismos resultados. La principal diferencia radica en que Reports &amp; Analytics aplica el segmento en cada paso de la secuencia. Esto puede producir resultados ligeramente distintos.

Veamos un ejemplo de visitas en el orden previsto con dos pasos:

![](assets/fallout_segments1.png)

Si a continuación aplica un segmento en el nivel de panel de Workspace, el segmento se combina con las visitas en el orden previsto de este modo:

![](assets/fallout_seg.png)

Por el contrario, cuando Reports &amp; Analytics calcula el segmento, este se combina de esta manera:

![](assets/fallout_segments3.png)

Reports &amp; Analytics combina el segmento con cada paso. Cuando los contenedores se encuentran en el mismo nivel que las visitas en el orden previsto (p. ej., el nivel de visita o de visitante), el resultado es una coincidencia con el número de visitas o visitantes.

Sin embargo, si el segmento aplicado al panel es menor que el nivel de las visitas en el orden previsto (p. ej., el nivel de visita individual), muestra resultados diferentes por el modo en que el informe lo combina. Para reiterar, en la mayoría de los casos, los números de Analysis Workspace coinciden con los de Reports &amp; Analytics. **No** coincidirán únicamente si se cumplen todas las condiciones siguientes:

* El segmento no está en el mismo nivel que los abandonos.
* El segmento incluye una variable por la que el visitante/visita puede adoptar distintos valores durante una visita/visitante.

En el extraño caso de que necesite que Analysis Workspace refleje el modo de Reports &amp; Analytics de aplicar segmentos a visitas en el orden previsto/flujo, solo tiene que incluir el segmento en cada paso de las visitas en el orden previsto en Workspace. De este modo, los resultados serán idénticos.
