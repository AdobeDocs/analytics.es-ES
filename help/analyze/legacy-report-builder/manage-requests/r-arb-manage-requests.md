---
description: Obtenga información sobre las descripciones de los campos para administrar solicitudes en Report Builder.
title: Administración de solicitudes en Report Builder
uuid: 01b21d0e-c870-4df8-95b9-f4aef1f4d16b
feature: Report Builder
role: User, Admin
exl-id: fd8c0145-4c7e-4f07-aa63-656a8a20724c
TQID: https://experienceleague.adobe.com/ZAVAW4NN9WCHCdj-ZPXDOflV4oC0-WPbClzkdlrf3JM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 563
ht-degree: 26%

---

# Administrar solicitudes: definiciones

{{legacy-arb}}

Vea los detalles del estado de una solicitud y utilice las descripciones de los campos para administrar solicitudes en Report Builder.

## Información general {#section_75C288C945FA4781A4EDF806711A5660}

El [!UICONTROL Administrador de solicitudes] proporciona una vista detallada del estado de todas las solicitudes creadas para todas las hojas o solo una hoja del libro activo. También puede agregar, editar, actualizar y eliminar una solicitud. Estas funciones suelen estar asociadas con el [!UICONTROL Asistente para solicitudes] y el [!UICONTROL Administrador de solicitudes] cuando se hace clic con el botón secundario en una celda disponible en la hoja de cálculo de Excel que contiene solicitudes anteriores.

Se muestra [!UICONTROL Administrador de solicitudes] al hacer clic en **[!UICONTROL Administrar]** ![](assets/edit_request.gif) en la barra de herramientas de Report Builder.

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
   <td colname="col2"> <p>Muestra las solicitudes de todas las hojas del libro activo. Para ver solicitudes de hojas específicas, desactive esta opción. Si desactiva esta opción, debe hacer clic en una ficha Hoja situada en la parte inferior del informe de Excel para ver las solicitudes asociadas a dicha hoja en el <span class="wintitle">Administrador de solicitudes</span>. La etiqueta junto a la casilla de verificación indica qué hoja del libro tiene actualmente el enfoque. </p> </td> 
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
   <td colname="col2"> <p>Muestra el intervalo de fechas especificado en el informe. </p> </td> 
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
   <td colname="col2"> <p>Muestra el diálogo Asistente para solicitudes. Consulte <a href="/help/analyze/legacy-report-builder/data-requests/t-create-a-data-request.md"   > Crear una solicitud de datos</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Editar </p> </td> 
   <td colname="col2"> <p> (O Editar varias) Edita una solicitud seleccionada. El sistema muestra el cuadro de diálogo <span class="wintitle">Asistente para solicitudes</span>. Consulte <a href="/help/analyze/legacy-report-builder/manage-requests/t-edit-multiple-requests.md"   >Editar varias solicitudes</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eliminar </p> </td> 
   <td colname="col2"> <p>Elimina solicitudes. Puede eliminar varias solicitudes seleccionadas. También puede eliminar una solicitud de la lista seleccionando la solicitud y pulsando Eliminar en el teclado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Seleccionar todo </p> </td> 
   <td colname="col2"> <p>Seleccionar todas las solicitudes. El <span class="wintitle">Administrador de solicitudes</span> muestra el número de solicitudes seleccionadas en la parte inferior de la lista. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Desde celda </p> </td> 
   <td colname="col2"> <p>Obtiene datos de una solicitud de la hoja de cálculo. Si una solicitud está asociada con la celda seleccionada actualmente en la hoja de cálculo activa, se seleccionará la solicitud asociada en la lista. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Actualizar </p> </td> 
   <td colname="col2"> <p>Actualiza una única solicitud o una selección de solicitudes. (Consulte <a href="/help/analyze/legacy-report-builder/manage-requests/t-refresh-a-request.md"   > Actualizar una solicitud</a>.) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Actualizar lista </p> </td> 
   <td colname="col2"> <p>Actualiza todas las solicitudes mostradas. Al actualizar todas las solicitudes, el tiempo para actualizar la información del servidor al informe es directamente proporcional a la complejidad de las solicitudes del informe. En el caso de los informes de gran tamaño, la actualización de todas las solicitudes puede tardar varios minutos. Por este motivo, puede que desee actualizar las solicitudes más urgentes de forma independiente y seleccionar la opción <span class="wintitle">Actualizar todo</span> en otro momento. </p> <p> <p>Nota: Se recomienda comprobar con frecuencia los resultados en el <span class="wintitle">Administrador de solicitudes</span> si se actualiza una hoja de cálculo que incluye varias solicitudes. Si se produce un error de solicitud, el mensaje de error de la columna de diagnóstico le ayuda a localizar el origen del error. Aunque en la mayoría de los casos se muestra un mensaje de error cuando falla una solicitud, tenga en cuenta que ocasionalmente no se genera ningún mensaje de error. Es posible que observe que una actualización no actualiza los datos en una celda que contiene una referencia o que una actualización elimina los datos de la celda. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>
