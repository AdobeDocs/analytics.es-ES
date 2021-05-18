---
description: Cree, administre y visualice la utilización de fuentes de datos en un grupo de informes.
subtopic: Data sources
title: Administrador de fuentes de datos
topic-fix: Developer and implementation
uuid: ccfa4a1c-7c56-421b-8ee6-a42b334659b1
exl-id: a63137b8-deeb-4865-9be9-322416b00186
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 98%

---

# Administrador de fuentes de datos

Cree, administre y visualice la utilización de fuentes de datos en un grupo de informes.

**[!UICONTROL Analytics]**  >  **[!UICONTROL Administración]**  >  **[!UICONTROL Todos los administradores]**  > Fuentes  **[!UICONTROL de datos]**.

## Pestaña Crear {#section_74603FDA3D8842E49F1A51624A06DE20}

La pestaña [!UICONTROL Crear] permite configurar una fuente de datos nueva para el grupo de informes seleccionado. Al activar una fuente de datos, un [!UICONTROL asistente] le guiará por el proceso de crear una plantilla y creará una ubicación FTP para cargar los datos.

Las selecciones que realice en la pestaña Crear determinarán los campos iniciales que contendrá la plantilla al ser creada. Consulte [Generación de plantillas de archivo de importación](/help/import/c-data-sources/datasrc-template/t-datasrc-creating-data-sources-file.md).

## Pestaña Administrar {#section_DD559A6701CA45F1A85E56F840F48DBE}

<table id="table_F74696EC855441328CFE0BF49C20D9B0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Opción </p> </th> 
   <th colname="col2" class="entry"> <p>Descripción </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Reiniciar procesamiento </p> </td> 
   <td colname="col2"> <p>Reinicia el procesamiento de la fuente de datos cuando antes se detuvo debido a errores o advertencias. El procesamiento continúa hasta que se encuentre el siguiente error. El procesamiento de los archivos de fuente de datos solamente se detiene si se selecciona <span class="uicontrol">Detener procesamiento si hay errores</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Completar procesamiento </p> </td> 
   <td colname="col2"> <p>Indica al sistema de fuentes de datos que cierre todas las visitas abiertas que haya en el archivo y finalice el procesamiento del archivo de fuente de datos como si estuviera completo. Esto es útil cuando se tienen visitas que se extienden a lo largo de varios archivos de fuente de datos. Esto solo concierne al <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md"   > Procesamiento completo</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Desactivar </p> </td> 
   <td colname="col2"> <p> Cuando una fuente de datos se desactiva, se elimina del sistema. Si en el servidor ya se había comenzado a procesar alguno de los archivos, el procesamiento continuará hasta finalizar. Los archivos que aún no se hayan empezado a procesar se omitirán. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Detener procesamiento si hay errores/advertencias </p> </td> 
   <td colname="col2"> <p> Indica al motor de procesamiento de fuentes de datos que detenga el procesamiento si encuentra un error. El procesamiento de la fuente de datos no se reanudará hasta que el usuario seleccione Reiniciar procesamiento. La opción Detener procesamiento si hay advertencias solo concierne al <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md"   > Procesamiento completo</a>. </p> <p>Cuando las fuentes de datos encuentran un error de archivo, se lo notifican. El sistema traslada el archivo de fuente de datos que tiene el error a una carpeta llamada <span class="filepath">files_with_errors</span> del servidor FTP. Cuando haya resuelto el problema, vuelva a enviar el archivo de fuente de datos para que el sistema lo procese. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurar </p> </td> 
   <td colname="col2"> <p>Permite modificar la plantilla u otras opciones específicas de la fuente de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Información de FTP </p> </td> 
   <td colname="col2"> <p>Muestra la información de la fuente de datos referida a la conexión FTP. Use esta información para acceder a la plantilla de fuente de datos y enviar los datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nombre del archivo </p> </td> 
   <td colname="col2"> <p>Nombre del archivo cargado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Estado </p> </td> 
   <td colname="col2"> <p> Estado actual del archivo. Puede ser alguno de los siguientes valores: </p> 
    <ul id="ul_56A0BF8C1BE249F6BB39B0D11DA3997F"> 
     <li id="li_BAB359E08EDE4E0298C0362258789603">En cola (paso 1 de 3): el archivo existe, pero no se ha empezado a procesar. Si el archivo no aparece en los próximos 30 minutos, verifique que esté presente el archivo <span class="filepath">.fin</span> correspondiente. </li> 
     <li id="li_A09A14F42CB74F01B694799740B3DA17">Preparación (paso 2 de 3): el sistema está revisando el archivo en busca de errores o advertencias. </li> 
     <li id="li_793FDCDB64CF434D82CAF5B6E9BDE557">Procesamiento (paso 3 de 3): el sistema está procesando el archivo. </li> 
     <li id="li_1D8C4B241FF0453EAF7DDFD8354C5573">Fallido: el archivo no se ha procesado debido a errores. </li> 
     <li id="li_A52507602FB4492B83A70AF6449A539A">Éxito: el archivo se ha procesado completamente. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Pestaña Registro de archivos {#section_B7AC7EE8CAD740A59DD53CF1919373F0}

El registro de archivos incluye una función de búsqueda que permite buscar información por nombre de fuente de datos, tipo de fuente de datos, nombre de archivo, fecha de recepción o estado.
