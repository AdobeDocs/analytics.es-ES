---
description: Describe las evars y los eventos que se reservarán para cada implementación del grupo de informes.
seo-description: Describe las evars y los eventos que se reservarán para cada implementación del grupo de informes.
seo-title: Configurar variables de Adobe Analytics para Lyris
solution: Analytics
title: Configurar variables de Adobe Analytics para Lyris
uuid: 12 e 150 c 4-052 a -481 c -8 c 27-ef 45 ee 801977
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Configurar variables de Adobe Analytics para Lyris{#configure-adobe-analytics-variables-for-lyris}

Describe las evars y los eventos que se reservarán para cada implementación del grupo de informes.

Esta integración requiere que se reserven por lo menos 2 evars para cada implementación de grupo de informes. Aparte de estas evars, pueden reservarse algunos eventos según los datos de Lyris que desee ver en Analytics. Estas evars y eventos se describen en la siguiente tabla:

<table id="table_43E32344E9E54FED8491F28047249329"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de variable </th> 
   <th colname="col2" class="entry"> Nombre de variable </th> 
   <th colname="col3" class="entry"> Cómo se usa la variable </th> 
   <th colname="col4" class="entry"> Configuración </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> ID de mensaje </td> 
   <td colname="col3"> Para capturar la identificación de campaña de mensaje de correo electrónico individual </td> 
   <td colname="col4"> <p>Estado: Habilitado </p> <p>Asignación: Más reciente </p> <p>Caduca después de: «Decisión empresarial» </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Email Recipient ID </td> 
   <td colname="col3"> Para capturar la identificación anónima del cliente que hizo clic en la campaña de correo electrónico </td> 
   <td colname="col4"> <p>Estado: Habilitado </p> <p>Asignación: Más reciente </p> <p>Caduca después de: «Decisión empresarial» </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Correo electrónico enviado </td> 
   <td colname="col3"> Para almacenar no. de correos electrónicos enviados desde Lyris </td> 
   <td colname="col4">Tipo: Numérico <p>Participación: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Correo electrónico abierto </td> 
   <td colname="col3"> Para almacenar no. de mensajes de correo electrónico que se abrieron </td> 
   <td colname="col4">Tipo: Numérico <p>Participación: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Correo electrónico único abierto </td> 
   <td colname="col3"> Para almacenar no. de correos electrónicos únicos que se abrieron </td> 
   <td colname="col4">Tipo: Numérico <p>Participación: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Pulsaciones de correo electrónico </td> 
   <td colname="col3"> Para almacenar no. de veces en que se hizo clic en un correo electrónico </td> 
   <td colname="col4">Tipo: Numérico <p>Participación: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Correo electrónico Devoluciones </td> 
   <td colname="col3"> Para almacenar el no. de mensajes de correo electrónico que se devolvieron </td> 
   <td colname="col4">Tipo: Numérico <p>Participación: Habilitado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento </td> 
   <td colname="col2"> Lyris - Correo electrónico cancelado </td> 
   <td colname="col3"> Para almacenar el no. de suscripciones por correo electrónico deshabilitadas </td> 
   <td colname="col4">Tipo: Numérico <p>Participación: Habilitado </p> </td> 
  </tr> 
 </tbody> 
</table>

