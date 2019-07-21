---
description: En esta sección se describen los archivos que se encuentran en una entrega de fuentes de datos.
keywords: Fuente de datos; trabajo; contenido; manifest; archivo; buscar; datos de visitas; contenido de entrega
seo-description: En esta sección se describen los archivos que se encuentran en una entrega de fuentes de datos.
seo-title: 'Contenido de fuente de datos: información general'
solution: Analytics
subtopic: fuentes de datos
title: 'Contenido de fuente de datos: información general'
topic: Reports and Analytics
uuid: 82 a 86314-4841-4133-a 0 dc -4 e 7 c 6 cd 14 fc 1
translation-type: tm+mt
source-git-commit: 7fe23291d8ee9675181065025692108aee3ea9a5

---


# Contenido de fuente de datos: información general

En esta sección se describen los archivos que se encuentran en una entrega de fuente de datos.

## Archivo de manifiesto {#section_044BBDE2906D49518F8264CD4832D429}

El archivo de manifiesto contiene los siguientes detalles sobre cada archivo que forma parte del conjunto de datos cargados:

* nombre del archivo
* tamaño del archivo
* hash MD5
* cantidad de registros incluidos en el archivo

El archivo de manifiesto sigue el mismo formato que un archivo de manifiesto JAR de Java.

The manifest file is always delivered last as a separate `.txt` file, so that its existence indicates that the complete data set for that request period has already been delivered. Los nombres de los archivos de manifiesto se asignan según los criterios siguientes:

```
<report_suite_id>_YYYY_MM_DD.txt
```

Un archivo de manifiesto típico contiene datos parecidos a los siguientes:

```
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 1
 Data-Files: 1
 Total-Records: 611

 Lookup-File: bugzilla_2012-09-09-lookup_data.tar.gz
 MD5-Digest: af6de42d8b945d4ec1cf28360085308
 File-Size: 63750

 Data-File: 01-bugzilla_2012-09-09.tsv.gz
 MD5-Digest: 9c70bf783cb3d0095a4836904b72c991
 File-Size: 122534
 Record-Count: 611
```

Cada archivo de manifiesto contiene un encabezado, que indica el número total de archivos de búsqueda, archivos de datos y el número total de registros incluidos en todos los archivos de datos. Este encabezado va seguido de varias secciones que contienen información para cada archivo incluido en la entrega de fuente de datos.

Some feeds are configured to receive a `rsid_YYYY-MM-DD.fin` file instead of a `.txt` manifest. `.fin` Indica que la carga se ha completado, pero no contiene metadatos sobre la carga.

## Archivos de búsqueda {#section_B5863537A48D47D78D0F7274838923C1}

Los archivos de búsqueda no contienen datos de visitas, sino que son archivos complementarios que proporcionan los encabezados de columna para los datos de visitas y los archivos de búsqueda para traducir en valores reales los ID que se encuentran en la fuente de datos. Por ejemplo, un valor de "497" en la columna de navegador indica que la visita provenía de "Microsoft Internet Explorer 8".

Note that the `column_headers.tsv` and `event_list.tsv` are specific to the data feed and report suite. Otros archivos, como puede ser `browser.tsv`, son genéricos.

Los archivos de búsqueda se entregan juntos en un zip comprimido al que se le asigna un nombre según los criterios siguientes:

```
<report_suite_id>_<YYYY-mm-dd>-<HHMMSS>-lookup_data.<compression_suffix>
```

* [!DNL column_headers.tsv] (personalizado para esta fuente de datos)
* [!DNL browser.tsv]
* [!DNL browser_type.tsv]
* [!DNL color_depth.tsv]
* [!DNL connection_type.tsv]
* [!DNL country.tsv]
* [!DNL javascript_version.tsv]
* [!DNL languages.tsv]
* [!DNL operating_systems.tsv]
* [!DNL plugins.tsv]
* [!DNL resolution.tsv]
* [!DNL referrer_type.tsv]
* [!DNL search_engines.tsv]
* [!DNL event_lookup.tsv] (personalizado para esta fuente de datos)

## Archivos de datos de visitas {#section_B0745236104E41F2BA625D24AB442636}

Hit data is provided in a [!DNL hit_data.tsv] file. La cantidad de datos incluida en este archivo viene determinada por el formato de entrega (por hora o por día, y en un archivo o en varios). El archivo contiene solo datos de visitas. Los encabezados de columna se entregan por separado con los archivos de búsqueda. Cada fila del archivo contiene una sola llamada al servidor.

## Contenido de las entregas {#section_994B43D1E71A4EFDB2E4183C0929A397}

>[!NOTE]
>
>Los archivos se codifican usando ISO -8859-1.

Los archivos reales que Adobe entrega varían en función del tipo de fuente de datos que usted haya configurado. Para ver una descripción de los archivos entregados, busque la configuración que coincida con su fuente de datos en la tabla siguiente.

La hora (HHMMSS) señalada en el nombre de un archivo indica el inicio del intervalo de fechas de los datos del archivo, sin tener en cuenta cuándo se creó o se cargó el archivo.

<table id="table_DBF34F39D29D4DA2B2689029CDA24B92"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Formato de entrega </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> A diario, archivo único </td> 
   <td colname="col2"> <p>Después de recopilar datos durante un día, recibirá una entrega que incluye lo siguiente: </p> 
    <ul id="ul_D630D73D0DBA440FA704CF31856243C7"> 
     <li id="li_717873DBBF264422A39217E1A8829742">Un solo archivo de datos comprimido. </li> 
     <li id="li_9F75D42FD56E4CC89C4683D32E59337B">Un archivo de manifiesto. </li> 
    </ul> <p>El archivo de datos se entrega con el nombre siguiente: </p> 
    <code>&lt; report_ suite &gt;_ &lt; AAAA-mm-dd &gt;.&lt;compression_suffix&gt;
    </code> <p> Donde <code>&lt;compression_suffix&gt;</code> es <code>tar.gz</code> o <code>zip</code>. </p> <p>Cuando se extrae, el archivo de datos contiene un solo archivo <span class="filepath">hit_data.tsv</span> con todos los datos de ese día, así como los archivos de búsqueda comprimidos que se han descrito anteriormente. </p> <p>El archivo de datos de visitas varía en gran medida en función del número de variables que se usa de forma activa y del volumen de tráfico que hay en el grupo de informes. Sin embargo, una fila de datos tiene un tamaño medio aproximado de 500 B (comprimido) o de 2 KB (sin comprimir). Si se multiplica esta cifra por el número de llamadas al servidor, se puede obtener un cálculo aproximado del tamaño que tendrá un archivo de fuentes de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> A diario, varios archivos </td> 
   <td colname="col2"> <p>Después de recopilar datos durante un día, recibirá una entrega que incluye lo siguiente: </p> 
    <ul id="ul_4B873D3F6F18467890C36AE8E86F49DA"> 
     <li id="li_227315384B954A5784FA370D9B30E2AF">Uno o más archivos de datos comprimidos, divididos en dos unidades de 2 GB. </li> 
     <li id="li_4169D889CEA3446CB5FAA08FD60AA0D0">Un archivo de manifiesto. </li> 
    </ul> <p>Cada archivo de datos se entrega con el nombre siguiente: </p> 
    <code>&lt; index &gt;-&lt; report_ suite &gt;_ &lt; AAAA-mm-dd &gt;.&lt;compression_suffix&gt;
    </code> <p> Donde <code>&lt;index&gt;</code> es un índice de archivos incremental entre <i>1</i> y <i>n</i>, dados <i>n</i> archivos, y <code>&lt;compression_suffix&gt;</code> es <code>tar.gz</code> o <code>zip</code>. </p> <p>Cuando se extrae, cada archivo de datos contiene un solo archivo <span class="filepath">hit_data.tsv</span> que incluye aproximadamente 2 GB de datos sin comprimir, así como los archivos de búsqueda comprimidos que se han descrito anteriormente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cada hora, un solo archivo </td> 
   <td colname="col2"> <p>Después de recopilar datos durante una hora, recibirá una entrega que incluye lo siguiente: </p> 
    <ul id="ul_29B06981A4F74D2AA1171D733C5FB1F4"> 
     <li id="li_072BBC4BA9B84C61B4E8EFA35F54707B">Un solo archivo de datos. </li> 
     <li id="li_E2D05E9DAE814309B6BC91798BB29FBB">Un archivo de manifiesto. </li> 
    </ul> <p>El archivo de datos se entrega con el nombre siguiente: </p> 
    <code>&lt; report_ suite &gt;_ &lt; AAAA-mm-dd &gt;-&lt; HHMMSS &gt;.&lt;compression_suffix&gt;
    </code> <p> Donde <code>&lt;compression_suffix&gt;</code> es <code>tar.gz</code> o <code>zip</code>. </p> <p>Cuando se extrae, el archivo de datos contiene un solo archivo <span class="filepath">hit_data.tsv</span> con todos los datos de esa hora. Los archivos de búsqueda comprimidos que se han descrito anteriormente se entregan únicamente con los datos de la primera hora de cada día. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cada hora, varios archivos </td> 
   <td colname="col2"> <p>Después de recopilar datos durante una hora, recibirá una entrega que incluye lo siguiente: </p> 
    <ul id="ul_A739BA12B66547A28BA45E0B9B747B16"> 
     <li id="li_C0DF059D1E6843C8A38E24CA1B59D99C">Uno o más archivos de datos comprimidos, divididos en dos unidades de 2 GB. </li> 
     <li id="li_604266DA9B8A4000905C44C95DA65D14">Un archivo de manifiesto. </li> 
    </ul> <p>Cada archivo de datos se entrega con el nombre siguiente: </p> 
    <code>&lt; index &gt;-&lt; report_ suite &gt;_ &lt; AAAA-mm-dd &gt;-&lt; HHMMSS &gt;. tsv.&lt;compression_suffix&gt;
    </code> <p>Donde <code>&lt;index&gt;</code> es un índice de archivos incremental entre <i>1</i> y <i>n</i>, dados <i>n</i> archivos, y <code>&lt;compression_suffix&gt;</code> es <code>gz</code> o <code>zip</code>. </p> <p>Cuando se extrae, cada archivo de datos contiene un solo archivo <span class="filepath">hit_data.tsv</span> que incluye aproximadamente 2 GB de datos sin comprimir. Los archivos de búsqueda comprimidos que se han descrito anteriormente se entregan únicamente con los datos de la primera hora de cada día. </p> </td> 
  </tr> 
 </tbody> 
</table>

