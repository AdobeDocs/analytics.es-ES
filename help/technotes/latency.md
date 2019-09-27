---
description: La siguiente información puede ayudar a solucionar problemas de latencia de grupos de informes en los datos de Analytics.
keywords: datos faltantes;lento
seo-description: La siguiente información puede ayudar a solucionar problemas de latencia de grupos de informes en los datos de Analytics.
seo-title: Disponibilidad y latencia de los datos
solution: Analytics
subtopic: Datos actuales
title: Disponibilidad y latencia de los datos
topic: Informes
uuid: 1f0e67e3-6cea-4af8-8b18-7ae9223df7c8
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Latencia y disponibilidad de datos en Adobe Analytics

Generalmente, puede esperar ver los datos completos en los informes dos horas después de que se recopilen los datos. La siguiente información puede ayudar a solucionar problemas de latencia de grupos de informes en los datos de Analytics.

## Explicación del agrupamiento de datos

Cada servidor de recopilación de datos captura y procesa los datos de análisis sin procesar y, a continuación, carga los datos por lotes una vez cada hora para registrarlos. El proceso de transferencia suele durar 30 minutos aproximadamente, por lo que la latencia normal del tráfico que se produce inmediatamente después de completarse un proceso de carga se aproxima a los 90 minutos (60 minutos hasta que se produce la siguiente carga por lotes más 30 minutos para que la transferencia de archivos se cargue y se muestre). Para el tráfico que se produce directamente antes de una carga, la latencia de datos puede ser de hasta 30 minutos (0 minutos hasta que se produzca la siguiente carga por lotes y 30 minutos para la transferencia y visualización de archivos).

Si es necesario, el Servicio de atención al cliente de Adobe puede habilitar cargas de datos por lotes de 30 minutos (en lugar de cada hora) para los grupos de informes más utilizados.

## Contribuyentes a la latencia

La latencia es un retraso que supera las 2 horas típicas que tardan los servidores de recopilación de datos en procesar los datos por completo. No afecta a la recopilación de datos; los datos se siguen recopilando para una implementación en funcionamiento, independientemente de la latencia de un grupo de informes. Su gravedad (la actualidad de los datos) y duración (el tiempo que se tarda en resolverse) pueden variar considerablemente. Generalmente se limita a un solo grupo de informes.

La latencia está causada por una de las siguientes categorías generales:

* **** Pico de tráfico inesperado: Este tipo de latencia se produce cuando se envían más datos a un grupo de informes de los que se comprometieron o esperaron en el contrato. Es la causa más común de latencia.
* **** Problemas normales de hardware: Adobe emplea estrategias de primera categoría para la administración y supervisión de centros de datos, la redundancia de datos y la fiabilidad del hardware. El hardware se actualiza con regularidad y conjuntamente con ventanas de mantenimiento publicadas. El mantenimiento de emergencia de hardware fallido puede requerir una parada necesaria y temporal en el procesamiento de datos (no en la recopilación de datos) a medida que el hardware de reemplazo se pone en línea. Esta parada temporal en el procesamiento puede provocar una latencia marcada.
* **** Datos anormales: Los patrones de datos no naturales, como las visitas inusualmente largas causadas por un bot o un bot, pueden aumentar temporalmente ciertas cargas de procesamiento que resultan en latencia.

## Funciones que dependen de la latencia

Algunas funciones de Adobe Experience Cloud incluyen una cantidad innata de latencia además del tiempo de procesamiento estándar.

* Analytics para Target (A4T) requiere de 5 a 10 minutos de latencia adicionales para permitir que los datos recopilados de ambas plataformas se almacenen en la misma visita.
* Los datos con marca de hora requieren tiempo adicional debido a que estos datos se procesan en diferentes servidores. Las visitas con marca de tiempo recibidas en tiempo real o casi en tiempo real pueden tardar hasta 15 minutos. Las visitas recibidas con una marca de hora de ayer pueden tardar hasta 2 horas. Las visitas más antiguas pueden tardar más tiempo, aumentando cada día hasta un máximo de aproximadamente 24 horas.

## Formas de mitigar o prevenir la latencia

Existen varias estrategias para evitar la latencia o reducir el tiempo de recuperación cuando se produce:

* **** Notificar a Adobe de los picos de tráfico esperados: Aunque es imposible anticipar cada pico de tráfico en el sitio, puede haber casos en los que espere recibir un aumento significativo de tráfico. Algunos ejemplos son un período festivo particularmente exitoso o poco después de una gran campaña push. En estos casos, Adobe proporciona un método para que su organización nos informe de los incrementos de tráfico esperados. De este modo podremos asignar recursos de procesamiento adicionales a su grupo de informes. Consulte [Programar un pico](../admin/c-traffic-management/t-traffic-schedule-spike.md) de tráfico en la guía del usuario de administración para obtener información sobre cómo notificar a Adobe sobre el aumento de tráfico.
* **** Considere la carga de procesamiento al activar nuevas funciones: Algunas funciones requieren más procesamiento que otras. Cuantas más características haya habilitadas en un grupo de informes, más difícil será recuperarse de la latencia. Cuando active características en un grupo de informes, tenga en cuenta que las siguientes características incrementan la cantidad de datos que se deben procesar:

   * Implementación de más de 20 eventos en la misma página
   * Reglas de VISTA complejas
   * Más de 20 valores en la variable de productos
   * Serialización de eventos

* Enable IAB Bot filtering: [Bot filtering](https://marketing.adobe.com/resources/help/en_US/admin/c_bot_rules.html) can greatly reduce latency if your report suite is frequented by bots or crawlers. Se recomienda utilizar la lista de bots de la IAB, actualizada y mantenida por la asociación [Interactive Advertising Bureau](https://www.iab.net/about_the_iab). Un usuario puede personalizar sus propias reglas de bots para complementar las de la IAB.

## Qué hacer con la latencia

En los casos en los que se produce latencia, tenga la seguridad de que Adobe supervisa de forma proactiva la canalización de procesamiento y hace todo lo posible para devolver el tiempo de procesamiento a la normalidad lo antes posible. Muchos de los problemas de latencia se resuelven en unas horas. Para obtener información sobre un grupo de informes determinado, debe solicitarse a un usuario de asistencia técnica de la organización que averigüe el ID del grupo de informes que está experimentando la latencia y que se ponga en contacto con el Servicio de atención al cliente. El representante de Adobe puede validar la latencia e informará al usuario cuando el problema mejore y se resuelva.
