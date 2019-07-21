---
description: La siguiente información puede ayudar a solucionar problemas de latencia de los grupos de informes en los datos de Analytics.
keywords: faltan datos; lento
seo-description: La siguiente información puede ayudar a solucionar problemas de latencia de los grupos de informes en los datos de Analytics.
seo-title: Disponibilidad y latencia de los datos
solution: Analytics
subtopic: Datos actuales
title: Disponibilidad y latencia de los datos
topic: 'Informes '
uuid: 1 f 0 e 67 e 3-6 cea -4 af 8-8 b 18-7 ae 9223 df 7 c 8
translation-type: tm+mt
source-git-commit: 1fdd14497171dbf5850ec1b1d873a06931d58435

---


# Disponibilidad y latencia de los datos en Adobe Analytics

Normalmente, se espera ver los datos completos en los informes 2 horas después de recopilar los datos. La siguiente información puede ayudar a solucionar problemas de latencia de los grupos de informes en los datos de Analytics.

## Información sobre el agrupamiento de datos

Cada servidor de recopilación de datos captura y procesa los datos de análisis sin procesar y, a continuación, carga los datos por lotes una vez cada hora para registrarlos. El proceso de transferencia suele durar 30 minutos aproximadamente, por lo que la latencia normal del tráfico que se produce inmediatamente después de completarse un proceso de carga se aproxima a los 90 minutos (60 minutos hasta que se produce la siguiente carga por lotes más 30 minutos para que la transferencia de archivos se cargue y se muestre). Para el tráfico que se produce directamente antes de una carga, la latencia de los datos puede ser de tan sólo 30 minutos (0 minutos hasta que se produce la siguiente carga por lotes, 30 minutos para la transferencia de archivos y la visualización).

Si es necesario, el Servicio de atención al cliente de Adobe puede habilitar cargas de datos por lotes de 30 minutos (en lugar de por hora) para los grupos de informes más utilizados.

## Contribuidores a la latencia

La latencia es un retraso superior a las 2 horas típicas que tardan los servidores de recopilación de datos en procesar los datos por completo. No afecta a la recopilación de datos; aún se recopilan datos para una implementación de trabajo, independientemente de la latencia de un grupo de informes. Su gravedad (la actualidad de los datos) y la longitud (el tiempo que tarda en resolverse) pueden variar en gran medida. Generalmente está limitado a un único grupo de informes.

La latencia está causada por una de las siguientes categorías generales:

* **Pico de tráfico inesperado:** Este tipo de latencia se produce cuando se envían más datos a un grupo de informes que se comprometió o se esperaba de contrato. Es la causa más común de latencia.
* **Problemas normales de hardware:** Adobe emplea estrategias de vanguardia para la administración y supervisión del centro de datos, la redundancia de datos y la fiabilidad del hardware. El hardware se actualiza con regularidad y conjuntamente con ventanas de mantenimiento publicadas. El mantenimiento de emergencia de hardware defectuoso requiere una parada necesaria y temporal en el procesamiento de datos (no en la recopilación de datos), ya que el hardware de sustitución se pone en línea. Esta parada temporal en el procesamiento puede provocar una latencia marcada.
* **Datos anormales:** Los patrones de datos no naturales, como las visitas inusualmente largas causadas por un bot o un buscador, pueden aumentar temporalmente ciertas cargas de procesamiento que resultan en latencia.

## Funciones que dependen de latencia

Algunas capacidades de Adobe Experience Cloud incluyen una latencia innate sobre el tiempo de procesamiento estándar.

* Analytics para Target (A 4 T) requiere de otros 5-10 minutos de latencia para permitir que los datos recopilados de ambas plataformas se almacenen en la misma visita.
* Los datos con marca de hora requieren un tiempo adicional debido a que se procesan estos datos. Las visitas con marca de hora recibidas en tiempo real o casi en tiempo real pueden tardar hasta 15 minutos. Las visitas recibidas con una marca de fecha y hora de ayer pueden tardar hasta 2 horas. Las visitas más antiguas pueden demorar más, aumentando cada día hasta un límite de aproximadamente 24 horas.

## Formas de mitigar o prevenir la latencia

Existen varias estrategias para evitar la latencia o reducir el tiempo de recuperación cuando se produce:

* **Notificar a Adobe de picos de tráfico esperados:** Aunque es imposible anticipar todos los picos de tráfico a su sitio, es posible que haya casos en los que espera recibir un aumento significativo en el tráfico. Algunos ejemplos son un período de fiestas especialmente exitoso o poco después de una gran campaña push. En estos casos, Adobe proporciona un método para que su organización nos informe de los incrementos de tráfico esperados. De este modo podremos asignar recursos de procesamiento adicionales a su grupo de informes. See [Schedule a traffic spike](../admin/c-traffic-management/t-traffic-schedule-spike.md) in the Admin user guide to learn how to notify Adobe of increased traffic.
* **Tenga en cuenta la carga de procesamiento al activar nuevas funciones:** Algunas funciones requieren más procesamiento que otras. Cuantas más características haya habilitadas en un grupo de informes, más difícil será recuperarse de la latencia. Cuando active características en un grupo de informes, tenga en cuenta que las siguientes características incrementan la cantidad de datos que se deben procesar:

   * Implementación de más de 20 eventos en la misma página
   * Reglas de VISTA complejas
   * Más de 20 valores en la variable de productos
   * Serialización de eventos

* Enable IAB Bot filtering: [Bot filtering](https://marketing.adobe.com/resources/help/en_US/admin/index.html?f=c_bot_rules) can greatly reduce latency if your report suite is frequented by bots or crawlers. Se recomienda utilizar la lista de bots de la IAB, actualizada y mantenida por la asociación [Interactive Advertising Bureau](https://www.iab.net/about_the_iab). Un usuario puede personalizar sus propias reglas de bots para complementar a las de la IAB.

## Qué hacer con la latencia

En los casos en que se produce latencia, tenga la seguridad de que Adobe supervisa de forma proactiva el canal de procesamiento y hace todo lo posible para devolver el tiempo de procesamiento a normal lo más rápido posible. Muchos de los problemas de latencia se resuelven en unas horas. Para obtener información sobre un grupo de informes determinado, debe solicitarse a un usuario de asistencia técnica de la organización que averigüe el ID del grupo de informes que está experimentando la latencia y que se ponga en contacto con el Servicio de atención al cliente. El representante de Adobe puede validar la latencia e informará al usuario cuando el problema mejore y se resuelva.
