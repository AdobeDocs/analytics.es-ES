---
title: Informes de comportamiento en Adobe Analytics
description: Aprenda a crear informes de comportamiento en Adobe Analytics
translation-type: tm+mt
source-git-commit: e1cbdf87140b915dccbb8f64694797bb903d8ab8

---


# Informes de comportamiento

Los informes de comportamiento muestran información sobre cómo los usuarios interactúan con el sitio.

Esta página supone que el usuario tiene conocimientos básicos sobre el uso de Analysis Workspace. Consulte [Creación de un informe básico en Analysis Workspace para usuarios](create-report.md) de Google Analytics si todavía no está familiarizado con la herramienta en Adobe Analytics.

## Flujo de comportamiento

El informe de flujo de comportamiento se puede volver a crear con la visualización Flujo.

1. Haga clic en el icono de visualizaciones de la izquierda y arrastre una visualización de flujo al espacio de trabajo encima de la tabla improvisada
2. Busque la dimensión **Página** y, a continuación, haga clic en el icono de flecha para mostrar los valores de la página. Los valores de dimensión son de color amarillo.
3. Busque el valor de página deseado para comenzar y arrástrelo al espacio etiquetado como &#39;Dimensión o elemento&#39; en el centro
4. Este informe de flujo es interactivo. Haga clic en cualquiera de los valores para expandir los flujos a páginas posteriores o anteriores. Utilice el menú que aparece al hacer clic con el botón derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.

![Informe de flujo](/help/technotes/ga-to-aa/assets/flow.png)

## Contenido del sitio: todas las páginas

El informe de páginas muestra el rendimiento de las páginas individuales del sitio.

1. En el menú Componentes, busque la dimensión **Páginas** y arrástrela hasta el área grande de la tabla improvisada con la etiqueta &#39;Colocar una dimensión aquí&#39;.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

Como alternativa, Adobe proporciona varios espacios de trabajo precreados denominados plantillas. La plantilla Consumo de contenido (Web) proporciona un valor similar al del informe de todas las páginas.

1. Haga clic en *[!UICONTROL Proyecto]>[!UICONTROL Nuevo]*, que abre una ventana modal con opciones de proyecto.
2. Haga clic en la plantilla Consumo de contenido (Web) y, a continuación, haga clic en Crear.

## Contenido del sitio: desglose de contenido

El informe de desglose de contenido permite observar el tráfico de la página según la estructura de la dirección URL. Se requiere una implementación adicional para su uso en Analysis Workspace. Adobe recomienda trabajar con un consultor de implementación para garantizar que estos datos se recopilen con precisión.

## Contenido del sitio - Páginas de aterrizaje

El informe de páginas de aterrizaje muestra las páginas de aterrizaje más visitadas del sitio. Las páginas de aterrizaje están disponibles en Analysis Workspace como dimensión de página de **entrada** .

1. En el menú Componentes, localice la dimensión Página **de** entrada y arrástrela hasta el área grande de la tabla improvisada con la etiqueta &#39;Colocar una dimensión aquí&#39;.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

Adobe recomienda utilizar la métrica **Visitas** para esta dimensión.

## Contenido del sitio - Páginas de salida

El informe de páginas de salida muestra las páginas principales que se convirtieron en la última página de la visita individual. Está disponible en Analysis Workspace con el mismo nombre.

1. En el menú Componentes, busque la dimensión **Página** de salida y arrástrela hasta el área grande de la tabla improvisada con la etiqueta &#39;Colocar una dimensión aquí&#39;.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la guía [de traducción de](common-metrics.md) métricas para obtener detalles sobre cómo obtener cada métrica respectiva.

Adobe recomienda utilizar la métrica **Visitas** para esta dimensión.

## Informes de velocidad del sitio

Los informes de velocidad del sitio muestran la rapidez con la que se cargan las páginas, lo que revela las oportunidades de aumentar los tiempos de carga de las páginas.

Esta función requiere una implementación adicional en ambas plataformas; Adobe recomienda trabajar con un consultor de implementación para garantizar que estos datos estén correctamente configurados para Analysis Workspace. El complemento [](/help/implement/vars/plugins/getpageloadtime.md) getPageLoadTime generalmente se asigna a una eVar para obtener datos de rendimiento en Adobe Analytics.

## Informes de búsqueda del sitio

Los informes de búsqueda del sitio proporcionan una visión detallada de cómo los visitantes utilizan las capacidades de búsqueda interna del sitio.

Esta función requiere una implementación adicional en ambas plataformas; Adobe recomienda trabajar con un consultor de implementación para garantizar que estos datos estén correctamente configurados para Analysis Workspace. Generalmente, un término de búsqueda interna se extrae de un parámetro de cadena de consulta y se coloca en una eVar para los informes.

## Informes de eventos

Los eventos tienen algunas diferencias estructurales importantes entre Google y Adobe Analytics. Ambos requieren cambios de implementación adicionales para funcionar correctamente en su plataforma respectiva.

* En Google Analytics, los eventos se definen como texto en la implementación. Los eventos tienen categorías, acciones y etiquetas.
* En Adobe Analytics, los eventos se configuran primero en Admin Console, donde se le asigna un identificador. Este identificador se utiliza en el código de implementación. Por ejemplo:
   1. Puede establecer event1 en la Consola de administración como &#39;Registros&#39;.
   2. En la implementación, incluiría event1 en la variable events en la página de confirmación de registro. Cada vez que se muestra la página de confirmación de registro, event1 aumenta.
   3. En Analysis Workspace, &quot;Registros&quot; aparece como una métrica para su uso en cualquier informe.

Debido a que esta función requiere cambios en la implementación, Adobe recomienda trabajar con un consultor de implementación para garantizar que los datos estén correctamente configurados para Analysis Workspace.

## Informes de publicador

De forma similar a como Google requiere una conexión con Google Ad Manager, Adobe ofrece un producto específico para proporcionar una perspectiva denominada Adobe Advertising Cloud. Si su organización está interesada en utilizar este producto, póngase en contacto con el administrador de cuentas de su organización.
