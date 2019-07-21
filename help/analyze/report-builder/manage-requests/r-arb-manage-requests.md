---
description: Descripción de los campos para administrar solicitudes en el Creador de informes.
seo-description: Descripción de los campos para administrar solicitudes en el Creador de informes.
seo-title: 'Administrar solicitudes: definiciones'
solution: Analytics
title: 'Administrar solicitudes: definiciones'
topic: Creador de informes
uuid: 01 b 21 d 0 e-c 870-4 df 8-95 b 9-f 4 aef 1 f 4 d 16 b
translation-type: tm+mt
source-git-commit: 6a70b32b576cc7b5b6a6f0037d98e35b3f8c1426

---


# Administrar solicitudes: definiciones

Descripción de los campos para administrar solicitudes en el Creador de informes.

## Información general {#section_75C288C945FA4781A4EDF806711A5660}

El [!UICONTROL Administrador de solicitudes] proporciona una vista detallada del estado de todas las solicitudes creadas para una o todas las hojas del libro activo. También se pueden añadir, editar, actualizar y eliminar solicitudes (funciones asociadas generalmente al [!UICONTROL Asistente para solicitudes] y el [!UICONTROL Administrador de solicitudes]), haciendo clic con el botón derecho en una celda disponible de la hoja de cálculo de Excel que contenga solicitudes anteriores.

The [!UICONTROL Request Manager] displays when you click **[!UICONTROL Manage]** ( ![](assets/edit_request.gif) in the Report Builder toolbar.

>[!NOTE]
>
>El Creador de informes de Adobe impone dependencias de solicitud solo dentro de la misma hoja de cálculo, no entre hojas de cálculo. La restricción a las dependencias dentro de una única hoja de cálculo asegura la puntualidad de ejecución.

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
   <td colname="col2"> <p>Muestra las solicitudes de todas las hojas del libro activo. Para ver solicitudes de hojas concretas, desactive esta opción. Si desactiva esta opción, debe hacer clic en una ficha Hoja situada en la parte inferior del informe de Excel para ver las solicitudes asociadas a dicha hoja en el <span class="wintitle">Administrador de solicitudes</span>. La etiqueta situada junto a la casilla de verificación indica qué hoja del libro está seleccionada actualmente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hoja </p> </td> 
   <td colname="col2"> <p>Muestra el nombre de las hojas del libro. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Grupo de informes </p> </td> 
   <td colname="col2"> <p>Muestra el nombre del grupo de informes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervalo de fechas </p> </td> 
   <td colname="col2"> <p>Muestra el intervalo de fecha especificado del informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Granularidad </p> </td> 
   <td colname="col2"> <p>Determina la granularidad de la solicitud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Última ejecución </p> </td> 
   <td colname="col2"> <p>Especifica la fecha en la que el Creador de informes ejecutó la solicitud por última vez. Si corresponde, la columna <span class="wintitle">Última ejecución</span> de esta tabla también muestra un mensaje de diagnóstico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Agregar </p> </td> 
   <td colname="col2"> <p>Muestra el cuadro de diálogo Asistente para solicitudes. Consulte <a href="../../../analyze/report-builder/data-requests/t-create-a-data-request.md#task_65B453C8F015429A8EA73A1B64025B6C" type="task" format="dita" scope="local"> Crear una solicitud de datos</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Editar </p> </td> 
   <td colname="col2"> <p> (O Editar varias solicitudes) Edita una solicitud seleccionada. El sistema muestra el cuadro de diálogo <span class="wintitle">Asistente para solicitudes</span>. See <a href="../../../analyze/report-builder/manage-requests/t-edit-multiple-requests.md#task_70A13DBE43CD4BBEBE1B62459ADB3AD1" type="task" format="dita" scope="local"> Edit Multiple Requests</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eliminar </p> </td> 
   <td colname="col2"> <p>Elimina solicitudes. Es posible eliminar varias solicitudes seleccionadas. También se puede eliminar una solicitud de la lista seleccionándola y presionando Supr en el teclado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Seleccionar todo </p> </td> 
   <td colname="col2"> <p>Selecciona todas las solicitudes. El <span class="wintitle">Administrador de solicitudes</span> muestra el número de solicitudes seleccionadas en la parte inferior de la lista. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Desde celda </p> </td> 
   <td colname="col2"> <p>Obtiene datos para una solicitud desde la hoja de cálculo. Si una solicitud está asociada a la celda seleccionada en ese momento en la hoja de cálculo activa, la solicitud asociada se selecciona en la lista. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Actualizar </p> </td> 
   <td colname="col2"> <p>Actualiza una sola solicitud o una selección de ellas. (Consulte <a href="../../../analyze/report-builder/manage-requests/t-refresh-a-request.md#task_96556DB051A2479A955999D3837EE609" type="task" format="dita" scope="local"> Actualizar solicitudes</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Actualizar lista </p> </td> 
   <td colname="col2"> <p>Actualiza todas las solicitudes mostradas. Cuando se actualizan todas las solicitudes, el tiempo para actualizar la información desde el servidor al informe es directamente proporcional a la complejidad de las solicitudes de ese informe. En informes muy amplios, la actualización de todas las solicitudes puede tardar varios minutos. Por este motivo, puede que desee actualizar las solicitudes más urgentes de forma independiente y seleccionar la opción <span class="wintitle">Actualizar todo</span> en otro momento. </p> <p> <p>Nota: Se recomienda comprobar con frecuencia los resultados en el <span class="wintitle">Administrador de solicitudes</span> si se actualiza una hoja de cálculo que incluye varias solicitudes. Si se produce un error en la solicitud, el mensaje de error de la columna de diagnóstico ayuda a determinar el origen del error. Aunque casi siempre que falla una solicitud se genera un mensaje de error, se debe tener en cuenta que no siempre es así. Quizás observe que con una actualización no se actualizan los datos de una celda que incluye una referencia, o que una actualización elimina los datos de la celda. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

