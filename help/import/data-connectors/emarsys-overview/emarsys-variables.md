---
description: La integración de Data Connectors para emarsys utiliza variables de Analytics para rastrear distintas métricas de emarsys.
seo-description: La integración de Data Connectors para emarsys utiliza variables de Analytics para rastrear distintas métricas de emarsys.
seo-title: Variables de Analytics
title: Variables de Analytics
uuid: 4d5e087c-f495-4aab-9ad1-9b901d34a254
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Variables de Analytics{#analytics-variables}

La integración de Data Connectors para emarsys utiliza variables de Analytics para rastrear distintas métricas de emarsys.

Después de identificar el evento y las eVars que se usarán con la integración de emarsys, actívelos en la Consola [de administración](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/c-admin-tools.html).

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
   <td colname="col4"> <p>El evento Devoluciones totales permite ver el número de mensajes de correo electrónico que no se entregaron a los destinatarios debido a un problema de entrega. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numérico) </td> 
   <td colname="col2"> Clic </td> 
   <td colname="col3"> <p>Importado automáticamente desde emarsys </p> </td> 
   <td colname="col4"> <p>El evento en el que se hizo clic permite ver el número de visitantes que hicieron clic en el mensaje de correo electrónico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numérico) </td> 
   <td colname="col2"> Abierto </td> 
   <td colname="col3"> <p>Importado automáticamente desde emarsys </p> </td> 
   <td colname="col4"> <p>El evento Abrir permite ver el número de visitantes que abrieron el mensaje de correo electrónico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numérico) </td> 
   <td colname="col2"> Enviado </td> 
   <td colname="col3"> <p>Importado automáticamente desde emarsys </p> </td> 
   <td colname="col4"> <p>El evento Envíos permite ver el número de mensajes de correo electrónico que se han enviado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> event (numérico) </td> 
   <td colname="col2"> No suscrito </td> 
   <td colname="col3"> <p>Importado automáticamente desde emarsys </p> </td> 
   <td colname="col4"> <p>El evento Cancelar suscripción le permite ver el número de visitantes que abrieron el correo electrónico y luego hicieron clic en el vínculo Cancelar suscripción para rechazar futuros mensajes de correo electrónico de su organización. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> <p>Recopilado a partir de parámetros de consulta en vínculos de correo electrónico mediante el método de recopilación automatizada o un complemento de JavaScript. </p> </td> 
   <td colname="col4"> Recipient ID </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar o s.campaign </td> 
   <td colname="col2"> ID del mensaje </td> 
   <td colname="col3"> <p>Recopilado a partir de parámetros de consulta en vínculos de correo electrónico mediante el método de recopilación automatizada o un complemento de JavaScript. </p> </td> 
   <td colname="col4"> Este valor se almacena a menudo en la variable de campaña. </td> 
  </tr> 
 </tbody> 
</table>

