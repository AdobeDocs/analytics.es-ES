---
description: Descripción de los tipos de informes usados en Experience Cloud.
title: Tipos de informes
topic: Ad hoc analysis
uuid: 357102eb-a172-40ec-a302-01c87abaacb5
translation-type: tm+mt
source-git-commit: 5d96a2868bee48e2294ec2fb27e0340a3bcc50ae
workflow-type: tm+mt
source-wordcount: '1731'
ht-degree: 99%

---


# Tipos de informes

>[!IMPORTANT]
>
>El Adobe está llevando a Ad Hoc Analysis al final de su vida útil el 1 de marzo de 2021. [Más información](https://adobe.ly/discoverworkspace)

Descripción de los tipos de informes usados en Experience Cloud.

## Informes de clasificación {#concept_E1710FFFBB334F3D9DB63A1626DBCB01}

Muestran una tabla con una clasificación de artículos a partir de cantidades y porcentajes de las métricas. Por ejemplo, los [!UICONTROL informes de páginas] clasifican las páginas del sitio según el tráfico, y la tabla de detalles muestra los porcentajes y las cantidades correspondientes a diversas métricas, por ejemplo las vistas de páginas y los ingresos. El tipo de gráfico predeterminado es el gráfico de barras horizontales. Los gráficos muestran cada métrica en un color diferente. Los informes de clasificación pueden mostrar varias métricas a la vez.

<!-- 

c_reports_ranked.xml

 -->

La cantidad de elementos predeterminada de los gráficos de clasificación es cinco, pero en las opciones del gráfico se pueden incluir hasta treinta elementos.

## Informes de tendencias {#concept_65FEA92704024232BB21A5952939711F}

Permiten examinar las tendencias que siguen las conversiones y los eventos de acuerdo con una granularidad temporal seleccionada (hora, día, semana, mes, trimestre o año) durante un período de informe.

<!-- 

c_reports_trended.xml

 -->

En el gráfico, el eje vertical muestra los elementos de los que se hace seguimiento. El eje horizontal muestra la granularidad temporal. En la tabla, se puede analizar la tendencia desde una celda específica y abrir un informe completo desde la celda. Para ello, se emplea como fecha u hora el valor de la celda.

También se pueden seleccionar varias celdas y abrir un informe de tendencia en función de una granularidad seleccionada. Cuando se analizan tendencias desde varias celdas, las columnas del informe muestran datos de todo el período de informe.

Como ejemplo de un informe de tendencia podemos mencionar el [!UICONTROL informe de productos]. Se puede ver cuántos ingresos generó un producto durante un intervalo de fechas seleccionado. Si el período de informe es una semana, se puede ver cuántos ingresos generó el producto durante cada día del período de informe, mostrar un gráfico de tendencia para un determinado producto en ese día o abrir un informe de tendencia separado para la selección.

## Tendencia desde celdas {#task_AD9275BED5CE4D61AC25778D144406A4}

Instrucciones sobre cómo iniciar un informe de tendencia desde una o más celdas de una tabla.

<!-- 

t_trend_row.xml

 -->

**Para analizar tendencias desde celdas**

1. Abra un informe de clasificación.
1. En la tabla, ubique la celda deseada y haga clic en **[!UICONTROL Tendencia]**. 

   ![](assets/TrendInspector_Buttcon.png)

1. Para ver un informe completo desde la celda, haga clic en **[!UICONTROL Iniciar informe de tendencias]**.

   También se puede hacer clic en la celda con el botón derecho y luego hacer clic en **[!UICONTROL Celda de tendencias]**. Esta tarea también se puede realizar después de seleccionar varias celdas.

## Informes de totales {#concept_48E23FB3BCCD43DFB486A048960800A8}

<!-- 

c_reports_totals.xml

 -->

Un informe de nivel ejecutivo que muestra cifras totales. Contiene datos de totales de ingresos, vistas de página y pedidos. El informe se puede segmentar y se le pueden agregar métricas adicionales para ver otros datos.

## Informes de flujo {#concept_3E417D018F1B4566973F694B01E6439F}

Los informes de flujo muestran las rutas más comunes que siguen los usuarios en las páginas, secciones del sitio y servidores.

<!-- 

c_reports_flow.xml

 -->

**Flujo siguiente**

El grupo de informes de [!UICONTROL flujo de página siguiente] contiene tres informes: [!UICONTROL Flujo de página siguiente], [!UICONTROL Flujo de sección siguiente] y [!UICONTROL Flujo de servidor siguiente]. Los informes de este grupo muestran páginas, secciones del sitio y servidores a los que un visitante accede comúnmente luego de ingresar a la página, la sección del sitio o el servidor que usted especifique. Estos informes muestran las rutas más comunes que se recorren en el sitio web.

**Flujo anterior**

Los informes de flujo anterior son similares a los de flujo siguiente, excepto que en lugar de ver hacia dónde fueron los visitantes después de visitar una página, permiten ver dónde se encontraban antes de llegar a ella. Los controles para utilizar los informes son idénticos a los de los informes de flujo siguiente.

## Flujo de página siguiente {#concept_F7565234927942BEAF75D5D94A7AB47D}

Muestra las vistas de ruta, o la cantidad de veces y porcentajes que se vio una página, dentro de una restricción de ruta. Por ejemplo: puede ocurrir que la página de la política de privacidad tenga un total de 10 000 vistas, pero que solamente 500 de ellas se produjeron inmediatamente antes de la página de inicio. En este caso, se informarán 500 vistas de ruta. Estos datos se pueden analizar en el nivel de la visita o del visitante. El porcentaje de cada página se muestra al lado de su nombre. El ancho de una línea conectada a la página representa el porcentaje relativo de visitas.

<!-- 

c_reports_next_page_flow.xml

 -->

De manera predeterminada, este informe muestra las 10 páginas más comunes a las que fueron los usuarios después de la página seleccionada. Si hace clic en cualquier página subrayada se ampliará más el gráfico. No existen límites a la cantidad de páginas que se pueden tener en el gráfico. Además, al pasar el puntero del ratón por encima de una página, aparecerán datos sobre visitas e ingresos para esa página.

Utilice este informe para:

* Comprender los pasos que se siguen con mayor frecuencia después de ver una página seleccionada.
* Optimizar el diseño de rutas del sitio para canalizar el tráfico hacia una página objetivo.
* Identificar hacia dónde se dirigen los visitantes en lugar de visitar las páginas objetivo.

## Flujo de servidor siguiente {#concept_DB8C20E18AEA4051903C47A16C0E9C4E}

Presenta datos de navegación entre servidores del sitio. Al seleccionar el nombre de un servidor del sitio, el informe mostrará la cantidad de visitantes que navegaron desde dicho servidor a cada uno de los demás servidores del sitio dentro de una única visita o a lo largo de varias visitas.

<!-- 

c_reports_next_server_flow.xml

 -->

Por ejemplo, si se tienen datos específicos en diferentes servidores, o los mismos datos duplicados en servidores separados, el informe muestra la trayectoria que siguieron los usuarios. Esto también se aplica a los dominios dentro del sitio web. Se puede ver cuántos usuarios fueron de `https://www.mysite.com` a `https://info.mysite.com` o `https://sales.mysite.com`.

## Flujo de sección siguiente {#concept_7C9C8567E7DF477DA186E47DD3FD47A4}

El informe de [!UICONTROL flujo de sección siguiente] es similar al de [!UICONTROL flujo de página siguiente]. Muestra datos relacionados con secciones del sitio (grupos de páginas web relacionadas). Si una página está incluida en más de una sección del sitio, el informe muestra los datos de todas las secciones del sitio que la incluyan.

<!-- 

c_reports_next_section_flow.xml

 -->

Por ejemplo: una tienda minorista en línea puede tener secciones del sitio dedicadas a sus productos y secciones dedicadas a marcas de productos. En ese caso, la página web de un producto puede ser parte de varias secciones del sitio. Aunque la página del producto haya recibido una única visita, el informe de [!UICONTROL flujo de sección siguiente] muestra una vista de página para cada sección asociada con la página.

## Flujo de página anterior {#concept_ADEAEBAE3F37401B977A27E03B5A523B}

Es similar al informe de [!UICONTROL flujo de página siguiente]. El informe de [!UICONTROL flujo de página anterior] muestra gráficamente, con varios niveles, las páginas que con más frecuencia ven los visitantes antes de la página seleccionada. El informe también indica las páginas desde las cuales los visitantes ingresan al sitio.

<!-- 

c_reports_previous_page_flow.xml

 -->

Utilice este informe para:

* Comprender los pasos que se dan con mayor frecuencia después de ver una página seleccionada.
* Optimizar el diseño de rutas del sitio para canalizar el tráfico hacia una página objetivo.

## Flujo de sección anterior {#concept_30688D97B48449E1958866BAF376FA8C}

El informe de [!UICONTROL flujo de sección anterior] es similar al de [!UICONTROL flujo de página anterior]. Muestra datos relacionados con secciones del sitio (grupos de páginas web relacionadas). Si una página está incluida en más de una sección del sitio, el informe muestra los datos de todas las secciones del sitio que la incluyan.

<!-- 

c_reports_previous_section_flow.xml

 -->

Por ejemplo: una tienda minorista en línea puede tener secciones del sitio dedicadas a sus productos y secciones dedicadas a marcas de productos. En ese caso, la página web de un producto puede ser parte de varias secciones del sitio. Aunque la página del producto haya recibido una única visita, el informe de [!UICONTROL flujo de sección anterior] muestra una vista de página para cada sección asociada con la página.

## Flujo de servidor anterior {#concept_8E43208CAF2C4C358F19D4669B73822F}

Este informe muestra datos sobre la navegación entre servidores del sitio. Al seleccionar el nombre de un servidor del sitio, el informe mostrará la cantidad de visitantes que navegaron hasta ese servidor desde cada uno de los demás servidores del sitio dentro de una única visita o a lo largo de varias visitas.

<!-- 

c_reports_previous_server_flow.xml

 -->

Por ejemplo, si se tienen datos específicos en diferentes servidores, o los mismos datos duplicados en servidores separados, el informe muestra la trayectoria que siguieron los usuarios. Esto también se aplica a los dominios dentro del sitio web. Se puede ver cuántos usuarios fueron de `www.mysite.com` a `info.mysite.com` o `sales.mysite.com`.

## Informes de canal de conversión {#concept_35A2EB61E84441CBB670C2E02CA26F81}

Los informes de canal de conversión muestran los porcentajes de conversión entre determinados eventos de métricas. Estos informes se pueden usar para comprender con cuántas pulsaciones se generan ventas y la cantidad de unidades vendidas. Por ejemplo, un informe de [!UICONTROL conversión de productos] muestra el porcentaje de eventos de carro de compra en relación con los eventos de visita y luego muestra los totales de pedidos, ingresos y unidades, en función de esos eventos.

<!-- 

c_reports_conversion_funnel.xml

 -->

Están disponibles los siguientes informes de canal:

* [!UICONTROL Canal de conversión de compra]: muestra visitas (específicas del informe), carros de compras, pedidos, unidades e ingresos.
* [!UICONTROL Canal de conversión del carro de compras]: muestra visitas (específicas del informe), carros de compras, cierres de compra, pedidos e ingresos.
* [!UICONTROL Canal de eventos personalizados]: muestra eventos personalizados del sitio. Los eventos predeterminados son del 1 al 5.
* [!UICONTROL Canal de conversión de campañas]: muestra pulsaciones, cierres de compra, pedidos e ingresos.

La tabla del informe muestra estadísticas de ventas promedio por pulsación y unidades promedio vendidas por pulsación. A estos informes, se les pueden agregar métricas y eventos personalizados de otros grupos de informes. Aunque estos canales tienen muchos parecidos, se basan en variables y eventos diferentes. Estos informes se pueden usar para ver qué porcentajes y tendencias generales de los usuarios activan eventos específicos que se determinen. Permiten ver los lugares en los que los usuarios no siguen la ruta de eventos esperada, lo cual permite comprender ese punto en particular dentro del proceso de conversión.

## Informe de análisis del sitio {#concept_65694C6BDE424714B7975764F95497A4}

El informe de [!UICONTROL análisis del sitio] muestra la trayectoria que siguen los visitantes a través de determinadas páginas y eventos. Por ejemplo, se puede ver el flujo de tráfico entre páginas, la afinidad entre productos y canales de marketing y el modo en que las campañas y los canales llevan a que se realicen pedidos de productos. Se pueden arrastrar páginas, artículos (y listas) de dimensión y eventos de métricas. Cada cilindro representa uno o más artículos de dimensión (páginas) o un evento. Las flechas representan el flujo entre los valores de los cilindros. Se asignan métricas a las posiciones de los cilindros (X e Y), el ancho, la altura y el color del cilindro. La posición, el tamaño y el color cambian según los valores de las métricas.

<!-- 

c_reports_site_analysis.xml

 -->

Arrastre elementos desde los paneles de herramientas para agregarlos al gráfico o al campo de dimensiones.

Haga clic con el botón derecho en un cilindro para editarlo o eliminarlo.

<!-- Meike, UICONTROL and DNL stripped from tables. Re-add. -->

| Opción | Descripción |
|--- |--- |
| Mostrar el análisis de sitio en (visita o visitante) | Permite alternar entre visitas y visitantes para analizar las rutas seguidas por los visitantes. Estas opciones permiten analizar el interés de los visitantes, en el nivel de los visitantes, durante todas las visitas. Los informes de análisis de sitio, de flujo y de visitas en el orden previsto están habilitados para el control de rutas. Si se cambia esta opción, el informe se volverá a ejecutar y los datos se restringirán de acuerdo con la selección. |
| Agregar punto de comprobación | Abre el Editor de puntos de comprobación, desde el cual se pueden seleccionar dimensiones o eventos para agregar a la presentación. |
| Reemplazar gráfico | Reemplaza el gráfico de análisis del sitio con los puntos de comprobación que se agregaron al editor. |
| Ajustar a pantalla | Restablece la presentación original del gráfico. |
| Vista aérea | Muestra el gráfico desde arriba. |
| Alternar cuadrícula | Activa o desactiva la cuadrícula. |
| Dimensión | El artículo sobre el cual se informa. Arrastre el elemento desde Dimensiones. |

| Opción | Descripción |
|--- |--- |
| Editar | Permite agregar o quitar páginas en un cilindro. |
| Eliminar | Permite quitar un cilindro. |
| Informes | Permite iniciar otro informe desde el cilindro. |
| Guardar gráfico como | Permite guardar el gráfico como un archivo .jpg o .png. Si cambia los controles del gráfico (ángulo, tamaño del gráfico) antes de guardarlo, estos cambios se mantendrán en la salida. |
| Copiar gráfico al portapapeles | Copia el gráfico para pegarlo en otra aplicación. Si cambia los controles del gráfico (ángulo, tamaño del gráfico) antes de guardarlo, estos cambios se mantendrán en la salida. |
