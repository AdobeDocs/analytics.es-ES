---
title: Informes
description: Dimensiones y métricas que utiliza Informes y Analytics para cada informe.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '1863'
ht-degree: 1%

---


# Informes

Cada informe de Informes y Analytics utiliza una dimensión dedicada y una métrica predeterminada. Puede cambiar la métrica en cada informe y agregar desgloses si lo desea. Las siguientes listas proporcionan qué dimensión se utiliza en cada informe.

>[!NOTE]
>
>El menú de informes puede tener un aspecto diferente en función de las personalizaciones que haya realizado un administrador en su organización. See [Menu customizing](/help/admin/admin/customize-menus.md) in the Admin user guide.

## Métricas del sitio

Contiene informes que suelen generar tendencias mediante un intervalo de fechas. También contiene informes únicos, como los informes recomendados y los informes en tiempo real.

* Mis informes recomendados: Crea un panel que contiene varios informes breves para obtener perspectivas inmediatas.
* Métricas clave: Informe que permite realizar una tendencia de hasta cinco métricas a la vez. De forma predeterminada, [muestra tendencias de vistas](/help/components/metrics/page-views.md)de página, [visitas](/help/components/metrics/visits.md)y visitantes [](/help/components/metrics/unique-visitors.md) únicos.
* vistas de página: Tendencia de la métrica de vistas [de](/help/components/metrics/page-views.md) página con el paso del tiempo.
* Visitas: Tendencia de la métrica [Visitas](/help/components/metrics/visits.md) con el paso del tiempo.
* Visitantes: Tendencia de varias métricas de visitantes [](/help/components/metrics/unique-visitors.md) únicos con el paso del tiempo.
   * visitantes únicos: Cuenta visitantes sólo una vez para todo el intervalo de fechas seleccionado.
   * visitantes únicos por hora: Cuenta los visitantes varias veces si se visitan durante distintas horas del intervalo de fechas seleccionado.
   * visitantes únicos diarios: Cuenta los visitantes varias veces si se visitan durante diferentes días del intervalo de fechas seleccionado.
   * visitantes únicos semanales: Cuenta los visitantes varias veces si se visitan durante distintas semanas del intervalo de fechas seleccionado.
   * visitantes únicos mensuales: Cuenta los visitantes varias veces si se visitan durante diferentes meses del intervalo de fechas seleccionado.
   * visitantes únicos trimestrales: Cuenta visitantes varias veces si se visitan durante distintos trimestres del intervalo de fechas seleccionado. Los trimestres son de enero a marzo, de abril a junio, de julio a septiembre y de octubre a diciembre.
   * visitantes únicos anuales: Cuenta los visitantes varias veces si se visitan durante distintos años del intervalo de fechas seleccionado.
* Tiempo empleado por visita: Utiliza la dimensión [Tiempo empleado por visita - Agrupado](/help/components/dimensions/time-spent-per-visit.md) .
* Tiempo previo al evento: Utiliza la dimensión [Tiempo previo al evento](/help/components/dimensions/time-prior-to-event.md) .
* Compras: Contiene informes sobre métricas basadas en compras.
   * Canal de conversión de compra: Informe de [visitas](/help/components/metrics/visits.md), [carros](/help/components/metrics/carts.md), [pedidos](/help/components/metrics/orders.md), [ingresos](/help/components/metrics/revenue.md)y [unidades](/help/components/metrics/units.md) en un informe de canal. Se logra una visualización similar en Analysis Workspace mediante la visualización [Visitas en el orden previsto](../analysis-workspace/visualizations/fallout/fallout-flow.md).
   * Ingresos: Tendencia de la métrica [Ingresos](/help/components/metrics/revenue.md) con el paso del tiempo.
   * Pedidos: Tendencia de la métrica [Pedidos](/help/components/metrics/orders.md) con el paso del tiempo.
   * Unidades: Tendencia de las [unidades](/help/components/metrics/units.md) de métrica a lo largo del tiempo.
* Carro de compras: Contiene informes sobre las métricas del carro de compras.
   * Canal de conversión del carro de compras: Informes [Instancias](/help/components/metrics/instances.md), [Carros](/help/components/metrics/carts.md), [Cierres de compra](/help/components/metrics/checkouts.md), [Pedidos](/help/components/metrics/orders.md)e [Ingresos](/help/components/metrics/revenue.md) en un informe de canal.
   * Carros de compras: Tendencia de la métrica [Carros](/help/components/metrics/carts.md) de compras con el paso del tiempo.
   * vistas del carro de compras: Tendencia de las vistas [del](/help/components/metrics/cart-views.md) carro de compras con el paso del tiempo.
   * Adiciones al carro de compras: Tendencia de las adiciones [al](/help/components/metrics/cart-additions.md) carro de compras con el paso del tiempo.
   * Eliminaciones del carro de compras: Enumera las tendencias de las eliminaciones [del](/help/components/metrics/cart-removals.md) carro de compras con el paso del tiempo.
   * Cierres de compras: Tendencia de las métricas [Cierres de compras](/help/components/metrics/checkouts.md) con el paso del tiempo.
* eventos personalizados: Contiene todos los informes relacionados con [Eventos](/help/components/metrics/custom-events.md) personalizados específicos de la implementación.
* Bots: Muestra informes relacionados con bots.
   * Bots: Muestra los bots que más frecuentan el sitio. See [Bot rules](../../admin/admin/bot-removal/bot-rules.md) in the Admin user guide.
   * Páginas de bots: Muestra las páginas más visitadas por los bots.
* Tiempo real: Muestra determinadas dimensiones y métricas en segundos después de la recopilación de datos. See [Real-time reports](/help/components/c-real-time-reporting/realtime.md) for more information.

## Contenido del sitio

Contiene informes en torno a dimensiones que generalmente muestran el contenido del sitio. Puede aplicar clasificaciones a algunos de estos informes. Aplicar clasificaciones significa que un informe se convierte en un menú que contiene el informe de origen y los informes de clasificación.

* Páginas: Utiliza la dimensión [Página](/help/components/dimensions/page.md) .
* Sección del sitio: Utiliza la dimensión de sección [](/help/components/dimensions/site-section.md) Sitio.
* Servidores: Utiliza la dimensión [Servidor](/help/components/dimensions/server.md) .
* Vínculos: Contiene informes que utilizan el seguimiento de vínculos.
   * Vínculos de salida: Utiliza la dimensión [Vínculo](/help/components/dimensions/exit-link.md) de salida.
   * Descargas de archivos: Utiliza la dimensión [Descargar vínculo](/help/components/dimensions/download-link.md) .
   * Vínculos personalizados: Utiliza la dimensión Vínculo [](/help/components/dimensions/custom-link.md) personalizado.
   * Páginas no encontradas: Utiliza la dimensión [Páginas no encontradas](/help/components/dimensions/pages-not-found.md) .

## Mobile

Contiene informes sobre informes móviles heredados. Estos informes basan sus datos en la cadena del agente de usuario. Para sus informes respectivos, utilizan varias dimensiones [](/help/components/dimensions/mobile-dimensions.md) móviles.

* Dispositivos: Utiliza la dimensión de dispositivo [](/help/components/dimensions/mobile-dimensions.md) móvil.
* Tipo de dispositivo: Utiliza la dimensión de tipo [de dispositivo](/help/components/dimensions/mobile-dimensions.md) móvil.
* Fabricante: Utiliza la dimensión de fabricante [de](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Tamaño de la pantalla: Utiliza la dimensión de tamaño [de la pantalla](/help/components/dimensions/mobile-dimensions.md) Móvil.
* Altura de la pantalla: Utiliza la dimensión de altura [de la pantalla](/help/components/dimensions/mobile-dimensions.md) Móvil.
* Ancho de la pantalla: Utiliza la dimensión de anchura [de pantalla](/help/components/dimensions/mobile-dimensions.md) móvil.
* Compatibilidad con cookies: Utiliza la dimensión de compatibilidad con [cookies](/help/components/dimensions/mobile-dimensions.md) móviles.
* Compatibilidad con imágenes: Utiliza la dimensión de compatibilidad con [imágenes](/help/components/dimensions/mobile-dimensions.md) móviles.
* Profundidad de color: Utiliza la dimensión Profundidad [de color de](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Compatibilidad con audio: Utiliza la dimensión de compatibilidad con [audio de](/help/components/dimensions/mobile-dimensions.md) Mobile.
* Compatibilidad con vídeo: Utiliza la dimensión de compatibilidad [con vídeo](/help/components/dimensions/mobile-dimensions.md) móvil.
* Sistema operativo (desaprobado): Utiliza la dimensión Sistema operativo [móvil (obsoleto)](/help/components/dimensions/mobile-dimensions.md) .

## Rutas

Contiene informes que le permiten ver los datos de rutas de los visitantes.

* Flujo de página siguiente: Utiliza un informe de flujo en el elemento de dimensión de página principal. Las vistas de ruta son similares a [las instancias](/help/components/metrics/instances.md). Puede cambiar el elemento de dimensión del informe. Un informe similar en Analysis Workspace está disponible mediante una visualización [de flujo](../analysis-workspace/visualizations/c-flow/flow.md).
* Página siguiente: Toma el elemento de dimensión de página principal y muestra las páginas siguientes a las que fueron los visitantes.
* Flujo de página anterior: Utiliza un informe de flujo en el elemento de dimensión de página principal Un informe similar en Analysis Workspace está disponible mediante una visualización [de flujo](../analysis-workspace/visualizations/c-flow/flow.md).
* Página anterior: Toma el elemento de dimensión de página principal y muestra los visitantes de páginas anteriores.
* Visitas en el orden previsto: Permite seleccionar elementos de dimensión de página en los pasos y muestra la proporción de personas que siguieron y no siguieron esa ruta. Un informe similar en Analysis Workspace está disponible mediante una visualización [de visitas en el orden previsto](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Rutas completas: Muestra rutas individuales como elementos de dimensión. Retirada en Analysis Workspace; utilice la visualización [Flujo](../analysis-workspace/visualizations/c-flow/flow.md) en su lugar.
* PathFinder: Proporciona varios tipos de informes que permiten analizar las rutas (retiradas en Analysis Workspace).
* Longitud de ruta: Utiliza la dimensión de profundidad [de la](/help/components/dimensions/visit-depth.md) visita.
* Análisis de página
   * Resumen de página: Toma el elemento de dimensión de página principal y muestra una vista de tendencias. También muestra los puntos de entrada, las páginas anteriores, los puntos de salida y las páginas siguientes para ese elemento de dimensión de página principal.
   * Recargas: Utiliza la dimensión [Página](/help/components/dimensions/page.md) con la métrica [Recargas](/help/components/metrics/reloads.md) .
   * Tiempo empleado en la página: Utiliza la dimensión [Tiempo empleado en la página - agrupado](/help/components/dimensions/time-spent-on-page.md) .
   * Clics hasta la página: Toma el elemento de dimensión de página principal y muestra la cantidad de clics que se necesitaron para llegar a esa página en una visita determinada.
* Entradas y salidas
   * Páginas de entrada: Utiliza la dimensión [Páginas](/help/components/dimensions/entry-dimensions.md) de entrada.
   * Páginas de entrada originales: Utiliza la dimensión original [de la página](/help/components/dimensions/entry-dimensions.md) Entrada.
   * Visitas a una sola página: Utiliza la dimensión [Página](/help/components/dimensions/page.md) con el segmento &#39;Visitas a una sola página&#39; proporcionado por Adobe aplicado.
   * Páginas de salida: Utiliza la dimensión [Páginas](/help/components/dimensions/exit-dimensions.md) de salida.

>[!NOTE]
>
>En esta carpeta pueden aparecer otros informes. Son otras dimensiones, como las props, en las que tiene habilitadas [las](../../admin/admin/c-traffic-variables/traffic-var.md) rutas en la configuración del grupo de informes.

## Fuentes de tráfico

Contiene un informe que proporciona una perspectiva de dónde provienen los visitantes antes de llegar al sitio. Estos informes no funcionan correctamente a menos que establezca correctamente los filtros [de URL](../../admin/admin/internal-url-filter-admin.md) internas en la configuración del grupo de informes.

* Palabras clave de búsqueda: todas: Utiliza la dimensión de palabra clave [de](/help/components/dimensions/search-keyword.md) búsqueda.
* Palabras clave de búsqueda: paga: Utiliza la dimensión Palabra clave de [búsqueda: paga](/help/components/dimensions/search-keyword.md) .
* Palabras clave de búsqueda: natural: Utiliza la palabra clave [Buscar: dimensión natural](/help/components/dimensions/search-keyword.md)
* Motores de búsqueda: todos: Utiliza la dimensión [Motor](/help/components/dimensions/search-engine.md) de búsqueda.
* Motores de búsqueda: pago: Utiliza la dimensión Motor [de búsqueda - pago](/help/components/dimensions/search-engine.md) .
* Motores de búsqueda: natural: Utiliza la dimensión natural [del motor de](/help/components/dimensions/search-engine.md) búsqueda.
* Clasificación de todas las páginas de búsqueda: Utiliza la dimensión Clasificación [de página de búsqueda](/help/components/dimensions/all-search-page-rank.md) Todas.
* Dominios de referencia: Utiliza la dimensión de dominio [de](/help/components/dimensions/referring-domain.md) referencia
* Dominios de referencia originales: Utiliza la dimensión de dominio [de referencia](/help/components/dimensions/original-referring-domain.md) original
* Remitentes del reenvío: Utiliza la dimensión de [Remitente del reenvío](/help/components/dimensions/referrer.md) .
* Tipos de Remitente del reenvío: Utiliza la dimensión de tipo [de](/help/components/dimensions/referrer-type.md) Remitente del reenvío.

## Campañas

Contiene informes principalmente alrededor de la dimensión de código [de](/help/components/dimensions/tracking-code.md) seguimiento.

* Canal de conversión de Campañas: Informa de pulsaciones, [cierres](/help/components/metrics/checkouts.md)de compra, [pedidos](/help/components/metrics/orders.md)e [ingresos](/help/components/metrics/revenue.md) en un informe de canal. La métrica Pulsaciones es similar a la métrica [Instancias](/help/components/metrics/instances.md) en el contexto de la dimensión Código [de](/help/components/dimensions/tracking-code.md) seguimiento. Se logra una visualización similar en Analysis Workspace mediante la visualización [Visitas en el orden previsto](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Código de seguimiento: Utiliza la dimensión de código [de](/help/components/dimensions/tracking-code.md) seguimiento.

## Productos

Contiene informes principalmente alrededor de la dimensión [Producto](/help/components/dimensions/product.md) .

* Canal de conversión de productos: Informes vistas [](/help/components/metrics/product-views.md)del producto, adiciones [al](/help/components/metrics/cart-additions.md)carro de compras, cierres de [compra](/help/components/metrics/checkouts.md), [pedidos](/help/components/metrics/orders.md), [unidades](/help/components/metrics/units.md)[](/help/components/metrics/revenue.md) e ingresosen un informe de canal. Se logra una visualización similar en Analysis Workspace mediante la visualización [Visitas en el orden previsto](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Productos: Utiliza la dimensión [Productos](/help/components/dimensions/product.md) .
* Venta cruzada: Muestra los productos comúnmente vendidos juntos (retirados en Analysis Workspace).
* Categorías: Utiliza la dimensión de [Categoría](/help/components/dimensions/category.md) .

## Retención de visitantes

Contiene informes sobre visitantes que regresan al sitio.

* Frecuencia de retorno: Utiliza la dimensión [Frecuencia](/help/components/dimensions/return-frequency.md) de retorno.
* Visitas de retorno: Tendencia de la métrica [Visitas](/help/components/metrics/visits.md) con el paso del tiempo con el segmento &#39;Visitas de retorno&#39; proporcionado por Adobe aplicado.
* Número de visita: Utiliza la dimensión de número [de](/help/components/dimensions/visit-number.md) visita.
* Ciclo de ventas: Carpeta para informes relacionados con las compras.
   * Lealtad del cliente: Utiliza la dimensión de lealtad [del](/help/components/dimensions/customer-loyalty.md) cliente.
   * Días antes de la primera compra: Utiliza la dimensión [Días antes de la primera compra](/help/components/dimensions/days-before-first-purchase.md) .
   * Días transcurridos desde la última compra: Utiliza la dimensión [Días desde la última compra](/help/components/dimensions/days-since-last-purchase.md) .
   * Clientes únicos diarios: Enumera los visitantes [únicos](/help/components/metrics/unique-visitors.md) diarios con el paso del tiempo con el segmento &quot;compradores&quot; proporcionado por Adobe aplicado.
   * Clientes únicos semanales: Tendencia de visitantes [únicos](/help/components/metrics/unique-visitors.md) semanales con el paso del tiempo con el segmento &#39;compradores&#39; proporcionado por Adobe aplicado.
   * Clientes únicos mensuales: Tendencia de visitantes [únicos](/help/components/metrics/unique-visitors.md) mensuales a lo largo del tiempo con el segmento de &#39;compradores&#39; proporcionado por Adobe aplicado.
   * Clientes únicos trimestrales: Tendencias de visitantes [únicos](/help/components/metrics/unique-visitors.md) trimestrales con el paso del tiempo con el segmento &#39;compradores&#39; proporcionado por Adobe aplicado. Los trimestres son de enero a marzo, de abril a junio, de julio a septiembre y de octubre a diciembre.
   * Clientes únicos anuales: Tendencia de visitantes [únicos](/help/components/metrics/unique-visitors.md) anuales con el paso del tiempo con el segmento &#39;compradores&#39; proporcionado por Adobe aplicado.

## Perfil del visitante

Contiene informes sobre quién visita el sitio.

* Segmentación geográfica: Informes sobre de dónde provienen las visitas al sitio en todo el mundo.
   * Países: Utiliza la dimensión [Países](/help/components/dimensions/countries.md) .
   * Región: Utiliza la dimensión [Regiones](/help/components/dimensions/regions.md) .
   * Ciudades: Utiliza la dimensión [Ciudades](/help/components/dimensions/cities.md) .
   * Estados Unidos: Utiliza la dimensión Estados [](/help/components/dimensions/us-states.md) estadounidenses.
   * DMA de EE. UU.: Utiliza la dimensión DMA [de](/help/components/dimensions/us-dma.md) EE.UU.
* Idiomas: Utiliza la dimensión [Idioma](/help/components/dimensions/language.md) .
* Husos horarios: Utiliza la dimensión de zona horaria (se retira en Analysis Workspace). Los elementos de dimensión son el desplazamiento GMT de la visita.
* Dominio: Utiliza la dimensión [Dominio](/help/components/dimensions/domain.md) .
* Dominio de nivel superior: Utiliza la dimensión de dominio de nivel superior (se retira en Analysis Workspace). Agrupa la dimensión de [dominios](/help/components/dimensions/domain.md) en categorías de nivel superior, generalmente por país del dominio.
* Tecnología: Carpeta que contiene informes sobre lo que el visitante utilizó para acceder al sitio.
   * Exploradores: Utiliza la dimensión [Exploradores](/help/components/dimensions/browser.md) .
   * Tipo de explorador: Utiliza la dimensión de tipo [de](/help/components/dimensions/browser-type.md) navegador.
   * Ancho del explorador: Utiliza la dimensión de anchura del [explorador agrupada](/help/components/dimensions/browser-width.md) .
   * Altura del explorador: Utiliza la dimensión de altura del [explorador agrupada](/help/components/dimensions/browser-height.md) .
   * Sistema operativo: Utiliza la dimensión [Sistemas](/help/components/dimensions/operating-systems.md) operativos.
   * Tipo de sistema operativo: Utiliza la dimensión Tipos [de sistemas](/help/components/dimensions/operating-system-types.md) operativos.
   * Profundidad de color del monitor: Utiliza la dimensión [Profundidad](/help/components/dimensions/color-depth.md) de color.
   * Resolución del monitor: Utiliza la dimensión de resolución [del](/help/components/dimensions/monitor-resolution.md) monitor.
   * Java: Utiliza la dimensión habilitada [para](/help/components/dimensions/java-enabled.md) Java.
   * JavaScript: Utiliza la dimensión habilitada para JavaScript (retirada en Analysis Workspace). Los elementos de dimensión son &#39;Habilitado&#39;, &#39;Deshabilitado&#39; o &#39;Desconocido&#39;, según si el explorador tiene JavaScript habilitado.
   * Versión de JavaScript: utiliza la dimensión de versión de JavaScript (se retira en Analysis Workspace). Los elementos de dimensión muestran la versión de JavaScript que utiliza el explorador.
   * Cookies: Utiliza la dimensión de compatibilidad [con](/help/components/dimensions/cookie-support.md) cookies.
   * Tipos de conexión: Utiliza la dimensión [de tipo](/help/components/dimensions/connection-type.md) de conexión.
   * Operador de telefonía móvil: Utiliza la dimensión [Portadora](/help/components/dimensions/mobile-dimensions.md) móvil.
* Estado del Visitante: Utiliza la dimensión Estado (jubilado en Analysis Workspace). Los elementos de dimensión se originan en la [`state`](../../implement/vars/page-vars/state.md) variable.
* Código postal del Visitante: Utiliza la dimensión [Código](/help/components/dimensions/zip-code.md) postal.

## Conversión personalizada

Contiene informes específicos de la implementación. Los informes de conversión personalizados utilizan [eVars](/help/components/dimensions/evar.md) como dimensión.

## Tráfico personalizado

Contiene informes específicos de la implementación. Los informes de tráfico personalizados utilizan [props](/help/components/dimensions/prop.md) como dimensión.

## Canales de marketing

Contiene informes que involucran canales [de marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

* Informe de descripción general de Canal: Informe personalizado específico de Informes y Analytics. Utiliza canales de marketing como elementos de dimensión, con métricas que utilizan atribución de primer o último toque.
* canal de primer toque: Utiliza la dimensión de canal [de](/help/components/dimensions/first-touch-channel.md) primer toque.
* Detalles del canal de primer toque: Utiliza la dimensión de detalles [del canal de](/help/components/dimensions/first-touch-detail.md) primer toque.
* canal de último toque: Utiliza la dimensión de canal [de](/help/components/dimensions/last-touch-channel.md) último toque.
* Detalles del canal de último toque: Utiliza la dimensión de detalle [del canal de](/help/components/dimensions/last-touch-detail.md) último toque.

## Marcadores

Contiene los informes que ha marcado. See [Bookmarks](bookmarks.md) for more information.

## Tableros

Contiene paneles que ha creado. See [Dashboards](dashboard.md) for more information.

## Objetivos 

Contiene destinatarios que ha creado. See [Targets](targets.md) for more information.

>[!NOTE]
>
>Si no encuentra el informe en esta página de ayuda, es posible que el administrador haya cambiado el nombre de las carpetas o las haya ajustado. See [Menu customizing](/help/admin/admin/customize-menus.md) in the Admin user guide.
