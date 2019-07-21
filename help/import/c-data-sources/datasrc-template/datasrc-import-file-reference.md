---
description: Información sobre la plantilla .txt de fuentes de datos.
seo-description: Información sobre la plantilla .txt de fuentes de datos.
seo-title: Referencia de archivo de importación
solution: Analytics
subtopic: Fuentes de datos
title: Referencia de archivo de importación
topic: Desarrollador e implementación
uuid: cc 58 f 8 d 8-cb 6 e -4908-846 f -0 a 41 c 6 da 805 d
translation-type: tm+mt
source-git-commit: cce2c1c54f21244f856385aeaad811d89f2fda7f

---


# Referencia de archivo de importación

Información sobre la plantilla .txt de fuentes de datos.

Para generar una plantilla de importación, utilice el Asistente para fuentes de datos. El archivo de importación de fuente de datos incluye estos datos:

* El símbolo de almohadilla (#) identifica las filas que son comentarios.
* Puede agregar al archivo todos los comentarios que necesite.
* Un comentario que indica el título del archivo de plantilla.
* Un comentario que indica los nombres de métricas y dimensiones de datos externas indicadas en el [!UICONTROL Asistente para activación de fuentes de datos].

Para identificar los datos en las diferentes columnas del archivo de fuente de datos se usan encabezados de columna, que pueden ser de tres tipos:

**Fecha** (obligatorio): una marca temporal para cada fila de datos en el archivo.

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

Cuando haya terminado de rellenar el archivo de fuente de datos, puede enviarlo por FTP a Analytics. Pero, para que los datos se procesen, también deberá cargar, a continuación del otro, You will need to upload an empty text file with the same name of your data file, but with a [!DNL .fin] extension.

For example, if you upload a (tab-delimited) data file called [!DNL myproductdata.txt], you would also need to upload an empty text file called [!DNL myproductdata.fin]. Without the [!DNL .fin] file, data would never be processed.
