---
description: En esta sección se describen los archivos que se encuentran en una entrega de fuentes de datos.
keywords: Data Feed;job;contents;manifest;file;lookup;hit data;delivery contents
subtopic: data feeds
title: Resumen del contenido de la fuente de datos
topic: Reports and analytics
uuid: 82a86314-4841-4133-a0dc-4e7c6cd14fc1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Resumen del contenido de la fuente de datos

En esta sección se describen los archivos que se encuentran en una entrega de fuentes de datos.

## Archivo de manifiesto

El archivo de manifiesto contiene los siguientes detalles sobre cada archivo que forma parte del conjunto de datos cargados:

* Nombre del archivo
* Tamaño del archivo
* hash MD5
* Número de registros contenidos en el archivo

El archivo de manifiesto sigue el mismo formato que un archivo de manifiesto JAR de Java.

The manifest file is always delivered last as a separate `.txt` file, so that its existence indicates that the complete data set for that request period has already been delivered. Los nombres de los archivos de manifiesto se asignan según los criterios siguientes:

```text
[rsid]_[YYYY-mm-dd].txt
```

Un archivo de manifiesto típico contiene datos parecidos a los siguientes:

```text
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 1
 Data-Files: 1
 Total-Records: 611

 Lookup-File: rsid_date-lookup_data.tar.gz
 MD5-Digest: af6de42d8b945d4ec1cf28360085308
 File-Size: 63750

 Data-File: 01-rsid_date.tsv.gz
 MD5-Digest: 9c70bf783cb3d0095a4836904b72c991
 File-Size: 122534
 Record-Count: 611
```

Cada archivo de manifiesto contiene un encabezado, que indica el número total de archivos de búsqueda, archivos de datos y el número total de registros incluidos en todos los archivos de datos. Este encabezado va seguido de varias secciones que contienen información para cada archivo incluido en la entrega de fuente de datos.

Some feeds are configured to receive a `.fin` file instead of a `.txt` manifest. The `.fin` indicates that the upload is complete, but it contains no metadata about the upload.

## Archivos de búsqueda

Algunas columnas de fuentes de datos muestran un número que corresponde a su valor real. Los archivos de búsqueda se utilizan para hacer coincidir un número de una columna de fuente de datos con un valor real. Por ejemplo, un valor de "497" en la columna de datos de `browser` visitas indica que la visita procede de "Microsoft Internet Explorer 8" si se mira en `browser.tsv`.

Note that the `column_headers.tsv` and `event_list.tsv` are specific to the data feed and report suite. Otros archivos, como puede ser `browser.tsv`, son genéricos.

Los archivos de búsqueda se entregan juntos en un zip comprimido al que se le asigna un nombre según los criterios siguientes:

```text
[rsid]_[YYYY-mm-dd]-lookup_data.[compression_suffix]
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

## Archivos de datos de visitas

Hit data is provided in a [!DNL hit_data.tsv] file. La cantidad de datos incluida en este archivo viene determinada por el formato de entrega (por hora o por día, y en un archivo o en varios). El archivo contiene solo datos de visitas. Los encabezados de columna se entregan por separado con los archivos de búsqueda. Cada fila del archivo contiene una sola llamada al servidor.

Los archivos entregados por Adobe varían según el tipo de fuente de datos que haya configurado. Todos los archivos se codifican con ISO-8859-1.

* `[rsid]` hace referencia a la ID del grupo de informes desde la que proviene la fuente de datos.
* `[index]` solo se utiliza en varias fuentes de archivos y hace referencia al orden correcto de los archivos paginados.
* `[YYYY-mm-dd]` hace referencia al día de inicio de la fuente de datos.
* `[HHMMSS]` se utiliza solamente en fuentes por hora y se refiere a la hora de inicio para la que está la fuente de datos.
* `[compression_suffix]` hace referencia al tipo de compresión utilizado. Normalmente, las fuentes de datos se comprimen en `tar.gz` o `zip` archivos.

### A diario, archivo único

Una vez recopilados los datos durante un día, recibirá un único archivo de datos comprimido y un archivo de manifiesto. El nombre del archivo de datos es:

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

Cuando se extrae, el archivo de datos contiene un único `hit_data.tsv` archivo con todos los datos de ese día, así como archivos de búsqueda para las columnas requeridas.

### Diariamente, varios archivos

Una vez recopilados los datos durante un día, recibirá uno o más archivos de datos comprimidos y un archivo de manifiesto. El nombre del archivo de datos es:

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

Cuando se extrae, cada archivo de datos contiene un único `hit_data.tsv` que contiene aproximadamente 2 GB de datos sin comprimir, así como archivos de búsqueda para cualquier columna requerida.

### Cada hora, un solo archivo

Una vez recopilados los datos durante una hora, recibirá un único archivo de datos comprimido y un archivo de manifiesto. El nombre del archivo de datos es:

`[rsid]_[YYYY-mm-dd]-[HHMMSS].[compression_suffix]`

Cuando se extrae, el archivo de datos contiene un solo `hit_data.tsv` archivo con todos los datos de esa hora, así como archivos de búsqueda de las columnas requeridas.

### Por hora, varios archivos

Una vez recopilados los datos durante una hora, recibirá uno o más archivos de datos comprimidos y un archivo de manifiesto. El nombre del archivo de datos es:

`[index]-[rsid]_[YYYY-mm-dd]-[HHMMSS].[compression_suffix]`

Cuando se extrae, cada archivo de datos contiene un único `hit_data.tsv` que contiene aproximadamente 2 GB de datos sin comprimir, así como archivos de búsqueda para cualquier columna requerida.

## Tamaño del archivo de datos

El tamaño del archivo de datos de visitas varía en gran medida según la cantidad de variables utilizadas activamente y la cantidad de tráfico enviado al grupo de informes. Sin embargo, una fila de datos tiene un tamaño medio aproximado de 500 B (comprimido) o de 2 KB (sin comprimir). Si se multiplica esto por el número de llamadas al servidor, se puede obtener una estimación aproximada del tamaño de un archivo de fuente de datos. Una vez que las organizaciones empiecen a recibir archivos de fuente de datos, puede encontrar un número más preciso dividiendo el número de filas en `hit_data.tsv` por el tamaño total del archivo.
