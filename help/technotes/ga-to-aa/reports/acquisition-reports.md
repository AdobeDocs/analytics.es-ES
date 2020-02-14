---
title: Informes de adquisición en Adobe Analytics
description: Obtenga información sobre cómo crear informes basados en adquisiciones mediante Analysis Workspace.
translation-type: tm+mt
source-git-commit: 2e3896501a036e20f9f392c325e0c8ff1d586fba

---


# Informes de adquisición

Los informes de adquisición muestran cómo se obtienen los visitantes del sitio.

En Adobe Analytics, estos informes se conocen como Canales **de mercadotecnia**. Requieren una configuración inicial básica, pero permiten una vista de los canales mucho más personalizada.

> [!IMPORTANT]
>
> Configure las reglas de procesamiento del canal de mercadotecnia para utilizar estos informes. Consulte [Introducción a los canales](/help/components/c-marketing-channels/c-getting-started-mchannel.md) de mercadotecnia para obtener información sobre cómo configurar mejor los canales de mercadotecnia en su organización.

Esta página supone que el usuario tiene conocimientos básicos sobre el uso de Analysis Workspace. Consulte [Creación de un informe básico en Analysis Workspace para usuarios](create-report.md) de Google Analytics si todavía no está familiarizado con la herramienta en Adobe Analytics.

## Todo el tráfico - Canales

Muestra una vista agregada de todos los canales que los visitantes utilizan para llegar al sitio.

1. En el menú Componentes, localice la dimensión Canal **de mercadotecnia** y arrástrela al área grande de la tabla improvisada denominada &#39;Colocar una dimensión aquí&#39;.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

## Todo el tráfico: mapas de rectángulos

Muestra un mapa del tráfico del canal. Este informe es similar a Todo el tráfico - Canales, pero se muestra de una manera diferente.

1. Haga clic en el icono Visualizaciones de la izquierda y arrastre la visualización de rectángulos al espacio de trabajo encima de la tabla improvisada vacía.
2. Haga clic en el icono Componentes de la izquierda y, a continuación, arrastre la dimensión Canal **de mercadotecnia** al área grande de la tabla improvisada denominada &#39;Colocar una dimensión aquí&#39;.
3. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.
4. Tenga en cuenta que las métricas adicionales crean mapas de árbol adicionales. Si solo se desea una coincidencia:
   1. Haga clic en la celda superior de la métrica deseada para representar el mapa de árbol.
   2. Pulse Mayús y haga clic en la última celda de la misma columna de métrica para resaltar la columna azul. Si se realiza correctamente, en la visualización hay un mapa de temblores.
   3. Haga clic en el punto de color en la esquina superior derecha de la visualización del mapa de árbol y, a continuación, haga clic en la casilla de verificación &#39;Bloquear selección&#39;.

Los mapas de rectángulos se pueden aplicar a cualquier dimensión, no solo a los canales de mercadotecnia.

## Todo el tráfico - Origen/Medio

Los informes de fuente y medio muestran los dominios que condujeron el tráfico al sitio.

* La dimensión principal **Origen** está disponible en Analysis Workspace como dimensión Dominio **de** referencia.
* La dimensión principal **Media** está disponible en Analysis Workspace como dimensión Tipo **de** referente.
* La dimensión principal de **palabra clave** está disponible en Analysis Workspace como dimensión de palabra clave de **búsqueda** .

1. En el menú de componentes, localice la dimensión deseada indicada arriba y arrástrela al área grande de la tabla improvisada con la etiqueta &#39;Colocar una dimensión aquí&#39;.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

Consulte las páginas siguientes en la guía del usuario Componentes para obtener más información sobre sus dimensiones respectivas:

* [Dominio de referencia](/help/components/c-variables/dimensionslist/reports-referring-domains.md)
* [Tipo de referente](/help/components/c-variables/dimensionslist/reports-ref-types.md)
* [Palabra clave de búsqueda](/help/components/c-variables/dimensionslist/reports-search-keywords.md)

## Todo el tráfico - Referencias

* La dimensión principal **Origen** está disponible en Analysis Workspace como dimensión Dominio **de** referencia.
* La dimensión principal de la página **de aterrizaje** está disponible en Analysis Workspace como dimensión de página **de** entrada.

1. En el menú de componentes, localice la dimensión Dominio **de** referencia o Página **de** entrada y arrástrela al área grande de la tabla improvisada denominada &#39;Colocar una dimensión aquí&#39;.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

Consulte la dimensión Dominio [de](/help/components/c-variables/dimensionslist/reports-referring-domains.md) referencia en la guía del usuario Componentes para obtener más información.

## Informes Publicidades de Google e informes de Consola de búsqueda

Adobe utiliza una función en Analysis Workspace denominada Análisis de publicidad para incorporar datos de publicidad y búsqueda de varias plataformas, incluida Google.

La función de análisis de publicidad requiere configuración para devolver datos. Consulte la Ayuda [de análisis de](/help/integrate/c-advertising-analytics/overview.md) publicidad para obtener detalles sobre cómo habilitar estas dimensiones adicionales en Analysis Workspace.

## Informes sociales 

Los informes de Social proporcionan información similar a su respectivo informe de Comportamiento, excepto en el contexto de las redes sociales. Estos datos están disponibles en Analysis Workspace combinando una dimensión con un segmento.

A veces, los visitantes llegan al sitio a través de múltiples canales en la misma sesión. Por ejemplo: un visitante hace clic en una página de medios sociales y luego, unos minutos después, visita un motor de búsqueda para llegar a su sitio. En estos casos, los dominios no sociales pueden aparecer en este informe. Si desea excluir los dominios no sociales, ordene el informe por visitas o cree una copia del segmento que se base en las visitas en lugar de en las visitas. See [Segmentation Containers](/help/components/c-segmentation/seg-overview.md) in the Components user guide for more information.

### Social: referencias de red

El informe Referencias de red muestra los dominios de redes sociales que conducen el tráfico al sitio. Estos datos están disponibles en Analysis Workspace mediante la dimensión Dominio **de** referencia y el segmento **Visitas desde sitios** sociales.

1. En el menú Componentes, busque la dimensión Dominio **de** referencia y arrástrela al área grande de la tabla improvisada con la etiqueta &#39;Colocar una dimensión aquí&#39;.
2. En el menú Componentes, busque el segmento **Visitas desde sitios** sociales y arrástrelo hasta el área pequeña que se encuentra justo encima de la tabla improvisada denominada &#39;Colocar un segmento aquí&#39;.
3. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

### Social - Páginas de aterrizaje

El informe Páginas de aterrizaje muestra en qué páginas llegaron los visitantes después de hacer clic en un vínculo a través de una red social. Estos datos están disponibles en Analysis Workspace mediante la dimensión Página **de** entrada y el segmento **Visitas desde sitios** sociales.

1. En el menú Componentes, localice la dimensión Página **de** entrada y arrástrela hasta el área grande de la tabla improvisada con la etiqueta &#39;Colocar una dimensión aquí&#39;.
2. En el menú Componentes, busque el segmento **Visitas desde sitios** sociales y arrástrelo hasta el área pequeña que se encuentra justo encima de la tabla improvisada denominada &#39;Colocar un segmento aquí&#39;.
3. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

### Social - Conversiones

El informe Conversiones muestra los datos del comercio electrónico en el contexto de las redes sociales. Se requiere una implementación adicional para utilizar estos informes en ambas plataformas; Adobe recomienda trabajar con un consultor de implementación para garantizar que estos datos estén correctamente configurados para Analysis Workspace.

### Social - Complementos

El informe Complementos muestra cómo los visitantes interactúan con los complementos de medios sociales incrustados en el sitio. Se requiere una implementación adicional para su uso en Analysis Workspace. Adobe recomienda trabajar con un consultor de implementación para garantizar que estos datos se recopilen con precisión.

### Social: Flujo de usuarios

El informe Flujo de usuarios muestra los datos de rutas en el contexto de los visitantes que llegan a través de una red social.

1. Haga clic en el icono de visualizaciones de la izquierda y arrastre una visualización de flujo al espacio de trabajo encima de la tabla improvisada
2. Haga clic en el icono Componentes de la izquierda y, a continuación, arrastre el segmento **Visitas desde sitios** sociales a la pequeña área que hay justo encima de la visualización de flujo con la etiqueta &#39;Colocar un segmento aquí&#39;.
3. Busque la dimensión **Páginas** y, a continuación, haga clic en el icono de flecha para mostrar los valores de la página. Los valores de dimensión son de color amarillo.
4. Busque el valor de página deseado para comenzar y arrástrelo al espacio etiquetado como &#39;Dimensión o elemento&#39; en el centro
5. Este informe de flujo es interactivo. Haga clic en cualquiera de los valores para expandir los flujos a páginas posteriores o anteriores. Utilice el menú que aparece al hacer clic con el botón derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.

## Campañas: Todas

El informe de campañas está disponible en Analysis Workspace mediante la dimensión Código **de** seguimiento. Tenga en cuenta que el uso de la dimensión Código de seguimiento requiere una implementación adicional para recopilar datos.

Es posible recopilar parámetros de UTM en Adobe Analytics mediante variables personalizadas (eVars). Adobe recomienda trabajar con un consultor de implementación para garantizar que los valores del código de seguimiento se recopilen con precisión en Adobe Analytics.

1. En el menú Componentes, busque la dimensión Código **de** seguimiento y arrástrela hasta el área grande de la tabla improvisada con la etiqueta &#39;Colocar una dimensión aquí&#39;.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

## Campañas: Palabras clave pagas

El informe Palabras clave pagas muestra el rendimiento de cada palabra clave después de que un visitante haga clic en un vínculo de búsqueda paga desde un motor de búsqueda. La dimensión Palabras clave de **búsqueda: Pagado** está disponible en Analysis Workspace, pero requiere una configuración única de detección de búsqueda paga para recopilar datos. Consulte Detección [de búsqueda](/help/admin/admin/paid-search-detection/paid-search-detection.md) paga en la guía del usuario del administrador para obtener más información sobre la configuración.

1. En el menú Componentes, ubique la dimensión **Palabra clave de búsqueda - Paga** y arrástrela al área grande de la tabla improvisada denominada &#39;Colocar una dimensión aquí&#39;.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

## Campañas: Palabras clave orgánicas

El informe Palabras clave orgánicas muestra el rendimiento de cada palabra clave después de que un visitante haga clic en un vínculo de búsqueda orgánica desde un motor de búsqueda. La dimensión **Palabras clave de búsqueda: Natural** está disponible en Analysis Workspace. Tenga en cuenta que si la detección de búsqueda paga no está configurada, esta dimensión recopila palabras clave pagas y naturales.

1. En el menú Componentes, busque la dimensión **Buscar palabra clave - Natural** y arrástrela al área grande de la tabla improvisada con la etiqueta &#39;Colocar una dimensión aquí&#39;.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

## Análisis de costos

Este informe muestra los datos de rendimiento de visitas, costos e ingresos de los canales de mercadotecnia paga. Adobe proporciona un producto específico para proporcionar una perspectiva denominada Adobe Advertising Cloud. Si su organización está interesada en utilizar este producto, póngase en contacto con el administrador de cuentas de su organización.
