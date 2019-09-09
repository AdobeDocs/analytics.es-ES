---
description: El procesamiento de intervalo de tiempo es una configuración de grupo de informes virtuales que permite procesar datos de forma retroactiva y no destructiva.
seo-description: El procesamiento de intervalo de tiempo es una configuración de grupo de informes virtuales que permite procesar datos de forma retroactiva y no destructiva.
seo-title: Procesamiento de tiempo de los informes
title: Procesamiento de tiempo de los informes
uuid: 1 a 1 d 82 ea -8 c 93-43 cc -8689-cdcf 59 c 309 b 1
translation-type: tm+mt
source-git-commit: 658aba8a456f5760d4871fdc941150d64e9e2e94

---


# Procesamiento de tiempo de los informes

El procesamiento de intervalo de tiempo es una configuración de grupo de informes virtuales que permite procesar datos de forma retroactiva y no destructiva.

> [!NOTE] Procesamiento de intervalo de tiempo solo está disponible para Analysis Workspace.

Procesamiento de intervalo de tiempo solo afecta a los datos en el grupo de informes virtuales y no tiene efecto sobre ningún dato o recopilación de datos en el grupo de informes base. La diferencia entre Procesamiento de intervalo de tiempo y el procesamiento tradicional de Analytics se entiende mejor con el siguiente diagrama:

![Google1](assets/google1.jpg)

Durante el procesamiento de datos de Analytics, los datos fluyen por el canal de recopilación de datos hasta un paso de preprocesamiento que los prepara para la realización de informes. Este paso de preprocesamiento aplica lógica de caducidad de visitas y de persistencia de eVars (entre otras cosas) a los datos que se van recopilando. La principal desventaja de este modelo de preprocesamiento es que requiere que la configuración esté completada antes de recabar los datos. Por tanto, cualquier cambio realizado en la configuración de preprocesamiento solo se aplica a los nuevos datos desde ese momento en adelante. Esto puede suponer un problema si los datos no llegan ordenados, o si la configuración presenta errores.

Procesamiento de intervalo de tiempo es un modo fundamentalmente distinto de procesar datos de Analytics para la realización de informes. En lugar de predeterminar la lógica de procesamiento antes de la recopilación de datos, Analytics ignora el conjunto de datos durante el paso de preprocesamiento y aplica la lógica cada vez que se ejecuta un informe:

![Google2](assets/google2.jpg)

Esta arquitectura de procesamiento ofrece opciones de realización de informes mucho más flexibles. Por ejemplo, puede cambiar el tiempo de espera de visita a cualquier periodo que desee de forma no destructiva, cambios que se reflejan retroactivamente en la persistencia de eVars y los contenedores de segmentos, como si estos ajustes se hubieran aplicado antes de la recopilación de los datos. Además, puede crear cualquier número de grupos de informes virtuales, cada uno con distintas opciones de Procesamiento de intervalo de tiempo y basados en el mismo grupo de informes base, sin alterar ninguno de los datos del grupo de informes base.

Procesamiento de intervalo de tiempo también permite a Analytics impedir que las visitas en segundo plazo comiencen nuevas visitas, y permite al [SDK para móviles](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) indicar a la creación de informes que inicie una nueva visita cada vez que se active un evento de inicio de aplicación.

Los grupos de informes virtuales con Procesamiento de intervalo de tiempo habilitado disponen en este momento de las siguientes opciones de configuración:

* **Tiempo de espera de visita:** El valor de tiempo de espera de visita define la cantidad de inactividad que debe tener un visitante único antes de que se inicie automáticamente una nueva visita. El valor predeterminado es de 30 minutos. Por ejemplo, si establece el tiempo de espera de visita en 15 minutos, se crea un nuevo grupo de visitas por cada secuencia de visitas obtenida separada de la anterior por al menos 15 minutos de inactividad. Estos ajustes afectan no solo al recuento de visitas, sino también al modo de evaluar los contenedores de segmentos de visita y a la lógica de caducidad de visitas para cualquier eVar que caduque durante una visita. Reducir el tiempo de espera de visita probablemente aumente el número total de visitas en los informes, y viceversa.
* **Configuración de visitas de aplicaciones móviles:** Para los grupos de informes que contienen datos generados por aplicaciones móviles a través de los SDK de [Adobe Mobile](https://www.adobe.io/apis/cloudplatform/mobile.html), están disponibles los ajustes de visitas adicionales. Dichos ajustes no son destructivos y afectan únicamente a las visitas recopiladas mediante los SDK para móviles. Estos ajustes no tienen efecto en los datos recopilados fuera del SDK para móviles.
* **Impedir que las visitas en segundo plano inicien una nueva visita:** Los SDK para móviles recopilan visitas en segundo plano cuando la aplicación está en segundo plano.
* **Iniciar una nueva visita en cada inicio de aplicación:** Además del tiempo de espera de visita, puede forzar que una visita comience cada vez que se registra un evento de inicio de aplicación desde los SDK de Mobile independientemente de la ventana de inactividad. Esta configuración afecta a la métrica de visitas y al contenedor de segmentos de visita, así como a la lógica de caducidad de visitas de las eVars.
* **Iniciar nueva visita con evento:** Una nueva sesión se inicia cuando se activa un evento, independientemente de si se ha agotado el tiempo de espera de una sesión. La sesión recién creada incluye el evento que la ha iniciado. Además, es posible utilizar varios eventos para iniciar una sesión, y se activa una nueva si se observa en los datos cualquiera de esos eventos. Este ajuste afecta al recuento de visitas, al contenedor de segmentación de visitas y a la lógica de caducidad de las visitas en eVars.

Procesamiento de intervalo de tiempo no admite todas las métricas y dimensiones disponibles en los informes tradicionales de Analytics. Virtual report suites utilizing Report Time Processing are only accessible in Analysis Workspace and will not be accessible in [!UICONTROL Reports &amp; Analytics], Ad Hoc Analysis, Data Warehouse, Report Builder, Data Feeds, or the reporting API.

Además, Procesamiento de intervalo de tiempo solo procesa los datos que se producen dentro del intervalo de fechas del informe (lo que se refiere como “limitación de fechas” más adelante). Esto significa que los valores de eVar establecidos para no caducar nunca para un visitante antes de intervalo de fechas del informe no persisten hasta el periodo del informe y no aparecen en este. También significa que las mediciones de lealtad de los clientes se basan exclusivamente en los datos presentes en el intervalo de fechas del informe, y no en el historial completo anterior a dicho intervalo.

A continuación se ofrece una lista de métricas y dimensiones que en este momento no son compatibles con Procesamiento de intervalo de tiempo:

* **Analytics para Target:** Actualmente no se admite. Está prevista la compatibilidad futura.
* **Analytics para métricas/dimensiones reservadas de Marketing Cloud:** Actualmente no se admite. Está prevista la compatibilidad futura.
* **Métrica de acceso único:** Permanentemente no compatible.
* **Variables de lista:** Actualmente no se admite. Está prevista la compatibilidad futura.
* **Evars de contador:** Permanentemente no compatible.
* **Variables de canales de mercadotecnia:** Actualmente no se admite. Está prevista la compatibilidad futura.
* **Dimensión Días desde la última compra:** Debido a la naturaleza de la limitación de fechas de Procesamiento de intervalo de tiempo, esta dimensión no es compatible.
* **Dimensión Días antes de la primera compra:** Debido a la naturaleza de la limitación de fechas de Procesamiento de intervalo de tiempo, esta dimensión no es compatible.
* **Dimensión Frecuencia de retorno:** Debido a la naturaleza de la limitación de fechas de Procesamiento de intervalo de tiempo, esta dimensión no es compatible. Se puede utilizar un enfoque alternativo empleando una métrica de recuento de visitas en un segmento, o utilizando la métrica de visitas en un informe de histograma.
* **Dimensión Días desde la última visita:** Debido a la naturaleza de la limitación de fechas de Procesamiento de intervalo de tiempo, esta dimensión no es compatible.
* **Dimensión original de la página de entrada:** Debido a la naturaleza de la limitación de fechas de Procesamiento de intervalo de tiempo, esta dimensión no es compatible.
* **Evars de asignación lineal:** Actualmente no se admite. Está prevista la compatibilidad futura.
* **Dimensión del dominio de referencia original:** Actualmente no se admite. Está prevista la compatibilidad futura.
* **Número de visita:** Debido a la naturaleza de la limitación de fechas de Procesamiento de intervalo de tiempo, esta métrica no es compatible. Como alternativa en las aplicaciones móviles, puede utilizar una métrica calculada que incluya visitantes/visitas con la métrica Instalación de aplicación para identificar nuevos visitantes o visitas.
* **Fuentes de datos de ID de transacción:** Actualmente no se admite. Está prevista la compatibilidad futura.

A continuación se ofrece una lista de dimensiones y métricas que pueden verse afectadas por la configuración seleccionada para Procesamiento de intervalo de tiempo:

* Si «Impedir que las visitas en segundo plano inicien una nueva visita» está habilitado, se producen los cambios siguientes. Consulte [Sesionización según el contexto](vrs-mobile-visit-processing.md) para obtener más información.
   * **Devoluciones/Tasa de salida hacia otro sitio:** Las visitas en segundo plano no seguidas por una visita en primer plano no se consideran una devolución y no contribuyen a la tasa de devoluciones.
   * **Tiempo empleado segundos por visita:** Solo las visitas que incluyen visitas en primer plano contribuyen a esta métrica.
   * **Tiempo empleado por visita:** Solo las visitas que incluyen visitas en primer plano contribuyen a esta métrica.
   * **Dimensiones de entrada/salida y métricas:** En esta dimensión solo aparecen las entradas y salidas de visitas con visitas en primer plano.
   * **Métrica Visitantes únicos:** Los visitantes únicos no incluyen a los visitantes que solo tuvieron visitas en segundo plano en el intervalo de fechas del informe.
* **Visitas:** Las visitas reflejan cualquier configuración que haya configurado el grupo de informes virtuales, que puede ser diferente del grupo de informes base.
* **Eventos serializados con ID de evento:** Los eventos que utilizan serialización de eventos con un ID de evento solo se deduplican para los eventos que se producen dentro del intervalo de fechas del informe para un visitante. Estos eventos no se eliminan en todas las fechas o visitantes globalmente debido a la limitación de fechas de Procesamiento de intervalo de tiempo.
* **Compras/Ingresos/Pedidos/Unidades:** Cuando se utiliza la ID de compra, estas métricas solo se deduplican para los ID de compra duplicados que se producen dentro del intervalo de fechas del informe para un visitante, en lugar de para todos los visitantes y la fecha globalmente debido a la limitación de fechas de Procesamiento de intervalo de tiempo.
* **Evars no comercializadas/evars reservadas:** Los valores establecidos en una evar solo persisten si el valor se estableció dentro del intervalo de fechas del informe debido a la limitación de fechas de Procesamiento de intervalo de tiempo. Además, las caducidades basadas en el tiempo pueden caducar una hora antes o una hora si la persistencia abarca un cambio de horario de verano.
* **Evars de comercialización/evars reservadas:** Véase más arriba. Además, para la conversión de sintaxis, cuando el enlace está establecido en “cualquier evento”, se utiliza “cualquier visita”.
* **Tipo de visita:** Esta dimensión especifica si una visita es en primer o en segundo plano.
