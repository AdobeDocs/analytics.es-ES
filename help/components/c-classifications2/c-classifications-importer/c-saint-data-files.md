---
description: El importador permite realizar cargas masivas de datos de clasificaciones a los informes de análisis, mediante un archivo. Para que las cargas de datos sean correctas, es necesario usar un formato de archivo específico en la importación.
seo-description: El importador permite realizar cargas masivas de datos de clasificaciones a los informes de análisis, mediante un archivo. Para que las cargas de datos sean correctas, es necesario usar un formato de archivo específico en la importación.
seo-title: Archivos de datos de clasificación
solution: Analytics
subtopic: Clasificaciones
title: Archivos de datos de clasificación
topic: Herramientas de administración
uuid: f 27 bb 812-56 e 0-472 a -9993-d 869 f 0 fea 700
translation-type: tm+mt
source-git-commit: c0c4a3f42a7236c6f9e5001f5ca0ef9173dbaa66

---


# Archivos de datos de clasificación

El importador permite realizar cargas masivas de datos de clasificaciones a los informes de análisis, mediante un archivo. Para que las cargas de datos sean correctas, es necesario usar un formato de archivo específico en la importación.

Para ayudarle a crear archivos de datos válidos, puede descargar un archivo de plantilla que ofrece una estructura de datos en la que puede pegar los datos de las clasificaciones. Para obtener más información, consulte [Descargar la plantilla de clasificaciones](../../../components/c-classifications2/c-classifications-importer/c-download-saint-data.md#concept_0F06847AD8D042F5BA818AE3C37E2417).

See [General File Structure](../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_9EFF968DF5D244A887DE94075431C1BE) for more information about character limits in classifications.

See [Numeric 2 Classifications](../../../components/c-classifications2/c-numeric-2/c-numeric-2-classifications.md#concept_71024B7B91DF4E909076062AB1380D8B) for information about uploading data using numeric 2 classifications.

## Estructura general de archivos

La siguiente ilustración es un archivo de datos de muestra:

![](assets/completed-saint-file.png)

Los archivos de datos deben cumplir las siguientes reglas estructurales:

* Las clasificaciones no pueden tener un valor de 0 (cero).
* Adobe recomienda limitar a 30 el número de columnas de importación y exportación.
* Los archivos actualizados deben usar la codificación de caracteres UTF-8 sin BOM.
* En una celda se pueden incrustar caracteres especiales, como por ejemplo tabulaciones, líneas nuevas y comillas, siempre que el formato de archivo especificado sea v2.1 y que en la celda se hayan usado convenientemente [secuencias de escape](../../../components/c-classifications2/c-classifications-importer/t-classifications-escape-data.md#task_EB47E80063F14F9CB2D186C0CAA9CBAD). Los caracteres especiales incluyen:

   ```
   \t     tab character 
   \r     form feed character 
   \n    newline character 
   "       double quote
   ```

   La coma no es un carácter especial.

* Las clasificaciones no pueden contener un acento circunflejo (^) porque este carácter se usa para denotar una subclasificación.
* Utilice los guiones con cuidado. For example, if you use a hyphen (-) in a Social term, Social recognizes the hyphen as a [!DNL Not] operator (the minus sign). For example, if you specify *`fragrance-free`* as a term using the import, Social recognizes the term as fragrance *`minus`* free and collects posts that mention *`fragrance`*, but not *`free`*.
* Para clasificar los datos de los informes, se aplican límites de caracteres. For example, if you upload a classifications text file for products ( *`s.products`*) with product names longer than 100 characters (bytes), the products will not display in reporting. Los códigos de seguimiento y todas las variables de conversión personalizadas (eVar) admiten un máximo de 255 bytes.
* Archivo de datos delimitado por tabuladores (crear el archivo de plantilla con un editor de texto o una aplicación de hoja de cálculo).
* Either a [!DNL .tab] or [!DNL .txt] file extension.
* El signo de almohadilla (#) identifica la línea como comentario del usuario. Adobe ignora las líneas que comienzan por #.
* Un signo de almohadilla doble seguido de SC (## SC) identifica la línea como un comentario de encabezado previo al procesamiento que usan los informes. No elimine estas líneas.
* Las exportaciones de clasificación pueden tener claves duplicadas debido a los caracteres de línea nueva de la clave. En una exportación del FTP o del explorador, esto se puede resolver activando las comillas de la cuenta FTP. Esto colocará comillas alrededor de cada clave con caracteres de línea nueva.
* La celda C1 en la primera línea del archivo de importación contiene un identificador de versión que determina cómo las clasificaciones administran el uso de comillas a lo largo del resto del archivo.

   * v2.0 ignora las comillas y supone que todas forman parte de las claves y los valores especificados. Por ejemplo, considere este valor: "Este es ""un valor""". v2.0 lo interpretaría literalmente como: "Este es ""un valor""".
   * v2.1 indica a las clasificaciones que supongan que las comillas forman parte del formato del archivo utilizado en archivos de Excel. Entonces, v2.1 aplicaría el siguiente formato para el ejemplo anterior: Este es "un valor".
   * Pueden surgir problemas cuando se especifica v2.1 en el archivo, pero lo que realmente se desea es v2.0, concretamente, cuando las comillas se utilizan de formas que son ilegales según el formato de Excel. Por ejemplo, si tiene un valor: "VP SIN REPS" S/l Dress w/ Overlay. Con v2.1, este formato es incorrecto (el valor debería estar comprendido entre comillas de apertura y cierre, y las comillas que forman parte del valor real deberían estar especificadas con comillas) y las clasificaciones no funcionarán más allá de este punto.
   * Asegúrese de realizar una de las siguientes acciones: cambiar el formato de archivo a v2.0 al cambiar el encabezado (celda C1) en los archivos que carga, O implementar correctamente el entrecomillado de Excel en todos los archivos.

* La primera fila (que no es de comentario) del archivo de datos contiene los encabezados de columna que se usan para identificar los datos de clasificación de esa columna. El importador requiere un formato específico para los encabezados de columna. Para obtener más información, consulte [Formato del encabezado de las columnas](../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_ADC08C783477451B959782CEA23AF5EF).
* Justo después de la fila del encabezado de los archivos de datos, están las filas de datos. Cada línea de datos debe contener un campo de datos por cada encabezado de columna.
* El archivo de datos admite los códigos de control que se indican a continuación y que Adobe utiliza para dar estructura al archivo e importar correctamente los datos de clasificaciones:

<table id="table_0548F2E58B6644208147434EB9B3C21B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CÓDIGO DE CONTROL </th> 
   <th colname="col2" class="entry"> DESCRIPCIÓN </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>&lt;Nueva línea&gt; </p> </td> 
   <td colname="col2"> <p>Un carácter de nueva línea es el único delimitador que se admite entre líneas/registros de datos en el archivo de datos. Normalmente, solo debe insertar expresamente estos caracteres al escribir un programa para generar automáticamente archivos de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~autogen~ </p> </td> 
   <td colname="col2"> <p>Solicita que Adobe genere automáticamente un identificador único para este elemento. </p> <p>En el contexto de campaña, este valor de control ordena a Adobe que asigne un identificador a cada elemento creativo. Consulte <a href="../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_0B77B3079B5C414F9956058688990443" format="dita" scope="local"> Clave </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>Designa que la columna de datos representa el rango de fechas asociado con el elemento. Consulte <a href="../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_9ECCD5ED97764CDC90C0B7B0F9461825" format="dita" scope="local"> Fecha </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campo vacío </p> </td> 
   <td colname="col2"> <p>Representa un valor NULL para el campo actual. Utilícelo si una columna de datos concreta no aplica al registro actual. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificadores PER </p> </td> 
   <td colname="col2"> <p>Designa que la columna de datos representa un campo de <span class="wintitle">Modificador PER</span>. See <a href="../../../components/c-classifications2/c-classifications-importer/c-saint-data-files.md#concept_7E199A26E3274B31B07CCAF8DFE3B274" format="dita" scope="local"> PER Modifier Headings </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_LIKE_THIS]
>
>* [Problemas comunes de carga](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html)


## Formato de encabezado de columna

>[!NOTE]
>
>Adobe recomienda limitar a 30 el número de columnas de importación y exportación.

Los archivos de clasificación admiten los siguientes encabezados de columna:

### Clave

Cada valor debe ser único en todo el sistema. The value in this field corresponds to a value assigned to the [!DNL Analytics] variable in your Web site’s [!DNL JavaScript] beacon. Data in this column might include ~autogen~ or any other unique tracking code.

### Encabezado de la columna Clasificación

Por ejemplo, Reports &amp; Analytics incluye automáticamente dos clasificaciones para variables de [!UICONTROL Campaña]: [!UICONTROL Campañas] y [!UICONTROL Elementos creativos]. Para añadir datos a la clasificación [!UICONTROL Campañas], el encabezado de la columna del archivo de datos de clasificación sería [!UICONTROL Campañas].

>[!NOTE]
>
>The values in the [!UICONTROL Classifications] column heading must exactly match the classification’s naming convention, or the import fails. Por ejemplo, si el administrador cambia [!UICONTROL Campañas] por [!UICONTROL Nombres de campaña internos] en el [!UICONTROL Gestor de configuración de campañas], el encabezado de la columna del archivo debe cambiar también para que coincidan.

Además, el archivo de datos admite las siguientes convenciones de encabezado adicionales, para identificar subclasificaciones y otras columnas de datos especializados:

### Encabezamiento de subclasificación

Por ejemplo, [!UICONTROL Campaigns^Owner] es el encabezamiento de columna de la columna que contiene valores [!UICONTROL Propietario de la campaña]. Del mismo modo, [!UICONTROL Creative Elements^Size] es el encabezamiento de columna de la columna que contiene la subclasificación [!UICONTROL Tamaño] de la clasificación [!UICONTROL Elementos creativos].

### Encabezados de métricas de clasificación

Por ejemplo, [!UICONTROL Campañas^~Coste] hace referencia a la métrica [!UICONTROL Coste] en la clasificación [!UICONTROL Campañas].

### Encabezamiento de modificador PER

*`Per Modifier`* los encabezados se marcan agregando *`~per`* al encabezamiento de métrica de clasificación. For example, if the *`Metric`* heading is *`Campaigns^~Cost`*, the PER modifier heading is *`Campaigns^~Cost~per`*. Adobe supports the following *`PER Modifier`* keywords:

Estos caracteres tienen un significado especial dentro de un archivo de datos. Cuando sea posible, evite utilizar estas palabras en datos y nombres de atributos.

**FIJO:** valor fijo. No realice ningún escalamiento.

**DÍA**: multiplicar el valor por el número de días en el informe.

**ORDEN:** multiplicar el valor por el número de pedidos para el elemento de línea en el informe.

**CIERRE DE COMPRA:** multiplicar el valor por el número de cierres de compras para el elemento de línea en el informe.

**UNIDAD:** multiplicar el valor por el número de unidades para el elemento de línea en el informe.

**INGRESOS:** multiplicar el valor por la cantidad de ingresos para el elemento de línea en el informe.

**SCADD:** multiplicar el valor por el número de veces que se llamó el evento de [!UICONTROL adiciones del carro de compras] por cada elemento de línea en el informe.

**SCREMOVE:** multiplicar el valor por el número de veces que se llamó el evento de [!UICONTROL eliminaciones del carro de compras] por cada elemento de línea en el informe.

**INSTANCIA:** multiplicar el valor por el número de instancias para el elemento de línea en el informe.

**CLIC:** multiplicar el valor por el número de clics para el elemento de línea en el informe.

**EVENTO:** multiplicar el valor por el número de veces que el evento personalizado específico se produjo por cada elemento de línea del informe.

**Ejemplo:** Si la Campaña A cuesta $ 10.000, [!UICONTROL la columna Campaigns ^ ~ Cost] contiene un valor de 10000 y la [!UICONTROL columna Campaigns ^~Costper~] contiene [!UICONTROL FIJO]. Al mostrar el Coste de la Campaña A en los informes, verá 10 000 $ como el coste fijo de la Campaña A correspondiente al intervalo de fechas.

**Ejemplo:** Si Campaña B cuesta aproximadamente 2 $ por clic, la [!UICONTROL columna Campaigns ^ ~ Cost] contiene 2 y la **[!UICONTROL columna Campaigns ^~Costper~]** contiene [!UICONTROL CLIC]. When displaying the Cost for Campaign B in the reports, Adobe calculates (2 * [number of clicks]) on the fly for the date range of the report. Esto le proporciona un cálculo del coste total basado en el número de clics realizados con la Campaña B.

### Fecha

Las fechas de las campañas suelen ser rangos (fechas de inicio y de finalización) asociados con campañas individuales. Las fechas deben aparecer en el formato AAAA/MM/DD. Por ejemplo, 2013/06/15-2013/06/30.

Para obtener más información, consulte [Clasificaciones de conversión](https://marketing.adobe.com/resources/help/en_US/admin/index.html#Conversion%20Classifications).

>[!NOTE]
>
>In the May 10, 2018, [!DNL Analytics] Maintenance release, Adobe started to limit the functionality of date-enabled and numeric classifications. Estos tipos de clasificaciones se eliminaron de las interfaces del Administrador y del Importador de clasificaciones. No es posible añadir nuevas clasificaciones numéricas y habilitadas por fecha. Las clasificaciones existentes se podrán seguir administrando (cargado y eliminado) a través del flujo de trabajo de clasificación estándar y permanecerán disponibles en los informes.

## Using dates in conjunction with [!UICONTROL classifications] {#section_966A07B228CD4643B258E73FB8BA150A}

[!UICONTROL Las clasificaciones] se pueden utilizar para asignar intervalos de fechas a las campañas u otras [!UICONTROL clasificaciones de conversión], lo que permite una medición de campañas más precisa. Después de especificar el intervalo de fechas de un valor, cualquier valor coincidente que ocurra fuera del intervalo de fechas no se clasificará. Esto es útil para la medición de campañas que desea utilizar las fechas exactas en que la campaña estaba en activo, y no todas las visitas que coinciden con la propia campaña. Para clasificar correctamente un valor con un intervalo de fechas, se debe cumplir lo siguiente:

* [!UICONTROL La clasificación] debe basarse en una variable de conversión.
* The [!UICONTROL classification] used must be set as Date-Enabled or Numeric 2.
* El intervalo de fechas involucrado debe contener una fecha de inicio y (opcionalmente) una fecha de finalización.

Para clasificar campañas basadas en intervalos de fechas:

1. Log in to [!DNL Analytics] and go to Admin &gt; Classifications.
1. Haga clic en la ficha **[!UICONTROL Exportación del explorador], compruebe que los ajustes de su clasificación habilitada mediante datos son correctos y, a continuación, haga clic en Exportar archivo.**
1. Abra este archivo en Microsoft Excel o cualquier otro editor de hoja de cálculo con el que esté familiarizado.
1. Una de las columnas terminará con

   ^~period~
which is the column to enter the date range in.
1. En esta columna, introduzca cada intervalo de fechas del valor en el formato siguiente:

   `YYYY/MM/DD - YYYY/MM/DD`. Compruebe lo siguiente:

   * Deje espacios en ambos lados del guión.
   * Utilice un guión (-) para separar intervalos, no un guión corto ni un guión largo.
   * Si el mes o el día es un dígito simple, hay un cero al inicio.
   * Hay un intervalo de fechas de inicio; el intervalo de fechas de finalización es opcional.

1. Save the file, and upload it to [!DNL Analytics] by going to Admin | Classifications | Import File.

>[!NOTE]
>
>Un valor clave específico no puede tener más de un intervalo de fechas.

## Resolución de problemas de clasificaciones

* [Problemas comunes de la carga ](https://helpx.adobe.com/analytics/kb/common-saint-upload-issues.html): Artículo de la base de conocimiento que describe los problemas que surgen de los formatos de archivo y del contenido de archivo incorrectos.

