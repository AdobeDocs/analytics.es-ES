---
title: Informes
description: Dimensiones y métricas que utiliza Reports & Analytics para cada informe.
feature: Informes Conceptos básicos y conceptos básicos de Analytics
role: Business Practitioner, Administrator
exl-id: e3c23d17-fc4b-479e-9c48-6f27ef0de4e3
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '1868'
ht-degree: 99%

---

# Informes

Cada informe de Reports &amp; Analytics utiliza una dimensión dedicada y una métrica predeterminada. Puede cambiar la métrica en cada informe y agregar desgloses si lo desea. Las siguientes listas indican qué dimensión se utiliza en cada informe.

>[!NOTE]
>
>El menú de informes puede tener un aspecto diferente en función de las personalizaciones que haya realizado un administrador en su organización. Consulte [Personalización de menús](/help/admin/admin/customize-menus.md) en la guía de usuario de administración.

## Métricas del sitio

Contiene informes que suelen generar tendencias mediante un intervalo de fechas. También contiene informes únicos, como los informes recomendados y los informes en tiempo real.

* Mis informes recomendados: Crea un panel que contiene varios informes breves para obtener datos inmediatamente.
* Métricas clave: Informe que permite realizar una tendencia de hasta cinco métricas a la vez. Puede obtener las tendencias de [Vistas de página](/help/components/metrics/page-views.md), [Visitas](/help/components/metrics/visits.md) y [Visitantes únicos](/help/components/metrics/unique-visitors.md).
* Vistas de página: Obtiene la tendencia de la métrica [Vistas de página](/help/components/metrics/page-views.md) a lo largo del tiempo.
* Visitas: Obtiene la tendencia de la métrica [Visitas](/help/components/metrics/visits.md) a lo largo del tiempo.
* Visitantes: Obtiene la tendencia de varias métricas de [visitantes únicos](/help/components/metrics/unique-visitors.md) a lo largo del tiempo.
   * Visitantes únicos: Cuenta visitantes solo una vez para todo el intervalo de fechas seleccionado.
   * Visitantes únicos por hora: Cuenta los visitantes varias veces si visitan durante distintas horas del intervalo de fechas seleccionado.
   * Visitantes únicos diarios: Cuenta los visitantes varias veces si visitan durante diferentes días del intervalo de fechas seleccionado.
   * Visitantes únicos semanales: Cuenta los visitantes varias veces si visitan durante distintas semanas del intervalo de fechas seleccionado.
   * Visitantes únicos mensuales: Cuenta los visitantes varias veces si visitan durante diferentes meses del intervalo de fechas seleccionado.
   * Visitantes únicos trimestrales: Cuenta visitantes varias veces si visitan durante distintos trimestres del intervalo de fechas seleccionado. Los trimestres son de enero a marzo, de abril a junio, de julio a septiembre y de octubre a diciembre.
   * Visitantes únicos anuales: Cuenta los visitantes varias veces si visitan durante distintos años del intervalo de fechas seleccionado.
* Tiempo empleado por visita: Utiliza la dimensión [Tiempo empleado por visita: Agrupado](/help/components/dimensions/time-spent-per-visit.md).
* Tiempo previo al evento: Utiliza la dimensión [Tiempo previo al evento](/help/components/dimensions/time-prior-to-event.md).
* Compras: Contiene informes sobre métricas basadas en compras.
   * Canal de conversión de compra: Informe de [Visitas](/help/components/metrics/visits.md), [Carros de compras](/help/components/metrics/carts.md), [Pedidos](/help/components/metrics/orders.md), [Ingresos](/help/components/metrics/revenue.md) y [Unidades](/help/components/metrics/units.md) en un informe de canal. Se logra una visualización similar en Analysis Workspace mediante la [Visualización de abandonos](../analysis-workspace/visualizations/fallout/fallout-flow.md).
   * Ingresos: Obtiene la tendencia de la métrica [Ingresos](/help/components/metrics/revenue.md) a lo largo del tiempo.
   * Pedidos: Obtiene la tendencia de la métrica [Pedidos](/help/components/metrics/orders.md) a lo largo del tiempo.
   * Unidades: Obtiene la tendencia de [Unidades](/help/components/metrics/units.md) a lo largo del tiempo.
* Carro de compras: Contiene informes sobre las métricas del carro de compras.
   * Canal de conversión del carro de compras: Crea un informe de canal de las métricas [Instancias](/help/components/metrics/instances.md), [Carros de compras](/help/components/metrics/carts.md), [Cierres de compra](/help/components/metrics/checkouts.md), [Pedidos](/help/components/metrics/orders.md) e [Ingresos](/help/components/metrics/revenue.md).
   * Carros de compras: Obtiene la tendencia de la métrica [Carros de compras](/help/components/metrics/carts.md) a lo largo del tiempo.
   * Vistas del carro de compras: Obtiene la tendencia de la métrica [Vistas del carro de compras](/help/components/metrics/cart-views.md) a lo largo del tiempo.
   * Añadidos al carro de compras: Obtiene la tendencia de la métrica [Añadidos al carro de compras](/help/components/metrics/cart-additions.md) a lo largo del tiempo.
   * Eliminaciones del carro de compras: Obtiene la tendencia de la métrica [Eliminaciones del carro de compras](/help/components/metrics/cart-removals.md) a lo largo del tiempo.
   * Cierres de compras: Obtiene la tendencia de la métrica [Cierres de compras](/help/components/metrics/checkouts.md) a lo largo del tiempo.
* Eventos personalizados: Contiene todos los informes relacionados con [Eventos](/help/components/metrics/custom-events.md) personalizados específicos de su implementación.
* Bots: Muestra informes relacionados con bots.
   * Bots: Muestra los bots que más frecuentan el sitio. Consulte [Reglas de bots](../../admin/admin/bot-removal/bot-rules.md) en la guía de usuario de administración.
   * Páginas de bots: Muestra las páginas más visitadas por los bots.
* Tiempo real: Muestra determinadas dimensiones y métricas segundos después de su recopilación de datos. Consulte [Informes en tiempo real](/help/components/c-real-time-reporting/realtime.md) para obtener más información.

## Contenido del sitio

Contiene informes sobre dimensiones que generalmente muestran el contenido del sitio. Puede aplicar clasificaciones a algunos de estos informes. Aplicar clasificaciones significa que un informe se convierte en un menú que contiene el informe de origen y los informes de clasificación.

* Páginas: Utiliza la dimensión [Página](/help/components/dimensions/page.md).
* Sección del sitio: Utiliza la dimensión [Sección del sitio](/help/components/dimensions/site-section.md).
* Servidores: Utiliza la dimensión [Servidor](/help/components/dimensions/server.md).
* Vínculos: Contiene informes que utilizan el seguimiento de vínculos.
   * Vínculos de salida: Utiliza la dimensión [Vínculo de salida](/help/components/dimensions/exit-link.md).
   * Descargas de archivos: Utiliza la dimensión [Vínculo de descarga](/help/components/dimensions/download-link.md).
   * Vínculos personalizados: Utiliza la dimensión [Vínculo personalizado](/help/components/dimensions/custom-link.md).
   * Páginas no encontradas: Utiliza la dimensión [Páginas no encontradas](/help/components/dimensions/pages-not-found.md).

## Mobile

Contiene informes sobre informes móviles heredados. Estos informes basan sus datos en la cadena del agente de usuario. Para sus informes respectivos, utilizan varias [dimensiones móviles](/help/components/dimensions/mobile-dimensions.md).

* Dispositivos: Utiliza la dimensión [Dispositivo móvil](/help/components/dimensions/mobile-dimensions.md).
* Tipo de dispositivo: Utiliza la dimensión [Tipo de dispositivo móvil](/help/components/dimensions/mobile-dimensions.md).
* Fabricante: Utiliza la dimensión [Fabricante del dispositivo móvil](/help/components/dimensions/mobile-dimensions.md).
* Tamaño de la pantalla: Utiliza la dimensión [Tamaño de la pantalla del dispositivo móvil](/help/components/dimensions/mobile-dimensions.md).
* Altura de la pantalla: Utiliza la dimensión [Altura de la pantalla del dispositivo móvil](/help/components/dimensions/mobile-dimensions.md).
* Anchura de la pantalla: Utiliza la dimensión [Anchura de la pantalla del dispositivo móvil](/help/components/dimensions/mobile-dimensions.md).
* Compatibilidad con cookies: Utiliza la dimensión [Compatibilidad con cookies móviles](/help/components/dimensions/mobile-dimensions.md).
* Compatibilidad con imágenes: Utiliza la dimensión [Compatibilidad con imágenes móviles](/help/components/dimensions/mobile-dimensions.md).
* Profundidad de color: Utiliza la dimensión [Profundidad de color del dispositivo móvil](/help/components/dimensions/mobile-dimensions.md).
* Compatibilidad con audio: Utiliza la dimensión [Compatibilidad con audio del dispositivo móvil](/help/components/dimensions/mobile-dimensions.md).
* Compatibilidad con vídeo: Utiliza la dimensión [Compatibilidad con vídeo del dispositivo móvil](/help/components/dimensions/mobile-dimensions.md).
* Sistema operativo (obsoleto): Utiliza la dimensión [Sistema operativo del dispositivo móvil (obsoleto)](/help/components/dimensions/mobile-dimensions.md).

## Rutas

Contiene informes que le permiten ver los datos de rutas de los visitantes.

* Flujo de página siguiente: Utiliza un informe de flujo en el elemento de dimensión de página superior. Las vistas de ruta son similares a las [instancias](/help/components/metrics/instances.md). Puede cambiar el elemento de dimensión del informe. Un informe similar en Analysis Workspace está disponible mediante una [visualización de flujo](../analysis-workspace/visualizations/c-flow/flow.md).
* Página siguiente: Toma el elemento de dimensión de página principal y muestra las páginas siguientes a las que se dirigieron los visitantes.
* Flujo de página anterior: Utiliza un informe de flujo en el elemento de dimensión de la página principal Un informe similar en Analysis Workspace está disponible mediante una [visualización de flujo](../analysis-workspace/visualizations/c-flow/flow.md).
* Página anterior: Toma el elemento de dimensión de la página principal y muestra las páginas de las que proceden los visitantes.
* Abandonos: Permite seleccionar elementos de dimensión de página por pasos y muestra la proporción de personas que siguieron esa ruta y las que la abandonaron. Un informe similar en Analysis Workspace está disponible mediante una [visualización de abandonos](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Rutas completas: Muestra rutas individuales como elementos de dimensión. Se ha eliminado en Analysis Workspace; utilice la [Visualización de flujo](../analysis-workspace/visualizations/c-flow/flow.md) en su lugar.
* PathFinder: Proporciona varios tipos de informes que permiten analizar las rutas (se ha eliminado en Analysis Workspace).
* Longitud de ruta: Utiliza la dimensión de [profundidad de la visita](/help/components/dimensions/visit-depth.md).
* Análisis de página
   * Resumen de página: Toma el elemento de dimensión de página superior y muestra una vista de tendencias. También muestra los puntos de entrada, las páginas anteriores, los puntos de salida y las páginas siguientes para ese elemento de dimensión de página principal.
   * Recargas: Utiliza la dimensión [Página](/help/components/dimensions/page.md) con la métrica [Recargas](/help/components/metrics/reloads.md).
   * Tiempo empleado en la página: Utiliza la dimensión [Tiempo empleado en la página: agrupado](/help/components/dimensions/time-spent-on-page.md).
   * Clics hasta la página: Toma el elemento de dimensión de página principal y muestra el número de clics que se necesitaron para llegar a esa página en una visita determinada.
* Entradas y salidas
   * Páginas de entrada: Utiliza la dimensión [Páginas de entrada](/help/components/dimensions/entry-dimensions.md).
   * Páginas de entrada originales: Utiliza la dimensión [Página de entrada original](/help/components/dimensions/entry-dimensions.md).
   * Visitas a una sola página: Utiliza la dimensión [Página](/help/components/dimensions/page.md) con el segmento “Visitas a una sola página” de Adobe aplicado.
   * Páginas de salida: Utiliza la dimensión [Páginas de salida](/help/components/dimensions/exit-dimensions.md).

>[!NOTE]
>
>En esta carpeta pueden aparecer otros informes. Son otras dimensiones, como las propiedades (props), en las que tiene [habilitadas las rutas](../../admin/admin/c-traffic-variables/traffic-var.md) en la configuración del grupo de informes.

## Fuentes de tráfico

Contiene un informe que proporciona una perspectiva de desde dónde proceden los visitantes antes de llegar al sitio. Estos informes no funcionarán de forma adecuada a menos que establezca correctamente los [filtros de URL internas](../../admin/admin/internal-url-filter-admin.md) en la configuración del grupo de informes.

* Palabras clave de búsqueda - todas: Utiliza la dimensión [Palabra clave de búsqueda](/help/components/dimensions/search-keyword.md).
* Palabras clave de búsqueda - de pago: Utiliza la dimensión [Palabra clave de búsqueda: de pago](/help/components/dimensions/search-keyword.md).
* Palabras clave de búsqueda - natural: Utiliza la dimensión [Palabra clave de búsqueda: natural](/help/components/dimensions/search-keyword.md)
* Motores de búsqueda - todos: Utiliza la dimensión [Motor de búsqueda](/help/components/dimensions/search-engine.md).
* Motores de búsqueda - de pago: Utiliza la dimensión [Motor de búsqueda: de pago](/help/components/dimensions/search-engine.md).
* Motores de búsqueda - natural: Utiliza la dimensión [Motor de búsqueda: natural](/help/components/dimensions/search-engine.md).
* Clasificación de todas las páginas de búsqueda: Utiliza la dimensión [Todas las clasificaciones de páginas de búsqueda](/help/components/dimensions/all-search-page-rank.md).
* Dominios de referencia: Utiliza la dimensión [Dominio de referencia](/help/components/dimensions/referring-domain.md)
* Dominios de referencia originales: Utiliza la dimensión [Dominio de referencia original](/help/components/dimensions/original-referring-domain.md)
* Remitentes del reenvío: Utiliza la dimensión [Remitente del reenvío](/help/components/dimensions/referrer.md).
* Tipos de remitente del reenvío: Utiliza la dimensión [Tipo de remitente del reenvío](/help/components/dimensions/referrer-type.md).

## Campañas

Contiene informes principalmente alrededor de la dimensión [Código de seguimiento](/help/components/dimensions/tracking-code.md).

* Canal de conversión de Campañas: Informa de clics, [cierres de compra](/help/components/metrics/checkouts.md), [pedidos](/help/components/metrics/orders.md) e [ingresos](/help/components/metrics/revenue.md) en un informe de canal. La métrica de clics es similar a la métrica [Instancias](/help/components/metrics/instances.md) en el contexto de la dimensión [Código de seguimiento](/help/components/dimensions/tracking-code.md). Se logra una visualización similar en Analysis Workspace mediante la [Visualización de abandonos](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Código de seguimiento: Utiliza la dimensión [Código de seguimiento](/help/components/dimensions/tracking-code.md).

## Productos

Contiene informes principalmente sobre la dimensión [Producto](/help/components/dimensions/product.md).

* Canal de conversión de productos: Crea informes sobre [Vistas del producto](/help/components/metrics/product-views.md), [Adiciones al carro de compras](/help/components/metrics/cart-additions.md), [Cierres de compras](/help/components/metrics/checkouts.md), [Pedidos](/help/components/metrics/orders.md), [Unidades](/help/components/metrics/units.md) e [Ingresos](/help/components/metrics/revenue.md) en un informe de canal. Se logra una visualización similar en Analysis Workspace mediante la [Visualización de abandonos](../analysis-workspace/visualizations/fallout/fallout-flow.md).
* Productos: Utiliza la dimensión [Productos](/help/components/dimensions/product.md).
* Venta cruzada: Muestra los productos comúnmente vendidos juntos (se ha eliminado en Analysis Workspace).
* Categorías: Utiliza la dimensión [Categoría](/help/components/dimensions/category.md).

## Retención de visitantes

Contiene informes sobre visitantes que regresan al sitio.

* Frecuencia de retorno: Utiliza la dimensión [Frecuencia de retorno](/help/components/dimensions/return-frequency.md).
* Visitas de retorno: Obtiene la tendencia de la métrica [Visitas](/help/components/metrics/visits.md) a lo largo del tiempo con el segmento “Visitas recurrentes” de Adobe aplicado.
* Número de visita: Utiliza la dimensión [Número de visita](/help/components/dimensions/visit-number.md).
* Ciclo de ventas: Carpeta para informes relacionados con las compras.
   * Lealtad del cliente: Utiliza la dimensión [Lealtad del cliente](/help/components/dimensions/customer-loyalty.md).
   * Días antes de la primera compra: Utiliza la dimensión [Días antes de la primera compra](/help/components/dimensions/days-before-first-purchase.md).
   * Días desde la última compra: Utiliza la dimensión [Días desde la última compra](/help/components/dimensions/days-since-last-purchase.md).
   * Clientes únicos diarios: Obtiene la tendencia de [Visitantes únicos diarios](/help/components/metrics/unique-visitors.md) a lo largo del tiempo con el segmento “Compradores” de Adobe aplicado.
   * Clientes únicos semanales: Obtiene la tendencia de [Visitantes únicos semanales](/help/components/metrics/unique-visitors.md) a lo largo del tiempo con el segmento “Compradores” de Adobe aplicado.
   * Clientes únicos mensuales: Obtiene la tendencia de [Visitantes únicos mensuales](/help/components/metrics/unique-visitors.md) a lo largo del tiempo con el segmento “Compradores” de Adobe aplicado.
   * Clientes únicos trimestrales: Obtiene la tendencia de [Visitantes únicos trimestrales](/help/components/metrics/unique-visitors.md) a lo largo del tiempo con el segmento “Compradores” de Adobe aplicado. Los trimestres son de enero a marzo, de abril a junio, de julio a septiembre y de octubre a diciembre.
   * Clientes únicos anuales: Obtiene la tendencia de [Visitantes únicos anuales](/help/components/metrics/unique-visitors.md) a lo largo del tiempo con el segmento “Compradores” de Adobe aplicado.

## Perfil del visitante

Contiene informes sobre quién visita el sitio.

* Segmentación geográfica: Informes sobre de dónde provienen las visitas al sitio en todo el mundo.
   * Países: Utiliza la dimensión [Países](/help/components/dimensions/countries.md).
   * Región: Utiliza la dimensión [Regiones](/help/components/dimensions/regions.md).
   * Ciudades: Utiliza la dimensión [Ciudades](/help/components/dimensions/cities.md).
   * Estados Unidos: Utiliza la dimensión [Estados estadounidenses](/help/components/dimensions/us-states.md).
   * DMA de EE. UU.: Utiliza la dimensión [DMA de EE. UU.](/help/components/dimensions/us-dma.md)
* Idiomas: Utiliza la dimensión [Idioma](/help/components/dimensions/language.md).
* Husos horarios: Utiliza la dimensión de zona horaria (se ha eliminado en Analysis Workspace). Los elementos de dimensión son el desajuste GMT de la visita.
* Dominio: Utiliza la dimensión [Dominio](/help/components/dimensions/domain.md).
* Dominio de nivel superior: Utiliza la dimensión de dominio de nivel superior (se ha eliminado en Analysis Workspace). Agrupa la dimensión [Dominios](/help/components/dimensions/domain.md) en categorías de nivel superior, generalmente por país del dominio.
* Tecnología: Carpeta que contiene informes sobre lo que el visitante utilizó para acceder al sitio.
   * Exploradores: Utiliza la dimensión [Exploradores](/help/components/dimensions/browser.md).
   * Tipo de explorador: Utiliza la dimensión [Tipo de navegador](/help/components/dimensions/browser-type.md).
   * Anchura del explorador: Utiliza la dimensión [Anchura del explorador: agrupado](/help/components/dimensions/browser-width.md).
   * Altura del explorador: Utiliza la dimensión [Altura del explorador: agrupado](/help/components/dimensions/browser-height.md).
   * Sistema operativo: Utiliza la dimensión [Sistemas operativos](/help/components/dimensions/operating-systems.md).
   * Tipo de sistema operativo: Utiliza la dimensión [Tipos de sistemas operativos](/help/components/dimensions/operating-system-types.md).
   * Profundidad de color del monitor: Utiliza la dimensión [Profundidad de color](/help/components/dimensions/color-depth.md).
   * Resolución del monitor: Utiliza la dimensión [Resolución del monitor](/help/components/dimensions/monitor-resolution.md).
   * Java: Utiliza la dimensión [Java habilitado](/help/components/dimensions/java-enabled.md).
   * JavaScript: Utiliza la dimensión JavaScript habilitado (se ha eliminado en Analysis Workspace). Los elementos de dimensión son “Habilitado”, “Deshabilitado” o “Desconocido”, según si el explorador tiene JavaScript habilitado.
   * Versión de JavaScript: utiliza la dimensión Versión de JavaScript (se ha eliminado en Analysis Workspace). Los elementos de dimensión muestran la versión de JavaScript que utiliza el explorador.
   * Cookies: Utiliza la dimensión [Compatibilidad con cookies](/help/components/dimensions/cookie-support.md).
   * Tipos de conexión: Utiliza la dimensión [Tipo de conexión](/help/components/dimensions/connection-type.md).
   * Operador de telefonía móvil: Utiliza la dimensión [Operador de telefonía móvil](/help/components/dimensions/mobile-dimensions.md).
* Estado del visitante: Utiliza la dimensión Estado (se ha eliminado en Analysis Workspace). Los elementos de dimensión proceden de la variable [`state`](../../implement/vars/page-vars/state.md).
* Código postal del visitante: Utiliza la dimensión [Código postal](/help/components/dimensions/zip-code.md).

## Conversión personalizada

Contiene informes específicos de la implementación. Los informes de conversión personalizados utilizan [eVars](/help/components/dimensions/evar.md) como dimensión.

## Tráfico personalizado

Contiene informes específicos de la implementación. Los informes de tráfico personalizados utilizan [props](/help/components/dimensions/prop.md) como dimensión.

## Canales de marketing

Contiene informes que involucran [Canales de marketing](/help/components/c-marketing-channels/c-getting-started-mchannel.md).

* Informe de descripción general de canal: Informe personalizado específico de Reports &amp; Analytics. Utiliza canales de marketing como elementos de dimensión, con métricas que utilizan atribución de primer o último contacto.
* Canal de primer contacto: Utiliza la dimensión [Canal de primer contacto](/help/components/dimensions/first-touch-channel.md).
* Detalles del canal de primer contacto: Utiliza la dimensión [Detalles del canal de primer contacto](/help/components/dimensions/first-touch-detail.md).
* Canal de último contacto: Utiliza la dimensión [Canal de último contacto](/help/components/dimensions/last-touch-channel.md).
* Detalles del canal de último contacto: Utiliza la dimensión [Detalle del canal de último contacto](/help/components/dimensions/last-touch-detail.md).

## Marcadores

Contiene los informes que ha marcado. Consulte [Marcadores](bookmarks.md) para obtener más información.

## Tableros

Contiene los paneles que ha creado. Consulte [Paneles](dashboard.md) para obtener más información.

## Objetivos

Contiene los destinatarios que ha creado. Consulte [Destinatarios](targets.md) para obtener más información.

>[!NOTE]
>
>Si no encuentra el informe en esta página de ayuda, es posible que el administrador haya cambiado el nombre de las carpetas o las haya ajustado. Consulte [Personalización de menús](/help/admin/admin/customize-menus.md) en la guía de usuario de administración.
