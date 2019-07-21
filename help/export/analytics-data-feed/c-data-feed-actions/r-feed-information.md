---
description: Utilice la sección Información de la fuente para asignar un nombre a la fuente, especificar el grupo de informes que debe generarse con esta, determinar su recurrencia y especificar cuándo empieza y finaliza.
keywords: Fuente de datos; información; name; grupo de informes; email when complete; email; intervalo; feed; retrasar procesamiento; delay; start; end; date; fuente continua
seo-description: Utilice la sección Información de la fuente para asignar un nombre a la fuente, especificar el grupo de informes que debe generarse con esta, determinar su recurrencia y especificar cuándo empieza y finaliza.
seo-title: Información de la fuente
solution: Analytics
title: Información de la fuente
uuid: adf 92 f 42-a 957-4 de 0-a 5 a 1-683 f 2933 af 04
translation-type: tm+mt
source-git-commit: 5a30ea6ac47ddd8612728e488afda868491a1ddc

---


# Información de la fuente

Utilice la sección Información de la fuente para asignar un nombre a la fuente, especificar el grupo de informes que debe generarse con esta, determinar su recurrencia y especificar cuándo empieza y finaliza.

![](assets/feed-info.jpg)

<table id="table_C98C7C3CE4194BEF819E792793EBC517">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Campo </th>
   <th colname="col2" class="entry"> Descripción </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nombre (requerido) </p> </td>
   <td colname="col2"> <p>Introduzca un nombre para la fuente. </p> <p>Debe ser único dentro del grupo de informes seleccionado y puede tener hasta 255 caracteres de longitud. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Conjunto de informes (requerido) </p> </td>
   <td colname="col2"> <p>Especifique los grupos de informes correspondientes a la consulta de la fuente. </p> <p>Debe seleccionar al menos un grupo de informes y no se puede incluir el mismo grupo dos veces. </p> <p>Están disponibles todos los grupos de informes no virtuales disponibles para el usuario que ha iniciado sesión. </p></td>
  </tr>
  <tr>
   <td colname="col1"> <p>Enviar correo electrónico al completarse (requerido) </p> </td>
   <td colname="col2"> <p>Especifique el destinatario del correo electrónico que recibirá las actualizaciones de entrega de la fuente. </p> <p>Este campo no puede quedar vacío y debe incluir una dirección de correo electrónico con el formato correcto. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Intervalo de la fuente (requerido) </p> </td>
   <td colname="col2"> <p>Especifique la periodicidad de la programación. </p> <p>Nota: Debido al tamaño potencial de los archivos comprimidos de fuentes de datos, compruebe que su proceso de ETL utiliza un programa de compresión de 64 bits. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Retrasar procesamiento (opcional) </p> </td>
   <td colname="col2"> <p>Especifique el retraso que se aplicará a cada instancia de programación. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <p>Fecha de inicio y finalización (requerido) </p> <p>Fuente continua (opcional) </p> </td>
   <td colname="col2"> <p>Defina las fechas de inicio y finalización de la fuente. </p> <p>
     <ul id="ul_509977336CD34032924B48E043E8CBC7">
      <li id="li_BFB5B6ADCB184D839C9BA42DB3DCAF32">Fecha de inicio: el valor predeterminado es la fecha actual </li>
      <li id="li_34F8DB45D9B54076840D1A0B782812D3">Fecha de finalización: el valor predeterminado es la fecha del día siguiente </li>
     </ul>
     </p> </td>
  </tr>
 </tbody>
</table>