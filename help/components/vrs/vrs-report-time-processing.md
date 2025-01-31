---
description: El procesamiento de intervalo de tiempo es una configuración de los grupos de informes virtuales que permite procesar los datos de una forma retroactiva y no destructiva.
title: Procesamiento de tiempo de los informes
role: Admin
solution: Analytics
feature: VRS
exl-id: 3742b9d1-f1fb-4690-bd44-b4719ff9d9bc
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '1319'
ht-degree: 68%

---

# Procesamiento de tiempo de los informes

[!UICONTROL Procesamiento de intervalo de tiempo] es una configuración de grupo de informes virtuales que permite procesar datos en Analysis Workspace de una manera retroactiva y no destructiva.

El [!UICONTROL Procesamiento de intervalo de tiempo] solo afecta a los datos en el grupo de informes virtuales y no tiene efecto sobre ningún dato o recopilación de datos en el grupo de informes base. La diferencia entre el [!UICONTROL Procesamiento de intervalo de tiempo] y el procesamiento tradicional de Analytics se entiende mejor con el siguiente diagrama:

![Canalización de procesamiento tradicional](assets/google1.jpg)

Durante el procesamiento de datos de Analytics, los datos fluyen por el canal de recopilación de datos hasta un paso de preprocesamiento que los prepara para la realización de informes. Este paso de preprocesamiento aplica lógica de caducidad de visitas y de persistencia de eVars (entre otras cosas) a los datos que se van recopilando. La principal desventaja de este modelo de preprocesamiento es que requiere que la configuración esté completada antes de recabar los datos. Por tanto, cualquier cambio realizado en la configuración de preprocesamiento solo se aplica a los nuevos datos desde ese momento en adelante. Esto puede suponer un problema si los datos no llegan ordenados, o si la configuración presenta errores.

El [!UICONTROL Procesamiento de intervalo de tiempo] es un modo fundamentalmente distinto de procesar datos de Analytics para la creación de informes. En lugar de predeterminar la lógica de procesamiento antes de la recopilación de datos, Analytics ignora el conjunto de datos durante el paso de preprocesamiento y aplica la lógica cada vez que se ejecuta un informe:

![Canalización de procesamiento de tiempo de informes](assets/google2.jpg)

Esta arquitectura de procesamiento ofrece opciones de realización de informes mucho más flexibles. Por ejemplo, puede cambiar el tiempo de espera de visita a cualquier periodo que desee de forma no destructiva, cambios que se reflejan en la persistencia de eVar y en los contenedores de segmentos durante el periodo completo del informe. Además, puede crear cualquier número de grupos de informes virtuales, cada uno con distintas opciones de Procesamiento de intervalo de tiempo y basados en el mismo grupo de informes base, sin alterar ninguno de los datos del grupo de informes base.

[!UICONTROL Procesamiento de intervalo de tiempo] también permite a Analytics impedir que las visitas en segundo plano comiencen nuevas visitas y permite que [Adobe Experience Platform Mobile SDK](https://experienceleague.adobe.com/docs/mobile.html?lang=es) inicie una nueva visita cada vez que se active un evento de inicio de aplicación.

## Opciones de configuración

Los grupos de informes virtuales con Procesamiento de intervalo de tiempo habilitado disponen en este momento de las siguientes opciones de configuración:

* **[!UICONTROL Tiempo de espera de visita]:** el tiempo de espera de visita es la cantidad de inactividad que un visitante único debe presentar antes de que se inicie automáticamente una nueva visita. El valor predeterminado es de 30 minutos. Por ejemplo, si establece el tiempo de espera de visita en 15 minutos, se crea un nuevo grupo de visitas por cada secuencia de visitas obtenida separada de la anterior por al menos 15 minutos de inactividad. Estos ajustes afectan no solo al recuento de visitas, sino también al modo de evaluar los contenedores de segmentos de visita y a la lógica de caducidad de visitas para cualquier eVar que caduque durante una visita. Reducir el tiempo de espera de visita probablemente aumente el número total de visitas en los informes, y viceversa.
* **[!UICONTROL Configuración de visitas de aplicación móvil]:** para los grupos de informes que contienen datos generados por aplicaciones móviles mediante los [SDK para móviles de Adobe](https://experienceleague.adobe.com/docs/mobile.html?lang=es) existen ajustes de visita adicionales. Dichos ajustes no son destructivos y afectan únicamente a las visitas recopiladas mediante los SDK para móviles. Estos ajustes no tienen efecto en los datos recopilados fuera del SDK para móviles.
* **[!UICONTROL Impedir que las visitas en segundo plano inicien una nueva visita]:** los SDK para móviles recopilan las visitas en segundo plano cuando la aplicación está en segundo plano.
* **[!UICONTROL Iniciar una nueva visita cada vez que se inicie la aplicación]:** además del tiempo de espera de visita, es posible forzar el comienzo de una visita cada vez que se registra un evento de inicio de aplicación procedente de los SDK para móviles, independientemente del tiempo de inactividad. Esta configuración afecta a la métrica de visitas y al contenedor de segmentos de visita, así como a la lógica de caducidad de visitas de las eVars.
* **[!UICONTROL Iniciar una nueva visita con el evento]:** una nueva sesión se inicia cuando se activa un evento, independientemente de si se ha superado o no el tiempo de espera de la sesión. La sesión recién creada incluye el evento que la ha iniciado. Además, es posible utilizar varios eventos para iniciar una sesión, y se activa una nueva si se observa cualquiera de esos eventos en los datos. Este ajuste afecta al recuento de visitas, al contenedor de segmentación de visitas y a la lógica de caducidad de las visitas en eVars.


>[!BEGINSHADEBOX]

Vea ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Inicio de una nueva visita con evento](https://video.tv.adobe.com/v/23129?quality=12&learn=on){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]



## Limitaciones del Procesamiento de intervalo de tiempo

El Procesamiento de intervalo de tiempo no admite todas las métricas y dimensiones disponibles en la creación de informes tradicional de Analytics. Solo se puede acceder a los grupos de informes virtuales que utilizan Procesamiento de intervalo de tiempo desde Analysis Workspace. No es posible hacerlo desde Data Warehouse, Report Builder, Fuentes de datos o la API de informes.

Además, Procesamiento de intervalo de tiempo solo procesa los datos que se producen dentro del intervalo de fechas del informe (lo que se refiere como “limitación de fechas” más adelante). Esto significa que los valores de eVar establecidos para no caducar nunca para un visitante antes de intervalo de fechas del informe no persisten hasta el periodo del informe y no aparecen en este. También significa que las mediciones de lealtad de los clientes se basan exclusivamente en los datos presentes en el intervalo de fechas del informe, y no en el historial completo anterior a dicho intervalo.

Las siguientes dimensiones y métricas no son compatibles con Procesamiento de intervalo de tiempo:

* **Analytics for Target**
* **Métricas/dimensiones de Analytics for Advertising Cloud**
* **eVars de contador**
* [**Días antes de la primera compra**](/help/components/dimensions/days-before-first-purchase.md)
* [**Días desde la última compra**](/help/components/dimensions/days-since-last-purchase.md)
* [**Días transcurridos desde la última visita**](/help/components/dimensions/days-since-last-visit.md)
* **Página de entrada original**
* **eVars de asignación lineal**
* **Variables de lista**
* [**Dimensiones de los canales de marketing**](/help/components/dimensions/marketing-channel.md)
* [**Dominio de referencia original**](/help/components/dimensions/original-referring-domain.md)
* [**Frecuencia de retorno**](/help/components/dimensions/return-frequency.md)
* [**Acceso único**](/help/components/metrics/single-access.md)
* **Fuentes de datos de ID de transacción**
* [**Número de visita**](/help/components/dimensions/visit-number.md)

## Dimensiones y métricas afectadas

A continuación se ofrece una lista de dimensiones y métricas que pueden verse afectadas por la configuración seleccionada para Procesamiento de intervalo de tiempo:

* Si “Impedir que las visitas en segundo plano inicien una nueva visita” está habilitado, se producirán los siguientes cambios: Consulte [Creación de sesiones según el contexto](vrs-mobile-visit-processing.md) para obtener más información.
   * [**Devoluciones**](/help/components/metrics/bounces.md) / [**Tasa de devoluciones:**](/help/components/metrics/bounce-rate.md) Las visitas en segundo plano que no van seguidas de una visita en primer plano no se consideran una devolución y no contribuyen a la tasa de devoluciones.
   * [**Tiempo empleado en segundos por visita:**](/help/components/metrics/time-spent-per-visit.md) Solo las visitas que incluyen visitas individuales que se producen en primer plano contribuyen a esta métrica.
   * **Tiempo empleado por visita:** Solo las visitas que incluyen visitas individuales en primer plano contribuyen a esta métrica.
   * [**Métrica de entrada**](/help/components/metrics/entries.md) / [**Métrica de salida:**](/help/components/metrics/exits.md) En esta dimensión solo aparecen las entradas y salidas de visitas con visitas en primer plano.
   * [**Dimensión de entrada**](/help/components/dimensions/entry-dimensions.md) / [**Dimensiones de salida:**](/help/components/dimensions/exit-dimensions.md) En esta dimensión solo aparecen las entradas y salidas de visitas con visitas en primer plano.
   * [**Métrica de visitantes únicos:**](/help/components/metrics/unique-visitors.md) En los visitantes únicos no se incluyen los visitantes que solo tuvieron visitas individuales en segundo plano en el intervalo de fechas del informe.
* [**Visitas:**](/help/components/metrics/visits.md) Las visitas reflejan cualquier configuración del grupo de informes virtuales, que pueden diferir de las del grupo de informes base.
* **Eventos serializados con ID de evento:** Los duplicados de los eventos que utilizan la serialización de eventos con un ID de evento solo se eliminan en el caso de los eventos que se producen dentro del intervalo de fechas del informe para un visitante. Los duplicados de estos eventos no se eliminan en todas las fechas o visitantes globalmente debido a la limitación de fechas del Procesamiento de intervalo de tiempo.
* **Compras** / [**Ingresos**](/help/components/metrics/revenue.md) / [**Pedidos**](/help/components/metrics/orders.md) / [**Unidades:**](/help/components/metrics/units.md) Cuando se usa el ID de compra, estas métricas solo se deduplican para los ID de compra duplicados que se producen dentro del intervalo de fechas del informe para un visitante, en lugar de en todas las fechas o visitantes globalmente debido a la limitación de fechas del Procesamiento de intervalo de tiempo.
* [**eVars que no son de comercialización**](/help/components/dimensions/evar.md) / **eVars reservadas:** Los valores establecidos en un eVar persisten solamente si el valor se estableció dentro del intervalo de fechas del informe debido a la limitación de fechas del Procesamiento de intervalo de tiempo. Además, las caducidades basadas en la hora pueden producirse 60 minutos antes o después si la persistencia se ve afectada por un cambio de hora.
* [**eVars de comercialización**](/help/components/dimensions/evar-merchandising.md) / **eVars reservadas:** Ver arriba. Además, para la conversión de sintaxis, cuando el enlace está establecido en “cualquier evento”, se utiliza “cualquier visita”.
* [**Tipo de visita individual:**](/help/components/dimensions/hit-type.md) Esta dimensión especifica si una visita individual es en primer o en segundo plano.
* **Dimension con (poco tráfico) o &quot;excesos en la cantidad de valores exclusivos&quot;:** El elemento de línea (poco tráfico) se determina de manera ligeramente diferente al usar Procesamiento de intervalo de tiempo y no se garantiza que coincida con lo que se observa al generar informes en el grupo de informes base. No se garantiza que los elementos de línea del Dimension que no forman parte de Poco tráfico representen el 100 % de los datos de ese elemento de línea. Estas diferencias pueden ser más pronunciadas cuanto mayor sea el número de valores únicos existentes en una dimensión.
