---
description: El procesamiento de intervalo de tiempo es una configuración de grupo de informes virtuales que permite procesar datos de forma retroactiva y no destructiva.
seo-description: El procesamiento de intervalo de tiempo es una configuración de grupo de informes virtuales que permite procesar datos de forma retroactiva y no destructiva.
seo-title: Procesamiento de intervalo de tiempo
title: Procesamiento de intervalo de tiempo
uuid: 1 a 1 d 82 ea -8 c 93-43 cc -8689-cdcf 59 c 309 b 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Procesamiento de intervalo de tiempo

El procesamiento de intervalo de tiempo es una configuración de grupo de informes virtuales que permite procesar datos de forma retroactiva y no destructiva.

>[!NOTE]
>
>Procesamiento de intervalo de tiempo solo está disponible para Analysis Workspace.

Procesamiento de intervalo de tiempo solo afecta a los datos en el grupo de informes virtuales y no tiene efecto sobre ningún dato o recopilación de datos en el grupo de informes base. La diferencia entre Procesamiento de intervalo de tiempo y el procesamiento tradicional de Analytics se entiende mejor con el siguiente diagrama:

![](assets/google1.jpg)

Durante el procesamiento de datos de Analytics, los datos fluyen por el canal de recopilación de datos hasta un paso de preprocesamiento que los prepara para la realización de informes. Este paso de preprocesamiento aplica lógica de caducidad de visitas y de persistencia de eVars (entre otras cosas) a los datos que se van recopilando. La principal desventaja de este modelo de preprocesamiento es que requiere que la configuración esté completada antes de recabar los datos. Por tanto, cualquier cambio realizado en la configuración de preprocesamiento solo se aplica a los nuevos datos desde ese momento en adelante. Esto puede suponer un problema si los datos no llegan ordenados, o si la configuración presenta errores.

Procesamiento de intervalo de tiempo es un modo fundamentalmente distinto de procesar datos de Analytics para la realización de informes. En lugar de predeterminar la lógica de procesamiento antes de la recopilación de datos, Analytics ignora el conjunto de datos durante el paso de preprocesamiento y aplica la lógica cada vez que se ejecuta un informe:

![](assets/google2.jpg)

Esta arquitectura de procesamiento ofrece opciones de realización de informes mucho más flexibles. Por ejemplo, puede cambiar el tiempo de espera de visita a cualquier periodo que desee de forma no destructiva, cambios que se reflejan retroactivamente en la persistencia de eVars y los contenedores de segmentos, como si estos ajustes se hubieran aplicado antes de la recopilación de los datos. Además, puede crear cualquier número de grupos de informes virtuales, cada uno con distintas opciones de Procesamiento de intervalo de tiempo y basados en el mismo grupo de informes base, sin alterar ninguno de los datos del grupo de informes base.

Procesamiento de intervalo de tiempo también permite a Analytics impedir que las visitas en segundo plazo comiencen nuevas visitas, y permite al [SDK para móviles](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) indicar a la creación de informes que inicie una nueva visita cada vez que se active un evento de inicio de aplicación.

Los grupos de informes virtuales con Procesamiento de intervalo de tiempo habilitado disponen en este momento de las siguientes opciones de configuración:

<table id="table_C086C5FD10A84A1ABC081F5DE28F802D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuración </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Tiempo de espera de visita </p> </td> 
   <td colname="col2"> <p> El tiempo de espera de visita es la cantidad de inactividad que un visitante exclusivo debe presentar antes de que se inicie automáticamente una nueva visita. El valor predeterminado es de 30 minutos. Por ejemplo, si establece el tiempo de espera de visita en 15 minutos, se crea un nuevo grupo de visitas por cada secuencia de visitas obtenida separada de la anterior por al menos 15 minutos de inactividad. Estos ajustes afectan no solo al recuento de visitas, sino también al modo de evaluar los contenedores de segmentos de visita y a la lógica de caducidad de visitas para cualquier eVar que caduque durante una visita. Reducir el tiempo de espera de visita probablemente aumente el número total de visitas en los informes, y viceversa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Configuración de visitas de la aplicación móvil </p> </td> 
   <td colname="col2"> <p> Para los grupos de informes que contienen datos generados por aplicaciones móviles mediante los <a href="https://www.adobe.io/apis/cloudplatform/mobile.html" format="html" scope="external">SDK para móviles de Adobe</a>, existen ajustes de visita adicionales. Dichos ajustes no son destructivos y afectan únicamente a las visitas recopiladas mediante los SDK para móviles. Estos ajustes no tienen efecto en los datos recopilados fuera del SDK para móviles. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Impedir que las visitas en segundo plano inicien una nueva visita </p> </td> 
   <td colname="col2"> <p> Los SDK para móviles recopilan visitas en segundo plano cuando la aplicación está en segundo plano. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Comenzar una nueva visita con cada inicio de aplicación </p> </td> 
   <td colname="col2"> <p> Además del tiempo de espera de visita, es posible forzar el comienzo de una visita cada vez que se registra un evento de inicio de aplicación procedente de los SDK para móviles, independientemente del tiempo de inactividad. Esta configuración afecta a la métrica de visitas y al contenedor de segmentos de visita, así como a la lógica de caducidad de visitas de las eVars. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Comenzar una nueva visita con un evento </p> </td> 
   <td colname="col2"> <p>Una nueva sesión se inicia cuando se activa un evento, independientemente de si se ha superado o no el tiempo de espera de la sesión. La sesión recién creada incluye el evento que la ha iniciado. Además, es posible utilizar varios eventos para iniciar una sesión, y se activa una nueva si se observa en los datos cualquiera de esos eventos. Este ajuste afecta al recuento de visitas, al contenedor de segmentación de visitas y a la lógica de caducidad de las visitas en eVars. </p> </td> 
  </tr> 
 </tbody> 
</table>

Procesamiento de intervalo de tiempo no admite todas las métricas y dimensiones disponibles en los informes tradicionales de Analytics. Virtual report suites utilizing Report Time Processing are only accessible in Analysis Workspace and will not be accessible in [!UICONTROL Reports &amp; Analytics], Ad Hoc Analysis, Data Warehouse, Report Builder, Data Feeds, or the reporting API.

Además, Procesamiento de intervalo de tiempo solo procesa los datos que se producen dentro del intervalo de fechas del informe (lo que se refiere como “limitación de fechas” más adelante). Esto significa que los valores de eVar establecidos para no caducar nunca para un visitante antes de intervalo de fechas del informe no persisten hasta el periodo del informe y no aparecen en este. También significa que las mediciones de lealtad de los clientes se basan exclusivamente en los datos presentes en el intervalo de fechas del informe, y no en el historial completo anterior a dicho intervalo.

A continuación se ofrece una lista de métricas y dimensiones que en este momento no son compatibles con Procesamiento de intervalo de tiempo:

<table id="table_127AFE8FA1BE4F2BAB3975CA12A2FA47"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre de la métrica/dimensión </th> 
   <th colname="col2" class="entry"> Notas sobre Procesamiento de intervalo de tiempo </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Analytics para Target </p> </td> 
   <td colname="col2"> <p> No compatible en este momento. Está prevista la compatibilidad futura. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Métricas/dimensiones AMO reservadas </p> </td> 
   <td colname="col2"> <p> No compatible en este momento. Está prevista la compatibilidad futura. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Métrica de un solo acceso </p> </td> 
   <td colname="col2"> <p> No compatible ahora y tampoco en el futuro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Vars de lista </p> </td> 
   <td colname="col2"> <p> No compatible en este momento. Está prevista la compatibilidad futura. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> eVars de contador </p> </td> 
   <td colname="col2"> <p> No compatible ahora y tampoco en el futuro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Variables de canales de marketing </p> </td> 
   <td colname="col2"> <p> No compatible en este momento. Está prevista la compatibilidad futura. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimensión Días desde la última compra </p> </td> 
   <td colname="col2"> <p> Debido a la naturaleza de la limitación de fechas de Procesamiento de intervalo de tiempo, esta dimensión no es compatible. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimensión Días antes de la primera compra </p> </td> 
   <td colname="col2"> <p> Debido a la naturaleza de la limitación de fechas de Procesamiento de intervalo de tiempo, esta dimensión no es compatible. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimensión Frecuencia de retorno </p> </td> 
   <td colname="col2"> <p> Debido a la naturaleza de la limitación de fechas de Procesamiento de intervalo de tiempo, esta dimensión no es compatible. </p> <p> Se puede utilizar un enfoque alternativo empleando una métrica de recuento de visitas en un segmento, o utilizando la métrica de visitas en un informe de histograma. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimensión Días desde la última visita </p> </td> 
   <td colname="col2"> <p> Debido a la naturaleza de la limitación de fechas de Procesamiento de intervalo de tiempo, esta dimensión no es compatible. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimensión Original de página de entrada </p> </td> 
   <td colname="col2"> <p> Debido a la naturaleza de la limitación de fechas de Procesamiento de intervalo de tiempo, esta dimensión no es compatible. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> eVars de asignación lineal </p> </td> 
   <td colname="col2"> <p> No compatible en este momento. Está prevista la compatibilidad futura. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimensión Dominio de referencia original </p> </td> 
   <td colname="col2"> <p> No compatible en este momento. Está prevista la compatibilidad futura. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Número de visitas </p> </td> 
   <td colname="col2"> <p> Debido a la naturaleza de la limitación de fechas de Procesamiento de intervalo de tiempo, esta métrica no es compatible. </p> <p> Para informar del número de visitantes nuevos frente a repetidos en las aplicaciones móviles, puede usarse una métrica calculada que incluye los visitantes y visitas con la métrica Instalación de la aplicación para identificar los nuevos visitantes y visitas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Fuentes de datos de ID de transacción </p> </td> 
   <td colname="col2"> <p> No compatible en este momento. Está prevista la compatibilidad futura. </p> </td> 
  </tr> 
 </tbody> 
</table>

A continuación se ofrece una lista de dimensiones y métricas que pueden verse afectadas por la configuración seleccionada para Procesamiento de intervalo de tiempo:

<table id="table_491E48C55BC84917B4A8EACBF04C939F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nombre de la métrica/dimensión </th> 
   <th colname="col2" class="entry"> Notas sobre Procesamiento de intervalo de tiempo </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Métrica Visitantes exclusivos </p> </td> 
   <td colname="col2"> <p> Si “Impedir que las visitas en segundo plano inicien una nueva visita” está habilitado, Visitantes exclusivos no incluye a aquellos que solo tuvieron visitas en segundo plano dentro del intervalo de fechas del informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Visitas </p> </td> 
   <td colname="col2"> <p> Las visitas reflejan cualquier configuración del grupo de informes virtuales, que pueden diferir de las del grupo de informes base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Eventos serializados con ID de evento </p> </td> 
   <td colname="col2"> <p> Debido a la naturaleza de la limitación de fechas de Procesamiento de intervalo de tiempo, los eventos que utilizan serialización con un ID de evento solo se deduplican cuando se producen dentro del intervalo de fechas del informe para un visitante, y no en cualquier fecha y para cualquier visitante globalmente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Compras/Ingresos/Pedidos/Unidades </p> </td> 
   <td colname="col2"> <p> Debido a la naturaleza de la limitación de fechas de Procesamiento de intervalo de tiempo, cuando se utiliza el ID de compra, estas métricas solo se deduplican para los ID de compra duplicados que se producen dentro del intervalo de fechas del informe para un visitante, y no en cualquier fecha y para cualquier visitante globalmente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Salidas hacia otro sitio/Tasa de salida hacia otro sitio </p> </td> 
   <td colname="col2"> <p> Si “Impedir que las visitas en segundo plano inicien una nueva visita” está habilitado, las visitas en segundo plano no seguidas por una visita en primer plano no se consideran una salida hacia otro sitio y no contribuyen a la tasa de salida hacia otro sitio. See <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> Context-Aware Sessionization</a> for more details. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Tiempo pasado en segundos por visita </p> </td> 
   <td colname="col2"> <p> Si “Impedir que las visitas en segundo plano inicien una nueva visita” está habilitado, solo las visitas que incluyen visitas en primer plano contribuyen a esta métrica. See <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> Context-Aware Sessionization</a> for more details. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Tiempo pasado por visita </p> </td> 
   <td colname="col2"> <p> Si “Impedir que las visitas en segundo plano inicien una nueva visita” está habilitado, solo las visitas que incluyen visitas en primer plano contribuyen a esta métrica. See <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> Context-Aware Sessionization</a> for more details. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Entradas </p> </td> 
   <td colname="col2"> <p> Si “Impedir que las visitas en segundo plano inicien una nueva visita” está habilitado, solo se consideran las entradas que contienen una visita en primer plano. See <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> Context-Aware Sessionization</a> for more details. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> eVars no de comercialización/eVars reservadas </p> </td> 
   <td colname="col2"> <p> Debido a la naturaleza de la limitación de fechas de Procesamiento de intervalo de tiempo, un valor establecido en una eVar persiste solo si se estableció dentro del intervalo de fechas del informe. </p> <p> Además, las caducidades basadas en la hora pueden producirse 60 minutos antes o después si la persistencia se ve afectada por un cambio de hora. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> eVars de comercialización/eVars reservadas </p> </td> 
   <td colname="col2"> <p> Véase más arriba. </p> <p> Además, para la conversión de sintaxis, cuando el enlace está establecido en “cualquier evento”, se utiliza “cualquier visita”. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Dimensiones de entrada y salida </p> </td> 
   <td colname="col2"> <p> Si “Impedir que las visitas en segundo plano inicien una nueva visita” está habilitado, solo las entradas y salidas de visitas con visitas en primer plano aparecen en esta dimensión. See <a href="../../components/vrs/vrs-mobile-visit-processing.md#concept_EC51308E4FD14E149F1B5D63C0AB34BD" format="dita" scope="local"> Context-Aware Sessionization</a> for more details. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Tipo de visita </p> </td> 
   <td colname="col2"> <p> Esta dimensión especifica si una visita es en primer o en segundo plano. </p> </td> 
  </tr> 
 </tbody> 
</table>

