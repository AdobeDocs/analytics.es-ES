---
description: Aprenda a configurar y especificar los puntos de contacto para crear una secuencia de visitas en el orden previsto multidimensional.
title: Configuración De Una Visualización De Abandonos
feature: Visualizations
role: User, Admin
exl-id: 9d2a0163-a5cb-4a1c-97e9-e78a8f99aaee
source-git-commit: 121fac9958dc34be513a23d5c3ad76d5f0e6b665
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 30%

---

# Configurar una visualización de abandonos

Puede especificar **puntos de contacto** para crear una secuencia de visitas en el orden previsto multidimensional. En muchos casos, un punto de contacto es una página del sitio. Sin embargo, los puntos de contacto no se limitan a las páginas. Por ejemplo, puede añadir eventos, como unidades, así como personas únicas y visitas de retorno. También puede agregar dimensiones, como una categoría, un tipo de explorador o un término de búsqueda interna.

Incluso puede añadir segmentos dentro de un punto de contacto. Por ejemplo, es posible que quiera comparar segmentos como los usuarios de iOS y Android. Arrastre los segmentos deseados sobre las visitas en el orden previsto, y la información sobre esos segmentos se añadirá al informe de visitas en el orden previsto. Si desea mostrar únicamente esos segmentos, puede eliminar la línea de base de Todas las visitas.

Las visualizaciones de visitas en el orden previsto no tienen limitaciones en cuanto al número de puntos de contacto que puede añadir o al número de componentes que puede utilizar.

Puede realizar rutas en dimensiones, métricas y segmentos. Por ejemplo, supongamos que alguien está mirando `shoes, shirt` en una página y en la siguiente mira `shirt, socks`. El siguiente informe de flujo de productos desde zapatos será camiseta y calcetines, NO camiseta.

## Usar

1. Añada una visualización de ![Canal de conversión](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL Abandonos]**. Consulte [Añadir una visualización a un panel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Arrastre un componente al menú desplegable **[!UICONTROL Agregar punto de contacto]**.

   >[!TIP]
   >
   >Puede agregar una sola página al informe de visitas en el orden previsto, en lugar de toda la dimensión. Haga clic en la flecha derecha ![ChevronRight](/help/assets/icons/ChevronRight.svg) de la dimensión de página para seleccionar una página específica, como **[!UICONTROL inicio]**, y agregarla al informe de visitas en el orden previsto.


   ![La página de inicio de la dimensión Página de inicio se arrastró al campo Añadir punto de contacto.](assets/fallout-drag.png)

1. Siga añadiendo puntos de contacto hasta que la secuencia se haya completado.

   Los números dentro de un círculo en la parte gris de la barra muestran la visita en el orden previsto entre puntos de contacto (no la visita en el orden previsto total hasta ese punto). Los números en círculo de la parte verde de la barra muestran la caída correcta desde el punto de contacto anterior al punto de contacto actual.

   ![Visualización de abandonos](assets/fallout-visualization.png)

   Al agregar puntos de contacto, puede realizar cualquiera de las siguientes acciones:

   * Combine varios componentes arrastrando uno o más componentes adicionales a un único punto de contacto.

     >[!NOTE]
     >
     >Varios segmentos se unen con AND, mientras que los elementos (como elementos de dimensión y métricas) se unen con OR.

   * Reordene los puntos de contacto arrastrándolos a un nivel diferente dentro de la jerarquía de visitas en el orden previsto.

   * Combine dos puntos de contacto arrastrando un punto de contacto a otro. Suelte el punto de contacto cuando vea la palabra **[!UICONTROL Combinar]**.

   * Restrinja los puntos de contacto individuales a la siguiente visita individual (a diferencia de *eventualmente*) dentro de la ruta. Debajo de cada punto de contacto hay un selector con las opciones **[!UICONTROL Ruta de acceso eventual]** y **[!UICONTROL Siguiente visita]**, como se muestra a continuación:

     | Opción | Descripción |
     |---|---|
     | **[!UICONTROL Ruta eventual]** (predeterminada) | Se cuentan los visitantes que *eventualmente* llegarán a la siguiente página de la ruta, pero no necesariamente a la siguiente visita. |
     | **[!UICONTROL Siguiente visita]** | Se cuentan los visitantes que aterrizan en la siguiente página de la ruta en la siguiente visita. |

   * Pase el ratón sobre un punto de contacto para ver las visitas en el orden previsto y otra información sobre ese nivel. La información incluye el nombre del punto de contacto, el recuento de personas y la tasa de éxito. También puede comparar la tasa de éxito con otros puntos de contacto.

## Configuración

Los siguientes ajustes de visualización están disponibles:

| Contenedor de visitas en el orden previsto | Descripción |
|--- |--- |
| **[!UICONTROL Visitas]** o **[!UICONTROL Visitantes]** | Cambie entre [!UICONTROL visitas] y [!UICONTROL Visitantes] para analizar las rutas de las personas. El valor predeterminado es [!UICONTROL Visitantes]. Estos ajustes le permiten comprender el compromiso del visitante a nivel de visitante (a lo largo de visitas) o restringir el análisis a una única visita. |


## Menú contextual

Como parte de la visualización, hay opciones específicas de menú contextual disponibles.

### Acceso al menú contextual

Puede acceder al menú contextual de cualquiera de las siguientes maneras:

* Pase el ratón sobre un punto de contacto de la visualización y seleccione **[!UICONTROL Haga clic para analizar]**.

  ![Acceder al menú contextual desde el cursor](assets/fallout-tooltip-analyze.png)

* Haga clic con el botón derecho en un punto de contacto de la visualización.

  ![Opciones de visitas en el orden previsto](assets/fallout-options.png)

### Opciones del menú contextual

Las opciones de menú contextual disponibles son las siguientes:

| Opción | Descripción |
|--- |--- |
| **[!UICONTROL Punto de contacto de la tendencia]** | Consulte los datos de tendencia para un punto de contacto en un gráfico de líneas en el cual se hayan incorporado previamente algunos datos de detección de anomalías. |
| **[!UICONTROL Punto de contacto de tendencia (%)]** | Realiza la tendencia del porcentaje total de visitas en el orden previsto. |
| **[!UICONTROL Tendencia de todos los puntos de contacto (%)]** | Obtiene la tendencia de todos los porcentajes de puntos de contacto en la visita en el orden previsto (excepto **[!UICONTROL Todos los visitantes]**, si se incluye) en el mismo gráfico. |
| **[!UICONTROL Abandono del desglose en este punto de contacto]** | Vea qué hicieron los visitantes entre dos puntos de contacto (este punto de contacto y el siguiente) si continuaron hasta el siguiente punto de contacto. Esta opción crea una tabla de forma libre que muestra las dimensiones. Se pueden reemplazar dimensiones y otros elementos de la tabla. Por ejemplo, una tabla con la etiqueta **[!UICONTROL Visitas en el orden previsto: Todos los visitantes > Página es igual a cualquiera de las páginas de inicio]** y contiene **[!UICONTROL Página]** como dimensión y **[!UICONTROL Visitantes únicos]** segmentados por el [segmento rápido de solo proyecto](/help/components/segmentation/segmentation-workflow/seg-quick.md) **[!UICONTROL Visitantes en el orden previsto: Todos los visitantes > Página es igual a cualquiera de las páginas de inicio]** como métrica. Inspeccione el segmento para comprender cómo se determina el segmento de alternativa. |
| **[!UICONTROL Abandonos del desglose en este punto de contacto]** | Vea qué han hecho los visitantes que no han seguido la funnel inmediatamente después del paso seleccionado. Esta opción crea una tabla de forma libre que muestra las dimensiones. Se pueden reemplazar dimensiones y otros elementos de la tabla. Por ejemplo, una tabla con la etiqueta **[!UICONTROL Visitas en el orden previsto: Todos los visitantes > Página es igual a cualquiera de las páginas de inicio]** y contiene **[!UICONTROL Página]** como dimensión y **[!UICONTROL Visitantes únicos]** segmentados por el [segmento rápido de solo proyecto](/help/components/segmentation/segmentation-workflow/seg-quick.md) **[!UICONTROL Visitantes en el orden previsto: Todos los visitantes > Página es igual a cualquiera de las páginas de inicio]** como métrica. Inspeccione el segmento para comprender cómo se determina el segmento de visitas en el orden previsto. |
| **[!UICONTROL Crear segmento a partir de touchpoint]** | Cree un nuevo segmento a partir de un punto de contacto seleccionado. |

>[!MORELIKETHIS]
>
>[Añadir una visualización a un panel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configuración de visualización](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menú contextual de visualización](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

