---
description: El cuadro de diálogo Administración de datos en Herramientas de administración proporciona una descripción general de los grupos de informes que se han configurado para el control de datos, si se han asignado a una organización de Experience Cloud y si se ha dispuesto una política de retención de datos para este grupo de informes.
title: Consulta o administración de la configuración de control de datos del grupo de informes
uuid: f3b83e8e-00af-4a60-a5de-29b5c43f6788
exl-id: 87b0be42-1098-4e72-8eb8-0c1bb56791f8
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 98%

---

# Consulta o administración de la configuración de control de datos del grupo de informes

El cuadro de diálogo Administración de datos en Herramientas de administración proporciona una descripción general de los grupos de informes que se han configurado para el control de datos, si se han asignado a una organización de Experience Cloud y si se ha dispuesto una política de retención de datos para este grupo de informes.

1. Inicie sesión en Adobe Experience Cloud.
1. Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Control de datos]**.

   Verá todos los grupos de informes que forman parte de su empresa de inicio de sesión:

   ![](assets/privacy_setup_an.png)

<table id="table_448292730FF0475E9DCB731882F9A29B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuración </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Grupos de informes </p> </td> 
   <td colname="col2"> <p>En la primera línea se enumera el nombre descriptivo del grupo de informes. La segunda línea contiene el nombre interno del grupo de informes. Si se le permite establecer etiquetas para un grupo de informes, la primera línea será un vínculo al que puede hacer clic que le conducirá a la página de etiquetado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Asignación a organizaciones </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EF8F613B0C5E42D19DB60BD0C89C114B"> 
     <li id="li_B35EE88555F547EFBF55ADE9D0C9EC3B"><b>Asignado</b>: este grupo de informes ya ha sido asignado a la organización Experience Cloud como la empresa de inicio de sesión de Analytics en la que inicia sesión. Solo pueden etiquetarse los grupos de informes que tengan esta configuración. </li> 
     <li id="li_4E800BF80CFF477BAA091EF272D9071C"><b>Asignar grupo de informes:</b> al hacer clic en este vínculo, podrá <a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/report-suite-mapping.html">asignar un grupo de informes</a> a una organización Experience Cloud. <p>Esto significa que se le redireccionará a la página de administración de asignación de grupos de informes de la organización de Experience Cloud, donde tendrá que encontrar el grupo de informes y asignarlo a la organización apropiada. Una vez que haya completado ese paso, vuelva a esta interfaz de usuario de control de datos. </p> </li> 
     <li id="li_FF825A65D089487BBF5FCB0D74D41CD7"><b>Asignado a otra organización:</b> otra organización de Experience Cloud ya ha asignado este grupo de informes a su organización. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Política de retención de datos </p> </td> 
   <td colname="col2"> <p>La implementación de la privacidad datos de Analytics requiere que establezca una política de retención de datos. </p> <p>Esta configuración indica: </p> 
    <ul> 
     <li>Se ha implementado una política de retención de datos para este grupo de informes; y </li> 
     <li>cuánto tiempo retiene Adobe los datos antes de eliminarlos. El periodo de retención de datos predeterminado es de 25 meses. </li> 
    </ul> <p>Nota: Adobe Analytics no puede ayudarle con el tratamiento de solicitudes en la API de privacidad de datos (es decir, el procesamiento de las solicitudes de acceso o eliminación que reciba de sus usuarios finales) si no se ha establecido el periodo de retención de datos. Póngase en contacto con su gestor de éxito de los clientes para establecer el periodo de retención de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Grupos </p> </td> 
   <td colname="col2"> <p>La funcionalidad de agrupado actualmente no está implementada. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Barra lateral izquierda </p> </td> 
   <td colname="col2"> <p>Haga clic en el icono de embudo para abrir o cerrar la barra lateral. </p> <p>La sección de Asignación a organizaciones muestra el número de grupos de informes que se encuentran en cada una de las categorías descritas. </p> <p>La sección de Política de retención de datos muestra cada una de las políticas de retención de datos únicas en vigor para su organización y el número de grupos de informes que han sido asignados a dicha política de retención. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Exportar a CSV </p> </td> 
   <td colname="col2"> <p>Si marca la casilla de verificación que está junto a uno o más grupos de informes, se muestra la opción <span class="uicontrol">Exportar a CSV</span>. Esta opción le permite descargar un archivo CSV que contiene todas las definiciones de etiqueta actuales para todas las variables de todos los grupos de informes seleccionados. </p> <p>Le recomendamos que su equipo legal revise sus opciones de etiquetado, algo que esta opción facilita. En lugar de tener que realizar la revisión con una sesión iniciada en la interfaz de Administración de datos, puede compartir el archivo .CSV con ellos. </p> <p><img placement="break"  src="assets/export_csv.png" width="300px" id="image_5FE821B2D07B402D8E0F6FE53D6FC52E" /> </p> </td> 
  </tr> 
 </tbody> 
</table>
