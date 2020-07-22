---
title: Informes de adquisición en Adobe Analytics
description: Información sobre la creación de informes basados en adquisiciones, usando Analysis Workspace.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '1578'
ht-degree: 99%

---


# Informes de adquisición

Los informes de adquisición muestran cómo se consiguen visitantes para el sitio.

En Adobe Analytics, estos informes se conocen como **Canales de marketing**. Necesitan una configuración inicial básica, pero ofrecen una vista de los canales mucho más personalizada.

>[!IMPORTANT]
>
> Configure las reglas de procesamiento del canal de marketing para utilizar estos informes. Consulte [Introducción a los canales de marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md) para obtener información sobre una configuración óptima de los canales de marketing en su organización.

En esta página se da por hecho que el usuario tiene conocimientos básicos sobre el uso de Analysis Workspace. Consulte [Creación de un informe básico en Analysis Workspace para usuarios de Google Analytics](create-report.md) si todavía no está familiarizado con la herramienta en Adobe Analytics.

## Todo el tráfico: canales

Muestra una vista acumulada de todos los canales que los visitantes utilizan para llegar al sitio.

1. En el menú Componentes, busque la dimensión **Canal de marketing** y arrástrela hasta el área “Colocar una dimensión aquí” de la tabla de forma libre.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

## Todo el tráfico: diagramas de árbol

Muestra un diagrama del tráfico del canal. Este informe es similar a Todo el tráfico: canales, pero se muestra de una manera diferente.

1. Haga clic en el icono Visualizaciones de la izquierda y arrastre la visualización Diagrama de árbol al espacio de trabajo sobre la tabla de forma libre vacía.
2. Haga clic en el icono Componentes, a la izquierda y, a continuación, arrastre la dimensión **Canal de marketing** al área grande de la tabla de forma libre denominada “Colocar una dimensión aquí”.
3. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.
4. Tenga en cuenta que las métricas adicionales generan diagramas de árbol adicionales. Si solo se desea obtener un diagrama:
   1. Haga clic en la celda superior de la métrica deseada para representar el diagrama de árbol.
   2. Pulse la tecla Mayús y haga clic en la última celda de la misma columna de métrica para resaltar la columna en azul. Si se realiza correctamente, en la visualización aparece un diagrama de árbol.
   3. Haga clic en el punto de color en la esquina superior derecha de la visualización del diagrama y, a continuación, haga clic en la casilla de verificación “Bloquear selección”.

Los mapas de rectángulos se pueden aplicar a cualquier dimensión, no solo a los canales de marketing.

## Todo el tráfico: fuente/medio

Los informes de fuente y medio muestran los dominios que condujeron el tráfico al sitio.

* La dimensión principal **Origen** está disponible en Analysis Workspace como dimensión **Dominio de referencia**.
* La dimensión principal **Medio** está disponible en Analysis Workspace como dimensión **Tipo de referente**.
* La dimensión principal de **Palabra clave** está disponible en Analysis Workspace como dimensión de **Palabra clave de búsqueda**.

1. En el menú de componentes, localice la dimensión deseada indicada arriba y arrástrela al área “Colocar una dimensión aquí” de la tabla de forma libre.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

Consulte las siguientes páginas en la Guía del usuario de componentes para obtener más información sobre sus dimensiones:

* [Dominio de referencia](/help/components/dimensions/referring-domain.md)
* [Tipo de referente](/help/components/dimensions/referrer-type.md)
* [Palabra clave de búsqueda](/help/components/dimensions/search-keyword.md)

## Todo el tráfico: referencias

* La dimensión principal **Origen** está disponible en Analysis Workspace como dimensión **Dominio de referencia**.
* La dimensión principal de la **Página de aterrizaje** está disponible en Analysis Workspace como dimensión de **Página de entrada**.

1. En el menú de componentes, localice la dimensión **Dominio de referencia** o **Página de entrada** y arrástrela al área grande de la tabla de forma libre denominada “Colocar una dimensión aquí”.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

Consulte la dimensión [Dominio de referencia](/help/components/dimensions/referring-domain.md) en la guía del usuario sobre Componentes para obtener más información.

## Informes de Google Ads e informes de Search Console

Adobe utiliza una característica de Analysis Workspace llamada Advertising Analytics para incorporar datos de publicidad y búsqueda de varias plataformas, como Google.

Esta característica de análisis de publicidad debe estar configurada para que devuelva datos. Consulte la [Ayuda de Advertising Analytics](/help/integrate/c-advertising-analytics/overview.md) sobre la habilitación de estas dimensiones adicionales en Analysis Workspace.

## Informes de actividad social

Los informes de Actividad social proporcionan información similar a la de su correspondiente informe de Comportamiento, excepto en el contexto de las redes sociales. Estos datos están disponibles en Analysis Workspace, al combinar una dimensión con un segmento.

A veces, los visitantes llegan al sitio a través de diversos canales en la misma sesión. Por ejemplo: un visitante hace clic en una página de medios sociales y unos minutos más tarde utiliza un motor de búsqueda para llegar a su sitio. En estos casos, los dominios no sociales pueden aparecer en este informe. Para excluir los dominios no sociales, ordene el informe por visitas o cree una copia del segmento para que se base en las visitas individuales. Consulte la dimensión [Contenedores de segmentación](/help/components/c-segmentation/seg-overview.md) en la Guía de usuario para obtener más información.

### Social: referencias de red

El informe Referencias de red muestra los dominios de redes sociales que conducen el tráfico al sitio. Estos datos están disponibles en Analysis Workspace mediante la dimensión **Dominio de referencia** y el segmento **Visitas desde medios sociales**.

1. En el menú Componentes, busque la dimensión **Dominio de referencia** y arrástrela al área grande de la tabla de forma libre con la etiqueta “Colocar una dimensión aquí”.
2. En el menú Componentes, busque el segmento **Visitas desde medios sociales** y arrástrelo hasta el área pequeña que se encuentra justo encima de la tabla de forma libre denominada “Colocar un segmento aquí”.
3. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

### Social: Páginas de destino

El informe Páginas de destino muestra a qué páginas llegaron los visitantes después de hacer clic en un vínculo a través de una red social. Estos datos están disponibles en Analysis Workspace, con la dimensión **Página de entrada** y el segmento **Visitas desde sitios sociales**.

1. En el menú Componentes, localice la dimensión **Página de entrada** y arrástrela hasta el área “Colocar una dimensión aquí” de la tabla de forma libre.
2. En el menú Componentes, busque el segmento **Visitas desde medios sociales** y arrástrelo hasta el área pequeña que se encuentra justo encima de la tabla de forma libre denominada “Colocar un segmento aquí”.
3. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

### Social: conversiones

El informe Conversiones muestra los datos de comercio electrónico en el contexto de las redes sociales. Es necesaria una implementación adicional para utilizar estos informes en ambas plataformas. Adobe recomienda trabajar con un consultor de implementación para garantizar que estos datos estén correctamente configurados para Analysis Workspace.

### Social: plug-ins

El informe Plug-ins muestra las interacciones de los visitantes con los complementos de medios sociales incrustados en el sitio. Se requiere una implementación adicional para su uso en Analysis Workspace. Adobe recomienda trabajar con un consultor de implementación para garantizar que estos datos se recopilen con precisión.

### Social: flujo de usuarios

El informe Flujo de usuarios muestra los datos de rutas en el contexto de los visitantes que llegan a través de una red social.

1. Haga clic en el icono de visualizaciones de la izquierda y arrastre una visualización de flujo al espacio de trabajo sobre la tabla de forma libre
2. Haga clic en el icono Componentes, a la izquierda y, a continuación, arrastre el segmento **Visitas desde medios sociales** a la pequeña área que se encuentra justo encima de la visualización de flujo denominada “Colocar un segmento aquí”.
3. Busque la dimensión **Páginas** y, a continuación, haga clic en el icono de flecha para mostrar los valores de la página. Los elementos de dimensión son de color amarillo.
4. Busque el valor de página deseado para comenzar y arrástrelo al espacio etiquetado como “Dimensión o elemento” en el centro
5. Este informe de flujo es interactivo. Haga clic en cualquiera de los valores para expandir los flujos a páginas posteriores o anteriores. Utilice el menú que aparece al hacer clic con el botón derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.

## Campañas: todas

El informe de campañas está disponible en Analysis Workspace con la dimensión **Código de seguimiento**. El uso de la dimensión Código de seguimiento requiere una implementación adicional para recopilar datos.

Es posible recopilar parámetros de UTM en Adobe Analytics mediante variables personalizadas (eVars). Adobe recomienda trabajar con un consultor de implementación para garantizar que los valores del código de seguimiento se recopilen con precisión en Adobe Analytics.

1. En el menú Componentes, busque la dimensión **Código de seguimiento** y arrástrela hasta el área grande de la tabla de forma libre denominada “Colocar una dimensión aquí”.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

## Campañas: palabras clave de pago

El informe Palabras clave de pago muestra el rendimiento de cada palabra clave después de que un visitante haga clic desde un motor de búsqueda en un vínculo de búsqueda de pago. La dimensión **Palabras clave de búsqueda de pago** está disponible en Analysis Workspace, pero requiere una configuración única de detección de búsqueda de pago para recopilar datos. Consulte [Detección de búsqueda de pago](/help/admin/admin/paid-search-detection/paid-search-detection.md) en la guía de usuario del administrador para obtener más información sobre la configuración.

1. En el menú Componentes, ubique la dimensión **Palabra clave de búsqueda de pago** y arrástrela al área grande de la tabla de forma libre denominada “Colocar una dimensión aquí”.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

## Campañas: palabras clave orgánicas

El informe de palabras clave orgánicas muestra el rendimiento de cada palabra clave después de que un visitante haga clic desde un motor de búsqueda en un vínculo de búsqueda orgánica. La dimensión **Palabras clave de búsqueda: natural** está disponible en Analysis Workspace. Si no está configurada la detección de búsqueda de pago, esta dimensión recopila palabras clave tanto de pago como naturales.

1. En el menú Componentes, busque la dimensión **Buscar palabra clave: natural** y arrástrela al área grande de la tabla de forma libre denominada “Colocar una dimensión aquí”.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

## Análisis de costes

Este informe muestra los datos de rendimiento de visitas, costes e ingresos de los canales de marketing de pago. Adobe ofrece un producto específico para proporcionar información, denominado Adobe Advertising Cloud. Si su organización está interesada en utilizar este producto, póngase en contacto con el administrador de cuentas de su organización.
