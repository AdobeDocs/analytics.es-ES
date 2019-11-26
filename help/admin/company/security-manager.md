---
description: Permite controlar el acceso a los datos de los informes. Las opciones incluyen contraseñas seguras, caducidad de las contraseñas, restricciones de inicio de sesión de direcciones IP y restricciones de dominio de correo electrónico.
solution: Analytics
title: Administrador de seguridad
topic: Admin tools
uuid: b3fbdba0-e2bf-4d67-92e3-ef05711141d4
translation-type: tm+mt
source-git-commit: 229ce50a24bd7b86e3859775bb4fbeba1c6a5668

---


# Administrador de seguridad

Permite controlar el acceso a los datos de los informes. Las opciones incluyen contraseñas seguras, caducidad de las contraseñas, restricciones de inicio de sesión de direcciones IP y restricciones de dominio de correo electrónico.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Administración]** &gt; Configuración **[!UICONTROL de empresa]** &gt; **[!UICONTROL Seguridad]**

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
   <td colname="col2"> <p>(Esta funcionalidad no se puede usar junto con el inicio de sesión de Experience Cloud. Tenga en cuenta que esta funcionalidad ya no estará disponible a partir de octubre de 2020). Limita el acceso a los informes para direcciones IP individuales o en intervalos. </p> <p>Se pueden agregar hasta 100 entradas en la lista de filtro de direcciones IP, y cada una de ellas puede ser una dirección determinada o un rango de direcciones. </p> <p> <span class="wintitle"> Aplicar restricciones de inicio de sesión IP</span> no se aplicará mientras no haya al menos una entrada en la lista de filtro de direcciones IP. </p> <p> <span class="uicontrol"> Dirección IP aceptada</span>: para especificar un intervalo de direcciones IP, este debe escribirse entre corchetes (por ejemplo, 
     <code>
       192.168.10.[20-240]
     </code>). También pueden utilizarse caracteres comodín (*) para especificar cualquier número del 0 al 255 (por ejemplo, 
     <code>
       192.168.[10-14].*
     </code>) </p> <p>Los inicios de sesión que generan errores se registran y pueden verse desde <a href="/help/admin/admin/logs.md#section_6FBAF92D9EA244809C45A78A2F0A7232">Uso del registro y acceso a él</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Aplicar restricciones de dominio de correo electrónico</span> </td> 
   <td colname="col2"> <p>Filtra las direcciones de correo electrónico y los dominios a los que Analytics envía marcadores, informes descargables y alertas. </p> <p>La lista de filtro de correo electrónico admite hasta 100 entradas, y cada una de ellas puede ser una dirección o un dominio completo de correo electrónico. </p> <p>Si un informe programado tiene un destino de correo electrónico no autorizado, Analytics enviará una notificación sobre el problema por correo electrónico, con un vínculo para anular la programación del informe. </p> <p> <span class="wintitle"> Aplicar restricciones de dominio de correo electrónico</span> no se aplicará mientras no haya al menos una entrada en la lista de <span class="wintitle">filtro de dominio de correo electrónico aceptado</span>. </p> <p> <span class="uicontrol"> Direcciones de correo electrónico y dominios aceptados</span>: para especificar un intervalo de direcciones IP, este debe escribirse entre corchetes (por ejemplo, 
     <code>
       192.168.10.[20-240]
     </code>). También pueden utilizarse caracteres comodín (*) para especificar cualquier número del 0 al 255 (por ejemplo, 
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

## Fin de vida útil para [!UICONTROL aplicar restricciones de inicio de sesión IP]

La función **[!UICONTROL Aplicar restricciones]** de inicio de sesión IP es una función de Analytics heredada que le permite incluir direcciones IP específicas que se consideran seguras, para permitir inicios de sesión exitosos y acceder a su entorno de Adobe Analytics. En muchos casos, esta función se utiliza para configurar una dirección IP corporativa como la única dirección IP segura desde la que los usuarios pueden iniciar sesión. Por lo tanto, para utilizar Adobe Analytics, esto requiere que los usuarios estén en una oficina corporativa o que inicien sesión en la red a través de VPN.

### ¿Por qué lo estamos considerando para el final de la vida útil?

Esta función se rompe en algunas circunstancias con la migración de inicio de sesión de Experience Cloud o el inicio de sesión de Experience Cloud. Se sabe que se produce un error en los clientes que utilizan Atributos **** del cliente o Biblioteca **[!UICONTROL de]** audiencias.

Además, si posee varias soluciones de Experience Cloud, puede eludir este requisito si inicia sesión en Experience Cloud con una de las otras soluciones, ya que esta función no existe o no se admite fuera de Analytics. Los usuarios también pueden evitar esto a través de la falsificación de IP.

Por último, Adobe cuenta con una solución alternativa funcional y muy superior mediante el inicio de sesión único y Federated ID. Esta función le proporciona un mayor control y seguridad sobre la experiencia de inicio de sesión de los usuarios.

### ¿Cómo le afecta la eliminación de esta función?

Esta función se eliminará en octubre de 2020 para cualquier cliente que tenga **[!UICONTROL configurado las restricciones]** de inicio de sesión de la IP de aplicación. En ese momento, ya no se aplicará ninguna restricción de inicio de sesión IP que aún exista. Si todavía necesita restringir el inicio de sesión por dirección IP, debe revisar e implementar la solución recomendada de inicio de sesión único y Federated ID (más información y recursos a continuación).

Además, el administrador de restricciones **[!UICONTROL de inicio de sesión de]** Aplicar IP se eliminará del **[!UICONTROLAadministrador &gt; Configuración de la empresa &gt; Administrador]** de seguridad en la interfaz de usuario de Analytics (como se muestra a continuación).

![](assets/sec-manager2.png)

### ¿Cuáles son sus otras opciones?

Como se ha indicado anteriormente, esta función de Analytics finalizará su vida útil. Para darle tiempo para implementar SSO e Federated ID, hemos retrasado la fecha de EOL hasta octubre de 2020.

Tanto los SSO como los Federated ID son soluciones superiores a la función de restricción de inicio de sesión IP que tenemos en la actualidad y le proporcionarán más control, seguridad y características.

Para obtener información sobre cómo configurar los SSO/Federated ID, tenemos disponible la siguiente documentación de ayuda. Le recomendamos que los lea a fondo y trabaje con su departamento de TI para implementarlos:

* [Inicio de sesión único y Experience Cloud](https://spark.adobe.com/page/JeSB8EPEQIvjD/)
* [Consola de administración: documentación de configuración de identidad](https://helpx.adobe.com/enterprise/using/set-up-identity.html)
* [Consola de administración: tutorial de configuración de identidad (vídeo)](https://helpx.adobe.com/enterprise/how-to/identity-directories-domains.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [Tutorial sobre la configuración de Federated ID (vídeo)](https://helpx.adobe.com/enterprise/how-to/identity-configure-ids.html?playlist=/ccx/v1/collection/product/enterprise/topics/enterprise-identity/collection.ccx.js&ref=helpx.adobe.com)
* [Inicio de sesión único: preguntas frecuentes](https://helpx.adobe.com/enterprise/using/sso-faq.html)
* [Tipos de identidad compatibles con Adobe](https://helpx.adobe.com/enterprise/using/identity.html)

Si desea seguir expresando su compatibilidad con las restricciones de inicio de sesión IP y solicitar que Experience Cloud la proporcione, puede votar por esta función en nuestra página [](https://forums.adobe.com/ideas/11648)de foro. Para más preguntas o información sobre SSO/Federated ID y el EXC, póngase en contacto con Ryan Monger (monger@adobe.com).
