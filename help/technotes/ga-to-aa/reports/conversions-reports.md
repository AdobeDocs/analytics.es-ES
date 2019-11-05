---
title: Informes de conversiones en Adobe Analytics
description: Descubra cómo utilizar los informes de conversión en Adobe Analytics.
translation-type: tm+mt
source-git-commit: 3ce18f3f222286aed08c81dd2c958dab7e443df3

---


# Informes de conversión

Una 'conversión' es una acción que realiza un visitante en el sitio y que se traduce directamente en los indicadores clave de la organización. Los informes de conversiones muestran detalles sobre la conversión de los visitantes.

Esta página supone que el usuario tiene conocimientos básicos sobre el uso de Analysis Workspace. Consulte [Creación de un informe básico en Analysis Workspace para usuarios](create-report.md) de Google Analytics si todavía no está familiarizado con la herramienta en Adobe Analytics.

## Informes de objetivos

Los objetivos proporcionan a los usuarios de Google Analytics una forma de definir la conversión de un sitio web. Son la forma predeterminada de crear embudos, flujo de comportamiento inverso, embudos multicanal y atribución. Los objetivos de Google Analytics no son retroactivos y solo se pueden configurar en la página de administración. Además, se basan únicamente en una página, evento, tiempo empleado o número promedio de páginas.

En Adobe Analytics, el concepto de objetivo no es obligatorio porque las métricas se pueden aplicar en cualquier contexto. Siempre que la implementación se ajuste a los eventos que desee rastrear, puede modificar cualquier informe de conversión y obtener resultados de inmediato para los datos históricos.

### Visualización de canales

El informe de visualización de canal ayuda a los analistas a centrarse en una serie concreta de pasos necesarios para la conversión. Por ejemplo: antes de realizar una compra, un visitante en un sitio de comercio electrónico tendría que acceder al carro de compras, a la página de facturación y envío, a la página de pago y a la página de revisión de pedidos.

En Analysis Workspace, estos datos se pueden ver mediante la visualización de visitas en el orden previsto.

1. Haga clic en el icono de visualizaciones de la izquierda y arrastre una visualización de visitas en el orden previsto al espacio de trabajo sobre la tabla improvisada
2. Haga clic en el icono de componentes de la izquierda y, a continuación, busque la dimensión **Páginas** .
3. Haga clic en el icono de flecha junto a la dimensión Páginas para mostrar los valores de la página. Los valores de dimensión son de color amarillo.
4. Busque la página que desee para que actúe como primer punto de contacto y arrástrela al espacio etiquetado como 'Agregar punto de contacto' en la visualización.
5. Continúe agregando los puntos de contacto deseados arrastrando los valores de página a la visualización.

La visualización de visitas en el orden previsto no se limita solo a la dimensión Páginas. Cualquier dimensión, métrica o segmento puede utilizarse para adaptar el informe de visitas en el orden previsto a las necesidades de su organización.

![Visualización de visitas en el orden previsto](/help/technotes/ga-to-aa/assets/fallout.png)

## Informes de comercio electrónico

Los informes de comercio electrónico generalmente los utilizan los sitios que venden productos o servicios para medir los pedidos y los ingresos de los artículos comprados. Esta función está disponible en Adobe Analytics y se conoce como informes de productos.

Tanto los informes de comercio electrónico de Google Analytics como los informes de productos de Adobe Analytics requieren cambios de implementación personalizados para su uso. Consulte la dimensión [Productos](/help/components/c-variables/dimensionslist/reports-products.md) en la guía del usuario Componentes para obtener más información.

## Informes de canal multicanal

Los informes de canal multicanal proporcionan datos adicionales de canal de mercadotecnia más allá de los informes de adquisición. Estos informes se centran en la forma en que los visitantes se convierten, en lugar de en cómo llegan al sitio.

> [!NOTE]
>
> El uso de informes multicanal en Adobe Analytics requiere tanto la configuración de canales de mercadotecnia como una implementación personalizada para dar cabida a la variable products y al evento purchase. Adobe recomienda trabajar con un consultor de implementación si estas funciones aún no están configuradas para su grupo de informes.

### Multicanal: conversiones asistidas

Las conversiones asistidas muestran la cantidad de veces que cada canal ayudó con una conversión. En Analysis Workspace, se puede utilizar la métrica **Ayudas** para pedidos.

1. En el menú Componentes, localice la dimensión Canal **de mercadotecnia** y arrástrela al área grande de la tabla improvisada denominada 'Colocar una dimensión aquí'.
2. Arrastre la métrica **Ayudas** para pedidos sobre el encabezado de métrica **Ocurrencias** creado automáticamente para reemplazarla. Si lo desea, se pueden arrastrar métricas adicionales al espacio de trabajo.

### Varios canales: rutas de conversión principales

El informe de rutas de conversión principales muestra las rutas de canales principales que toma un usuario antes de realizar la conversión. Analysis Workspace utiliza un informe de flujo para visualizar las rutas de conversión principales.

1. Haga clic en el icono Paneles de la izquierda y arrastre un panel Atribución sobre la tabla improvisada.
2. Haga clic en el icono Componentes de la izquierda, busque la dimensión Canal **de** mercadotecnia y arrástrela al cuadro con la etiqueta 'Agregar dimensión'.
3. Busque el evento de conversión deseado en Métricas (por ejemplo: Pedidos) y arrástrelo al cuadro rotulado 'Agregar métrica'. Tenga en cuenta que las métricas calculadas no son compatibles con el panel Atribución.
4. Haga clic en Crear.
5. En el informe resultante, busque la visualización 'Flujo de canal'. Este flujo muestra las rutas principales que un visitante tocó antes de una compra.

Esta visualización de flujo es interactiva. Haga clic en cada canal para expandir el flujo en cualquier dirección.

![Visualización de flujo](/help/technotes/ga-to-aa/assets/flow.png)

### Multicanal: retraso de tiempo

El informe de lapso de tiempo muestra la cantidad de tiempo en días que un visitante tardó en realizar la conversión en el sitio. En Analysis Workspace, estos datos están disponibles mediante la dimensión **Días antes de la primera compra** . Solo está disponible en el contexto de un evento de compra correctamente implementado.

1. En el menú Componentes, busque la dimensión **Días antes de la primera compra** y arrástrela al área grande de la tabla improvisada con la etiqueta 'Colocar una dimensión aquí'.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

Adobe recomienda utilizar con esta dimensión las métricas **Pedidos**, **Unidades** o **Ingresos** .

Para otros tipos de conversiones, incluidos los eventos personalizados, está disponible la dimensión **Tiempo previo al evento** . Muestra la cantidad de tiempo, en minutos, que un visitante tardó en desencadenar el evento dentro de la visita.

1. En el menú Componentes, busque la dimensión **Tiempo previo al evento** y arrástrela al área grande de la tabla improvisada con la etiqueta 'Colocar una dimensión aquí'.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

Adobe recomienda utilizar esta dimensión junto con eventos personalizados o eventos de compra.

### Varios canales: longitud de ruta

El informe Longitud de ruta muestra la cantidad de canales tocados antes de un evento de conversión. En Analysis Workspace, el panel Atribución contiene estos datos en una de sus visualizaciones.

1. Haga clic en el icono Paneles de la izquierda y arrastre un panel Atribución sobre la tabla improvisada
2. Haga clic en el icono Componentes de la izquierda, busque la dimensión Canal **de** mercadotecnia y arrástrela al cuadro con la etiqueta 'Agregar dimensión'.
3. Busque el evento de conversión deseado en Métricas (por ejemplo: Pedidos) y arrástrelo al cuadro rotulado 'Agregar métrica'. Tenga en cuenta que las métricas calculadas no son compatibles con el panel Atribución.
4. Haga clic en Crear.
5. En el informe resultante, localice la visualización 'Puntos de contacto por viaje'. Este histograma muestra la cantidad de canales que un visitante tocó antes de una compra.
