---
title: Informes de comportamiento en Adobe Analytics
description: Descubra cómo crear informes de comportamiento en Adobe Analytics
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 99%

---


# Informes de comportamiento

Los informes de comportamiento muestran información sobre cómo los usuarios interactúan con el sitio.

En esta página se da por hecho que el usuario tiene conocimientos básicos sobre el uso de Analysis Workspace. Consulte [Creación de un informe básico en Analysis Workspace para usuarios de Google Analytics](create-report.md) si todavía no está familiarizado con la herramienta en Adobe Analytics.

## Flujo de comportamiento

El informe de flujo de comportamiento se puede volver a crear con la visualización Flujo.

1. Haga clic en el icono de visualizaciones de la izquierda y arrastre una visualización de flujo al espacio de trabajo sobre la tabla de forma libre
2. Busque la dimensión **Página** y, a continuación, haga clic en el icono de flecha para mostrar los valores de la página. Los elementos de dimensión son de color amarillo.
3. Busque el valor de página deseado para comenzar y arrástrelo al espacio etiquetado como “Dimensión o elemento” en el centro
4. Este informe de flujo es interactivo. Haga clic en cualquiera de los valores para expandir los flujos a páginas posteriores o anteriores. Utilice el menú que aparece al hacer clic con el botón derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.

![Informe de flujo](/help/technotes/ga-to-aa/assets/flow.png)

## Contenido del sitio: todas las páginas

El informe de páginas muestra el rendimiento de las páginas individuales del sitio.

1. En el menú Componentes, busque la dimensión **Páginas** y arrástrela hasta el área “Colocar una dimensión aquí” de la tabla de forma libre.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

Como alternativa, Adobe proporciona varios espacios de trabajo precreados denominados plantillas. La plantilla Consumo de contenido (Web) proporciona un valor similar al del informe de todas las páginas.

1. Haga clic en *[!UICONTROL Proyecto]>[!UICONTROL Nuevo]*, que abre una ventana modal con opciones de proyecto.
2. Haga clic en la plantilla Consumo de contenido (Web) y, a continuación, haga clic en Crear.

## Contenido del sitio: desglose de contenido

El informe de desglose de contenido permite observar el tráfico de la página según la estructura de la dirección URL. Se requiere una implementación adicional para su uso en Analysis Workspace. Adobe recomienda trabajar con un consultor de implementación para garantizar que estos datos se recopilen con precisión.

## Contenido del sitio: Páginas de destino

El informe de páginas de aterrizaje muestra las páginas de aterrizaje más visitadas del sitio. Las páginas de aterrizaje están disponibles en Analysis Workspace como dimensión de **Página de entrada**.

1. En el menú Componentes, localice la dimensión **Página de entrada** y arrástrela hasta el área “Colocar una dimensión aquí” de la tabla de forma libre.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

Adobe recomienda utilizar la métrica **Visitas** para esta dimensión.

## Contenido del sitio: Páginas de salida

El informe de páginas de salida muestra las páginas principales que se convirtieron en la última página de la visita individual. Está disponible en Analysis Workspace con el mismo nombre.

1. En el menú Componentes, busque la dimensión **Página de salida** y arrástrela hasta el área “Colocar una dimensión aquí” de la tabla de forma libre.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

Adobe recomienda utilizar la métrica **Visitas** para esta dimensión.

## Informes de velocidad del sitio

Los informes de velocidad del sitio muestran la rapidez con la que se cargan las páginas, lo que revela las oportunidades de aumentar los tiempos de carga de las páginas.

Esta función requiere una implementación adicional en ambas plataformas; Adobe recomienda trabajar con un consultor de implementación para garantizar que estos datos estén correctamente configurados para Analysis Workspace. El [complemento getPageLoadTime](/help/implement/vars/plugins/getpageloadtime.md) generalmente se asigna a una eVar para obtener datos de rendimiento en Adobe Analytics.

## Informes de búsqueda del sitio

Los informes de búsqueda del sitio proporcionan una visión detallada de cómo utilizan los visitantes los recursos de búsqueda interna del sitio.

Esta función requiere una implementación adicional en ambas plataformas; Adobe recomienda trabajar con un consultor de implementación para garantizar que estos datos estén correctamente configurados para Analysis Workspace. Generalmente, un término de búsqueda interna se extrae de un parámetro de cadena de consulta y se coloca en una eVar para los informes.

## Informes de eventos

Los eventos presentan algunas diferencias estructurales importantes entre Google Analytics y Adobe Analytics. Ambos requieren cambios de implementación adicionales para funcionar correctamente en su plataforma respectiva.

* En Google Analytics, los eventos se definen como texto en la implementación. Los eventos tienen categorías, acciones y etiquetas.
* En Adobe Analytics, los eventos se configuran primero en Admin Console, donde se les asigna un identificador. Este identificador se utiliza en el código de implementación. Por ejemplo:
   1. Puede establecer evento1 en Admin Console como “Registros”.
   2. En la implementación, incluiría evento1 en la variable events en la página de confirmación de registro. Cada vez que se muestra la página de confirmación de registro, evento1 aumenta.
   3. En Analysis Workspace, “Registros” aparece como una métrica para su uso en cualquier informe.

Ya que esta función requiere cambios en la implementación, Adobe recomienda trabajar con un consultor de implementación para garantizar que los datos estén correctamente configurados para Analysis Workspace.

## Informes de editor

De forma similar a como Google requiere una conexión con Google Ad Manager, Adobe tiene un producto diseñado para proporcionar información denominado Adobe Advertising Cloud. Si su organización está interesada en utilizar este producto, póngase en contacto con el administrador de cuentas de su organización.
