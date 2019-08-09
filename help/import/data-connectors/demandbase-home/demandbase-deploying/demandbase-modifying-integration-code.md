---
description: En la mayoría de los casos, no es necesario realizar modificaciones en el código de integración producido por el asistente de Data Connector.
seo-description: En la mayoría de los casos, no es necesario realizar modificaciones en el código de integración producido por el asistente de Data Connector.
seo-title: Modificación del código de integración
title: Modificación del código de integración
uuid: 3 f 49 a 29 b-ad 38-4967-894 a-ef 7 ecf 4 d 268 f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Modificación del código de integración{#modifying-the-integration-code}

En la mayoría de los casos, no es necesario realizar modificaciones en el código de integración producido por el asistente de Data Connector.

Sin embargo, si necesita realizar ajustes, algunas de las opciones de código se describen a continuación.

<table id="table_5405A73CEFD44466B3C39559F4A037C9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Configuración de código </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s.maxDelay </td> 
   <td colname="col2">El número máximo de milisegundos que la solicitud de imagen de Adobe Analytics esperará a los datos Demandbase antes de activarse en el servidor de recopilación de Analytics. <p>Nota: Esta configuración se aplica a todas las integraciones que puedan estar ejecutándose en el módulo Integrate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._key </td> 
   <td colname="col2"> La clave de API Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Apiurl </td> 
   <td colname="col2"> La plantilla URL para la API Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._delim </td> 
   <td colname="col2"> Delimitador utilizado para separar los valores de dimensión de Demandbase cuando se envían a Adobe Analytics. Cambiar esta configuración puede hacer que las reglas de clasificación predeterminadas no funcionen correctamente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Settnt </td> 
   <td colname="col2">Si es true, el código de integración intentará utilizar un mbox oculto para enviar las dimensiones Demandbase a Adobe Target como parámetros de perfil. <p>Nota: Esto requiere que el código mbox. js exista en la página. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Tntvarprefix </td> 
   <td colname="col2"> Esta cadena se antepone a cada nombre de dimensión de Demandbase antes de enviarlo a Adobe Target. Ejemplo, si esta configuración tiene el valor «db_», la dimensión «industria» se enviará a Adobe Target como «db_ industry». </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Dimensionsarray </td> 
   <td colname="col2"> Las dimensiones Demandbase estándar que se envían a Adobe Analytics. Se recomienda no modificar esta configuración. La propiedad «max_ size» es el número de caracteres permitidos para la dimensión antes de que se produzca truncamiento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Dimensionsarraycustom </td> 
   <td colname="col2"> Las dimensiones Demandbase personalizadas que se envían a Adobe Analytics. La propiedad «max_ size» es el número de caracteres permitidos para la dimensión antes de que se produzca truncamiento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Cname </td> 
   <td colname="col2"> El nombre de la cookie de sesión utilizada para mantener el estado de la comunicación de la API Demandbase. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Contextname </td> 
   <td colname="col2"> Nombre de la variable contextdata que se utiliza para enviar las dimensiones estándar a Adobe Analytics. Se recomienda no modificar esta configuración. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> _ db._ Contextnamecustom </td> 
   <td colname="col2"> Nombre de la variable contextdata que se utiliza para enviar las dimensiones personalizadas a Adobe Analytics. Se recomienda no modificar esta configuración. </td> 
  </tr> 
 </tbody> 
</table>

