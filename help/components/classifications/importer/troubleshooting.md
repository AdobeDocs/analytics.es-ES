---
title: Solución de problemas del importador de clasificaciones
description: Problemas comunes de carga al usar el importador de clasificaciones.
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 12%

---


# Solución de problemas del importador de clasificaciones

Los problemas más comunes al cargar datos de clasificación en Adobe.

## Extensión o formato de archivo incorrecto

Las clasificaciones requieren un tipo de archivo y un formato específicos para cargar correctamente. Si se guardan indebidamente, aparecerá un error y las filas no se procesarán. El error devuelto es frecuentemente *&quot;La primera columna debe ser la clave&quot;*, pero puede ser cualquier número de errores. Asegúrese de comprobar lo siguiente:

* **Carga de una hoja de cálculo (.xlsx) en lugar de un archivo**.tab o .txt: Puede obtener el mensaje de error *&quot;La primera columna debe ser la clave&quot;* al cargar los archivos de clasificación en un formato incorrecto. El importador de clasificaciones no sabe cómo manejar archivos .xls o .xlsx. En el cuadro de diálogo &#39;Guardar como&#39; de Excel, defina el tipo correcto Guardar como:
   * En Windows, utilice el formato de archivo `Text (Tab delimited) (*.txt)`
   * En Mac, utilice el formato de archivo `Windows Formatted Text`.
* **Cambiar la extensión de nombre de archivo después de guardarla como un libro**: Si se intenta cambiar directamente el nombre de una extensión de archivo, se generará un libro no válido. Utilice solamente la función Guardar como de Excel o edite las clasificaciones en un editor de texto como Bloc de notas++.
* **Uso de extensiones** en mayúsculas: Las extensiones en mayúsculas (como `fileupload.TXT`) no funcionan. Rename the file to a lowercase extension (`fileupload.txt`).
* **Codificación** de caracteres no coincidente: Asegúrese de que la codificación de la carga de clasificación guardada coincide con la codificación original cuando se descargó la plantilla. Si carga un archivo UTF-16 cuando se codificó originalmente en UTF-8, las cargas producen resultados inesperados. Adobe recomienda cargar archivos con UTF-8 sin marcas de orden de bytes.

## Contenido de archivo no válido

Si carga un archivo con un formato incorrecto, el cargador intentará importar todas las filas válidas posibles. Algunos problemas comunes con los datos de clasificación:

* **Filas que ya están clasificadas**: Al intentar cargar filas que ya están clasificadas con el mismo valor, el importador devuelve filas que no tuvieron ningún efecto. Este resultado es de esperar, ya que las clasificaciones no reclasifican un valor de clave con la misma clasificación. Se trata de una notificación en lugar de un error. Si no modifica todas las filas de un archivo de exportación, no debe preocuparse. Adobe solo recomienda cargar las filas cambiadas.
* **El encabezado no coincide con la variable que se está cargando**: Si descarga una plantilla de clasificación para la dimensión Código de seguimiento e intenta cargarla en una clasificación de eVar, se producirá un error. Utilice solo archivos de exportación para las variables específicas desde las que se haya realizado la exportación.
* **Un valor de clave o clasificación contiene el valor 0**: Las clasificaciones no pueden diferenciar el valor 0 de una celda en blanco, por lo que no pueden clasificar este valor. Consulte Preguntas más frecuentes sobre [clasificaciones](../faq.md).
* **El archivo de clasificación contiene comas o caracteres** especiales: Consulte Preguntas más frecuentes sobre [clasificaciones](../faq.md).
* **Fichas adicionales del archivo** cargado: A veces, al editar archivos de clasificación, se puede deslizar accidentalmente una ficha adicional. Cada fila requiere un número idéntico de tabulaciones para que se pueda procesar correctamente. Para buscar fichas adicionales dentro del archivo, resalte todo el texto en un editor de texto sin formato y asegúrese de que ninguna fila tenga espacio adicional al final.
* **Existen valores de clave de duplicado en el archivo**: Cada valor clave sólo puede tener una clasificación por columna. Si intenta clasificar el mismo valor varias veces, el importador genera un error.
* **Las subclasificaciones existen y están configuradas** incorrectamente: Si existen subclasificaciones, compruebe lo siguiente:
   * Todos los valores de las subclasificaciones deben tener un valor de clasificación principal.
   * No puede haber dos subclasificaciones que hagan referencia al mismo valor de clasificación principal.
* **Coincidencia** de columna: Puede obtener el mensaje de error *&quot;La clave en línea tiene demasiadas columnas&quot;* si hay un número no válido de columnas en una fila determinada. Por ejemplo: tiene 3 columnas en la carga de la clasificación y la variable solo tiene una clasificación. Valide el archivo de carga para asegurarse de que el número de columnas no es bueno al número de clasificaciones configuradas para esa variable.

## Solución de problemas de importación de FTP

Las siguientes son causas comunes de que las clasificaciones de FTP no procesen los archivos cargados:

* **Falta el archivo**.fin: Cree un documento de texto en blanco en el escritorio y cambie el nombre de la extensión de nombre de archivo de .txt a .fin. El nombre de este archivo .fin debe coincidir con el nombre del archivo de clasificación en cuestión. Por ejemplo, si el nombre del archivo FTP es `fileupload.tab`, asigne un nombre al archivo .fin `fileupload.fin`. Una vez cargado el archivo .fin, ambos archivos desaparecen.
* **Cargando el archivo .fin antes del archivo** de clasificación: A veces se crea un archivo .fin antes de que el archivo de clasificaciones termine de cargarse en el sitio FTP. El procesamiento puede fallar cuando los archivos se cargan desordenados. Elimine ambos archivos, agregue primero el archivo de clasificación y, a continuación, el archivo .fin después de cargar completamente el archivo de clasificación.
* **El tamaño del archivo es demasiado grande**: Adobe recomienda mantener el tamaño de los archivos de clasificación lo más pequeño posible para garantizar un procesamiento rápido.
* **Los archivos existentes ya se están procesando**: Si se cargan varios archivos para la misma variable y grupo de informes, el archivo antiguo deja de procesarse en favor del nuevo. Si carga clasificaciones con varios archivos, espere a que se confirme que los archivos existentes han finalizado el procesamiento antes de cargar los nuevos.
* **Los archivos cargados no se colocan en el directorio** raíz: Los archivos cargados en el sitio FTP de Adobe deben colocarse en el directorio raíz. Si los archivos de importación de clasificación se colocan en subcarpetas, no se recogen ni se procesan.

Si sigue teniendo problemas al cargar un archivo de clasificación, póngase en contacto con el Servicio de atención al cliente de Adobe.
