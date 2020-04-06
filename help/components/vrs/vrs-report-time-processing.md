---
description: El procesamiento de intervalo de tiempo es una configuración de los grupos de informes virtuales que permite procesar los datos de una forma retroactiva y no destructiva.
title: Procesamiento de tiempo de los informes
uuid: 1a1d82ea-8c93-43cc-8689-cdcf59c309b1
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Procesamiento de tiempo de los informes

El procesamiento de intervalo de tiempo es una configuración de los grupos de informes virtuales que permite procesar los datos de una forma retroactiva y no destructiva.

>[!NOTE] El procesamiento de intervalo de tiempo solo está disponible para Analysis Workspace.

Procesamiento de intervalo de tiempo solo afecta a los datos del grupo de informes virtuales y no afecta a ningún dato o recopilación de datos del grupo de informes base. La diferencia entre Procesamiento de intervalo de tiempo y el procesamiento tradicional de Analytics se comprende mejor mediante el siguiente diagrama:

![Google1](assets/google1.jpg)

Durante el procesamiento de datos de Analytics, los datos fluyen a través de la canalización de recopilación de datos y a un paso de preprocesamiento que prepara los datos para su sistema de informes. Este paso de preprocesamiento aplica la lógica de caducidad de visitas y la lógica de persistencia de eVar (entre otras cosas) a los datos a medida que se recopilan. La principal desventaja de este modelo de preprocesamiento es que requiere que cualquier configuración se realice con antelación antes de recopilar los datos. Esto significa que cualquier cambio en la configuración de preprocesamiento solo se aplica a los nuevos datos a partir de ese momento. Esto es problemático si los datos llegan desordenados o si la configuración no está bien configurada.

Procesamiento de intervalo de tiempo es una forma fundamentalmente distinta de procesar datos de Analytics para sistema de informes. En lugar de predeterminar la lógica de procesamiento antes de la recopilación de datos, Analytics ignora el conjunto de datos durante el paso de preprocesamiento y aplica la lógica cada vez que se ejecuta un informe:

![Google2](assets/google2.jpg)

Esta arquitectura de procesamiento permite opciones de sistema de informes mucho más flexibles. Por ejemplo: puede cambiar el período de tiempo de espera de visita a cualquier período de tiempo que desee de manera no destructiva y esos cambios se reflejan en la persistencia de la eVar y en los contenedores de segmentos de forma retroactiva como si hubiera aplicado esa configuración antes de que se recopilaran los datos. Además, puede crear cualquier número de grupos de informes virtuales, cada uno con diferentes opciones de Procesamiento de intervalo de tiempo basadas en el mismo grupo de informes base, sin alterar ninguno de los datos del grupo de informes base.

Procesamiento de intervalo de tiempo también permite a Analytics evitar que las visitas en segundo plano inicien nuevas visitas y permite al SDK [](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) móvil indicar a sistema de informes que realice un inicio de una nueva visita cada vez que se active un evento de inicio de aplicación.

Los grupos de informes virtuales con Procesamiento de intervalo de tiempo habilitado disponen actualmente de las siguientes opciones de configuración:

* **Tiempo de espera de visita:** El tiempo de espera de visita es la cantidad de inactividad que un visitante exclusivo debe presentar antes de que se inicie automáticamente una nueva visita. El valor predeterminado es de 30 minutos. Por ejemplo, si establece el tiempo de espera de visita en 15 minutos, se crea un nuevo grupo de visitas para cada secuencia de visitas recopiladas, separadas por 15 minutos de inactividad. Esta configuración afecta no sólo a los recuentos de visitas, sino también a la forma en que se evalúan los contenedores de los segmentos de visitas y a la lógica de caducidad de las visitas para cualquier eVar que caduque en la visita. Reducir el tiempo de espera de visita probablemente aumente el número total de visitas en el sistema de informes, mientras que aumentar el tiempo de espera de visita probablemente disminuirá el número total de visitas en el sistema de informes.
* **Configuración de visitas de aplicación móvil:** Para los grupos de informes que contienen datos generados por aplicaciones móviles mediante los [SDK para móviles de Adobe](https://www.adobe.io/apis/cloudplatform/mobile.html), existen ajustes de visita adicionales. Esta configuración no es destructiva y solo afecta a las visitas recopiladas mediante los SDK para móviles. Esta configuración no afecta a los datos recopilados fuera del SDK de Mobile.
* **Impedir que las visitas en segundo plano inicien una nueva visita:** Los SDK para móviles recopilan las visitas en segundo plano cuando la aplicación está en segundo plano.
* **Iniciar una nueva visita cada vez que se inicie la aplicación:** Además del tiempo de espera de visita, es posible forzar el comienzo de una visita cada vez que se registra un evento de inicio de aplicación procedente de los SDK para móviles, independientemente del tiempo de inactividad. Esta configuración afecta a la métrica de visitas y al contenedor de segmentos de visita, así como a la lógica de caducidad de visitas de las eVars.
* **Iniciar una nueva visita con el evento:** Una nueva sesión se inicia cuando se activa un evento, independientemente de si se ha superado o no el tiempo de espera de la sesión. La sesión recién creada incluye el evento que la inició. Además, puede utilizar varios eventos para el inicio de una sesión y se activa una nueva si se observa alguno de esos eventos en los datos. Esta configuración afectará el recuento de visitas, el contenedor de segmentación de visitas y la lógica de caducidad de visitas en las eVars.

Procesamiento de intervalo de tiempo no admite todas las métricas y dimensiones disponibles en los informes tradicionales de Analytics. Solo se puede acceder a los grupos de informes virtuales que utilizan Procesamiento de intervalo de tiempo desde Analysis Workspace. No es posible hacerlo desde [!UICONTROL Reports & Analytics], Ad Hoc Analysis, Data Warehouse, Report Builder, Fuentes de datos o la API de informes.

Además, Procesamiento de intervalo de tiempo solo procesa los datos que provienen del intervalo de fechas del sistema de informes (denominado &quot;limitación de fechas&quot; más abajo). Esto significa que los valores de eVar establecidos en &quot;nunca caduca&quot; para un visitante antes del intervalo de fechas del sistema de informes no persisten en las ventanas de sistema de informes y no aparecen en los informes. Esto también significa que las mediciones de lealtad del cliente se basan exclusivamente en los datos presentes en el intervalo de fechas del sistema de informes y no en todo el historial anterior al intervalo de fechas del sistema de informes.

A continuación se muestra una lista de métricas y dimensiones que no se admiten actualmente al utilizar Procesamiento de intervalo de tiempo:

* **Analytics para Target:** Actualmente no es compatible. Está prevista la compatibilidad futura.
* **Métricas y dimensiones reservadas de Analytics para Advertising Cloud:** Actualmente no es compatible. Está prevista la compatibilidad futura.
* **Métrica de acceso único:** No es compatible de forma permanente.
* **Variables de lista:** Actualmente no es compatible. Está prevista la compatibilidad futura.
* **eVars de contador:** No es compatible de forma permanente.
* **Variables de canales de marketing:** Actualmente no es compatible. Está prevista la compatibilidad futura.
* **Dimensión de días desde la última compra:** Debido a la naturaleza de la limitación de fechas del Procesamiento de intervalo de tiempo, esta dimensión no es compatible.
* **Dimensión de días antes de la primera compra:** Debido a la naturaleza de la limitación de fechas del Procesamiento de intervalo de tiempo, esta dimensión no es compatible.
* **Dimensión de frecuencia de retorno:** Debido a la naturaleza de la limitación de fechas del Procesamiento de intervalo de tiempo, esta dimensión no es compatible. Se puede utilizar un enfoque alternativo empleando una métrica de recuento de visitas en un segmento, o utilizando la métrica de visitas en un informe de histograma.
* **Dimensión de días desde la última visita:** Debido a la naturaleza de la limitación de fechas del Procesamiento de intervalo de tiempo, esta dimensión no es compatible.
* **Dimensión original de página de entrada:** Debido a la naturaleza de la limitación de fechas del Procesamiento de intervalo de tiempo, esta dimensión no es compatible.
* **eVars de asignación lineal:** Actualmente no es compatible. Está prevista la compatibilidad futura.
* **Dimensión del dominio de referencia original:** Actualmente no es compatible. Está prevista la compatibilidad futura.
* **Número de visitas:** Debido a la naturaleza de la limitación de fechas del Procesamiento de intervalo de tiempo, esta métrica no es compatible. Como alternativa en las aplicaciones móviles, puede utilizar una métrica calculada que incluya visitantes/visitas con la métrica Instalación de la aplicación para identificar nuevos visitantes o visitas.
* **Fuentes de datos de ID de transacción:** Actualmente no es compatible. Está prevista la compatibilidad futura.

A continuación se muestra una lista de dimensiones y métricas que se ven afectadas según la configuración seleccionada para Procesamiento de intervalo de tiempo:

* Si “Impedir que las visitas en segundo plano inicien una nueva visita” está habilitado, se producirán los siguientes cambios: Consulte [Creación de sesiones según el contexto](vrs-mobile-visit-processing.md) para obtener más información.
   * **Devoluciones/Tasa de devoluciones:** Las visitas individuales en segundo plano que no van seguidas de una visita individual en primer plano no se consideran una devolución y no contribuyen a la tasa de devoluciones.
   * **Tiempo empleado en segundos por visita:** Solo las visitas que incluyen visitas individuales que se producen en primer plano contribuyen a esta métrica.
   * **Tiempo empleado por visita:** Solo las visitas que incluyen visitas individuales en primer plano contribuyen a esta métrica.
   * **Métricas y dimensiones de entrada y salida:** En esta dimensión solo aparecen las entradas y salidas de visitas con visitas individuales en primer plano.
   * **Métrica de visitantes únicos:** En los visitantes únicos no se incluyen los visitantes que solo tuvieron visitas individuales en segundo plano en el intervalo de fechas del informe.
* **Visitas:** Las visitas reflejan cualquier configuración del grupo de informes virtuales, que pueden diferir de las del grupo de informes base.
* **Eventos serializados con ID de evento:** Los duplicados de los eventos que utilizan la serialización de eventos con un ID de evento solo se eliminan en el caso de los eventos que se producen dentro del intervalo de fechas del informe para un visitante. Los duplicados de estos eventos no se eliminan en todas las fechas o visitantes globalmente debido a la limitación de fechas del Procesamiento de intervalo de tiempo.
* **Compras/Ingresos/Pedidos/Unidades:** Debido a la naturaleza de la limitación de fechas del Procesamiento de intervalo de tiempo, cuando se utiliza el ID de compra, los duplicados de estas métricas solo se eliminan para los ID de compra duplicados que se producen dentro del intervalo de fechas del informe para un visitante, y no en cualquier fecha y para cualquier visitante de forma global.
* **eVars que no sean de comercialización/eVars reservadas:** Debido a la naturaleza de la limitación de fechas del Procesamiento de intervalo de tiempo, un valor establecido en una eVar persiste solo si se estableció dentro del intervalo de fechas del informe. Además, las caducidades basadas en la hora pueden producirse 60 minutos antes o después si la persistencia se ve afectada por un cambio de hora.
* **eVars de comercialización/eVars reservadas:** Consulte lo anterior. Además, para la conversión de sintaxis, cuando el enlace está establecido en “cualquier evento”, se utiliza “cualquier visita”.
* **Tipo de visita individual:** Esta dimensión especifica si una visita individual es en primer o en segundo plano.
