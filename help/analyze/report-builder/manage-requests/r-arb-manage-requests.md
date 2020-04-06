---
description: Descripción de los campos para administrar solicitudes en Report Builder.
title: 'Administrar solicitudes: definiciones'
topic: Report builder
uuid: 01b21d0e-c870-4df8-95b9-f4aef1f4d16b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Administrar solicitudes: definiciones

Descripción de los campos para administrar solicitudes en Report Builder.

## Información general {#section_75C288C945FA4781A4EDF806711A5660}

El [!UICONTROL Request Manager] proporciona una vista detallada del estado de todas las solicitudes creadas para todas las hojas o solo una hoja del libro activo. También puede agregar, editar, actualizar y eliminar una solicitud (funciones generalmente asociadas con [!UICONTROL Request Wizard] y [!UICONTROL Request Manager]) haciendo clic con el botón secundario en una celda disponible en la hoja de cálculo de Excel que contenga solicitudes anteriores.

The [!UICONTROL Request Manager] displays when you click **[!UICONTROL Manage]** ( ![](assets/edit_request.gif) in the Report Builder toolbar.

>[!NOTE] Adobe Report Builder exige dependencias de solicitud únicamente en la misma hoja de cálculo, no entre hojas de cálculo. La restricción a las dependencias dentro de una única hoja de cálculo asegura la puntualidad de ejecución.

## Definiciones {#section_FD29D8614DE74F32A0027FA130F40304}

<table id="table_0880204181074BDBBA37E3DF2972A672"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Todas las hojas </p> </td> 
   <td colname="col2"> <p>Muestra las solicitudes de todas las hojas del libro activo. Para vista de solicitudes de hojas específicas, desactive esta opción. Si desactiva esta opción, debe hacer clic en una ficha Hoja situada en la parte inferior del informe de Excel para ver las solicitudes asociadas a dicha hoja en el <span class="wintitle">Administrador de solicitudes</span>. La etiqueta junto a la casilla de verificación indica qué hoja del libro está seleccionada actualmente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hoja </p> </td> 
   <td colname="col2"> <p>Muestra el nombre de las hojas del libro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Report Suite </p> </td> 
   <td colname="col2"> <p>Muestra el nombre del grupo de informes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervalo de fecha </p> </td> 
   <td colname="col2"> <p>Muestra el intervalo de fechas especificado del informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Granularidad </p> </td> 
   <td colname="col2"> <p>Especifica la granularidad de la solicitud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Última ejecución </p> </td> 
   <td colname="col2"> <p>Especifica la fecha en la que Report Builder ejecutó la solicitud por última vez. Si corresponde, la columna <span class="wintitle">Última ejecución</span> de esta tabla también muestra un mensaje de diagnóstico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Agregar </p> </td> 
   <td colname="col2"> <p>Muestra el cuadro de diálogo Asistente para solicitudes. Consulte <a href="/help/analyze/report-builder/data-requests/t-create-a-data-request.md"   >Crear una solicitud de datos</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Editar </p> </td> 
   <td colname="col2"> <p> (O Editar varias solicitudes) Edita una solicitud seleccionada. El sistema muestra el cuadro de diálogo <span class="wintitle">Asistente para solicitudes</span>. Consulte <a href="/help/analyze/report-builder/manage-requests/t-edit-multiple-requests.md"   >Editar varias solicitudes</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eliminar </p> </td> 
   <td colname="col2"> <p>Elimina solicitudes. Puede eliminar varias solicitudes seleccionadas. También puede eliminar una solicitud en la lista si selecciona la solicitud y pulsa Eliminar en el teclado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Seleccionar todo </p> </td> 
   <td colname="col2"> <p>Seleccione todas las solicitudes. El <span class="wintitle">Administrador de solicitudes</span> muestra el número de solicitudes seleccionadas en la parte inferior de la lista. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Desde celda </p> </td> 
   <td colname="col2"> <p>Obtiene datos de una solicitud de la hoja de cálculo. Si una solicitud está asociada a la celda seleccionada actualmente en la hoja de cálculo activa, se selecciona la solicitud asociada en la lista. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Actualizar </p> </td> 
   <td colname="col2"> <p>Actualiza una sola solicitud o una selección de ellas. (See <a href="/help/analyze/report-builder/manage-requests/t-refresh-a-request.md"   > Refresh a Request</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Actualizar Lista </p> </td> 
   <td colname="col2"> <p>Actualiza todas las solicitudes mostradas. Cuando se actualizan todas las solicitudes, el tiempo para actualizar la información del servidor al informe es directamente proporcional a la complejidad de las solicitudes del informe. Para informes muy grandes, la actualización de todas las solicitudes puede requerir varios minutos. Por este motivo, puede que desee actualizar las solicitudes más urgentes de forma independiente y seleccionar la opción <span class="wintitle">Actualizar todo</span> en otro momento. </p> <p> <p>Nota: Se recomienda comprobar con frecuencia los resultados en el <span class="wintitle">Administrador de solicitudes</span> si se actualiza una hoja de cálculo que incluye varias solicitudes. Si se produce un error en la solicitud, el mensaje de error en la columna de diagnóstico le ayuda a identificar el origen del error. Aunque en la mayoría de los casos se muestra un mensaje de error cuando falla una solicitud, tenga en cuenta que, ocasionalmente, no se genera ningún mensaje de error. Puede observar que una actualización no actualiza los datos de una celda que contiene una referencia o que una actualización elimina los datos de la celda. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

