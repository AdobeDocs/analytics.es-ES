---
description: La integración de Data Connectors para Emarsys usa variables de Analytics para rastrear distintas métricas de Emarsys.
title: Variables de Analytics
uuid: 4d5e087c-f495-4aab-9ad1-9b901d34a254
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Variables de Analytics {#analytics-variables}

La integración de Data Connectors para Emarsys usa variables de Analytics para rastrear distintas métricas de Emarsys.

Después de identificar el evento y las eVars que se usan con la integración de Emarsys, actívelos en [Admin Console](https://docs.adobe.com/content/help/es-ES/analytics/admin/admin-tools/c-admin-tools.html).

**Variables requeridas**

<table id="table_5B8F3A1EB55D4BB48F669FB84C857256"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de variable </th> 
   <th colname="col2" class="entry"> Nombre </th> 
   <th colname="col3" class="entry"> Método de obtención de datos </th> 
   <th colname="col4" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Evento (numérico) </td> 
   <td colname="col2"> Devoluciones totales </td> 
   <td colname="col3"> <p>Se importa automáticamente desde Emarsys. </p> </td> 
   <td colname="col4"> <p>El evento de devoluciones totales permite ver el número de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento (numérico) </td> 
   <td colname="col2"> Clics </td> 
   <td colname="col3"> <p>Se importa automáticamente desde Emarsys. </p> </td> 
   <td colname="col4"> <p>El evento en el que se hizo clic permite ver el número de visitantes que hicieron clic en el mensaje de correo electrónico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento (numérico) </td> 
   <td colname="col2"> Aperturas </td> 
   <td colname="col3"> <p>Se importa automáticamente desde Emarsys. </p> </td> 
   <td colname="col4"> <p>El evento de aperturas (Opened) permite ver el número de visitantes que abrieron el mensaje de correo electrónico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento (numérico) </td> 
   <td colname="col2"> Enviados </td> 
   <td colname="col3"> <p>Se importa automáticamente desde Emarsys. </p> </td> 
   <td colname="col4"> <p>El evento de enviados permite ver el número de mensajes de correo electrónico que se han enviado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento (numérico) </td> 
   <td colname="col2"> Cancelación de suscripción </td> 
   <td colname="col3"> <p>Se importa automáticamente desde Emarsys. </p> </td> 
   <td colname="col4"> <p>El evento de cancelación de suscripción le permite ver el número de visitantes que abrieron el correo electrónico y luego hicieron clic en el vínculo Cancelar suscripción para rechazar futuros mensajes de correo electrónico de su organización. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Recipient ID (ID de destinatario) </td> 
   <td colname="col3"> <p>Recopilado a partir de parámetros de consulta en vínculos de correo electrónico mediante el método de recopilación automatizada o un complemento de JavaScript. </p> </td> 
   <td colname="col4"> Recipient ID (ID de destinatario) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar o s.campaign </td> 
   <td colname="col2"> ID de mensaje </td> 
   <td colname="col3"> <p>Recopilado a partir de parámetros de consulta en vínculos de correo electrónico mediante el método de recopilación automatizada o un complemento de JavaScript. </p> </td> 
   <td colname="col4"> Este valor generalmente se almacena en la variable de campaña. </td> 
  </tr> 
 </tbody> 
</table>

