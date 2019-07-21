---
description: Descripción de los campos para el Administrador de tareas programadas.
seo-description: Descripción de los campos para el Administrador de tareas programadas.
seo-title: Administrador de tareas programadas
solution: Analytics
title: Administrador de tareas programadas
topic: Creador de informes
uuid: dec 259 f 0-2 a 04-4 c 94-abbc -5008 cf 2 f 1 cb 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Administrador de tareas programadas

Descripción de los campos para el Administrador de tareas programadas.

El Administrador de tareas programadas le permite ver una lista de los informes programados existentes, así como sus destinatarios, detalles de la programación y formato de los archivos. También le permite reactivar libros programados que no se ejecutaron debido a algún error.

<table id="table_21B07A0B5F1D4435A4E882E45A7A6B6E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ficha <b>Informes programados</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre del informe </p> </td> 
   <td colname="col2"> <p>Indica el nombre de la tarea programada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Correo electrónico/FTP </p> </td> 
   <td colname="col2"> <p>Dirección de correo electrónico o FTP del destinatario. </p> <p>Nota: Si el correo electrónico está seleccionado, los informes que tengan un tamaño mayor que 1 MB se adjuntan directamente al correo electrónico como un archivo .zip. Esta función no se puede desactivar y ayuda a que el tamaño de archivo siempre sea reducido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Opciones de publicación </p> </td> 
   <td colname="col2"> <p>Esta columna indicará Power BI si alguna de las <a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#concept_0C4105AA10F9460A872C2489C9CD7945" format="dita" scope="local"> opciones de publicación de Power BI</a> está seleccionada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Programa </p> </td> 
   <td colname="col2"> <p>Tipo de envío programado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Formato del archivo </p> </td> 
   <td colname="col2"> <p> Formato de envío del informe como, por ejemplo, Excel, PDF, HTML, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Reactivar </p> </td> 
   <td colname="col2"> <p>Cuando un libro programado no puede ejecutarse, el Creador de informes intenta ejecutar el libro dos veces más cada quince minutos. Tras tres intentos fallidos, el Creador de informes desactiva la programación y muestra el botón <span class="wintitle">Reactivar</span>. Cuando se reactiva un libro, el envío programado se reinicia desde el momento en que se desactivó. </p> <p>Por ejemplo, si un libro programado se desactivó hace 14 días y se ha reactivado hoy, se ejecuta por cada día que falte y se enviará 14 veces. Si no desea que el libro se envíe los días que faltan, puede eliminar el libro programado y posteriormente crear un nuevo libro utilizando los mismos parámetros de programación. </p> <p> <p>Nota: No se debe reactivar un libro a no ser que se conozcan los motivos por el que el sistema lo desactivó. Una solución al problema consiste en descargar un libro desactivado y actualizarlo en el cliente. Si no aparecen errores, debería poder reactivarlo. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enviado por última vez </p> </td> 
   <td colname="col2"> <p>La fecha y la hora en que se envió el informe por última vez. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ficha <b>Destinatario</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Correo electrónico del destinatario </p> </td> 
   <td colname="col2"> Destinatario de correo electrónico del informe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Informes </p> </td> 
   <td colname="col2"> El informe o informes enviados a cada destinatario. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ficha <b>Historial de informes</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre del archivo </p> </td> 
   <td colname="col2"> Indica el nombre de la tarea programada. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fecha </p> </td> 
   <td colname="col2"> La fecha y la hora en que se envió el informe por última vez. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Estado </p> </td> 
   <td colname="col2"> El estado indica si el informe está Enviado o No enviado. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Correo electrónico/FTP </p> </td> 
   <td colname="col2"> La dirección de correo electrónico o FTP del destinatario del informe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Formato del archivo </p> </td> 
   <td colname="col2"> Formato de envío del informe como, por ejemplo, Excel, PDF, HTML, etc. </td> 
  </tr> 
 </tbody> 
</table>
