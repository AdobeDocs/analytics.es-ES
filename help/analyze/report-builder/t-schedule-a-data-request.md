---
description: Los informes se pueden programar para enviarlos de acuerdo al formato de archivo y la hora que se definan.
seo-description: Los informes se pueden programar para enviarlos de acuerdo al formato de archivo y la hora que se definan.
seo-title: Programar una solicitud de datos
solution: Analytics
title: Programar una solicitud de datos
topic: Creador de informes
uuid: f 6 d 8 c 90 f-e 185-4 d 60-8035-f 20 f 74 bfcd 89
translation-type: tm+mt
source-git-commit: 6a70b32b576cc7b5b6a6f0037d98e35b3f8c1426

---


# Programar una solicitud de datos

Los informes se pueden programar para enviarlos de acuerdo al formato de archivo y la hora que se definan.

**Para programar una solicitud de datos**

1. Genere y guarde un informe.
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]**.

   La ficha [!UICONTROL Informes programados] resume todas las tareas que se han creado, así como el número de tareas restantes.
1. En la ficha **** Informes programados, haga clic en **[!UICONTROL Nuevo]**.
1. El Asistente de programación básico muestra:

   ![](assets/simple-schedule-wizard.png)

1. En el [!UICONTROL Asistente de programación básico], configure las siguientes opciones:

* **Seleccionar informe**: El nombre del informe. Para los nuevos informes programados, este campo se completa con el nombre del libro activo.

<table id="table_6D5B1B832EB0451293F1902E2A1D1068"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Seleccionar informe </p> </td> 
   <td colname="col2"> <p>El nombre del informe. Para los nuevos informes programados, este campo se completa con el nombre del libro activo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Seleccionar </p> </td> 
   <td colname="col2"> <p>Muestra la página <span class="wintitle">Seleccionar informe</span>. Se puede seleccionar un informe del servidor (donde se almacenan todos los libros programados previamente) o del equipo local. Si se selecciona un libro de la unidad local en formato <span class="filepath">.xls</span>, el sistema convierte el archivo a <span class="filepath">.xlsx</span>. Como parte de la conversión, el archivo se abre en Excel y se activa. Si el libro seleccionado para el informe programado tiene el mismo nombre de archivo que el libro abierto actualmente en Excel, el sistema selecciona el archivo local en lugar del archivo cargado previamente. Si selecciona un informe desde el repositorio de programación, se creará una copia del libro en el servidor, con su nombre de archivo actualizado con 1, y el informe programado recién creado utilizará el libro copiado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Personalizar </p> </td> 
   <td colname="col2"> <p>Le permite personalizar el formato de fecha. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Para </p> </td> 
   <td colname="col2"> <p>Muestra la libreta de direcciones de Outlook, si corresponde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enviar a: Correo electrónico </p> </td> 
   <td colname="col2"> <p>Destinatario de correo electrónico del informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enviar a: Lista de publicación </p> </td> 
   <td colname="col2"> <p>Muestra las listas de distribución disponibles para esta empresa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Power BI </p> </td> 
   <td colname="col2"> <p>Consulte <a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_BA137EA92A46483F83BB5C1C40FBA002" format="dita" scope="local">Publicar libro en Microsoft Power BI</a> para obtener más información. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Asunto </p> </td> 
   <td colname="col2"> <p>Descripción definida por el usuario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Programación </p> </td> 
   <td colname="col2"> <p> Permite especificar el momento de envío del informe. (Inmediatamente, por hora, diariamente, semanalmente, mensualmente, trimestralmente y anualmente). </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Advanced Delivery Options]** to configure file and publishing options:

<table id="table_1BA8A5600DE94A33B83B096E69CE15F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ficha <b>Programación</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hora de envío </p> </td> 
   <td colname="col2"> <p>Permite programar el informe inmediatamente o para un momento posterior. La hora del día se relaciona con la zona horaria especificada en el equipo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modelo de periodicidad </p> </td> 
   <td colname="col2"> <p>Envía el informe en función de sus selecciones. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervalo de periodicidad </p> </td> 
   <td colname="col2"> <p>Permite especificar cuándo iniciar y detener la recepción del informe. </p> <p> <p>Nota: Si se programa un informe el primer día de cualquier período actual (semana, mes, trimestre o año), solo se devuelven datos del primer día. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ficha <b>Opciones de archivo</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Formato del archivo </p> </td> 
   <td colname="col2"> <p>Permite seleccionar un formato de envío de Excel 2007 (<span class="filepath">.xlsx</span>) o 2003 (<span class="filepath">.xls</span>), <span class="filepath">.pdf</span>, <span class="filepath">.csv</span>, <span class="filepath">.mht</span>, <span class="filepath">.txt</span> y <span class="filepath">.xml</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Destino del archivo </p> </td> 
   <td colname="col2"> <p> Especifica un correo electrónico o FTP. Las opciones de la página dependen de lo que seleccione. Para los datos de FTP, debe comprobar que el host se encuentra disponible de forma externa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lista de publicaciones </p> </td> 
   <td colname="col2"> <p> Si el informe programado se envía a varias listas de publicación, el informe se ejecuta una vez para cada lista. Los grupos de informes variables se reemplazan por el grupo de informes asignado a la lista de publicación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Idioma del contenido del archivo </p> </td> 
   <td colname="col2"> <p>Especifica el idioma que desea utilizar para la carta de presentación. Puede seleccionar chino (simplificado o tradicional), alemán, francés, japonés, coreano, portugués de Brasil o español. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ficha <b>Opciones de publicación</b> </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Publicación en Power BI </p> </td> 
   <td colname="col2"> 
    <ul id="ul_40697E4FB2CE4F34B857FBF153D6D6D5"> 
     <li id="li_023E4750814D415EBC899269C9EA5D46"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_BA137EA92A46483F83BB5C1C40FBA002" format="dita" scope="local"> Publicar libro en Power BI</a> </li> 
     <li id="li_9B684BE22AF94ABC903405EE83951A80"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_E48148793E794169B766C73995897B9F" format="dita" scope="local"> Publicar todas las solicitudes del Creador de informes como conjuntos de datos de Power BI</a> </li> 
     <li id="li_7B0BD285BC1749D1B2C65759CA97877B"><a href="../../analyze/report-builder/c-publish-power-bi/integration-power-bi.md#section_6F8422B90D3F4F7EB5D4C97BFFA807AD" format="dita" scope="local"> Publicar todas las tablas con formato como conjuntos de datos de Power BI</a> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Etiquetar este informe de Power BI como </p> </td> 
   <td colname="col2"> <p>Detalles de etiquetado </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL OK]**, then click **[!UICONTROL Exit]**.

   El Creador de informes muestra el informe programado en el [Administrador de tareas programadas](../../analyze/report-builder/r-arb-scheduled-reports.md#section_69306B8D833F4DF7BBFA53753B0E6C31).
