---
description: Obtenga información sobre las descripciones de los campos para administrar solicitudes en Report Builder.
title: Administración de solicitudes en Report Builder
uuid: 01b21d0e-c870-4df8-95b9-f4aef1f4d16b
feature: Report Builder
role: User, Admin
exl-id: fd8c0145-4c7e-4f07-aa63-656a8a20724c
source-git-commit: 66b7de0b008364e47253d319785c204ca479ab26
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 74%

---

# Administrar solicitudes: definiciones

Vea los detalles del estado de una solicitud y utilice las descripciones de los campos para administrar solicitudes en Report Builder.

## Información general {#section_75C288C945FA4781A4EDF806711A5660}

El [!UICONTROL Administrador de solicitudes] proporciona una vista detallada del estado de todas las solicitudes creadas para todas las hojas o solo una hoja del libro activo. También puede agregar, editar, actualizar y eliminar una solicitud. Estas funciones suelen estar asociadas con el [!UICONTROL Asistente para solicitudes] y el [!UICONTROL Administrador de solicitudes] cuando se hace clic con el botón secundario en una celda disponible en la hoja de cálculo de Excel que contiene solicitudes anteriores.

Se muestra [!UICONTROL Administrador de solicitudes] al hacer clic en **[!UICONTROL Administrar]** ![](assets/edit_request.gif) en la barra de herramientas del Report Builder.

>[!NOTE]
>
>Adobe Report Builder exige dependencias de solicitud únicamente en la misma hoja de cálculo, no entre hojas de cálculo. La restricción a las dependencias dentro de una sola hoja de cálculo garantiza la puntualidad de ejecución.

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
   <td colname="col1"> <p>Report Suite </p> </td> 
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
   <td colname="col2"> <p>Especifica la fecha en la que Report Builder ejecutó la solicitud por última vez. Si corresponde, la columna <span class="wintitle">Última ejecución</span> de esta tabla también muestra un mensaje de diagnóstico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Agregar </p> </td> 
   <td colname="col2"> <p>Muestra el cuadro de diálogo Asistente para solicitudes. Consulte <a href="/help/analyze/report-builder/data-requests/t-create-a-data-request.md"   > Crear una solicitud de datos</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Editar </p> </td> 
   <td colname="col2"> <p> (O Editar varias solicitudes) Edita una solicitud seleccionada. El sistema muestra el cuadro de diálogo <span class="wintitle">Asistente para solicitudes</span>. Consulte <a href="/help/analyze/report-builder/manage-requests/t-edit-multiple-requests.md"   >Editar varias solicitudes</a>. </p> </td> 
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
   <td colname="col2"> <p>Actualiza una sola solicitud o una selección de ellas. (Consulte <a href="/help/analyze/report-builder/manage-requests/t-refresh-a-request.md"   > Actualizar una solicitud</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Actualizar lista </p> </td> 
   <td colname="col2"> <p>Actualiza todas las solicitudes mostradas. Cuando se actualizan todas las solicitudes, el tiempo para actualizar la información desde el servidor al informe es directamente proporcional a la complejidad de las solicitudes de ese informe. En informes muy amplios, la actualización de todas las solicitudes puede tardar varios minutos. Por este motivo, puede que desee actualizar las solicitudes más urgentes de forma independiente y seleccionar la opción <span class="wintitle">Actualizar todo</span> en otro momento. </p> <p> <p>Nota: Se recomienda comprobar con frecuencia los resultados en el <span class="wintitle">Administrador de solicitudes</span> si se actualiza una hoja de cálculo que incluye varias solicitudes. Si se produce un error en la solicitud, el mensaje de error de la columna de diagnóstico ayuda a determinar el origen del error. Aunque casi siempre que falla una solicitud se genera un mensaje de error, se debe tener en cuenta que no siempre es así. Quizás observe que con una actualización no se actualizan los datos de una celda que incluye una referencia, o que una actualización elimina los datos de la celda. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>
