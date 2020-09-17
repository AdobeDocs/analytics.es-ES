---
description: La programación de envío de los informes se puede personalizar. Por ejemplo, detener el envío de informes en un momento determinado o indicar la cantidad de veces que se desea enviar un informe. Cuando se crea una programación nueva, esta usa el intervalo de fechas definido en el informe. Por ejemplo, si crea un informe para los últimos 90 días y lo programa de modo que se ejecute en forma diaria, cada día recibirá un informe de los últimos 90 días. Si crea un informe con un intervalo de fechas estático del calendario, verá el mismo informe cada vez que se envíe.
title: Administrador de programación
topic: Ad hoc analysis
uuid: 82a054ef-109d-414d-a6e1-e09ee57c163f
translation-type: tm+mt
source-git-commit: d4cb2acb4ecaecce3644a2f3cf29913440e5cd6a
workflow-type: tm+mt
source-wordcount: '986'
ht-degree: 98%

---


# Administrador de programación

>[!IMPORTANT]
>
>Adobe está moviendo Ad Hoc Analysis al estado de fin de vida el 1 de marzo de 2021. [Más información...](https://adobe.ly/discoverworkspace).

La programación de envío de los informes se puede personalizar. Por ejemplo, detener el envío de informes en un momento determinado o indicar la cantidad de veces que se desea enviar un informe. Cuando se crea una programación nueva, esta usa el intervalo de fechas definido en el informe. Por ejemplo, si crea un informe para los últimos 90 días y lo programa de modo que se ejecute en forma diaria, cada día recibirá un informe de los últimos 90 días. Si crea un informe con un intervalo de fechas estático del calendario, verá el mismo informe cada vez que se envíe.

## Administrador de programación {#concept_A1CDE14B72A54DD6AE17B816092CAB8B}

La programación de envío de los informes se puede personalizar. Por ejemplo, detener el envío de informes en un momento determinado o indicar la cantidad de veces que se desea enviar un informe. Cuando se crea una programación nueva, esta usa el intervalo de fechas definido en el informe. Por ejemplo, si crea un informe para los últimos 90 días y lo programa de modo que se ejecute en forma diaria, cada día recibirá un informe de los últimos 90 días. Si crea un informe con un intervalo de fechas estático del calendario, verá el mismo informe cada vez que se envíe.

>[!NOTE]
>
>Cuando se deshabilita la cuenta de un usuario, todos los envíos de informes programados que hayan sido creados por ese usuario se suspenderán.

Para garantizar que los elementos de línea de un desglose son persistentes en los informes programados y guardados, utilice la función **[!UICONTROL Editar elementos]** del [Generador de tablas](/help/analyze/ad-hoc-analysis/c-tablebuilder.md) para crear listas de dimensiones fijas en los desgloses.

>[!IMPORTANT]
>
>Ad Hoc Analysis le permite definir y programar rápidamente informes para la generación de informes específicos, adecuados y específicos que necesita. No se ha diseñado para la exportación completa de datos con una gran cantidad de datos o filas, columnas, evaluaciones métricas o desgloses exhaustivos con extractos de datos.
>
>Las restricciones prácticas para los informes programados en Ad Hoc Analysis se basan en este principio: si su informe no se genera en diez minutos (el tiempo de espera para Ad Hoc Analysis), lo más probable es que su informe sea demasiado complejo.
>
>Lo más probable es que su informe tenga demasiadas métricas, demasiados desgloses de elementos de dimensión, demasiadas filas o columnas u otros extremos que hacen que el proceso de generación de informes sea demasiado largo para Ad Hoc Analysis. Este tipo de informe debe ejecutarse en el Data Warehouse, una función de Adobe Analytics creada para la extracción de datos completa que se ejecuta sin conexión con la generación de informes que pueden tardar varias horas o días.
>
>Por ejemplo, Ad Hoc Analysis puede encargarse de 50 000 filas de datos, pero desglosar esos datos entre diez tipos de explorador distintos supone 50 000 veces 10, un aumento exponencial que puede ser demasiado complejo para la herramienta de informes específicos. Los desgloses adicionales también aumentan las filas de datos exponencialmente. Definir el número real de filas o columnas y de desgloses de restricción para la generación de informes de Ad Hoc Analysis no se puede definir en términos absolutos si no que es una combinación de todos estos factores.

## Programación de envío de informes {#task_7A3165C8C5C349718FE3B2B0C727ACFD}

Instrucciones sobre cómo programar el envío de informes.

<!-- 

t_schedule_delivery.xml

 -->

1. Haga clic en **[!UICONTROL Herramientas]** y, a continuación, en **[!UICONTROL Administrador de programación]**.
1. En el [!UICONTROL Administrador de programación], haga clic en **[!UICONTROL Nuevo]**. 

## Opciones de envío: definiciones {#reference_CA49AC560258471AAE959BCA243F170C}

Definiciones de las opciones de envío.

<!-- 

r_delivery_options.xml

 -->

La información que se muestra en el informe seleccionado en un determinado momento se puede enviar a un archivo en el formato que se elija. El envío puede realizarse una vez o configurar una programación de envío y especificar el formato de archivo preferido. Para que el receptor del archivo pueda tener la certeza de que es auténtico, se puede crear una firma digital y adjuntarla con el envío. El archivo se puede enviar a una dirección de correo electrónico o cargarlo a un servidor FTP.

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Campo </p> </th> 
   <th colname="col2" class="entry"> <p>Definición </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nombre </p> </td> 
   <td colname="col2"> <p> El nombre del informe (se puede configurar). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> <p>El ID del informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Formato del archivo </p> </td> 
   <td colname="col2"> 
    <ul id="ul_711C2D9B216C48359F7B42521D927872"> 
     <li id="li_36E8DEFDA1B84890A4204A6DFF4E0267">Excel: el informe se guarda como hoja de cálculo; se incluyen todas las imágenes. Se puede editar en Microsoft Excel. </li> 
     <li id="li_C918FA3AE8194BD2B59E554DAC7CBBE2">CSV: guarda el informe como un archivo de valores separados por comas. Se puede editar con cualquier editor de texto (por ejemplo, el Bloc de notas) o con un editor de hojas de cálculo (como Excel). En este formato no se guardará ninguna de las imágenes. </li> 
     <li id="li_B7C8C098C5264B349C21077A0DEFE059">PDF: guarda el informe en formato de documento portátil. Este formato no se puede editar; se puede ver en Adobe Acrobat o Adobe Reader. </li> 
     <li id="li_B1183DB25DE34B689FBD0E5B44691F49">HTML: el informe se guarda como un archivo adjunto en formato de Lenguaje de Marcado de Hipertexto. Es el formato del que están hechos la mayoría de los sitios web. Para editarlo quienes es preciso estar familiarizado con el código HTML. </li> 
     <li id="li_5ED5F1862AB1490A9FF5695FF9F52C5E">Word: el informe se guarda en formato de texto enriquecido; se incluyen todas las imágenes. Se puede editar dentro de Microsoft Word o WordPad. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Avanzado </p> </td> 
   <td colname="col2"> <p> Consulte <a href="/help/analyze/ad-hoc-analysis/c-schedule.md"   >Configuración avanzada de formato</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Destino del archivo </p> </td> 
   <td colname="col2"> <p>Correo electrónico: opciones de configuración para envío por correo electrónico. </p> <p>FTP: opciones para la carga del archivo en un servidor FTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Programación de los envíos e intervalo de los informes </p> </td> 
   <td colname="col2"> <p>Indica cuándo enviar el informe. Cuando se crea una programación nueva, esta usa el intervalo de fechas definido en el informe. Por ejemplo, si crea un informe para los últimos 90 días y lo programa de modo que se ejecute en forma diaria, cada día recibirá un informe de los últimos 90 días. Si crea un informe con un intervalo de fechas estático del calendario, verá el mismo informe cada vez que se envíe. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Opciones de formato avanzadas: definiciones {#reference_F99B65BF7C9746638D8147EED147015B}

Definiciones de opciones de formato avanzadas.

<!-- 

r_advanced_format_settings_dsc.xml

 -->

<table id="table_CD0888E8390745F4B83DF6AC69CB0854"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Campo </p> </th> 
   <th colname="col2" class="entry"> <p>Definición </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nombre de archivo </p> </td> 
   <td colname="col2"> <p>El nombre de archivo definido por el usuario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anexar ID al nombre de archivo </p> </td> 
   <td colname="col2"> <p>Agrega automáticamente el ID del informe al nombre de archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Anexar fecha al nombre de archivo </p> </td> 
   <td colname="col2"> <p> Agrega automáticamente la fecha del informe al nombre de archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Idioma </p> </td> 
   <td colname="col2"> <p> Permite seleccionar el idioma del informe. Puede enviar el informe en cualquiera de los siguientes idiomas, independientemente del que use en el equipo: </p> 
    <ul id="ul_BD3D331B0D6146F79A6D254136E43920"> 
     <li id="li_0EE6A371B1BB4627BD3F64BD0EF07E44">Inglés </li> 
     <li id="li_5EF76261928543FDB36D99E4C89DE994">Español </li> 
     <li id="li_FABF47E8CD64486BA1567E02460422C5">Chino simplificado </li> 
     <li id="li_8A6BC2DE92DB47DA9397B8931D8DCC6E">Chino tradicional </li> 
     <li id="li_EDA24D700BE040E8B839B82E31DABC28">Francés </li> 
     <li id="li_A8D41DCCC91542BB8D0A522EC99575E8">Alemán </li> 
     <li id="li_E9F73C93C94A46B78BCE85A7261CEDD4">Japonés </li> 
     <li id="li_699B97050AA54D818659C191F4594E4E">Portugués </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codificación </p> </td> 
   <td colname="col2"> <p>Indica el tipo de codificación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Enviar el informe como archivo comprimido </p> </td> 
   <td colname="col2"> <p> Comprime el archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enviar el archivo de firma digital </p> </td> 
   <td colname="col2"> <p>Crea una firma digital para enviar junto con el mensaje de correo electrónico. </p> </td> 
  </tr> 
 </tbody> 
</table>

