---
title: Informes de audiencia en Adobe Analytics
description: Obtenga información sobre cómo crear informes basados en audiencias mediante Analysis Workspace.
exl-id: 739b0c3d-3f74-41fa-a2cc-f02c17d85ce2
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '1715'
ht-degree: 100%

---

# Informes de audiencia

Los informes de audiencia muestran información sobre los tipos de usuarios que visitan el sitio.

En esta página se da por hecho que el usuario tiene conocimientos básicos sobre el uso de Analysis Workspace. Consulte [Creación de un informe básico en Analysis Workspace para usuarios de Google Analytics](create-report.md) si todavía no está familiarizado con la herramienta en Adobe Analytics.

## Usuarios activos

Los usuarios activos muestran el número acumulado de usuarios en el sitio el día anterior o en los 7, 14 o 28 días anteriores. Aunque Adobe no tiene el cálculo exacto utilizado en Google Analytics, puede utilizar la métrica Visitantes únicos para ver un recuento deduplicado de usuarios en su sitio en función del intervalo de fechas seleccionado.

Para obtener un gráfico de líneas de visitantes únicos:

1. Haga clic en el icono Visualizaciones de la izquierda y arrastre la visualización Línea al espacio de trabajo sobre la tabla de forma libre vacía.
2. Haga clic en el icono Componentes de la izquierda y, a continuación, arrastre la métrica **Visitantes únicos** al espacio más pequeño rotulado “Colocar una métrica aquí”.
3. Si desea utilizar una granularidad diferente, arrastre el intervalo de fechas deseado (por ejemplo, **Día**, **Semana**, **Mes**, etc.) sobre el encabezado de dimensión de fecha existente.

Consulte [Visitantes únicos](/help/components/metrics/unique-visitors.md) en la Guía del usuario de componentes para obtener más información sobre cómo calcula Adobe los visitantes únicos.

## Valor de duración

El valor de duración es una característica que requiere una implementación especializada adicional en ambas plataformas. Adobe recomienda trabajar con un consultor de implementación para obtener estos datos.

## Análisis de cohorte

El análisis de cohorte muestra la frecuencia con la que los mismos usuarios regresan al sitio.

Para crear una tabla de cohorte:

1. Haga clic en el icono Visualización de la izquierda y arrastre la visualización Tabla de cohorte al espacio de trabajo.
2. Haga clic en el icono Componentes de la izquierda y, a continuación, arrastre la métrica **Visitas** a los criterios de inclusión y de retorno.
3. Haga clic en Crear.

Consulte [Análisis de cohorte](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) en la guía del usuario de Analysis Workspace para obtener más información sobre las personalizaciones adicionales de la visualización de cohorte.

## Audiencias

El informe Audiencias en Google Analytics necesita la configuración de audiencias. Las audiencias también se deben configurar en Adobe a través de Adobe Audience Manager. Consulte la guía del usuario de Adobe Audience Manager para obtener más información.

## Explorador de usuarios

El informe Explorador de usuarios permite a un analista ver visitas individuales mediante identificadores anónimos. Adobe no muestra los identificadores backend fuera de las fuentes de datos, que son exportaciones de datos sin procesar en el nivel de visita.

* Si se necesitan estos datos en Analysis Workspace, se puede trabajar con un consultor de implementación para pasar el valor de cookie de identificador único anónimo a una eVar. Tenga en cuenta que esto solo funciona con implementaciones pequeñas que consistan en menos de 1 millón de visitantes únicos por mes.
* Si el usuario quiere incluir estos datos dentro de las fuentes de datos, las columnas concatenadas `visid_high` y `visid_low` son la forma más común de identificar visitantes únicos. Obtenga más información sobre las [Fuentes de datos](/help/export/analytics-data-feed/data-feed-overview.md) en la Guía del usuario de exportación.

## Informes demográficos y de intereses

Los datos demográficos y de intereses proporcionan información sobre la edad, el sexo y los intereses de los usuarios del sitio. Google recopila esos datos mediante sus capacidades de seguimiento entre sitios.

Adobe no recopila automáticamente los datos demográficos y de intereses. Sin embargo, si su organización obtiene estos datos, puede utilizar Atributos del cliente, una función de Adobe Experience Cloud Platform. Permite controlar la organización de los datos por atributos, y no se limita solo a la demografía o a los intereses.

Consulte la Ayuda sobre atributos del cliente para obtener más información.

## Geografía: Idioma

El informe geográfico de idioma muestra el tráfico del sitio según la configuración de idioma del explorador del visitante.

Para crear un informe de idioma:

1. En el menú Componentes, busque la dimensión **Idioma** y arrástrela hasta el área “Colocar una dimensión aquí” de la tabla de forma libre.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

Consulte la dimensión [Idioma](/help/components/dimensions/language.md) en la Guía del usuario de componentes para obtener más información.

## Geografía: Ubicación

El informe de ubicación geográfica proporciona una vista de mapa mundial, en el que se desglosan los datos por país.

Para crear un informe de ubicación geográfica:

1. Haga clic en el icono Visualizaciones de la izquierda y arrastre la visualización Mapa al espacio de trabajo sobre la tabla de forma libre vacía.
2. Haga clic en el icono Componentes de la izquierda y, a continuación, arrastre la métrica **Visitantes únicos** al espacio rotulado “Agregar métrica”.
3. Haga clic en Crear.

Si, además del mapa, también desea utilizar la tabla:

1. En el menú Componentes, busque la dimensión **Países** y arrástrela al área “Colocar una dimensión aquí” de la tabla de forma libre.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

Consulte las dimensiones [Países](/help/components/dimensions/countries.md) en la Guía del usuario de componentes para obtener más información.

## Comportamiento: Visitas nuevas y visitas recurrentes

El informe que compara las visitas nuevas con las recurrentes incluye información resumida sobre las primeras sesiones (visitas nuevas) frente a las sesiones subsiguientes (visitas recurrentes).

Para crear un informe de visitas nuevas y recurrentes:

1. En el menú de componentes, busque el segmento **Visitas por primera vez** y arrástrelo al área “Colocar una dimensión aquí” de la tabla de forma libre. Tenga en cuenta que **Visitas por primera vez** es un segmento, mientras que Workspace suele utilizar dimensiones para representar filas.
2. Busque el segmento **Visitas de retorno** y arrástrelo sobre el encabezado de fila Segmentos. Esto agrega el segmento como una dimensión debajo de Visitas por primera vez, lo que permite realizar una comparación sencilla.
3. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

Si también se desea un gráfico de líneas:

1. Haga clic en el icono de visualizaciones en la izquierda y arrastre una visualización Línea al espacio de trabajo sobre la tabla de forma libre
2. Utilice ctrl+clic (Windows) o cmd+clic (Mac) en cada fila de la tabla de forma libre para resaltarlos. Esto permite que ambas tendencias aparezcan en la visualización de líneas.
3. Haga clic en el pequeño punto coloreado en la esquina superior izquierda de la visualización de línea y, a continuación, haga clic en la casilla de verificación “Bloquear selección”.

## Comportamiento: frecuencia y actualización

El informe de frecuencia y actualización es aproximadamente igual a la dimensión **Número de visita** en Analysis Workspace.

1. En el menú de componentes, localice la dimensión **Número de visita** y arrástrela hasta el área “Colocar una dimensión aquí” de la tabla de forma libre.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

Consulte la dimensión [Número de visita](/help/components/dimensions/visit-number.md) en la Guía del usuario de componentes para obtener más información.

## Comportamiento: Participación

El informe de participación es aproximadamente igual a la dimensión **Tiempo empleado por visita: Agrupado**.

1. En el menú de componentes, busque la dimensión **Tiempo empleado por visita: Agrupado** y arrástrela al área “Colocar una dimensión aquí” de la tabla de forma libre.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

Consulte la dimensión [Tiempo empleado por visita](/help/components/dimensions/time-spent-per-visit.md) en la Guía del usuario de componentes para obtener más información.

## Tecnología: explorador y SO

Hay varias dimensiones principales disponibles en el informe Explorador y SO.

* La dimensión principal del **explorador** también está disponible en Analysis Workspace como dimensión.
* La dimensión principal del **sistema operativo** también está disponible en Analysis Workspace como dimensión.
* La dimensión principal de la **resolución de pantalla** está disponible en Analysis Workspace como la dimensión **Resolución del monitor**.
* La dimensión principal **Colores de pantalla** está disponible en Analysis Workspace como la dimensión **Profundidad de color**.
* La dimensión principal **Versión de Flash** no está disponible en Adobe Analytics, pero si se desea, una eVar puede recopilar estos datos.

1. En el menú de componentes, localice la dimensión deseada indicada arriba y arrástrela al área “Colocar una dimensión aquí” de la tabla de forma libre.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

Consulte las siguientes páginas en la Guía del usuario de componentes para obtener más información sobre sus dimensiones:

* [Explorador](/help/components/dimensions/browser.md)
* [Sistema operativo](/help/components/dimensions/operating-systems.md)
* [Resolución del monitor](/help/components/dimensions/monitor-resolution.md)
* [Profundidad de color](/help/components/dimensions/color-depth.md)

## Tecnología: Red

El informe de red es aproximadamente igual a la dimensión **Dominio**.

1. En el menú de componentes, busque la dimensión **Dominio** y arrástrela al área “Colocar una dimensión aquí” de la tabla de forma libre.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

Consulte la dimensión [Dominio](/help/components/dimensions/domain.md) en la Guía del usuario de componentes para obtener más información.

## Móvil: Información general

El informe de información general móvil es aproximadamente igual a la dimensión **Tipo de dispositivo móvil**. Tenga en cuenta que el valor “Otro” es equivalente al tráfico de escritorio.

1. En el menú de componentes, busque la dimensión **Tipo de dispositivo móvil** y arrástrela al área “Colocar una dimensión aquí” de la tabla de forma libre.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

Consulte la dimensión [Tipo de dispositivo móvil](/help/components/dimensions/mobile-dimensions.md) en la Guía del usuario de componentes para obtener más información.

## Móviles: Dispositivos

El informe de dispositivos móviles es prácticamente igual que la dimensión de **Dispositivos móviles**.

1. En el menú de componentes, busque la dimensión **Dispositivo móvil** y arrástrela hasta el área “Colocar una dimensión aquí” de la tabla de forma libre.
2. Arrastre las métricas deseadas al espacio de trabajo junto con la métrica **Ocurrencias** creada automáticamente. Consulte la [Guía de traducción de métricas](common-metrics.md) para saber cómo obtener cada métrica.

Consulte la dimensión [Dispositivo móvil](/help/components/dimensions/mobile-dimensions.md) en la Guía del usuario de componentes para obtener más información.

## Personalizado

Los informes personalizados se definen por implementación. Póngase en contacto con el administrador de Analytics de su organización o con el consultor de implementación para interpretar estos informes. Normalmente, una organización mantiene un [documento de diseño de la solución](/help/implement/prepare/solution-design.md) para realizar un seguimiento de los valores de las variables personalizadas y de cómo se rellenan.

## Prueba comparativa

Los informes de prueba comparativa permiten ver cómo se compara la información de los datos con los promedios del sector. Adobe no comparte datos de las pruebas comparativas con sus clientes en este momento.

## Flujo de usuarios

El informe de flujo está disponible en ambas plataformas. Para crear un informe de flujo:

1. Haga clic en el icono de visualizaciones de la izquierda y arrastre una visualización de flujo al espacio de trabajo sobre la tabla de forma libre
2. Busque la dimensión **Páginas** y, a continuación, haga clic en el icono de flecha para mostrar los valores de la página. Los elementos de dimensión aparecen en color amarillo.
3. Busque el valor de página deseado para comenzar y arrástrelo al espacio etiquetado como “Dimensión o elemento” en el centro
4. Este informe de flujo es interactivo. Haga clic en cualquiera de los valores para expandir los flujos a páginas posteriores o anteriores. Utilice el menú que aparece al hacer clic con el botón derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.
