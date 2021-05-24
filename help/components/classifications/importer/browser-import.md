---
description: Los datos de clasificación pueden importarse (cargarse) a través del explorador web. Este método restringe la carga de datos de clasificación a un solo grupo de informes.
subtopic: Classifications
title: Importación del explorador
feature: Herramientas de administración
uuid: 56dfbf4c-36e6-49f4-b5cb-8ab714432825
exl-id: 5bef1f6d-9b27-464d-8343-472f300a7437
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 100%

---

# Importación del explorador

Los datos de clasificación pueden importarse (cargarse) a través del explorador web. Este método restringe la carga de datos de clasificación a un solo grupo de informes.

## Importación del explorador {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

Los datos de clasificación pueden importarse (cargarse) a través del explorador web. Este método restringe la carga de datos de clasificación a un solo grupo de informes.

**[!UICONTROL Administración]** > **[!UICONTROL Importador de clasificaciones]**

## Importación del explorador de clasificaciones: descripciones de los campos {#section_F628C47081DA4026A4D30E3D3454B1DA}

<table id="table_7FC7E510E7E74C2D9E8F316C5C6B66DB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Seleccionar grupo de informes </td> 
   <td colname="col2"> <p>El grupo de informes donde deben importarse los datos de las clasificaciones. El archivo de datos de importación debe coincidir con el formato del conjunto de datos del grupo de informes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conjunto de datos a clasificar </td> 
   <td colname="col2"> <p>El conjunto de datos que debe recibir las clasificaciones. La lista desplegable incluye todos los informes de los conjuntos de informes que se han configurado para las clasificaciones. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Seleccionar un archivo para importar </td> 
   <td colname="col2"> <p>Permite explorar para buscar el archivo de datos de importación que debe cargarse. </p> <p>Nota: El límite de tamaño del archivo de carga es de 1 MB. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sobrescribir datos sobre conflictos </td> 
   <td colname="col2"> <p>Sobrescribe automáticamente los datos existentes que entran en conflicto con los datos importados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Descargar automáticamente el archivo de clasificaciones una vez completada la importación </td> 
   <td colname="col2"> <p>Descarga automáticamente un archivo delimitado por tabuladores que representa el conjunto de datos con los datos de las clasificaciones que se acaban de cargar. Adobe genera automáticamente este archivo si la importación crea algún ID único o si se produce algún error. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Importar clasificaciones a través del explorador {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

<!-- 

t_upload_a_saint_data_file_via_web_browser.xml

 -->

1. Haga clic en **[!UICONTROL Administración]** > **[!UICONTROL Importador de clasificaciones]**.
1. Haga clic en **[!UICONTROL Importar archivo]**.
1. Configure los campos **[!UICONTROL Importación del explorador]**.
1. Haga clic en **[!UICONTROL Importar archivo]**.
1. Observe la ventana de estado para ver los mensajes de procesamiento.
1. (Condicional) Si activó **[!UICONTROL Descargar automáticamente el archivo de clasificación cuando se haya completado la carga]**, indique dónde desea almacenar el archivo resultante cuando termine el procesamiento.
>Si la importación es correcta, se muestran inmediatamente los cambios correspondientes en una exportación. Pese a ello, los cambios de datos en los informes pueden tardar hasta cuatro horas si utiliza una importación mediante explorador y hasta 24 horas si utiliza una importación mediante FTP.
