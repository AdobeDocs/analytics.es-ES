---
description: Permite controlar el acceso a los datos de los informes. Las opciones incluyen contraseñas seguras, caducidad de las contraseñas, restricciones de inicio de sesión de direcciones IP y restricciones de dominio de correo electrónico.
seo-description: Permite controlar el acceso a los datos de los informes. Las opciones incluyen contraseñas seguras, caducidad de las contraseñas, restricciones de inicio de sesión de direcciones IP y restricciones de dominio de correo electrónico.
seo-title: Administrador de seguridad
solution: Analytics
title: Administrador de seguridad
topic: Herramientas de administración
uuid: b 3 fbdba 0-e 2 bf -4 d 67-92 e 3-ef 05711141 d 4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Administrador de seguridad

Permite controlar el acceso a los datos de los informes. Las opciones incluyen contraseñas seguras, caducidad de las contraseñas, restricciones de inicio de sesión de direcciones IP y restricciones de dominio de correo electrónico.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Administración]** &gt; **[!UICONTROL Configuraciones de la empresa]** &gt; **[!UICONTROL Seguridad]**

<table id="table_F1AD9DE5094A4FC2B9DA8D01198F944B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Requiere contraseñas sólidas </span> </td> 
   <td colname="col2">Obliga a los usuarios a crear contraseñas más seguras conforme a las reglas siguientes: 
    <ul id="ul_100CC57EB4374DAA87B2074BA8B46F26"> 
     <li id="li_4D9102C361044FADBC14402A8398F2F3">Tener al menos ocho caracteres. </li> 
     <li id="li_AFE9568C14894E93BFDFDC84DCD2838D">Tener al menos un símbolo o número entre los caracteres primero y último. </li> 
     <li id="li_ECA05BEF7BFD4430B09D4A953B41D2A6">Tener al menos un carácter alfanumérico. </li> 
     <li id="li_6928045588E94E28851BB15991C8D51E">No figurar en un diccionario ni contener palabras del diccionario (inglés). </li> 
     <li id="li_C3DD4608CA6F43E4B1E4FCFC6D116371">No incluir tres (3) caracteres consecutivos del nombre de usuario. </li> 
     <li id="li_687838CA01B94EE29EF4C09F485C5537">Ser diferente de las 10 contraseñas anteriores. </li> 
    </ul> <p>Nota: Esta función se refuerza en las nuevas contraseñas a partir de este momento. No comprueba las contraseñas anteriores ni obliga a los usuarios a cambiar sus contraseñas actuales. Por este motivo, puede activar la caducidad de las contraseñas para obligar a los usuarios a cambiar sus contraseñas conforme a las reglas de las contraseñas sólidas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Caducidad de la contraseña</span> </td> 
   <td colname="col2"> Obliga a los usuarios a cambiar la contraseña de cuenta de usuario periódicamente. Puede especificarse el intervalo en el que deben caducar las contraseñas y forzar su caducidad inmediata. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Aplicar restricciones de inicio de sesión IP</span> </td> 
   <td colname="col2"> <p>Limita el acceso a los informes para direcciones IP individuales o en intervalos. </p> <p>Se pueden agregar hasta 100 entradas en la lista de filtro de direcciones IP, y cada una de ellas puede ser una dirección determinada o un rango de direcciones. </p> <p> <span class="wintitle"> Aplicar restricciones de inicio de sesión IP</span> no se aplicará mientras no haya al menos una entrada en la lista de filtro de direcciones IP. </p> <p> <span class="uicontrol"> Dirección IP aceptada</span>: Para especificar un intervalo de direcciones IP, escriba el rango entre corchetes (por ejemplo,
       <code>
        192.168.10.[20-240]
       </code>). You can also use wildcards (*) to specify any number from 0 to 255 (por ejemplo, 
       <code>
        192.168.[10-14].*
       </code>) </p> <p>Los inicios de sesión que generan errores se registran y pueden verse desde <a href="../../admin/admin/logs.md#section_6FBAF92D9EA244809C45A78A2F0A7232" format="dita" scope="local">Uso del registro y acceso a él</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Aplicar restricciones de dominio de correo electrónico</span> </td> 
   <td colname="col2"> <p>Filtra las direcciones de correo electrónico y los dominios a los que Analytics envía marcadores, informes descargables y alertas. </p> <p>La lista de filtro de correo electrónico admite hasta 100 entradas, y cada una de ellas puede ser una dirección o un dominio completo de correo electrónico. </p> <p>Si un informe programado tiene un destino de correo electrónico no autorizado, Analytics enviará una notificación sobre el problema por correo electrónico, con un vínculo para anular la programación del informe. </p> <p> <span class="wintitle"> Aplicar restricciones de dominio de correo electrónico</span> no se aplicará mientras no haya al menos una entrada en la lista de <span class="wintitle">filtro de dominio de correo electrónico aceptado</span>. </p> <p> <span class="uicontrol"> Dirección de correo electrónico y dominios aceptados</span>: Para especificar un intervalo de direcciones IP, escriba el rango entre corchetes (por ejemplo,
    <code>
      192.168.10.[20-240]
    </code>). You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
    <code>
      192.168.[10-14].*
    </code>) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Notificación de recuperación de contraseña</span> </td> 
   <td colname="col2"> <p>Avisa a los administradores especificados cuando los usuarios intentan restablecer contraseñas de cuenta de usuario. </p> <p> <span class="uicontrol"> Administradores disponibles</span>: muestra todos los administradores. Con las combinaciones Ctrl+clic y Mayús+clic pueden seleccionarse varios administradores. </p> <p> <span class="uicontrol">Miembros de correo electrónico</span>: muestra el grupo de correo electrónico definido actualmente. </p> </td> 
  </tr> 
 </tbody> 
</table>

