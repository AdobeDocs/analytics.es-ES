---
description: En esta sección se describen los archivos que se encuentran en una entrega de fuentes de datos.
keywords: Fuente de datos;trabajo;contenido;manifiesto;archivo;búsqueda;datos de visitas;contenido de entrega
subtopic: data feeds
title: Resumen del contenido de la fuente de datos
feature: Data Feeds
exl-id: 7456ed99-c2f3-4b19-a63e-6b4e457e7d55
source-git-commit: 6b8366b451be1612331f517ee80fd57744deafdc
workflow-type: tm+mt
source-wordcount: '1002'
ht-degree: 69%

---

# Resumen del contenido de las fuentes de datos

Las secciones siguientes describen cómo acceder y comprender los archivos que se encuentran en una entrega de fuentes de datos.

## Acceso al contenido de fuentes de datos

Para acceder al contenido de una fuente de datos:

1. Inicie sesión en el sitio de destino de la fuente de datos.

   Este es el sitio de destino que configura al crear la fuente de datos, como un bloque de Amazon S3 o Google Cloud Platform.

1. Descargue el archivo de fuente de datos comprimido en el equipo local.

1. Descomprima el archivo comprimido con un programa que admita extensiones de archivo `.tar.gz`.

1. Abra el archivo `hit_data.tsv` en la hoja de cálculo o aplicación de base de datos que desee para ver los datos sin procesar de ese día. —>

## Archivo de manifiesto {#feed-manifest}

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

Algunas fuentes están configuradas para recibir un archivo `.fin` en lugar de un manifiesto `.txt`. `.fin` indica que la carga se ha completado, pero los metadatos que contiene tienen un formato anterior.

## Archivos de búsqueda

Algunas columnas de fuentes de datos muestran un número que corresponde a su valor real. Los archivos de búsqueda se utilizan para hacer coincidir un número de una columna de fuente de datos con un valor real. Por ejemplo, un valor de “497” en la columna de datos de visitas `browser` indica que la visita procede de &quot;Microsoft Internet Explorer 8&quot; si se mira en `browser.tsv`.

Tenga en cuenta que `column_headers.tsv` y `event_list.tsv` son específicos de la fuente de datos y del grupo de informes. Otros archivos, como puede ser `browser.tsv`, son genéricos.

Los archivos de búsqueda se entregan juntos en un zip comprimido al que se le asigna un nombre según los criterios siguientes:

```text
[rsid]_[YYYY-mm-dd]-lookup_data.[compression_suffix]
```

* **`column_headers.tsv`**: una sola fila que contiene los encabezados de columna de `hit_data.tsv`.
* **`browser.tsv`**: asigna el identificador de explorador (la columna de fuente `browser`) al nombre descriptivo del explorador.
* **`browser_type.tsv`**: asigna el identificador de explorador (la columna de fuente `browser`) al tipo de explorador.
* **`color_depth.tsv`**: asigna el identificador de profundidad de color (la columna de fuente `color`) a la profundidad de color.
* **`connection_type.tsv`**: asigna el identificador de tipo de conexión (la columna de fuente `connection_type`) al tipo de conexión.
* **`country.tsv`**: asigna el identificador de país (la columna de fuente `country`) al nombre del país.
* **`javascript_version.tsv`**: asigna el identificador de versión de JavaScript (la columna de fuente `javascript`) a la versión de JavaScript.
* **`languages.tsv`**: asigna el identificador de idioma (la columna de fuente `language`) al idioma.
* **`operating_systems.tsv`**: asigna el identificador del sistema operativo (la columna de fuente `os`) al nombre del sistema operativo.
* **`plugins.tsv`**: asigna los ID de complemento (la columna de fuente `plugin`) a cada nombre de complemento correspondiente.
* **`resolution.tsv`**: asigna el identificador de resolución (la columna de fuente `resolution`) a la resolución del monitor.
* **`referrer_type.tsv`**: asigna el id. de tipo de referente (la columna de fuente `ref_type`) al tipo de referente.
* **`search_engines.tsv`**: asigna el identificador de motor de búsqueda (la columna de fuente `search_engine`) al nombre del motor de búsqueda.
* **`event.tsv`**: asigna cada ID de evento (la columna de fuente `event_list`) a su nombre de evento respectivo.

## Archivos de datos de visitas

Los datos de visitas se proporcionan en un archivo `hit_data.tsv`. La cantidad de datos incluida en este archivo viene determinada por el formato de entrega (por hora o por día, y en un archivo o en varios). El archivo contiene solo datos de visitas. Los encabezados de columna se entregan por separado con los archivos de búsqueda. Cada fila del archivo contiene una sola llamada al servidor.

Los archivos que Adobe entrega varían en función del tipo de fuente de datos que usted haya configurado. Todos los archivos se codifican con ISO-8859-1.

* `[rsid]` hace referencia al ID del grupo de informes desde el que proviene el origen de datos.
* `[index]` solo se utiliza en varias fuentes de archivos y hace referencia al orden correcto de los archivos paginados.
* `[YYYY-mm-dd]` hace referencia al día de inicio del origen de datos.
* `[HHMMSS]` solo se utiliza en fuentes por hora y se refiere a la hora de inicio para la que está la fuente de datos.
* `[compression_suffix]` hace referencia al tipo de compresión utilizado. Normalmente, las fuentes de datos se comprimen en `tar.gz` o `zip` archivos.
* `[format_suffix]` hace referencia al tipo de formato de archivo. Normalmente, el formato del archivo de fuente de datos es `.tsv`.

### A diario, archivo único

Una vez recopilados los datos durante un día, recibirá un único archivo de datos comprimido y un archivo de manifiesto. El nombre del archivo de datos es:

`[rsid]_[YYYY-mm-dd].[compression_suffix]`

Cuando se extrae, el archivo de datos contiene un único archivo `hit_data.tsv` con todos los datos de ese día, así como archivos de búsqueda para las columnas requeridas.

### Diariamente, varios archivos

Una vez recopilados los datos durante un día, recibirá uno o varios archivos de datos comprimidos y un archivo de manifiesto. El nombre del archivo de datos es:

`[index]-[rsid]_[YYYY-mm-dd].[compression_suffix]`

Cuando se extrae, cada archivo de datos contiene un único `[index]-[rsid]_[YYYY-mm-dd].[format_suffix]` que contiene aproximadamente 2 GB de datos sin comprimir, así como archivos de búsqueda para cualquier columna requerida.

### Cada hora, un solo archivo

Una vez recopilados los datos durante una hora, recibirá un único archivo de datos comprimido y un archivo de manifiesto. El nombre del archivo de datos es:

`[rsid]_[YYYYmmdd]-[HHMMSS].[compression_suffix]`

Cuando se extrae, el archivo de datos contiene un solo archivo `hit_data.tsv` con todos los datos de esa hora, así como archivos de búsqueda de las columnas requeridas.

### Por hora, varios archivos

Una vez recopilados los datos durante una hora, recibirá uno o más archivos de datos comprimidos y un archivo de manifiesto. Los archivos de datos se denominan:

`[index]-[rsid]_[YYYYmmdd]-[HHMMSS].[format_suffix].[compression_suffix]`

Cuando se extrae, cada archivo de datos contiene un único archivo de `[index]-[rsid]_[YYYYmmdd]-[HHMMSS].[format_suffix]` que contiene aproximadamente 2 GB de datos sin comprimir, así como archivos de búsqueda para las columnas requeridas.

## Tamaño del archivo de datos

El tamaño del archivo de datos de la visita varía en gran medida en función del número de variables que se usa de forma actica y del volumen de tráfico enviado al grupo de informes. Sin embargo, una fila de datos tiene un tamaño medio aproximado de 500 B (comprimido) o de 2 KB (sin comprimir). Si se multiplica esta cifra por el número de llamadas al servidor, se puede obtener un cálculo aproximado del tamaño del archivo de la fuente de datos. Una vez que las organizaciones empiecen a recibir archivos de fuente de datos, puede obtener un número más preciso dividiendo el número de filas en `hit_data.tsv` por el tamaño total del archivo.