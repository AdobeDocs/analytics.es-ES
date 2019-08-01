---
description: Esta integración requiere que se reserven 2 evars para cada implementación de grupo de informes.
seo-description: Esta integración requiere que se reserven 2 evars para cada implementación de grupo de informes.
seo-title: Configurar variables de Analytics para Selligent
solution: Analytics
title: Configurar variables de Analytics para Selligent
uuid: 3 b 7 b 8 b 4 b -7614-4439-bcb 0-dbdec 5304844
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Configure Analytics Variables for Selligent{#configure-analytics-variables-for-selligent}

Esta integración requiere que se reserven 2 evars para cada implementación de grupo de informes.

Aparte de estas evars, puede que se reserven algunos eventos según los datos de Selligent, que le gustaría ver en Analytics. Estas evars y eventos se describen de la siguiente manera:

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de variable </th> 
   <th colname="col2" class="entry"> Nombre de variable </th> 
   <th colname="col3" class="entry"> Cómo se utiliza </th> 
   <th colname="col4" class="entry"> Configuración </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID de mensaje </td> 
   <td colname="col3"> Para capturar la identificación de campaña de mensaje de correo electrónico individual. </td> 
   <td colname="col4"> <p><b>Estado</b>: Habilitado </p> <p><b>Asignación</b>: Más reciente </p> <p><b>Caduca después</b>de: «Decisión empresarial» </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eV ar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> Para capturar la identificación anónima del cliente que hizo clic en la campaña de correo electrónico. </td> 
   <td colname="col4"> <p><b>Estado</b>: Habilitado </p> <p><b>Asignación</b>: Más reciente </p> <p><b>Caduca después</b>de: «Decisión empresarial» </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Enviado </td> 
   <td colname="col3"> Para almacenar el número de correos electrónicos enviados desde Selligent. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participación</b>: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Entregado </td> 
   <td colname="col3"> Para almacenar el número de correos electrónicos que se han entregado. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participación</b>: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Vistas </td> 
   <td colname="col3"> Para almacenar la cantidad de correos electrónicos únicos que se vieron. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participación</b>: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Clics </td> 
   <td colname="col3"> Para almacenar la cantidad de veces que se hizo clic en un correo electrónico. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participación</b>: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Rebotado </td> 
   <td colname="col3"> Para almacenar el número de correos electrónicos que se devolvieron. </td> 
   <td colname="col4"> <p><b>Tipo</b>: Numérico </p> <p><b>Participación</b>: Habilitado </p> </td> 
  </tr> 
 </tbody> 
</table>

