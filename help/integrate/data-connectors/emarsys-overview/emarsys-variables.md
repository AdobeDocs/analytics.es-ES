---
description: La integración de Data Connectors para emarsys usa variables de Analytics para rastrear varias métricas de emarsys.
seo-description: La integración de Data Connectors para emarsys usa variables de Analytics para rastrear varias métricas de emarsys.
seo-title: Variables de Analytics
title: Variables de Analytics
uuid: 4 d 5 e 087 c-f 495-4 aab -9 ad 1-9 b 901 d 34 a 254
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Variables de Analytics{#analytics-variables}

La integración de Data Connectors para emarsys usa variables de Analytics para rastrear varias métricas de emarsys.

After identifying the Event and eVars to use with the emarsys integration, enable them in the [Admin Console](https://microsite.omniture.com/t2/help/en_US/reference/index.html?f=conversion_var_admin).

**Variables requeridas**

<table id="table_5B8F3A1EB55D4BB48F669FB84C857256"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de variable </th> 
   <th colname="col2" class="entry"> Nombre  </th> 
   <th colname="col3" class="entry"> Método de obtención de datos </th> 
   <th colname="col4" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> event (numérico) </td> 
   <td colname="col2"> Devoluciones totales </td> 
   <td colname="col3"> <p>Importado automáticamente desde emarsys </p> </td> 
   <td colname="col4"> <p>El evento Devoluciones totales permite ver la cantidad de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numérico) </td> 
   <td colname="col2"> Pulsado </td> 
   <td colname="col3"> <p>Importado automáticamente desde emarsys </p> </td> 
   <td colname="col4"> <p>El evento Clics permite ver la cantidad de visitantes que hicieron clic en el mensaje de correo electrónico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numérico) </td> 
   <td colname="col2"> Abierto </td> 
   <td colname="col3"> <p>Importado automáticamente desde emarsys </p> </td> 
   <td colname="col4"> <p>El evento Abierto permite ver la cantidad de visitantes que abrieron el mensaje de correo electrónico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numérico) </td> 
   <td colname="col2"> Enviado </td> 
   <td colname="col3"> <p>Importado automáticamente desde emarsys </p> </td> 
   <td colname="col4"> <p>El evento Envíos permite ver la cantidad de mensajes de correo electrónico que se enviaron. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numérico) </td> 
   <td colname="col2"> Sin suscripción </td> 
   <td colname="col3"> <p>Importado automáticamente desde emarsys </p> </td> 
   <td colname="col4"> <p>El evento Sin suscripción permite ver la cantidad de visitantes que abrieron el correo electrónico pero luego hicieron clic en el vínculo Cancelar suscripción para rechazar los futuros mensajes de correo electrónico de su organización. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> <p>Se recopilan de los parámetros de consulta en vínculos de correo electrónico a través del método de recopilación automatizada o de un complemento JavaScript. </p> </td> 
   <td colname="col4"> Recipient ID </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar o s. campaign </td> 
   <td colname="col2"> ID de mensaje </td> 
   <td colname="col3"> <p>Se recopilan de los parámetros de consulta en vínculos de correo electrónico a través del método de recopilación automatizada o de un complemento JavaScript. </p> </td> 
   <td colname="col4"> Este valor suele almacenarse en la variable campaign. </td> 
  </tr> 
 </tbody> 
</table>

