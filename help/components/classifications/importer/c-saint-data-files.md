---
description: El importador permite realizar cargas masivas de datos de clasificaciones a los informes de análisis, mediante un archivo. Para que las cargas de datos sean correctas, es necesario usar un formato de archivo específico en la importación.
subtopic: Classifications
title: Archivos de datos de clasificación
topic: Admin tools
uuid: f27bb812-56e0-472a-9993-d869f0fea700
translation-type: tm+mt
source-git-commit: af41b67c4fb1bb3cfe363be5619d382399cf5bca
workflow-type: tm+mt
source-wordcount: '1771'
ht-degree: 100%

---


# Archivos de datos de clasificación

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
* En una celda se pueden incrustar caracteres especiales, como por ejemplo tabulaciones, líneas nuevas y comillas, siempre que el formato de archivo especificado sea v2.1 y que en la celda se hayan usado convenientemente   [secuencias de escape](/help/components/classifications/importer/t-classifications-escape-data.md). Los caracteres especiales incluyen:

   ```
   \t     tab character 
   \r     form feed character 
   \n    newline character 
   "       double quote
   ```

   La coma no es un carácter especial.

* Las clasificaciones no pueden contener un acento circunflejo (^) porque este carácter se usa para denotar una subclasificación.
* Utilice los guiones con cuidado. Por ejemplo, si se utiliza un guión (-) en un término de Social, Social interpretará el guión como un operador [!DNL Not] (el signo menos). Por ejemplo, si especifica *`fragrance-free`* como término al usar la importación, Social reconoce el término como sin fragancia *`minus`* y recopila publicaciones que mencionan *`fragrance`* pero no *`free`*.
* Para clasificar los datos de los informes, se aplican límites de caracteres. Por ejemplo, si carga un archivo de texto de clasificaciones para productos ( *`s.products`*) con nombres de productos superiores a 100 caracteres (bytes), los productos no se mostrarán en los informes. Los códigos de seguimiento y todas las variables de conversión personalizadas (eVar) admiten un máximo de 255 bytes.
* Archivo de datos delimitado por tabuladores (crear el archivo de plantilla con un editor de texto o una aplicación de hoja de cálculo).
* Extensión de archivo [!DNL .tab] o [!DNL .txt].
* El signo de almohadilla (#) identifica la línea como comentario del usuario. Adobe ignora las líneas que comienzan por #.
* Un signo de almohadilla doble seguido de SC (## SC) identifica la línea como un comentario de encabezado previo al procesamiento que usan los informes. No elimine estas líneas.
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
   <td colname="col2"> <p>Solicita que Adobe genere automáticamente un identificador único para este elemento. </p> <p>En el contexto de campaña, este valor de control ordena a Adobe que asigne un identificador a cada elemento creativo. Consulte <a href="/help/components/classifications/importer/c-saint-data-files.md"  > Clave </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>~period~ </p> </td> 
   <td colname="col2"> <p>Designa que la columna de datos representa el rango de fechas asociado con el elemento. Consulte <a href="/help/components/classifications/importer/c-saint-data-files.md"  > Fecha </a>. </p> </td> 
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

>[!MORELIKETHIS]
>
>* [Problemas comunes de carga de ](https://helpx.adobe.com/es/analytics/kb/common-saint-upload-issues.html)


## Formato del encabezado de las columnas

>[!NOTE]
>
>Adobe recomienda limitar a 30 el número de columnas de importación y exportación.

Los archivos de clasificación admiten los siguientes encabezados de columna:

### Clave

Cada valor debe ser único en todo el sistema. El valor de este campo corresponde a un valor asignado a la variable de [!DNL Analytics] en la señalización de [!DNL JavaScript] de su sitio web. Los datos de esta columna pueden incluir ~autogen~ o cualquier otro código de seguimiento único.

### Encabezado de la columna Clasificación

Por ejemplo, Reports &amp; Analytics incluye automáticamente dos clasificaciones para variables de [!UICONTROL Campaña]: [!UICONTROL Campañas] y [!UICONTROL Elementos creativos]. Para añadir datos a la clasificación [!UICONTROL Campañas], el encabezado de la columna del archivo de datos de clasificación sería [!UICONTROL Campañas].

>[!NOTE]
>
>Los valores del encabezado de la columna [!UICONTROL Clasificaciones] deben coincidir exactamente con la convención de nomenclatura de la clasificación; si no es así, la importación no se realizará correctamente. Por ejemplo, si el administrador cambia [!UICONTROL Campañas] por [!UICONTROL Nombres de campaña internos] en el [!UICONTROL Gestor de configuración de campañas], el encabezado de la columna del archivo debe cambiar también para que coincidan.

Además, el archivo de datos admite las siguientes convenciones de encabezado adicionales, para identificar subclasificaciones y otras columnas de datos especializados:

### Encabezado de subclasificación

Por ejemplo, [!UICONTROL Campaigns^Owner] es el encabezamiento de columna de la columna que contiene valores [!UICONTROL Propietario de la campaña]. Del mismo modo, [!UICONTROL Creative Elements^Size] es el encabezamiento de columna de la columna que contiene la subclasificación [!UICONTROL Tamaño] de la clasificación [!UICONTROL Elementos creativos].

### Encabezados de métricas de clasificación

Por ejemplo, [!UICONTROL Campañas^~Coste] hace referencia a la métrica [!UICONTROL Coste] en la clasificación [!UICONTROL Campañas].

### Encabezados de modificador PER

Los encabezados de *`Per Modifier`* se marcan añadiendo *`~per`* al encabezado de métrica de la clasificación. Por ejemplo, si el encabezado *`Metric`* es *`Campaigns^~Cost`*, el encabezado del modificador PER es *`Campaigns^~Cost~per`*. Adobe admite las siguientes palabras clave *`PER Modifier`*:

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

**CLICK:** multiplicar el valor por el número de clics para el elemento de línea en el informe.

**EVENTO:** multiplicar el valor por el número de veces que el evento personalizado específico se produjo por cada elemento de línea del informe.

**Ejemplo:** Si la Campaña A tuvo un coste de 10 000 $, la columna [!UICONTROL Campaigns^~Cost] contiene un valor de 10 000 y la columna [!UICONTROL Campaigns^~Cost~per] contiene [!UICONTROL FIJO]. Al mostrar el Coste de la Campaña A en los informes, verá 10 000 $ como el coste fijo de la Campaña A correspondiente al intervalo de fechas.

**Ejemplo:** si la Campaña B cuesta aproximadamente 2 $ por clic, la columna [!UICONTROL Campaigns^~Cost] contiene 2 y la columna **[!UICONTROL Campaigns^~Cost~per]** contiene [!UICONTROL CLICK]. Al mostrar el Coste de la Campaña B en los informes, Adobe calcula (2 * [número de clics]) de inmediato para el intervalo de fechas del informe. Esto le proporciona un cálculo del coste total basado en el número de clics realizados con la Campaña B.

### Fecha

Las fechas de las campañas suelen ser rangos (fechas de inicio y de finalización) asociados con campañas individuales. Las fechas deben aparecer en el formato AAAA/MM/DD. Por ejemplo, 2013/06/15-2013/06/30.

Para obtener más información, consulte [Clasificaciones de conversión](https://docs.adobe.com/content/help/es-ES/analytics/admin/admin-tools/conversion-variables/conversion-classifications.html).

>[!NOTE]
>
>En la versión de mantenimiento de [!DNL Analytics] del 10 de mayo de 2018, Adobe empezó a limitar la funcionalidad de las clasificaciones numéricas y habilitadas por fecha. Estos tipos de clasificaciones se eliminaron de las interfaces del Administrador y del Importador de clasificaciones. No es posible añadir nuevas clasificaciones numéricas y habilitadas por fecha. Las clasificaciones existentes se podrán seguir administrando (cargado y eliminado) a través del flujo de trabajo de clasificación estándar y permanecerán disponibles en los informes.

## Usar fechas en conjunción con las [!UICONTROL clasificaciones] {#section_966A07B228CD4643B258E73FB8BA150A}

Las [!UICONTROL clasificaciones] se pueden usar para asignar intervalos de fechas a las campañas u otras [!UICONTROL clasificaciones] de conversión, lo que permite una medición de campaña más exacta. Después de especificar el intervalo de fechas de un valor, cualquier valor coincidente que ocurra fuera del intervalo de fechas no se clasificará. Esto es útil para la medición de campañas que desea utilizar las fechas exactas en que la campaña estaba en activo, y no todas las visitas que coinciden con la propia campaña. Para clasificar correctamente un valor con un intervalo de fechas, se debe cumplir lo siguiente:

* La [!UICONTROL clasificación] se debe basar en una variable de conversión.
* La [!UICONTROL clasificación] utilizada debe establecerse como Habilitada para la fecha o Numérica 2.
* El intervalo de fechas involucrado debe contener una fecha de inicio y (opcionalmente) una fecha de finalización.

Para clasificar campañas basadas en intervalos de fechas:

1. Inicie sesión en [!DNL Analytics] y vaya a Administración > Clasificaciones.
1. Haga clic en la ficha **[!UICONTROL Exportación del explorador]**, compruebe que los ajustes de su clasificación habilitada mediante datos son correctos y, a continuación, haga clic en Exportar archivo.
1. Abra este archivo en Microsoft Excel o cualquier otro editor de hoja de cálculo con el que esté familiarizado.
1. Una de las columnas finalizará con

   ^~period~, que es la columna en la que se introduce el intervalo de fechas.
1. En esta columna, introduzca cada intervalo de fechas del valor en el formato siguiente:

   `YYYY/MM/DD - YYYY/MM/DD`. Compruebe lo siguiente:

   * Deje espacios en ambos lados del guión.
   * Utilice un guión (-) para separar intervalos, no un guión corto ni un guión largo.
   * Si el mes o el día es un dígito simple, hay un cero al inicio.
   * Hay un intervalo de fechas de inicio; el intervalo de fechas de finalización es opcional.

1. Guarde el archivo y cárguelo en [!DNL Analytics] en Administración | Clasificaciones | Importar archivo.

>[!NOTE]
>
>Un valor clave específico no puede tener más de un intervalo de fechas.

## Clasificaciones de resolución de errores

* [Problemas comunes de la carga](https://helpx.adobe.com/es/analytics/kb/common-saint-upload-issues.html): Artículo de la base de conocimiento que describe los problemas que surgen de los formatos de archivo y del contenido de archivo incorrectos.

