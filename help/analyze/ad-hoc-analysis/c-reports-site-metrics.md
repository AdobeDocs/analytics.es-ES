---
description: Muestran información cuantitativa sobre el sitio web, tal como la cantidad de veces que los visitantes miraron determinadas páginas, la cantidad de compras totales realizadas desde páginas específicas, el momento de ingreso de los visitantes y datos cuantitativos similares. Cada uno de estos informes es una métrica que se puede incluir en otros informes basados en elementos.
title: Informes de métricas del sitio
topic: Ad hoc analysis
uuid: 0730747a-216f-4a58-b62b-a9812968cde5
translation-type: tm+mt
source-git-commit: 5d96a2868bee48e2294ec2fb27e0340a3bcc50ae
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Informes de métricas del sitio

>[!IMPORTANT]
>
>El Adobe está llevando a Ad Hoc Analysis al final de su vida útil el 1 de marzo de 2021. [Más información](https://adobe.ly/discoverworkspace)

Muestran información cuantitativa sobre el sitio web, tal como la cantidad de veces que los visitantes miraron determinadas páginas, la cantidad de compras totales realizadas desde páginas específicas, el momento de ingreso de los visitantes y datos cuantitativos similares. Cada uno de estos informes es una métrica que se puede incluir en otros informes basados en elementos.

## Informes de métricas del sitio {#concept_0639CA16551749A693F49ADED4842CCE}

Muestran información cuantitativa sobre el sitio web, tal como la cantidad de veces que los visitantes miraron determinadas páginas, la cantidad de compras totales realizadas desde páginas específicas, el momento de ingreso de los visitantes y datos cuantitativos similares. Cada uno de estos informes es una métrica que se puede incluir en otros informes basados en elementos.

Los informes de métricas son de tendencias con el tiempo. se les pueden aplicar diversos niveles de granularidad, como “hora” y “día de la semana”. También permiten analizar el tiempo empleado en el sitio, las compras, los ingresos y métricas similares.

En el menú [!UICONTROL Métricas del sitio] se encuentran disponibles los siguientes informes.

## Informe de vistas de página {#concept_5331AFB6948547F7B8DF367B49360E6B}

<!-- 

c_reports_pageviews.xml

 -->

Es un informe de tendencia que muestra el número de veces que se vieron las páginas del sitio web en un período determinado (hora, día, semana, mes, trimestre o año). Una [!UICONTROL Vista de página] es una solicitud de un documento de una página completa, en vez de un elemento de una página, como, por ejemplo, una imagen o un vídeo. Si un mismo visitante ve 15 páginas durante una visita, se cuentan 15 vistas de página. Si un visitante ve la misma página tres veces durante una visita, se cuentan tres vistas de página. Este informe permite hacer un seguimiento de vistas para cada página del sitio, como así también del total agregado de vistas para todas las páginas del sitio.

## Informe de visitas {#concept_50CA55CF2A41430CBC754AEEEE6023A9}

Muestra la cantidad de visitas realizadas al sitio web durante un período determinado. Una *visita* es una secuencia de vistas de páginas. La visita comienza cuando el visitante carga una página y termina después de 30 minutos de inactividad. Una visita puede durar varias horas, en tanto el visitante cargue por lo menos una página antes de que expire el plazo de inactividad. Una visita no es necesariamente lo mismo que una sesión de navegador. Si un visitante cierra el navegador, lo vuelve a abrir y regresa al sitio cinco minutos después, se reconoce como continuación de la visita original. Esto también significa que si un visitante se queda mirando una página durante 35 minutos, la visita se cierra y se procesa; si luego hace clic y abre otra página, se considerará que es el comienzo de otra visita. Las visitas se rastrean mediante cookies. Las visitas se terminan después de 12 horas de actividad continua.

<!-- 

c_reports_visits.xml

 -->

En los Reports and Analytics de marketing, puede ejecutar un [!UICONTROL informe de visitas] en una página seleccionada. Ad Hoc Analysis le permite segmentar los datos para ver páginas específicas.

## Informe de visitantes únicos {#concept_39097C54E46C496CBAD537329DB3C84A}

Es un informe de tendencia que muestra la cantidad de visitantes únicos que entraron al sitio. Cada visitante se cuenta solamente una vez, independientemente de cuántas veces haya visitado el sitio web. Para distinguir los visitantes únicos de los visitantes de retorno, Adobe utiliza una tecnología, con patente pendiente, de identificación mediante cookies, que supera las limitaciones usuales de las cookies en los navegadores de Internet.

<!-- 

c_reports_unique_visitors.xml

 -->

Puede utilizar este informe para:

* Ver la cantidad de personas distintas que ingresaron al sitio web durante un período de tiempo seleccionado.
* Ver los patrones de tráfico recientes y comprender cómo las promociones atraen visitantes únicos al sitio.
* Comparar la cantidad de visitantes únicos con la cantidad de vistas de páginas.

## Informe de visitantes {#concept_7371DAB5DA474D03A2D1448F151E011B}

Muestra el número de visitantes únicos del sitio durante la hora, el día, la semana, el mes, el trimestre o el año que se haya seleccionado. Cada visitante único se cuenta solo una vez durante el lapso seleccionado. Los visitantes que regresan al sitio no se cuentan nuevamente como usuarios únicos hasta que haya transcurrido el intervalo de tiempo.

<!-- 

c_reports_visitors.xml

 -->

El total que se muestra al final de la tabla es la suma de todas las visitas durante el período especificado y no siempre refleja la cantidad de visitantes únicos. Por ejemplo: si se ejecuta un [!UICONTROL informe de visitantes únicos diarios] con un intervalo de tiempo de varios días, el total puede incluir visitantes repetidos, porque si un mismo visitante regresa en dos días sucesivos, se lo contará por separado en cada visita. Sin embargo, si se ejecuta un [!UICONTROL informe de visitantes únicos mensuales], el valor en la columna Totales reflejará con precisión la cantidad de visitantes únicos que ingresaron durante el mes.

## Informe de tiempo invertido por visita {#concept_5CDB759F9C9B4002A786A71F2BDBB292}

Muestra la cantidad de tiempo que los visitantes emplean viendo el contenido del sitio durante cada visita. También incluye una estadística de tiempo promedio empleado en el sitio.

<!-- 

c_reports_time_spent_per_visit.xml

 -->

Utilice este informe para:

* Identificar el tiempo que los visitantes permanecen en el sitio.
* Identificar el contenido y las promociones del sitio que despiertan el interés de los visitantes.
* Averiguar por qué el sitio tiene mucho tráfico pero los visitantes se retiran rápidamente.

## Informe de compras {#concept_E3B9AF43CCD24F25A85D05DFB51C4740}

Muestra datos resumidos sobre ingresos, pedidos y unidades. También puede ver el informe [!DNL Purchase Conversion Funnel].

<!-- 

c_reports_purchases.xml

 -->

* **Ingresos**: permite ver la ganancia bruta para los períodos de tiempo seleccionados. Ejemplos: ingresos durante el mes de marzo, compras realizadas la semana anterior o ingresos en el día.
* **Pedidos**: muestra el número de pedidos realizados en el sitio web durante el período de tiempo especificado. Los pedidos pueden contener varios productos.
* **Unidades**: muestra las unidades totales que se pidieron durante el período de tiempo seleccionado.
* **Canal de conversión de compra**: idóneo para mostrar eventos de conversión en el sitio si se produjeron en un orden específico, por ejemplo en un contexto de venta minorista. Un informe de canal muestra las métricas de conversión para cada paso del proceso de conversión, así como también Pedidos, Ingresos y Unidades.

## Informe de carro de compras {#concept_6AEC5A6C707B46B790C1A79E72F9A339}

Muestra cuántos carros de compras se abrieron en un período determinado. Se pueden ejecutar informes para analizar las vistas, adiciones, eliminaciones y cierres de compra que se realizan en relación con el carro de compras. Un carro de compras generalmente se abre cuando un cliente selecciona un artículo que desea adquirir, aunque también se puede abrir sin ningún artículo.

<!-- 

c_reports_shopping_cart.xml

 -->

Puede utilizar el [!UICONTROL Informe de carro de compras] para:

* Determinar los patrones, las altas y las bajas en la cantidad de carros abiertos en el sitio.
* Examinar períodos de tiempo específicos, obtener más información sobre las métricas que contribuyeron específicamente a la apertura del carro de compras.

## Informe de eventos personalizados {#concept_9337B2FB8A3F417BA8689FE7FD64629F}

Acciones de conversión en el sitio que se desea que realicen los visitantes. Ejemplos de estas acciones podrían ser: un registro, una suscripción, la cumplimentación de un formulario de posible cliente, un inicio de conversación (chat), una compra, una reserva o una encuesta finalizada.

<!-- 

c_reports_custom_events.xml

 -->

Dado que cada grupo de informes de análisis es distinto, este conjunto de informes se utiliza de forma diferente con cada cliente. El informe de [!UICONTROL eventos personalizados] se puede utilizar como contador para indicar la cantidad de veces que se produce un evento. Por ejemplo, si **[!UICONTROL evento1]** se configura para mostrar la cantidad de veces que se descarga un documento, el informe de [!UICONTROL eventos personalizados] para el Evento 1 mostrará la cantidad total de descargas. Es posible tener varios informes de eventos personalizados.

## Informes de conversión {#concept_BDD3DD8A46F043BB916C7E346E7C314F}

Muestran los ingresos obtenidos gracias a diferentes aspectos del sitio web. Se pueden ver informes que muestran los ingresos obtenidos gracias a campañas publicitarias, los ingresos provenientes de clientes fieles comparados con aquellos obtenidos de los clientes nuevos, un desglose de ingresos por producto y muchos otros informes de ingresos. Los informes de conversión también pueden mostrar otros eventos de éxito, como clics en las publicidades, descargas u otros eventos.

<!-- 

c_reports_conversion.xml

 -->

Los informes de conversión incluyen estadísticas en tiempo real de todas las actividades relevantes de los clientes, entre ellas:

* Patrones de compra de los clientes
* Métricas del carro de compra, incluido el orden de las visitas
* Tasas de conversión de los clientes
* Eficacia de los socios de canal y de la publicidad
* Rendimiento de la campaña de marketing a través de Internet y sin conexión
* Métricas de lealtad del cliente
* Comprensión de ciclos de ventas

## Informes de canales de marketing {#concept_81FFA8C15A9B4914BFED37488ADD17FD}

Los informes de canales de marketing muestran la asignación a canales de primer Contacto e último contacto, con métricas estándar críticas, tales como ingresos, pedidos y coste, lo cual permite saber los ingresos que cada canal genera. Las reglas de definición de canal se configuran en [!DNL Admin Console] y también existen API específicas para los informes de canal.

<!-- 

c_reports_marketing_channel.xml

 -->

**[!UICONTROL Informe de canales de primer o último contacto]**: muestran métricas con datos sobre un canal determinado de primer contacto o último contacto. En dichos informes, puede desglosar los canales y mostrar los detalles de cada uno de ellos. Si ha habilitado AdLens, verá clasificaciones en sus Reports and Analytics de marketing de canal.

**[!UICONTROL Informes de detalles de canales de primer o último contacto]**: muestran detalles, tales como nombres de página y referentes, tomados de los valores de canal que se configuren en la opción [!UICONTROL Definir el valor del canal en], al configurar las reglas. Los informes de detalles de canal permiten examinar minuciosamente los valores detallados del canal en el informe de resumen.

Para obtener información detallada sobre la configuración del canal de marketing en los informes y análisis de marketing, consulte el sistema de [ayuda para canales de marketing](/help/components/c-marketing-channels/analyze-mc.md).
