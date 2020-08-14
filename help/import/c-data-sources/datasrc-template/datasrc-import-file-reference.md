---
description: Información sobre la plantilla .txt de fuentes de datos.
subtopic: Data sources
title: Referencia sobre el archivo de importación
topic: Developer and implementation
uuid: cc58f8d8-cb6e-4908-846f-0a41c6da805d
translation-type: ht
source-git-commit: a28a05047e95d12343fd94f7b11e5cabf7fac070
workflow-type: ht
source-wordcount: '430'
ht-degree: 100%

---


# Referencia sobre el archivo de importación

Información sobre la plantilla .txt de fuentes de datos.

Para generar una plantilla de importación, utilice el asistente para fuentes de datos. El archivo de importación de fuente de datos incluye estos datos:

* El símbolo de almohadilla (#) identifica las filas que son comentarios.
* Puede agregar al archivo todos los comentarios que necesite.
* Un comentario que indica el título del archivo de plantilla.
* Un comentario que indica los nombres de métricas y dimensiones de datos externas indicadas en el [!UICONTROL asistente para activación de fuentes de datos].

Para identificar los datos en las diferentes columnas del archivo de fuente de datos se usan encabezados de columna, que pueden ser de tres tipos:

**Fecha**: (Obligatoria) Una marca de tiempo de cada fila de datos del archivo, con el formato `m/d/yyyy`.

**Variables**: nombres de las variables de informes asignadas a las dimensiones de datos de la fuente de datos.

**Eventos**: nombres de los eventos asignados a las métricas de la fuente de datos.

Utilice la plantilla de fuente de datos para crear un archivo de fuente de datos con los datos que desea cargar. Al crear el archivo de fuente de datos, tenga en cuenta lo siguiente:

* En la práctica, cada fila del archivo de fuente de datos contiene un registro de datos y cada registro de datos está formado por una serie de campos separados por tabulaciones. El orden de los campos se define mediante los encabezados de columna en la plantilla de fuente de datos. Por ejemplo:

   ```
     #Sample data file for mycorp_report_suite 
     #Imported data for ad impressions applied to Event 6
     Date     Tracking Code      Event 6 
     1/1/2009     NYT8453A      8754
     1/1/2009     WSJ4453B      9492
     1/1/2009     BHG44563      10553
     1/2/2009     NYT8453A      6452
     1/2/2009     WSJ4453B      7237
     1/2/2009     BHG44563      9031
   ```

* Si carga varios archivos de fuente de datos, el sistema los cargará en orden alfabético. Es decir que si necesita que los archivos se procesen en orden cronológico, debe ponerles nombres que hagan corresponder el orden alfabético con el orden cronológico. Por ejemplo:

   ```
   log_2009-01-01_13:00.txt
   log_2009-01-01_13:15.txt
   log_2009-01-01_13:30.txt
   ```

* Para acelerar el procesamiento del archivo de fuente de datos, Adobe recomienda consolidar los datos de evento (métrica) en una sola fila por cada fecha.

   Por ejemplo, si el archivo de fuente de datos asigna los datos de impresión de anuncios al evento 6, incluya la cantidad total de impresiones de cada día en una sola fila para ese día, en vez de crear una fila de datos diferente para cada impresión que se haya producido en un día concreto.
* Si necesita cargar datos de fechas anteriores a la fecha de creación del grupo de informes, póngase en contacto con su administrador de cuentas para que modifique la fecha más antigua a partir de la cual usted puede ejecutar informes.

**Archivo .FIN**

Cuando haya terminado de rellenar el archivo de fuente de datos, solo necesita cargarlo a Analytics mediante FTP. Pero, para que los datos se procesen, también deberá cargar, a continuación del otro, un archivo de texto vacío con el mismo nombre que el archivo de datos, pero con la extensión [!DNL .fin].

Por ejemplo, si carga un archivo de datos (delimitado con tabulaciones) llamado [!DNL myproductdata.txt], también tiene que cargar un archivo de texto vacío llamado [!DNL myproductdata.fin]. Si no carga el archivo [!DNL .fin], los datos no se procesan.
