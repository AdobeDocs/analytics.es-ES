---
description: 'Puede personalizar la programación de envíos para los informes. Puede detener el envío en un momento determinado o especificar la cantidad de veces que desee enviar un informe. Las nuevas programaciones utilizan el intervalo de fechas definido en el informe. Por ejemplo: si crea un informe para los últimos 90 días y lo programa para que se ejecute diariamente, recibirá un informe de los últimos 90 días cada día. Si crea un informe con un intervalo de fechas estático a partir del calendario, verá el mismo informe cada vez que se envíe.'
title: Administrador de programación
topic: Ad hoc analysis
uuid: 82a054ef-109d-414d-a6e1-e09ee57c163f
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Administrador de programación

Puede personalizar la programación de envíos para los informes. Puede detener el envío en un momento determinado o especificar la cantidad de veces que desee enviar un informe. Las nuevas programaciones utilizan el intervalo de fechas definido en el informe. Por ejemplo: si crea un informe para los últimos 90 días y lo programa para que se ejecute diariamente, recibirá un informe de los últimos 90 días cada día. Si crea un informe con un intervalo de fechas estático a partir del calendario, verá el mismo informe cada vez que se envíe.

## Administrador de programación {#concept_A1CDE14B72A54DD6AE17B816092CAB8B}

Puede personalizar la programación de envíos para los informes. Puede detener el envío en un momento determinado o especificar la cantidad de veces que desee enviar un informe. Las nuevas programaciones utilizan el intervalo de fechas definido en el informe. Por ejemplo: si crea un informe para los últimos 90 días y lo programa para que se ejecute diariamente, recibirá un informe de los últimos 90 días cada día. Si crea un informe con un intervalo de fechas estático a partir del calendario, verá el mismo informe cada vez que se envíe.

>[!NOTE] Cuando se deshabilita la cuenta de un usuario, todos los envíos de informes programados que hayan sido creados por ese usuario se suspenderán.

To ensure that line items in a breakdown are persistent in saved and scheduled reports, use the **[!UICONTROL Edit Items]** feature in the [Table Builder](/help/analyze/ad-hoc-analysis/c-tablebuilder.md) to create fixed dimension lists in breakdowns.

>[!IMPORTANT]
>
>Ad Hoc Analysis le permite definir y programar rápidamente informes para la generación de informes específicos, adecuados y específicos que necesita. No está diseñado para la exportación completa de datos con un número o filas masivos, columnas, evaluaciones de métricas o desgloses extensos mediante extracciones de datos.
>
>Las limitaciones prácticas para el sistema de informes programado en la Análisis ad hoc se basan en este principio: Si el informe no se genera en diez minutos (tiempo de espera para la Análisis ad hoc), lo más probable es que el informe sea demasiado complejo.
>
>Lo más probable es que el informe tenga demasiadas métricas, demasiados desgloses de elementos de dimensión, demasiadas filas o columnas u otros extremos que hacen que el proceso de generación de informes sea demasiado largo para la Análisis ad hoc. Este tipo de informe debe ejecutarse en el almacén de datos, una función de Adobe Analytics creada para la extracción de datos completa que se ejecuta sin conexión con la generación de informes que puede tardar muchas horas o días.
>
>Por ejemplo, la Análisis ad hoc puede manejar 50.000 filas de datos, pero desglosar esos datos para diez tipos de explorador significa 50.000 veces 10, un aumento exponencial que puede ser demasiado complejo para una herramienta de sistema de informes ad hoc. Los desgloses adicionales aumentan de nuevo las filas de datos de forma exponencial. La definición del número real o de filas, columnas y desgloses para restringir el sistema de informes de Análisis ad hoc no se puede definir en términos claros, sino que es una combinación de todos estos factores.

## Programación de envío de informes {#task_7A3165C8C5C349718FE3B2B0C727ACFD}

Instrucciones sobre cómo programar el envío de informes.

<!-- 

t_schedule_delivery.xml

 -->

1. Haga clic en **[!UICONTROL Tools]** y luego en **[!UICONTROL Schedule Manager]**.
1. En el [!UICONTROL Schedule Manager], haga clic en **[!UICONTROL New.]**

## Opciones de envío: definiciones {#reference_CA49AC560258471AAE959BCA243F170C}

Definiciones de la configuración en Opciones de Envío.

<!-- 

r_delivery_options.xml

 -->

Puede enviar la información tal como se muestra en el informe seleccionado en ese momento al formato que seleccione. Puede enviarlo una vez o configurar una programación de envíos, y especificar el formato de archivo que prefiera. Puede crear y enviar una firma digital para garantizar al destinatario que el archivo es auténtico. Puede enviar el archivo a una dirección de correo electrónico o cargarlo en un servidor FTP.

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
   <td colname="col2"> <p> Nombre configurable de este informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID </p> </td> 
   <td colname="col2"> <p>Indica la ID del informe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Formato del archivo </p> </td> 
   <td colname="col2"> 
    <ul id="ul_711C2D9B216C48359F7B42521D927872"> 
     <li id="li_36E8DEFDA1B84890A4204A6DFF4E0267">Excel: Genera el informe en una hoja de cálculo, incluidas todas las imágenes. Se puede editar en Microsoft Excel. </li> 
     <li id="li_C918FA3AE8194BD2B59E554DAC7CBBE2">CSV: Genera el informe en valores separados por comas. Se puede editar en un editor de texto simple (como Bloc de notas) o en un editor de hojas de cálculo (como Excel). No contiene ninguna imagen. </li> 
     <li id="li_B7C8C098C5264B349C21077A0DEFE059">PDF: Genera el informe en formato de Documento portátil. No editable y visible en Adobe Acrobat o Adobe Reader. </li> 
     <li id="li_B1183DB25DE34B689FBD0E5B44691F49">HTML: Extrae el informe en un archivo adjunto de lenguaje de marcado de hipertexto. Este formato es el que componen la mayoría de los sitios web. No se puede editar a menos que esté familiarizado con el código HTML. </li> 
     <li id="li_5ED5F1862AB1490A9FF5695FF9F52C5E">Word: Extrae el informe en formato de texto enriquecido, incluidas todas las imágenes. Se puede editar en Microsoft Word o WordPad. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Avanzado </p> </td> 
   <td colname="col2"> <p> Consulte <a href="/help/analyze/ad-hoc-analysis/c-schedule.md"   >Configuración avanzada de formato</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Destino del archivo </p> </td> 
   <td colname="col2"> <p>Correo electrónico: Configuración para enviar por correo electrónico. </p> <p>FTP: Configuración para cargar en un servidor FTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Intervalo de informes y programación de Envíos </p> </td> 
   <td colname="col2"> <p>Especifica cuándo enviar el informe. Las nuevas programaciones utilizan el intervalo de fechas definido en el informe. Por ejemplo: si crea un informe para los últimos 90 días y lo programa para que se ejecute diariamente, recibirá un informe de los últimos 90 días cada día. Si crea un informe con un intervalo de fechas estático a partir del calendario, verá el mismo informe cada vez que se envíe. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Opciones de formato avanzadas: definiciones {#reference_F99B65BF7C9746638D8147EED147015B}

Definiciones de la configuración en Configuración avanzada de formato.

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
   <td colname="col2"> <p>Nombre de archivo definido por el usuario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Anexar ID al nombre de archivo </p> </td> 
   <td colname="col2"> <p>Agrega automáticamente la ID del informe al nombre del archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Anexar fecha al nombre de archivo </p> </td> 
   <td colname="col2"> <p> Agrega automáticamente la fecha del informe al nombre del archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Idioma </p> </td> 
   <td colname="col2"> <p> Permite seleccionar un idioma para el informe. Puede enviar el informe en cualquiera de los siguientes idiomas, independientemente del idioma que utilice </p> 
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
   <td colname="col2"> <p>Especifica un tipo de codificación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Enviar un informe como archivo comprimido </p> </td> 
   <td colname="col2"> <p> Comprime el archivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enviar el archivo de firma digital </p> </td> 
   <td colname="col2"> <p>Crea una firma digital para enviarla con el correo electrónico. </p> </td> 
  </tr> 
 </tbody> 
</table>

