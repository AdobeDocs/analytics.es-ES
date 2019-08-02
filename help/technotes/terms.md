---
title: Términos utilizados en Adobe Analytics
description: Glosario para Adobe Analytics, definición de términos comunes utilizados.
translation-type: tm+mt
source-git-commit: aeb2fc9f53aec6b4e53378b87e64c01f0b437d87

---


# Términos utilizados en Adobe Analytics

Utilice este glosario para comprender el contexto de muchos términos que utiliza Adobe Analytics.

* **Activity Map:** Complemento del explorador que muestra las áreas del sitio donde se hizo clic más. Consulte [Activity Map](../analyze/activity-map/activity-map.md) en la Guía de análisis del usuario.
* **Consola de administración:** Puede hacer referencia a:
   * Herramientas de administración heredadas, donde se administran la configuración del grupo de informes en Adobe Analytics. En versiones anteriores de Adobe Analytics, los permisos de usuario también se administraban aquí. Consulte [Herramientas](../admin/admin/c-admin-tools.md) de administración en la Guía del usuario administrador.
   * Admin Console de Adobe, donde se aprovisiona el acceso al producto y se administran los permisos de usuario. Consulte [Consola de administración](../admin/admin-console/home.md) en la Guía del usuario administrador.
* **Asignación:** Si una variable de conversión encuentra más de un valor durante una visita, la configuración de asignación de la variable determina qué valor se conservará. See [Conversion variables](../admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin user guide.
* **Anomalía:** Se detecta usando modelado estadístico para buscar automáticamente tendencias inesperadas en los datos. El modelo analiza las métricas y determina un límite inferior, límite superior y rango esperado de valores. Consulte [Detección de anomalías](../analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) en la Guía de análisis de usuarios.
* **Appmeasurement:** Biblioteca de códigos utilizada para recopilar datos y enviarlos a Adobe. Consulte [la Página principal](../implement/home.md) de la guía de implementación del usuario.
* **Ranura ASI:** Ya no existe. En versiones anteriores de Adobe Analytics, las ranuras ASI proporcionan un contenedor de grupo de informes temporal para ver los datos segmentados. En la versión actual de Adobe Analytics, los segmentos se pueden aplicar instantáneamente a cualquier informe.
* **Desglose:** Permite ver una dimensión dentro del contexto de otra dimensión. Consulte [Desglose de dimensiones](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) en la Guía de análisis del usuario.
* **Devolución:** Visita que consiste en una sola visita. Consulte [Devoluciones](../components/c-variables/c-metrics/metrics-bounces.md) en la guía del usuario de Componentes. Consulte también Acceso único.
* **Métrica calculada:** Permite la combinación de métricas, funciones estadísticas y fórmulas existentes para su uso en los informes. Consulte [Métricas calculadas](../components/c-calcmetrics/cm-overview.md) en la guía del usuario de Componentes.
* **Campaña:** Puede hacer referencia a:
   * La variable Campaign, que rellena la dimensión Código de seguimiento. Consulte [Variables de página](../implement/js-implementation/c-variables/page-variables.md) en la guía de implementación del usuario.
   * Una clasificación predeterminada de la dimensión Código de seguimiento; se crea automáticamente para todos los grupos de informes.
   * Adobe Campaign, parte de Adobe Experience Cloud. Más información sobre [Adobe.com](https://www.adobe.com/marketing/campaign.html).
* **Canal:** Puede hacer referencia a:
   * La variable Canal, que rellena la dimensión Secciones del sitio. Consulte [Variables de página](../implement/js-implementation/c-variables/page-variables.md) en la guía de implementación del usuario.
   * Canales de marketing, componente que ayuda a comprender cómo llegan los usuarios al sitio. Consulte [Canales de mercadotecnia](../components/c-marketing-channels/c-overview.md) en la guía del usuario de Componentes.
* **Clasificación:** Una función de Adobe Analytics que permite la agrupación de valores de dimensión. Consulte [Clasificaciones](../components/c-classifications2/c-classifications.md) en la guía del usuario de componentes.
* **Clickmap:** Ya no se utiliza. Complemento preexistente del explorador que muestra las áreas del sitio donde se hizo clic más. Esta herramienta se retiró en favor del mapa de actividades.
* **Fuente de datos del flujo de navegación:** Consulte Fuente de datos.
* **Cohorte:** Grupo de personas que comparten características comunes durante un período de tiempo determinado. See [What is Cohort Analysis?](../analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) en la Guía de usuario Analizar.
* **Servidor de recopilación:** Consulte Servidor de recopilación de datos.
* **Variable de conversión:** Se denomina de forma colloquialmente evars. Almacena un valor personalizado y conserva el valor de la variable hasta que caduque. See [Conversion variables](../components/c-variables/dimensionslist/reports-conversion.md) in the Components user guide.
* **Correlación:** Ya no se usa como término; reemplazados por desgloses de dimensión. En versiones anteriores de Adobe Analytics, las correlaciones permitían desglosar las variables de tráfico. Consulte [Desglose de dimensiones](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) en la Guía de análisis del usuario.
* **Datos actuales:** Una opción en algunos informes que permite la inclusión de datos recopilados recientemente que aún no se han procesado completamente. Consulte [Datos actuales](../analyze/reports-analytics/current-data.md) en la Guía del usuario Analizar.
* **Vínculo personalizado:** Un tipo de visita que contiene datos de vista que no son de página. Consulte la función [s. tl ()](../implement/js-implementation/function-tl.md) en la guía de implementación del usuario. Consulte también Visita individual.
* **Atributos del cliente:** Una función de Experience Cloud que permite cargar datos de atributos. Consulte [Atributos del cliente](https://docs.adobe.com/content/help/en/core-services/interface/customer-attributes/attributes.html) en la guía del usuario de Servicios principales.
* **Delegado de asistencia al cliente:** Usuario designado autorizado para interactuar directamente con el Servicio de atención al cliente de Adobe. Consulte [Asistencia al cliente en](https://helpx.adobe.com/experience-cloud/supported-users.html) la base de conocimiento de Experience Cloud.
* **Servidor de recopilación de datos:** Servidores propiedad de Adobe que reciben y procesan datos. Las solicitudes de imagen se envían a los servidores de recopilación de datos de Adobe para su uso en los informes.
* **Conectores de datos:** Solución de desarrollo completa que permite a terceros automatizar la carga de datos en Adobe Analytics. Los clientes de terceros pueden utilizar un conector de datos para enriquecer sus datos en Adobe Analytics. La mayoría de los conectores de datos utiliza un flujo de trabajo similar en las fuentes de datos. Consulte Conectores de datos en la Guía Importar usuario.
* **Fuente de datos:** Exportación de datos sin procesar que enumera cada visita como una fila y variables como columnas separadas. Se utiliza comúnmente para exportar datos de Adobe Analytics a una base de datos de terceros. Consulte [Fuentes de datos](../export/analytics-data-feed/c-getstarted/data-feed-overview.md) en la guía de exportación del usuario.
* **Fuentes de datos:** Permite al usuario cargar datos desde un archivo en Adobe Analytics. Normalmente, el archivo se extrae de un sitio FTP. Consulte [Fuentes de datos](../import/c-data-sources/datasrc-home.md) en la Guía Importar usuario.
* **Almacén de datos:** Una función de Adobe Analytics que le permite solicitar informes más grandes. Consulte [Almacén de datos](../export/data-warehouse/data-warehouse.md) en la guía del usuario Exportar.
* **Dimensión:** Un tipo de componente que contiene valores de variable, como texto. Algunos ejemplos son Nombre de página, Código de seguimiento o Dominio de referencia. Una métrica suele ser su equivalente.
* **Administración dinámica de etiquetas:** Solución anterior de administración de etiquetas de Adobe. Consulte [Descripción general de la implementación de DTM](../implement/c-implement-with-dtm/dtm-implementation-overview.md) en la guía de implementación del usuario. Adobe recomienda utilizar Launch Platform Platform en su lugar.
* **Serialización de eventos:** Proceso de implementación de medidas para evitar la recopilación de eventos duplicados. Consulte [Serialización de eventos](../implement/js-implementation/event-serialization.md) en la guía de implementación del usuario.
* **Evar:** Consulte Variable de conversión.
* **Evento:** Consulte Evento de éxito.
* **Excelclient:** Ya no se utiliza como término. Nombre del predecesor del Creador de informes.
* **Caducidad:** En el contexto de una variable de conversión, el tiempo que el valor persiste en el back-end. Esta persistencia permite asociar eventos con valores de variables antes de la visita del evento. See [Conversion variables](../admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin user guide.
* **Flujo:** Un tipo de visualización en Analysis Workspace que muestra las rutas que tomaron los usuarios en el sitio. Consulte [Visualización de flujo](../analyze/analysis-workspace/visualizations/c-flow/flow.md) en la Guía del usuario Analizar.
* **Genesis:** Ya no se utiliza como término. El nombre anterior de Data Connectors.
* **Grupo de informes globales:** Término informal designado para un grupo de informes que recopila visitas de varios sitios.
* **Código H:** Predecesor a appmeasurement. En versiones anteriores de Adobe Analytics, las versiones de código se midieron por «versión H», como H .27 .5, H .26, etc.
* **Visita individual:** Una sola solicitud de imagen enviada a los servidores de recopilación de datos de Adobe. Las vistas de página y los vínculos personalizados pueden conocerse como visitas individuales.
* **Solicitud de imagen:** Imagen transparente de 1 x 1 píxeles utilizada para comunicarse con los servidores de recopilación de datos de Adobe. Un sitio Web solicita esta imagen invisible con una cadena de consulta larga que contiene datos; Adobe devuelve la imagen invisible y analiza la cadena de consultas recibida.
* **Insight:** Puede hacer referencia a:
   * Nombre anterior del Área de trabajo de datos.
   * Perspectiva personalizada, un nombre histórico para la variable de tráfico personalizada.
* **KPI:** Abreviación de indicador de rendimiento clave. Métricas que ayudan a una empresa a comprender el rendimiento de su sitio. Cada organización tiene KPI diferentes que miden distintos aspectos de su negocio. Consulte [Creación de un documento de diseño de solución](../implement/prepare/solution-design.md) en la guía de implementación del usuario.
* **Latencia:** Retraso entre cuándo se recopilan los datos y cuándo está disponible en los informes. La latencia típica de un grupo de informes es de 30 a 90 minutos. Consulte [Latencia](../technotes/latency.md) en la guía del usuario de Notas técnicas.
* **Lanzamiento:** Abreviado de Adobe Experience Platform Launch, la solución de implementación actual de Adobe. Consulte [Información general](https://docs.adobe.com/content/help/en/launch/using/overview.html) en la guía del usuario de Launch Platform Platform.
* **Prop de lista:** Una configuración que convierte una variable de tráfico típica para admitir varios valores en la misma visita. Cualquier variable de tráfico personalizada puede convertirse en una prop de lista si la configuración está habilitada. Consulte [Variables de página](../implement/js-implementation/c-variables/page-variables.md) en la guía de implementación del usuario.
* **Var de lista:** Variable diferente separada de variables de conversión. Las variables de lista admiten varios valores en la misma visita y los valores de variables se conservan en una visita, similar a las variables de conversión. Solo hay tres variables de lista disponibles para una organización. Consulte [Variables de página](../implement/js-implementation/c-variables/page-variables.md) en la guía de implementación del usuario.
* **Empresa de inicio de sesión:** Recopilación de grupos de informes utilizados por su organización. Algunas organizaciones tienen varias empresas de inicio de sesión que se aplican a distintas partes de su organización.
* **Canal de mercadotecnia:** Característica de Adobe Analytics que categoriza las visitas por la forma en que llegaron al sitio. La lógica utilizada para categorizar las visitas se puede personalizar mediante reglas de procesamiento de canal de marketing. Consulte [Introducción a los canales de mercadotecnia](../components/c-marketing-channels/c-getting-started-mchannel.md) en la guía del usuario de componentes.
* **Métrica:** Un tipo de componente que contiene datos cuantitativos. Los valores de las métricas suelen contener números, como Vistas de página, Visitas e Ingresos. Una dimensión suele ser su equivalente.
* **Etiquetado de grupos múltiples:** La práctica de enviar la misma visita a varios grupos de informes. Con la introducción a los grupos de informes virtuales, esta práctica ya no es necesaria. La mayoría de los esfuerzos de etiquetado de grupos múltiples ayudan a dar cabida a un grupo de informes globales.
* **Normalización:** Una manera de organizar una visualización que toma todas las métricas y forzarlas a proporciones iguales, lo que permite comparar las tendencias más fácilmente.
* **Ocurrencias:** Un tipo de métrica que muestra cuántas visitas al valor de dimensión se estableció o persistió. Consulte [Ocurrencias](../components/c-variables/c-metrics/metrics-occurrences.md) en la guía del usuario de Componentes.
* **Omniture:** Ya no se utiliza como término. Organización que posee Adobe Analytics antes de adquirir Adobe en 2009.
* **Rutas:** Consulte Flujo.
* **Vista de página:** Tipo de visita que incrementa las vistas de página. Consulte [Vistas de página](../components/c-variables/c-metrics/metrics-page-view.md) en la guía del usuario de Componentes. Consulte también Visita individual.
* **Persistencia:** Concepto abstracto para variables de conversión que permiten la vinculación entre un valor de variable y un evento que se produce en visitas individuales separadas. Consulte también Caducidad.
* **Llamada al servidor primario:** Nombre alternativo para solicitud de imagen o visita, utilizado principalmente en contexto de etiquetado y facturación de grupos múltiples. Cuando se envía la misma visita a varios grupos de informes, el primer grupo de informes es una llamada al servidor primario mientras que el resto son llamadas secundarias al servidor. Esta regla se aplica a todos los tipos de visitas, incluso a la vista de página y al seguimiento de vínculos. Consulte también Llamadas al servidor secundario.
* **Reglas de procesamiento:** Puede hacer referencia a:
   * Reglas de procesamiento, una manera de modificar la recopilación de datos utilizando ciertas reglas en la Consola de administración. See [Processing rules](../admin/admin/c-processing-rules/processing-rules.md) in the Admin user guide.
   * Reglas de procesamiento de canal de mercadotecnia, un conjunto de reglas que determina el canal de mercadotecnia en el que pertenece una visita. Consulte [Reglas de procesamiento de canal de mercadotecnia](../admin/admin/marketing-channels-admin.md) en la guía del usuario administrador.
* **Prop:** Consulte Variable de tráfico.
* **Informe clasificado:** Formato de informe que suele seguir una dimensión con una métrica. Este tipo de informe permite ver los artículos principales, como las páginas más visitadas del sitio. Consulte también Informe de tendencias.
* **Tiempo real:** Muestra las variables configuradas tan pronto como se recopila con poco latencia. Consulte [Informes en tiempo real](../admin/admin/realtime/realtime.md) en la guía del usuario administrador.
* **Grupo de informes:** Contenedor global al que envía datos. Todos los informes de Adobe Analytics hacen referencia a un grupo de informes.
* **Intervalo de fechas móvil:** Tipo de intervalo de fechas relativo que cambia con el transcurso del tiempo. Por ejemplo, un informe que muestre los últimos 7 días puede considerarse un intervalo de fechas móvil. Consulte también intervalo de fechas estático.
* **RSID:** Abreviación del ID de grupo de informes. Un grupo de informes tiene un nombre práctico y una ID de grupo de informes.
* **s. t ():** El nombre de la función en una biblioteca appmeasurement que envía una solicitud de imagen de vista de página. Algunas bibliotecas appmeasurement utilizan `s.track()` en su lugar. Consulte [s. t ()](../implement/js-implementation/function-t.md) en la guía de implementación del usuario.
* **s<span>.</span>tl ():** El nombre de la función en una biblioteca appmeasurement que envía una solicitud de imagen de seguimiento de vínculos. Algunas bibliotecas appmeasurement utilizan `s.trackLink()` en su lugar. Consulte [s. tl ()](../implement/js-implementation/function-tl.md) en la guía de implementación del usuario.
* **s_ code. js:** Nombre del archivo JavaScript utilizado en las versiones históricas de Adobe Analytics. El nombre actual del archivo JavaScript utilizado es appmeasurement. js.
* **Satélite:** Ya no se utiliza como término. Nombre del producto anterior para la administración dinámica de etiquetas.
* **Llamada al servidor secundario:** Nombre alternativo para solicitud de imagen o visita, utilizado principalmente en contexto de etiquetado y facturación de grupos múltiples. Cuando se envía la misma visita a varios grupos de informes, todos los grupos de informes después de la primera lista son llamadas secundarias al servidor. Consulte también Llamadas primarias al servidor.
* **Segmento:** Permite centrarse en un subconjunto específico de los datos. Consulte [Segmentación](../components/c-segmentation/seg-overview.md) en la guía del usuario de Componentes.
* **Contenedor de segmentos:** Parte de un segmento que determina cuántos datos introducen. Los contenedores pueden basarse en vistas de página, visitas o visitantes. Consulte [Segmentación](../components/c-segmentation/seg-overview.md) en la guía del usuario de Componentes.
* **Serialización:** Consulte Serialización de eventos.
* **Llamada al servidor:** Nombre alternativo para una solicitud de imagen o visita, utilizada principalmente en contexto de facturación.
* **Acceso único:** Visita donde una dimensión tenía un solo valor único. La visita puede tener varias visitas, siempre y cuando no haya varios valores únicos. Consulte [Acceso único](../components/c-variables/c-metrics/metrics-single-access.md) en la guía del usuario de Componentes. Consulte también Devolución.
* **Sitecatalyst:** Ya no se utiliza como término. Nombre del producto anterior para Adobe Analytics.
* **Subrelación:** Ya no se usa como término; reemplazados por desgloses de dimensión. En versiones anteriores de Adobe Analytics, las subrelaciones permitían desglosar las variables de conversión. Consulte [Desglose de dimensiones](../analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) en la Guía de análisis del usuario.
* **Evento de éxito:** Acción rastreada por un usuario. Su organización determina qué eventos se rastrearán y qué variables de evento de éxito utiliza para rastrearlo. Consulte [Eventos personalizados](../components/c-variables/c-metrics/metrics-custom.md) en la guía del usuario de Componentes.
* **Usuario admitido:** Consulte Delegado de asistencia al cliente.
* **Variable de tráfico:** Se denomina de forma colloquialmente props. Almacena un valor personalizado para una sola visita. Las versiones anteriores de Adobe Analytics proporcionan valores únicos, pero las mejoras en la plataforma hacen que las variables de tráfico personalizadas sean innecesarias. Adobe recomienda utilizar variables de conversión personalizadas (evars) en la mayoría de los casos. Consulte [Variables de tráfico personalizado](../components/c-variables/dimensionslist/reports-custom-traffic.md) en la guía del usuario de Componentes.
* **Informe de tendencias:** Formato de informe que generalmente muestra varios intervalos de fechas con una métrica. Este tipo de informe permite ver cómo funciona una métrica a través del tiempo. Consulte también Informe de clasificación.
* **Visitante único**: Representa la cantidad de individuos únicos que ingresaron al sitio. Un solo visitante único puede tener varias visitas. Consulte [Visitante único](../components/c-variables/c-metrics/metrics-unique-visitors.md) en la guía del usuario de Componentes.
* **Grupo de informes virtuales:** Contenedor virtual de datos que hace referencia a un grupo de informes normal y permite refinar los datos. Los datos no se envían a un grupo de informes virtuales; en su lugar, los datos se envían a un grupo de informes normal y un grupo de informes virtuales se desactiva de esos datos recopilados. Consulte [Grupos de informes virtuales](../components/vrs/vrs-about.md) en la guía del usuario de Componentes.
* **Visita:** Representa la cantidad de sesiones únicas que se han producido en el sitio. Consulte [Visitas](../components/c-variables/c-metrics/metrics-visit.md) en la guía del usuario de Componentes.
* **Regla VISTA:** Lógica personalizada creada por Adobe en la solicitud de un cliente para copiar, analizar o filtrar datos en el lado del servidor. Las reglas VISTA suelen suponer costes adicionales. Consulte también Reglas de procesamiento.
* **Señalización web:** Consulte Solicitud de imagen.
