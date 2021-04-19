---
description: En esta sección se describen los archivos que se encuentran en una entrega de fuentes de datos.
keywords: Fuente de datos;trabajo;contenido;manifiesto;archivo;búsqueda;datos de visitas;contenido de entrega
subtopic: data feeds
title: Resumen del contenido de la fuente de datos
feature: Conceptos básicos de Reports & Analytics y conceptos básicos de Analytics
uuid: 82a86314-4841-4133-a0dc-4e7c6cd14fc1
exl-id: 7456ed99-c2f3-4b19-a63e-6b4e457e7d55
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 97%

---

# Resumen del contenido de la fuente de datos

En esta sección se describen los archivos que se encuentran en una entrega de fuentes de datos.

## Archivo de manifiesto

El archivo de manifiesto contiene los siguientes detalles sobre cada archivo que forma parte del conjunto de datos cargados:

* Nombre del archivo
* Tamaño del archivo
* hash MD5
* Cantidad de registros incluidos en el archivo

El archivo de manifiesto sigue el mismo formato que un archivo de manifiesto JAR de Java.

El archivo de manifiesto siempre se entrega en último lugar como un archivo `.txt` independiente, de forma que su presencia indica que ya se ha entregado el conjunto de datos completo de ese período de solicitud. Los nombres de los archivos de manifiesto se asignan según los criterios siguientes:

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

Algunas fuentes están configuradas para recibir un archivo `.fin` en lugar de un manifiesto `.txt`. El sufijo `.fin` indica que la carga se ha completado pero que no contiene metadatos de la carga.

## Archivos de búsqueda

Algunas columnas de fuentes de datos muestran un número que corresponde a su valor real. Los archivos de búsqueda se utilizan para hacer coincidir un número de una columna de fuente de datos con un valor real. Por ejemplo, un valor de “497” en la columna de datos de visitas `browser` indica que la visita procede de &quot;Microsoft Internet Explorer 8&quot; si se mira en `browser.tsv`.

Tenga en cuenta que `column_headers.tsv` y `event_list.tsv` son específicos de la fuente de datos y del grupo de informes. Otros archivos, como puede ser `browser.tsv`, son genéricos.

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

Los datos de visitas se proporcionan en un archivo [!DNL hit_data.tsv]. La cantidad de datos incluida en este archivo viene determinada por el formato de entrega (por hora o por día, y en un archivo o en varios). El archivo contiene solo datos de visitas. Los encabezados de columna se entregan por separado con los archivos de búsqueda. Cada fila del archivo contiene una sola llamada al servidor.

Los archivos que Adobe entrega varían en función del tipo de fuente de datos que usted haya configurado. Todos los archivos se codifican con ISO-8859-1.

* `[rsid]` hace referencia al ID del grupo de informes desde el que proviene el origen de datos.
* `[index]` solo se utiliza en varias fuentes de archivos y hace referencia al orden correcto de los archivos paginados.
* `[YYYY-mm-dd]` hace referencia al día de inicio del origen de datos.
* `[HHMMSS]` solo se utiliza en fuentes por hora y se refiere a la hora de inicio para la que está la fuente de datos.
* `[compression_suffix]` hace referencia al tipo de compresión utilizado. Normalmente, las fuentes de datos se comprimen en `tar.gz` o `zip` archivos.

### A diario, archivo único

Una vez recopilados los datos durante un día, recibirá un único archivo de datos comprimido y un archivo de manifiesto. El nombre del archivo de datos es:

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

Cuando se extrae, el archivo de datos contiene un único archivo `hit_data.tsv` con todos los datos de ese día, así como archivos de búsqueda para las columnas requeridas.

### Diariamente, varios archivos

Una vez recopilados los datos durante un día, recibirá uno o varios archivos de datos comprimidos y un archivo de manifiesto. El nombre del archivo de datos es:

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

Cuando se extrae, cada archivo de datos contiene un único `hit_data.tsv` que contiene aproximadamente 2 GB de datos sin comprimir, así como archivos de búsqueda para cualquier columna requerida.

### Cada hora, un solo archivo

Una vez recopilados los datos durante una hora, recibirá un único archivo de datos comprimido y un archivo de manifiesto. El nombre del archivo de datos es:

`[rsid]_[YYYYmmdd]-[HHMMSS].[compression_suffix]`

Cuando se extrae, el archivo de datos contiene un solo archivo `hit_data.tsv` con todos los datos de esa hora, así como archivos de búsqueda de las columnas requeridas.

### Por hora, varios archivos

Una vez recopilados los datos durante una hora, recibirá uno o más archivos de datos comprimidos y un archivo de manifiesto. El nombre del archivo de datos es:

`[index]-[rsid]_[YYYYmmdd]-[HHMMSS].[compression_suffix]`

Cuando se extrae, cada archivo de datos contiene un único `hit_data.tsv` que incluye aproximadamente 2 GB de datos sin comprimir, así como archivos de búsqueda para cualquier columna requerida.

## Tamaño del archivo de datos

El tamaño del archivo de datos de la visita varía en gran medida en función del número de variables que se usa de forma actica y del volumen de tráfico enviado al grupo de informes. Sin embargo, una fila de datos tiene un tamaño medio aproximado de 500 B (comprimido) o de 2 KB (sin comprimir). Si se multiplica esta cifra por el número de llamadas al servidor, se puede obtener un cálculo aproximado del tamaño del archivo de la fuente de datos. Una vez que las organizaciones empiecen a recibir archivos de fuente de datos, puede obtener un número más preciso dividiendo el número de filas en `hit_data.tsv` por el tamaño total del archivo.
