---
description: Los datos de clasificación pueden importarse (cargarse) a través del explorador web. Este método restringe la carga de datos de clasificación a un solo grupo de informes.
seo-description: Los datos de clasificación pueden importarse (cargarse) a través del explorador web. Este método restringe la carga de datos de clasificación a un solo grupo de informes.
seo-title: Importación del explorador
solution: Analytics
subtopic: Clasificaciones
title: Importación del explorador
topic: Herramientas de administración
uuid: 56 dfbf 4 c -36 e 6-49 f 4-b 5 cb -8 ab 714432825
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Importación del explorador

Los datos de clasificación pueden importarse (cargarse) a través del explorador web. Este método restringe la carga de datos de clasificación a un solo grupo de informes.

## Browser import {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

Los datos de clasificación pueden importarse (cargarse) a través del explorador web. Este método restringe la carga de datos de clasificación a un solo grupo de informes.

**[!UICONTROL Administración]** &gt; **[!UICONTROL Importador de clasificaciones]**

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

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Click **[!UICONTROL Import File]**.
1. Configure the **[!UICONTROL Browser Import]** fields.
1. Click **[!UICONTROL Import File]**.
1. Observe la ventana de estado para ver los mensajes de procesamiento.
1. (Conditional) If you selected **[!UICONTROL Automatically Download Classification File After Upload is Complete]**, specify where you want to store the resulting file when processing completes.
>Si la importación es correcta, se muestran inmediatamente los cambios correspondientes en una exportación. Pese a ello, los cambios de datos en los informes pueden tardar hasta cuatro horas si utiliza una importación mediante explorador y hasta 24 horas si utiliza una importación mediante FTP.

