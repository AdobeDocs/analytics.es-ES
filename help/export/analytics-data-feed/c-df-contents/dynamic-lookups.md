---
title: Búsquedas dinámicas
description: Obtenga información sobre qué son las búsquedas dinámicas y cómo habilitarlas. Incluye operadores, atributos móviles y tipos de sistemas operativos.
exl-id: 12327239-06a2-4092-b27d-b94da39abf30
feature: Data Feeds
TQID: https://experienceleague.adobe.com/hKuBXw8dX419msIgSjvd3Dl5uE4rJS6nouIbR18RmVo
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 306
ht-degree: 20%

---

# Búsquedas dinámicas

Las búsquedas dinámicas permiten recibir archivos de búsqueda adicionales en la fuente de datos; de lo contrario, no estarán disponibles. Esta configuración permite enviar las siguientes tablas de búsqueda con cada archivo de feed de datos:

* **Nombre de operador**: proporciona contexto adicional para la columna `carrier`. El nombre de archivo incluido es `carrier.tsv`.
* **Atributos móviles**: proporciona contexto adicional para la columna `mobile_id`, incluidas todas las características rastreadas para cada dispositivo móvil. El nombre de archivo incluido es `mobile_attributes.tsv`.
* **Tipo de sistema operativo**: Proporciona un contexto alternativo para la columna `os`. Tanto `operating_systems.tsv` como `operating_system_type.tsv` utilizan la columna `os` como clave, pero solo `operating_system_type.tsv` es una búsqueda dinámica.

## Habilitar búsquedas dinámicas {#enable-dynamic-lookups}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datafeed_dynamic_lookups"
>title="Habilitar búsquedas dinámicas"
>abstract="Seleccione esta opción para recibir archivos de búsqueda adicionales en el feed de datos; de lo contrario, no estarán disponibles. Esta configuración permite enviar las siguientes tablas de búsqueda con cada archivo de feed de datos:<ul><li>Nombre de operador</li><li>Atributos móviles</li><li>Tipo de sistema operativo</li></ul>"

<!-- markdownlint-enable MD034 -->

Si desea recibir los archivos de búsqueda mencionados, debe cumplir todos los requisitos previos siguientes:

* La columna clave debe incluirse en la fuente de datos.
   * Para `carrier.tsv`, debe incluir `carrier`.
   * Para `mobile_attributes.tsv`, debe incluir `mobile_id`.
   * Para `operating_system_type.tsv`, debe incluir `os`.
* Las siguientes columnas deben estar **excluidas**. Si alguna de estas columnas se incluye en la fuente de datos, la búsqueda dinámica `mobile_attributes.tsv` no se incluye.
   * `user_agent`
   * `ch_hdr`
   * `ch_js`

Una vez que la fuente de datos cumpla los requisitos de inclusión y exclusión de columnas, póngase en contacto con el Servicio de atención al cliente con el ID de la fuente de datos y solicite habilitar las búsquedas dinámicas.

## Referencia del encabezado de búsqueda

Los encabezados de columna de estos archivos de búsqueda no cambian con el tiempo, por lo que los encabezados no se incluyen en cada archivo de fuente de datos. Use estos encabezados de columna como referencia o descargue su archivo `.tsv` correspondiente.

+++**Nombre de operador**
Descargue [carrier_headers.tsv](assets/carrier_headers.tsv) o haga referencia a los encabezados siguientes.

`carrier`
`Carrier Name`
+++

+++**Atributos móviles**
Descargue [mobile_attributes_headers.tsv](assets/mobile_attributes_headers.tsv) o haga referencia a los encabezados siguientes.

`mobile_id`
`Manufacturer`
`Device`
`Device Type`
`Operating System`
`Diagonal Screen Size`
`Screen Height`
`Screen Width`
`Cookie Support`
`Color Depth`
`MP3 Audio Support`
`AAC Audio Support`
`AMR Audio Support`
`Midi Monophonic Audio Support`
`Midi Polyphonic Audio Support`
`QCELP Audio Support`
`GIF87 Image Support`
`GIF89a Image Support`
`PNG Image Support`
`JPG Image Support`
`3GPP Video Support`
`MPEG4 Video Support`
`3GPP2 Video Support`
`WMV Video Support`
`MPEG4 Part 2 Video Support`
`Stream MP4 AAC LC Video Support`
`Stream 3GP H264 Level 10b Video Support`
`Stream 3GP AAC LC Video Support`
`3GP AAC LC Video Support`
`Stream MP4 H264 Level 11 Video Support`
`Stream MP4 H264 Level 13 Video Support`
`Stream 3GP H264 Level 12 Video Support`
`Stream 3GP H264 Level 11 Video Support`
`Stream 3GP H264 Level 10 Video Support`
`Stream 3GP H264 Level 13 Video Support`
`3GP AMR NB Video Support`
`3GP AMR WB Video Support`
`MP4 H264 Level 11 Video Support`
`3GP H263 Video Support`
`MP4 H264 Level 13 Video Support`
`Stream 3GP H263 Video Support`
`Stream 3GP AMR WB Video Support`
`3GP H264 Level 10b Video Support`
`MP4 ACC LC Video Support`
`Stream 3GP AMR NB Video Support`
`3GP H264 Level 10 Video Support`
`3GP H264 Level 13 Video Support`
`3GP H264 Level 11 Video Support`
`3GP H264 Level 12 Video Support`
`Stream HTTP Live Streaming Video Support`
+++

+++**Tipo de sistema operativo**
Descargue [operation_system_type_headers.tsv](assets/operating_system_type_headers.tsv) o haga referencia a los encabezados siguientes.

`os`
`Operating System Type`
+++
