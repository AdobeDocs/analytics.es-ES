---
description: Información sobre requisitos para el grupo de informes antes de utilizar fuentes de datos.
subtopic: Data sources
title: Requisitos y límites de carga
topic-fix: Developer and implementation
uuid: d79fca77-fa0e-4171-b978-cdee5c67d9df
exl-id: 97a7cc65-f99a-4227-94f2-6f428ebdfad3
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '634'
ht-degree: 97%

---

# Requisitos y límites de carga

Información sobre requisitos para el grupo de informes antes de utilizar fuentes de datos.

En las secciones siguientes se indican restricciones que rigen para las fuentes de datos y los datos importados a informes y análisis de marketing.

* [Límites de tamaño](/help/import/c-data-sources/datasrc-requirements.md#section_77B06D82CB374FFABD39F7D9A49D8E18)
* [Fechas](/help/import/c-data-sources/datasrc-requirements.md#section_2B8E69BA1E0B4DEAB4E2034C2B9E16C2)
* [General](/help/import/c-data-sources/datasrc-requirements.md#section_1CD337F660484ABDB7D8CAE96FF46ACF)
* [Compatibilidad con formatos multibyte](/help/import/c-data-sources/datasrc-requirements.md#section_96C8D26B21184C3E839865DB6F23EA22)
* [Carga de archivos de registro web](/help/import/c-data-sources/datasrc-requirements.md#section_DD736FC971FE45C89AB310BEDC1FE707)

## Límites de tamaño {#section_77B06D82CB374FFABD39F7D9A49D8E18}

* Cada cuenta FTP está limitada a un máximo de 50 MB para el total de datos de todos los archivos. Si el tamaño de datos supera los 50 MB, el procesamiento se detendrá y no se reanudará hasta que el total sea menor que 50 MB.

## Fechas {#section_2B8E69BA1E0B4DEAB4E2034C2B9E16C2}

* Por cada día del calendario, solamente se pueden cargar datos para 90 fechas distintas. Si supera este límite, la carga fallará y se mostrará un mensaje de error para indicar que ha excedido el número máximo de días únicos.
* Solo pueden importarse datos con fechas actuales o pasadas. No intente usar fechas futuras en las fuentes de datos.
* Para habilitar las funciones gráficas del informe, todas las filas deben tener indicada una fecha. Si una fila no incluye fecha, el sistema de fuentes de datos generará un error y rechazará el archivo. El formato de fecha y hora depende del tipo de fuente de datos:

   * **Fuentes de datos de procesamiento completo**: use el formato de fecha ISO 8601 `YYYY-MM-DDThh:mm:ss±UTC_offset` (por ejemplo, `2013-09-01T12:00:00-07:00`) o el formato de tiempo de Unix (UTF; la cantidad de segundos transcurridos desde el 1 de enero de 1970).

   * **Fuentes de datos estándar y de integración**: use el formato de fecha `MM/DD/YYYY/HH/mm/SS` (por ejemplo, `01/01/2013/06/00/00`).

## General {#section_1CD337F660484ABDB7D8CAE96FF46ACF}

* Cuando se carga un archivo al sistema de fuente de datos, este realiza una verificación básica de los datos, para comprobar que el archivo no contenga errores de formato. Si el sistema encuentra algún error en el archivo, envía al usuario un aviso por correo electrónico y detiene el procesamiento.
* Los campos de datos no pueden contener ningún punto y coma; si algún registro contiene un punto y coma, el sistema de fuente de datos lo omitirá.
* Los datos de los archivos de registro web, tráfico y algunos agrupamientos de fuentes de datos genéricas no se pueden usar en Data Warehouse ni en Discover. Para obtener más información, consulte [Tipos de datos y categorías](/help/import/c-data-sources/c-datasrc-types/datasrc-categories.md).
* Las fuentes de datos no admiten los eventos serializados.

## Compatibilidad con formatos multibyte {#section_96C8D26B21184C3E839865DB6F23EA22}

El sistema de fuentes de datos admite archivos con codificación multibyte. El sistema intentará detectar la codificación del archivo de fuente de datos entrante y, de ser necesario, lo convertirá a un formato compatible. En la tabla siguiente se indican algunas codificaciones de caracteres comunes y si son compatibles.

<table id="table_F9E685D7EEAB49A9ABAD622AE630EC21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Codificación de caracteres </th> 
   <th colname="col2" class="entry"> Asistencia </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> UTF-8 </td> 
   <td colname="col2"> <p>Admitido. El grupo de informes que se use con la fuente de datos debe tener habilitada la compatibilidad con codificación de caracteres multibyte. </p> <p>Consulte <a href="https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html"  >Nuevo grupo de informes</a> en la ayuda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-8 con marca de orden de bytes (EF BB BF) </td> 
   <td colname="col2"> <p>Admitido. Este formato no es estándar, pero muchas aplicaciones de Windows lo usan al guardar archivos. </p> <p>Por ejemplo, cuando se elige “UTF-8” en WordPad, el archivo se guarda en este formato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ISO-8859-1 (también llamado Latin-1 o Windows-1252) </td> 
   <td colname="col2"> Admitido. Microsoft Excel guarda los archivos en este formato cuando se elige exportar los datos a un archivo delimitado por tabulaciones. El grupo de informes debe utilizar la configuración regional ISO-8859-1. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 “little endian”, con marca de orden de bytes (FF FE) </td> 
   <td colname="col2"> Se convierte a ISO-8859-1 o UTF-8, según la configuración del grupo de informes. Microsoft Excel guarda los archivos en este formato cuando se elige exportar los datos en unicode. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 “big endian”, con marca de orden de bytes (EF FF) </td> 
   <td colname="col2"> Se convierte a ISO-8859-1 o UTF-8, según la configuración del grupo de informes. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UTF-16 sin marca de orden de bytes </td> 
   <td colname="col2"> No admitido. </td> 
  </tr> 
 </tbody> 
</table>

Si se envía un archivo UTF-8 o ISO-8859-1 y el grupo de informes no está configurado para admitirlo, sucederá alguna de las siguientes cosas:

* El error se detectará durante la conversión y aparecerá un mensaje similar a “Se encontró un carácter incorrecto en el archivo en la posición 18 mientras se realizaba la conversión de UTF-8 a ISO-8859-1”.
* El archivo se procesará sin errores, pero en el informe aparecerán datos ilegibles.

## Carga de archivos de registro web {#section_DD736FC971FE45C89AB310BEDC1FE707}

* Los informes más útiles para ver datos de registro web son los informes de tráfico como, por ejemplo, el de vistas de páginas.
* Los nombres de las páginas se muestran como direcciones URL completas, incluida la parte de consulta.
* Cada solicitud de archivo individual se muestra como una vista de página independiente; esto incluye las hojas de estilo y los archivos de imagen.
* Si se añade información a la URL, puede ocurrir que los archivos se registren como páginas separadas. Por ejemplo, Adobe registra las siguientes direcciones URL como dos páginas separadas:

`/jokes/misc/snail_joke.html?userid=12345`

`/jokes/misc/snail_joke.html?userid=98765`
