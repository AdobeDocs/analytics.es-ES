---
description: La siguiente información puede resultar de utilidad para solucionar los problemas de latencia del grupo de informes en los datos de Analytics.
keywords: missing data;slow
subtopic: Current data
title: Disponibilidad y latencia de los datos
topic: Reports
uuid: 1f0e67e3-6cea-4af8-8b18-7ae9223df7c8
translation-type: ht
source-git-commit: a4a4d9e6e2d3e3ed88b4ef66e9da3b05865a9b79
workflow-type: ht
source-wordcount: '803'
ht-degree: 100%

---


# Latencia y disponibilidad de datos en Adobe Analytics

Los datos de todas las aplicaciones suelen aparecer en los informes a las dos horas de la recopilación. La siguiente información puede resultar de utilidad para solucionar los problemas de latencia del grupo de informes en los datos de Analytics.

## Descripción del procesamiento por lotes

Cada servidor de recopilación de datos captura y procesa los datos de análisis sin procesar y, a continuación, carga los datos por lotes una vez cada hora para registrarlos. El proceso de transferencia suele durar 30 minutos aproximadamente, por lo que la latencia normal del tráfico que se produce inmediatamente después de completarse un proceso de carga se aproxima a los 90 minutos (60 minutos hasta que se produce la siguiente carga por lotes más 30 minutos para que la transferencia de archivos se cargue y se muestre). Respecto al tráfico que se produce justo antes de una carga, la latencia de datos puede reducirse hasta los 30 minutos (0 minutos hasta que se produce la siguiente carga por lotes más 30 minutos para que la transferencia de archivos se muestre).

Si se considera necesario, el Servicio de atención al cliente puede habilitar las cargas de datos por lotes cada treinta minutos (en lugar de cada hora) para los grupos de informes más usados.

## Factores que incrementan la latencia

La latencia es un retraso que supera el periodo de dos horas que suelen tardan los servidores de recopilación de datos en procesar los datos por completo. No afecta a la recopilación de datos. Los datos se siguen recopilando para permitir la implementación, independientemente de la latencia de un grupo de informes. Su gravedad (la actualidad de los datos) y duración (el tiempo que tarda en resolverse) pueden variar considerablemente. Suele quedar limitada a un único grupo de informes.

La latencia está causada por una de las siguientes categorías generales:

* **Pico de tráfico inesperado:** Este tipo de latencia se produce cuando un grupo de informes recibe un volumen de datos superior a lo esperado o a lo que se había acordado mediante contrato. Es la causa más común de latencia.
* **Problemas normales de hardware:** Adobe emplea estrategias de primer nivel en la administración y supervisión del centro de datos, la redundancia de datos y la fiabilidad del hardware. El hardware se actualiza con regularidad y conjuntamente con ventanas de mantenimiento publicadas. La reparación de emergencia del hardware defectuoso puede exigir una parada obligatoria y provisional en el procesamiento de los datos (no en la recopilación) mientras el nuevo hardware se pone en línea. Esta parada temporal en el procesamiento puede provocar una latencia marcada.
* **Datos anormales:** los patrones de datos no naturales, como las visitas inusualmente largas causadas por un bot o un rastreador, pueden incrementar temporalmente determinadas cargas de procesamiento, provocando una latencia.

## Funciones que dependen de la latencia

Algunas funciones de Adobe Experience Cloud tienen una cantidad innata de latencia además del tiempo de procesamiento estándar.

* Analytics for Target (A4T) requiere de cinco a diez minutos adicionales de latencia para que los datos recopilados de ambas plataformas se almacenen en la misma visita.
* En el caso de los datos con marca de tiempo la duración es mayor debido a que estos datos se procesan en diferentes servidores. Las visitas con marca de tiempo recibidas en tiempo real o casi en tiempo real pueden tardar hasta quince minutos. Las visitas recibidas con una marca de tiempo del día anterior pueden tardar hasta dos horas. Las visitas antiguas pueden tardar más tiempo, aumentando cada día hasta un máximo de aproximadamente veinticuatro horas.

## Modos de mitigar o evitar la latencia

Existen varias estrategias para evitar la latencia o reducir el tiempo de recuperación cuando se produce:

* **Informar a Adobe de los picos de tráfico esperados:** Aunque es imposible anticipar todos los picos de tráfico en el sitio, puede haber casos en los que se espere un aumento significativo de tráfico. Por ejemplo, en un periodo festivo muy rentable o poco después de una gran campaña. En estos casos, Adobe proporciona un método para que su organización nos informe de los incrementos de tráfico esperados. De este modo podremos asignar recursos de procesamiento adicionales a su grupo de informes. Consulte [Programar un pico de tráfico](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) en la guía del usuario de administración para obtener información sobre las notificaciones a Adobe relativas al aumento de tráfico.
* **Tenga en cuenta la carga de procesamiento al activar nuevas características:** Algunas necesitan más procesamiento que otras. Cuantas más características haya habilitadas en un grupo de informes, más difícil será recuperarse de la latencia. Cuando active características en un grupo de informes, tenga en cuenta que las siguientes características incrementan la cantidad de datos que se deben procesar:

   * Implementación de más de veinte eventos en la misma página
   * Reglas de VISTA complejas
   * Más de veinte valores en la variable de productos
   * Serialización de eventos

* Activar el filtrado para bots de la IAB: [el filtrado para bots](/help/admin/admin/bot-removal/bot-removal.md) puede reducir en gran medida la latencia si el grupo de informes se ve frecuentado por bots o rastreadores. Se recomienda utilizar la lista de bots de la IAB, actualizada y mantenida por la asociación [Interactive Advertising Bureau](https://www.iab.net/about_the_iab). Un usuario puede personalizar sus propias reglas de bots para complementar las de la IAB.

## Indicaciones sobre la latencia

Es importante señalar que, cuando se produce latencia, Adobe supervisa activamente los canales de procesamiento y hace todo lo posible para restaurar el tiempo de procesamiento a la normalidad lo antes posible. Muchos de los problemas de latencia se resuelven en unas horas. Para obtener información sobre un grupo de informes determinado, debe solicitarse a un usuario de asistencia técnica de la organización que averigüe el ID del grupo de informes que está experimentando la latencia y que se ponga en contacto con el Servicio de atención al cliente. El representante de Adobe puede validar la latencia e informará al usuario cuando el problema mejore y se resuelva.
