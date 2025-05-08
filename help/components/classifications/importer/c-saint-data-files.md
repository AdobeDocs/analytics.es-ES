---
description: El importador permite realizar cargas masivas de datos de clasificaciones a los informes de análisis, mediante un archivo. Para que las cargas de datos sean correctas, es necesario usar un formato de archivo específico en la importación.
title: Archivos de datos de clasificación
feature: Classifications
exl-id: aa919a03-d461-4d12-adc1-6441fb467e63
source-git-commit: 04c626b1159be3e61569e462bf9d12957bd2a333
workflow-type: tm+mt
source-wordcount: '1032'
ht-degree: 90%

---

# Archivos de datos de clasificación (heredados)

El importador permite realizar cargas masivas de datos de clasificaciones a los informes de análisis, mediante un archivo. Para que las cargas de datos sean correctas, es necesario usar un formato de archivo específico en la importación.

Para ayudarle a crear archivos de datos válidos, puede descargar un archivo de plantilla que ofrece una estructura de datos en la que puede pegar los datos de las clasificaciones. Para obtener más información, consulte [Descargar plantilla de clasificaciones](/help/components/classifications/importer/c-download-saint-data.md).

Consulte [Estructura general de archivos](/help/components/classifications/importer/c-saint-data-files.md) para obtener más información sobre los límites en el uso de caracteres en las clasificaciones.

## Estructura general de los archivos

La siguiente ilustración es un archivo de datos de muestra:

![](assets/completed-saint-file.png)

Los archivos de datos deben cumplir las siguientes reglas estructurales:

* Las clasificaciones no pueden tener un valor de 0 (cero).
* Adobe recomienda limitar a 30 el número de columnas de importación y exportación.
* Los archivos actualizados deben usar la codificación de caracteres UTF-8 sin BOM.
* En una celda se pueden incrustar caracteres especiales, como por ejemplo tabulaciones, líneas nuevas y comillas, siempre que el formato de archivo especificado sea v2.1 y que en la celda [se haya usado el carácter de escape](/help/components/classifications/importer/importer-faq.md) correctamente.  Los caracteres especiales incluyen:

  ```text
  \t     tab character 
  \r     form feed character 
  \n    newline character 
  "       double quote
  ```

  La coma no es un carácter especial.

* Los nombres de clasificación no pueden contener un acento circunflejo (^) porque este carácter se usa para denotar una subclasificación.
* Utilice los guiones con cuidado. Por ejemplo, si se utiliza un guión (-) en un término de Social, Social interpretará el guión como un operador [!DNL Not] (el signo menos). Por ejemplo, si especifica *`fragrance-free`* como término al usar la importación, Social reconoce el término como sin fragancia *`minus`* y recopila publicaciones que mencionan *`fragrance`* pero no *`free`*.
* Para clasificar los datos de los informes, se aplican límites de caracteres. Por ejemplo, si carga un archivo de texto de clasificaciones para productos ( *`s.products`*) con nombres de productos superiores a 100 caracteres (bytes), los productos no se mostrarán en los informes. Los códigos de seguimiento y todas las variables de conversión personalizadas (eVars) admiten un máximo de 255 bytes. Esta directiva también se extiende a los valores de columna de clasificación y subclasificación, que están sujetos al mismo límite de 255 bytes.
* Archivo de datos delimitado por tabuladores (crear el archivo de plantilla con un editor de texto o una aplicación de hoja de cálculo).
* Extensión de archivo `.tab` o `.txt`.
* El signo de almohadilla (#) identifica la línea como comentario del usuario. Adobe ignora las líneas que comienzan por #.
* Un signo de almohadilla doble seguido de SC (`## SC`) identifica la línea como un comentario de encabezado previo al procesamiento que usan los informes. No elimine estas líneas.
* Las exportaciones de clasificación pueden tener claves duplicadas debido a los caracteres de línea nueva de la clave. En una exportación del FTP o del explorador, esto se puede resolver activando las comillas de la cuenta FTP. Esto colocará comillas alrededor de cada clave con caracteres de línea nueva.
* La celda C1 en la primera línea del archivo de importación contiene un identificador de versión que determina cómo las clasificaciones administran el uso de comillas a lo largo del resto del archivo.

   * v2.0 ignora las comillas y supone que todas forman parte de las claves y los valores especificados. Por ejemplo, considere este valor: &quot;Este es &quot;&quot;un valor&quot;&quot;&quot;. v2.0 lo interpretaría literalmente como: &quot;Este es &quot;&quot;un valor&quot;&quot;&quot;.
   * v2.1 indica a las clasificaciones que supongan que las comillas forman parte del formato del archivo utilizado en archivos de Excel. Entonces, v2.1 aplicaría el siguiente formato para el ejemplo anterior: Este es &quot;un valor&quot;.
   * Pueden surgir problemas cuando se especifica v2.1 en el archivo, pero lo que realmente se desea es v2.0, concretamente, cuando las comillas se utilizan de formas que son ilegales según el formato de Excel. Por ejemplo, si tiene un valor: &quot;VP SIN REPS&quot; S/l Dress w/ Overlay. Con v2.1, este formato es incorrecto (el valor debería estar comprendido entre comillas de apertura y cierre, y las comillas que forman parte del valor real deberían estar especificadas con comillas) y las clasificaciones no funcionarán más allá de este punto.
   * Asegúrese de realizar una de las siguientes acciones: cambiar el formato de archivo a v2.0 al cambiar el encabezado (celda C1) en los archivos que carga, O implementar correctamente el entrecomillado de Excel en todos los archivos.

* La primera fila (que no es de comentario) del archivo de datos contiene los encabezados de columna que se usan para identificar los datos de clasificación de esa columna. El importador requiere un formato específico para los encabezados de columna. Para obtener más información, consulte [Formato de encabezado de columna](/help/components/classifications/importer/c-saint-data-files.md).
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
   <td colname="col2"> <p>Solicita que Adobe genere automáticamente un identificador único para este elemento. </p> <p>En el contexto de campaña, este valor de control ordena a Adobe que asigne un identificador a cada elemento creativo. Consulte <a href="/help/components/classifications/importer/c-saint-data-files.md"  >Clave</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>Designa que la columna de datos representa el rango de fechas asociado con el elemento. Consulte <a href="/help/components/classifications/importer/c-saint-data-files.md"  >Fecha</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campo vacío </p> </td> 
   <td colname="col2"> <p>Representa un valor NULL para el campo actual. Utilícelo si una columna de datos concreta no aplica al registro actual. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modificadores PER </p> </td> 
   <td colname="col2"> <p>Designa que la columna de datos representa un campo de <span class="wintitle">Modificador PER</span>. Consulte <a href="/help/components/classifications/importer/c-saint-data-files.md"  >Encabezados de modificador PER </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Formato del encabezado de las columnas

>[!NOTE]
>
>Adobe recomienda limitar a 30 el número de columnas de importación y exportación.

Los archivos de clasificación admiten los siguientes encabezados de columna:

### Clave

Cada valor debe ser único en todo el sistema. El valor de este campo corresponde a un valor asignado a la variable de [!DNL Analytics] en la señalización de [!DNL JavaScript] de su sitio web. Los datos de esta columna pueden incluir ~autogen~ o cualquier otro código de seguimiento único.

### Encabezado de la columna Clasificación

>[!NOTE]
>
>Los valores del encabezado de la columna [!UICONTROL Clasificaciones] deben coincidir exactamente con la convención de nomenclatura de la clasificación; si no es así, la importación no se realizará correctamente. Por ejemplo, si el administrador cambia [!UICONTROL Campañas] por [!UICONTROL Nombres de campaña internos] en el [!UICONTROL Gestor de configuración de campañas], el encabezado de la columna del archivo debe cambiar también para que coincidan. &quot;Clave&quot; es un valor de clasificación reservado (encabezado). No se admiten nuevas clasificaciones denominadas &quot;Clave&quot;.

Además, el archivo de datos admite las siguientes convenciones de encabezado adicionales para identificar subclasificaciones y otras columnas de datos especializados:

### Encabezado de subclasificación

Por ejemplo, `Campaigns^Owner` es un encabezado de columna para la columna que contiene `Campaign Owner` valores. Del mismo modo, `Creative Elements^Size` es un encabezado de columna para la columna que contiene la subclasificación `Size` de la clasificación `Creative Elements`.

## Clasificaciones de resolución de errores

* [Problemas comunes de la carga](https://helpx.adobe.com/es/analytics/kb/common-saint-upload-issues.html): Artículo de la base de conocimiento que describe los problemas que surgen de los formatos de archivo y del contenido de archivo incorrectos.
