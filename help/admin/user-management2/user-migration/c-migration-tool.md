---
description: Todo lo que debe saber sobre la migración de ID de usuario de Analytics a Admin Console en Adobe Experience Cloud.
title: Migración de usuarios de Analytics a Admin Console
uuid: 7d020713-693b-4945-aa52-3669a631aacb
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# Migración de usuarios de Analytics a Admin Console {#analytics-user-migration-to-the-admin-console}

Todo lo que debe saber sobre la migración de ID de usuario de Analytics a Admin Console en Adobe Experience Cloud.

Para obtener ayuda en general sobre los temas relacionados con Admin Console (no con la migración de Analytics), consulte la [guía del usuario de Admin Console](https://helpx.adobe.com/es/enterprise/administering/user-guide.html).

Después de realizar la migración, puede [administrar los usuarios y productos](https://docs.adobe.com/content/help/es-ES/core-services/interface/manage-users-and-products/admin-getting-started.html) de Experience Cloud en Admin Console.

## ¿Qué es la migración de ID de usuario de Analytics? {#section-adbe49aba10c4e62afa836a97894107c}

La migración de ID de usuario de Analytics permite a los administradores migrar fácilmente las cuentas de usuario de Administración de usuarios de Analytics a Admin Console de Adobe. Una vez migrados los usuarios, tendrán acceso a las soluciones y a los servicios principales disponibles en Experience Cloud. La migración se está implementando a los clientes en varias fases.

Las ventajas de utilizar la Consola de administración incluyen:

<table id="table_E4465796E224474680D750CAC5434ED3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beneficio </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Inicio de sesión único </p> </td> 
   <td colname="col2"> <p>Los usuarios de Analytics pueden iniciar sesión en Experience Cloud y en todas las soluciones con su Adobe ID o Enterprise ID. Este inicio de sesión permite el acceso a soluciones integradas y servicios principales en Experience Cloud. </p> <p>Tras la migración, los usuarios que intenten iniciar sesión con los accesos heredados (<span class="filepath">my.omniture.com</span> y <span class="filepath">sc.omniture.com</span>) se redirigen a <span class="filepath"> experiencecloud.adobe.com</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Administrar la identidad y los permisos de usuarios </p> </td> 
   <td colname="col2"> <p>Los administradores de Analytics solo pueden administrar usuarios y permisos en <a href="http://adminconsole.adobe.com/enterprise/">Admin Console</a> (http://adminconsole.adobe.com/enterprise/). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Administrar productos y servicios principales </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">Invitar a nuevos usuarios </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">Crear perfiles de producto </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">Conceder permiso a los usuarios para productos y servicios específicos </li> 
     <li id="li_9C8A340A7C9A45A98EC0BD4AF9E100FF">Obtener acceso a los <a href="https://docs.adobe.com/content/help/es-ES/core-services/interface/experience-cloud.html">servicios principales entre soluciones</a> disponibles en Adobe Experience Cloud </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Qué se debe tener en cuenta (y qué se debe hacer) antes de migrar ID de usuario (preguntas frecuentes) {#section-b0fc7f0bbd4b488e95b0c8e77ff077a9}

Respuestas a las preguntas que le puedan surgir antes de la migración.

<table id="table_36FD7EF1DAB44D359F4FC186D93147E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pregunta/Tarea </th> 
   <th colname="col2" class="entry"> Respuesta </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Soy administrador de Analytics y he recibido un correo electrónico previo a la migración. ¿Qué hago primero? </p> </td> 
   <td colname="col2"> <p>Compruebe que dispone de un Adobe ID y que puede acceder a <a href="https://adminconsole.adobe.com/enterprise/">Admin Console de Experience Cloud</a>. </p> <p>Si no lo tiene, póngase en contacto con el <a href="https://helpx.adobe.com/es/marketing-cloud/contact-support.html">servicio de atención al cliente de Adobe</a> (En primer lugar, debe ponerse en contacto con el administrador del sistema o del producto, que puede invitarlo a la organización adecuada). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Integraciones de AEM con Analytics </p> </td> 
   <td colname="col2"> <p> Los usuarios de AEM con una integración con Analytics deberán cambiar su configuración para utilizar la clave secreta compartida de Analytics en lugar de la contraseña. </p> <p> Debe hacerlo antes de habilitar la migración. Una vez deshabilitada la migración, la contraseña configurada originalmente ya no será válida. </p> <p><b>Para obtener la clave secreta compartida en Analytics</b> </p> <p> El secreto compartido se puede obtener en Analytics (<span class="uicontrol">Analytics</span> &gt; <span class="uicontrol">Administración de usuarios</span>) y es diferente para cada usuario. </p> <p><b>Para actualizar la configuración de AEM con el secreto compartido</b> </p> <p>Consulte <a href="https://helpx.adobe.com/es/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html">Connecting to Adobe Analytics and Creating Frameworks</a> (Conexión a Adobe Analytics y creación de módulos). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Actualizar el Report Builder </p> </td> 
   <td colname="col2"> <p> <p>Importante: Actualice la instalación del <a href="https://marketing.adobe.com/resources/help/es_ES/arb/t_install_arb.html">Report Builder</a> a la versión más reciente. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Cuándo empieza la migración? </p> </td> 
   <td colname="col2"> <p>Adobe notificará a los administradores de Analytics por correo electrónico con instrucciones sobre cuándo comenzará la migración. </p> <p>Las migraciones a Admin Console se producirán en olas. El día de la migración, Adobe notifica a los administradores de Analytics y les concede acceso a la herramienta de migración. Una vez que una compañía de inicio de sesión cumpla los criterios definidos para cada oleada de migración, Adobe: </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">Establezca las fechas de inicio y finalización de la migración de la compañía. </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">Envíe una notificación por correo electrónico a los administradores de Analytics actuales de la compañía, aproximadamente 30 días antes de la migración. </li> 
     <li id="li_476265B24CE2404B995201170C75D674">Muestre una notificación interna del producto que informe a los administradores de la fecha de inicio de la migración. </li> 
    </ul> <p> El día de la migración, los grupos de permisos anteriores se copian automáticamente en Admin Console. Ya no podrá invitar a nuevos usuarios ni crear grupos nuevos en las herramientas de administración de Analytics. </p> <p>Después de la migración: </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">Los administradores utilizarán Admin Console para administrar los usuarios y permisos de Analytics. (Ya no utilizará la interfaz de administración de usuarios en Analytics &gt; Administración &gt; Administración de usuarios). </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">Los usuarios accederán a Analytics con su Adobe ID o Enterprise ID a través de Experience Cloud, en lugar de usar <span class="filepath">my.omniture.com</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Qué ocurrirá en la fecha de inicio de la migración? </p> </td> 
   <td colname="col2"> <p>A las 10:00 horas UTC en la fecha de inicio de la migración: </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">Los grupos de permisos existentes en Analytics se replicarán automáticamente en Admin Console como Perfiles de producto, incluidos su descripción y permisos granulares en grupos de informes, métricas, dimensiones, Analytics y herramientas de grupos de informes. </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">Si alguno de los usuarios actuales de Analytics se creó en Admin Console (es decir, tiene un Adobe/Enterprise ID vinculado), se agregará a los Perfiles de producto correspondientes en Admin Console. </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">La sección Administración de usuarios de la ficha Administración de Analytics pasará a ser de <span class="term"> solo lectura</span>. Aquí ya no podrá crear nuevos usuarios ni grupos de permisos, por lo que deberá realizar estas funciones en Admin Console. Consulte <a href="/help/admin/user-management2/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56">Funciones de Analytics no soportadas en Admin Console</a> para obtener más información. </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">Como administrador, se le otorgará acceso a la herramienta <a href="https://marketing.adobe.com/resources/help/es_ES/experience-cloud/admin-console/analytics-migration/t_migrate-users.html">de migración de ID de</a>usuario. Además, aparece una notificación en el producto que incluye la fecha de finalización de la migración (normalmente, 60 días en el futuro), además de vínculos a contenido de ayuda y preguntas más frecuentes. </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">Se le otorgará acceso a una ficha Permisos en la Consola de administración que le permite crear Perfiles de producto con todas las opciones granulares que esté familiarizado con Analytics. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Cómo se migran los ID de usuario? </p> </td> 
   <td colname="col2"> <p> Click <a href="/help/admin/user-management2/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9"> Migrate User IDs</a> on the Admin page, under User Management. Utilice la herramienta para agregar usuarios a perfiles de productos en Admin Console (replicados desde grupos de permisos en Analytics). Puede migrar los ID de usuario a su propio ritmo. </p> <p>Se requieren privilegios de administración. Una vez completada la migración, no se puede revertir. </p> <p>En la fecha de fin de la migración, el acceso <span class="filepath">my.omniture.com</span> se desactivará para los usuarios de la empresa de inicio de sesión. Los usuarios (incluidos aquellos que aún no se han migrado) se redirigirán para que inicien sesión mediante la nueva URL de Experience Cloud (<span class="filepath">experiencecloud.adobe.com</span>). </p> <p>Nota: Adobe recomienda aprovechar la oportunidad para realizar una auditoría de los usuarios y grupos antes de llevar a cabo la migración. Elimine las cuentas antiguas y sin utilizar, o bien las cuentas que ya no deben tener acceso al producto (como las de los empleados que ya no pertenecen a la organización). </p> <p>Tema relacionado: <a href="/help/admin/user-management2/user-migration/migrate-enterprise.md"> Migrar cuentas de usuario de Analytics para Enterprise ID y Federated ID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Afectará la migración a mi implementación de Analytics o a cómo se recopilan los datos? </p> </td> 
   <td colname="col2"> <p>No. </p> <p>La herramienta de migración tiene como objetivo ayudarle con la transición de ID de usuario y permisos de la administración de usuarios de Analytics a <a href="https://adminconsole.adobe.com/enterprise/">Admin Console de Experience Cloud</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Cuánto tarda el proceso de migración? </p> </td> 
   <td colname="col2"> <p>Todos los administradores actuales de Analytics recibirán un correo electrónico de notificación previa a la migración cuatro semanas antes de la migración. (La fecha de inicio real aparecerá en la interfaz de Analytics). </p> <p>Cuando comience la migración, los administradores dispondrán de 60 días para completar el proceso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Puedo acelerar mi migración? </p> </td> 
   <td colname="col2"> <p>Sí. Sin embargo, Adobe recomienda que utilice el tiempo previo a la migración para: </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">Compruebe que es administrador del producto de Analytics en Admin Console. </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">Comunicar a la base de usuarios que su experiencia de inicio de sesión cambiará cuando comience la migración. </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">Audite los usuarios y permisos actuales y realice actividades de limpieza. </li> 
    </ul> <p>Para adelantar la migración, póngase en contacto con el administrador de éxitos del cliente en el <a href="https://helpx.adobe.com/es/marketing-cloud/contact-support.html">servicio de atención al cliente de Adobe</a> y envíe una solicitud para adelantar la fecha de inicio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Soy administrador de Analytics sin acceso a Admin Console. ¿Quién puede ayudarme a obtener acceso a Admin Console? </p> </td> 
   <td colname="col2"> <p>Cualquier administrador de sistemas o productos que tenga acceso a Admin Console en su organización podrá proporcionarle acceso. Si no sabe con seguridad qué persona de su organización dispone de privilegios de administrador en la consola, póngase en contacto con el <a href="https://helpx.adobe.com/es/marketing-cloud/contact-support.html">servicio de atención al cliente de Adobe</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Puedo posponer la fecha de inicio de la migración? </p> </td> 
   <td colname="col2"> <p>Sí. Póngase en contacto con el <a href="https://helpx.adobe.com/es/marketing-cloud/contact-support.html">servicio de atención al cliente de Adobe</a>. </p> 
    <draft-comment> 
     <p>Consulte a continuación una descripción de los cambios en la Administración de usuarios y permisos de Analytics actual en la fecha de inicio. </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ahora que mi compañía está migrando a Admin Console, ¿dónde creo nuevos usuarios y grupos de permisos antes de la fecha de inicio de la migración? </p> </td> 
   <td colname="col2"> <p>Antes de la fecha de inicio de la migración, puede crear usuarios en Admin Console o en Analytics &gt; Administración de usuarios. </p> <p>Una vez iniciada la migración, solo puede crear usuarios y grupos de permisos en Admin Console. </p> 
    <draft-comment> 
     <p>consulte la sección Migración a continuación para obtener más detalles sobre lo que sucede en la fecha de inicio de la migración). </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> ¿Cuándo puedo implementar el inicio de sesión único con Federated ID? </p> </td> 
   <td colname="col2"> <p> Pronto habrá una herramienta disponible en Admin Console que le permitirá cambiar los tipos de ID de Adobe ID a Federated ID. Durante la migración, no puede migrar usuarios como Federated ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Aspectos a tener en cuenta durante la migración (preguntas frecuentes) {#section-d394524aa6d046d79025bbd7499792bc}

Información importante sobre el proceso de migración y su impacto en la administración de usuarios actual.

<table id="table_0E37BB1DEA6143F0B5F4E861FCFA7189"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pregunta </th> 
   <th colname="col2" class="entry"> Respuesta </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>¿Cómo se replican los grupos de permisos en Admin Console? ¿Qué pasa con mis usuarios? </p> </td> 
   <td colname="col2"> <p>Un grupo de Analytics migrado se denomina Perfil <i>de</i> producto en la Consola de administración. La configuración de permisos del grupo original se conserva en la migración. Sin embargo, los usuarios asignados al grupo no se migran. Cuando un usuario que pertenece a ese grupo se migra mediante la herramienta de migración, ese usuario se asigna a ese perfil de producto. </p> <p>Por ejemplo, un grupo de permisos Operaciones de la Costa Oeste que asignó a sus miembros el Creador de informes y el Espacio de trabajo de Análisis (con determinados grupos de informes, métricas y dimensiones) se convertirá en un perfil de producto Operaciones de la Costa Oeste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Puedo delegar el esfuerzo de migración a otro administrador? </p> </td> 
   <td colname="col2"> <p>Una vez que comience la migración, cualquier administrador que acceda a la instancia de Analytics a través de Experience Cloud puede utilizar la herramienta de migración para iniciar (o continuar) la migración de usuarios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Puedo actualizar la pertenencia a grupos de permisos para usuarios no migrados? </p> </td> 
   <td colname="col2"> <p>Sí. Puede cambiar la pertenencia a grupos de usuarios no migrados desde la sección Administración de usuarios de Analytics. </p> 
    <draft-comment> 
     <p>A la espera de una aclaración de Ashok sobre dónde se ha hecho eso. </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Puedo crear usuarios y grupos de permisos en Analytics después de que comience la migración y, a continuación, utilizar la herramienta de migración para moverlos a Admin Console? </p> </td> 
   <td colname="col2"> <p> No. Una vez iniciada la migración, todos los usuarios y grupos de permisos nuevos (denominados Perfiles de producto en la Consola de administración) deben crearse en la Consola de administración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Se asignarían a los usuarios que migre con la herramienta de migración los mismos permisos que tenían en Analytics? </p> </td> 
   <td colname="col2"> <p>Sí. A los usuarios migrados mediante la herramienta se les concederán los permisos que tienen actualmente en Analytics. Además, conservarán el acceso a sus recursos de Analytics (como segmentos, proyectos, métricas calculadas, etc.) cuando accedan a Analytics a través de Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Siguen teniendo acceso a Analytics los usuarios migrados a Admin Console mediante <span class="filepath">my.omniture.com</span>? </p> </td> 
   <td colname="col2"> <p>Sí. Los usuarios migrados seguirán teniendo acceso a Analytics con el nombre de usuario y la contraseña existentes mediante <span class="filepath">my.omniture.com</span> hasta la fecha de fin de la migración, a menos que desactive el acceso de inicio de sesión heredado a través de la herramienta de migración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dos o más de mis usuarios tienen el mismo ID de correo electrónico en su registro de Analytics. ¿Qué sucede si los migro? </p> </td> 
   <td colname="col2"> <p>Dado que las cuentas de usuario de Admin Console requieren ID de correo electrónico únicos, se producirá un error de "ID de correo electrónico de Duplicado" al intentar migrar más de uno de estos usuarios. Puede actualizar los ID de correo electrónico de los usuarios no migrados en la sección Administración de usuarios (heredada) antes de volver a intentar la migración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> ¿Qué debo hacer después de migrar mis usuarios? </p> </td> 
   <td colname="col2"> <p>Desactive el acceso de inicio de sesión heredado a <span class="filepath">my.omniture.com</span>. No podrá desactivar el inicio de sesión heredado a menos que se hayan migrado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Puedo realizar un seguimiento del proceso de migración? </p> </td> 
   <td colname="col2"> <p>La herramienta de migración incluye un panel que muestra cuántos de los usuarios se han migrado correctamente y cuántos de ellos tienen deshabilitado el inicio de sesión heredado. </p> <p> Lo ideal es que haya migrado correctamente la compañía de inicio de sesión a Admin Console cuando el 100 % de los usuarios haya completado la migración y sus inicios de sesión heredados estén desactivados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Necesito realizar la administración de usuarios y permisos durante la migración. ¿Qué herramienta puedo utilizar para realizar esta tarea? </p> </td> 
   <td colname="col2"> <p>Una vez que comience la migración, utilizará la Consola de administración para crear y administrar nuevos usuarios y perfiles de productos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Qué experimentan mis usuarios cuando los migre con la herramienta? </p> </td> 
   <td colname="col2"> <p>Recibirán un correo electrónico de bienvenida dirigido al ID de correo electrónico en su registro de usuario de Analytics, en el que se les notificará la nueva forma de acceder a Analytics a través de Experience Cloud. Si no tienen un Adobe ID existente, se les pedirá que lo creen, tras lo cual podrán acceder a la solución con su Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Puedo utilizar las API para migrar mis usuarios en lugar de utilizar la herramienta de migración? </p> </td> 
   <td colname="col2"> <p>No. Debe utilizar la herramienta de migración para asegurarse de que todos los usuarios existentes se migran a Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Qué funciones de administración de usuarios de Analytics no están disponibles en Admin Console? </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">Transferencia de activos </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">Caducidad del usuario </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">Registros de usuarios </li> 
    </ul> <p>Estos seguirán estando disponibles en la administración de usuarios de Analytics. </p> <p>Consulte <a href="/help/admin/user-management2/user-migration/c-migration-tool.md">Funciones de Analytics no soportadas en Admin Console</a> para obtener más información. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hemos creado varias configuraciones en Admin Console y las hemos asignado a grupos de permisos de Analytics. ¿Qué ocurrirá con esas configuraciones cuando comience la migración? </p> </td> 
   <td colname="col2"> <p>Los grupos de permisos de Analytics se vuelven a crear en Admin Console como perfiles de productos, al igual que todos los demás grupos. Esto significa que verá dos perfiles de producto en la consola que, básicamente, tienen permisos de duplicado. Puede eliminar perfiles de productos de duplicado desde Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Cuál es el siguiente paso después de migrar el usuario? </p> </td> 
   <td colname="col2"> <p>Una vez que haya migrado un usuario o un conjunto de usuarios, el siguiente paso consiste en desactivar el inicio de sesión heredado de <span class="filepath">my.omniture.com</span>. Para ello, seleccione estos usuarios en la herramienta de migración y haga clic en la opción contextual "Deshabilitar inicio de sesión heredado" que aparece en la parte superior de la pantalla. Tenga en cuenta que esta opción solo está visible cuando selecciona un usuario o conjunto de usuarios que se han migrado correctamente a Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Qué sucede en la fecha de finalización de la migración? </p> </td> 
   <td colname="col2"> <p>Después de la fecha de finalización de la migración (60 días desde el inicio de la migración), todos los usuarios de la compañía de inicio de sesión se redirigen a iniciar sesión a través de la página de inicio de sesión de Experience Cloud con sus Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>No he podido migrar todos mis usuarios antes de la fecha de finalización de la migración. ¿Perderán los usuarios no migrados su acceso a Analytics? </p> </td> 
   <td colname="col2"> <p>Los usuarios que no se hayan migrado al llegar la fecha fin se redirigirán a la página de inicio de sesión de Experience Cloud (experiencecloud.adobe.com) y no podrán acceder a Analytics. Sin embargo, seguirá teniendo acceso a la herramienta de migración, por lo que podrá buscarlos y migrarlos para restaurar su acceso. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Qué se debe tener en cuenta después de la migración (preguntas frecuentes) {#section-9681baa01b8c41cdb9659b73b70b50ff}

<table id="table_F48CC9DFE3424AC9AD76A16882701C8F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pregunta/Problema </th> 
   <th colname="col2" class="entry"> Respuestas </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eliminación de usuarios de Admin Console </p> </td> 
   <td colname="col2"> <p> En Analytics, un usuario eliminado se establece como <span class="term"> ha expirado</span>, pero la cuenta sigue existiendo. La preservación de la cuenta permite la transferencia de recursos, como segmentos, métricas calculadas, informes programados, proyectos, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caducidad de la cuenta </p> </td> 
   <td colname="col2"> <p> Puede definir manualmente una fecha de caducidad de la cuenta en Analytics en las Herramientas de administración. Una vez cumplida la fecha de caducidad, el usuario no podrá acceder a Analytics, pero sí a su cuenta de usuario real de Experience Cloud (por ejemplo, Adobe ID, Enterprise ID, Federated ID, etc.) no caduca. Todavía pueden iniciar sesión en Experience Cloud, pero no podrán hacer clic en Analytics. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Funciones de Analytics no soportadas en Admin Console {#section-928ffba27a0446e0af575b720434ef56}

>[!IMPORTANT]
>
>Revise los problemas siguientes que pueden ser aplicables durante la migración.

<table id="table_88E2FA03D5F241B79AB54D12F64B51DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pregunta/Problema </th> 
   <th colname="col2" class="entry"> Respuestas </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Iniciar sesión como </p> </td> 
   <td colname="col2"> <p> Los administradores que realicen la migración a Admin Console ya no podrán utilizar la función "Iniciar sesión como" para acceder a las cuentas de usuario que no sean de administración migradas a Admin Console. Esta función está en desuso de Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caducidad de usuarios y transferencia de recursos </p> </td> 
   <td colname="col2"> <p> La Consola de administración no admite la caducidad del usuario ni la transferencia de recursos. Los administradores utilizarán la sección Usuarios y recursos de Analytics en Herramientas de administración en Analytics para ambas funciones. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Último acceso (último inicio de sesión) </p> </td> 
   <td colname="col2"> <p> Los detalles sobre la fecha y hora del último inicio de sesión de un usuario estarán disponibles en el vínculo Usuarios y recursos de Analytics y no en Admin Console. La fecha del último inicio de sesión en Analytics especifica cuándo accedieron realmente los usuarios a Analytics desde Experience Cloud, pero no refleja la fecha/hora en la que iniciaron sesión en Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://helpx.adobe.com/es/enterprise/using/identity.html">Tipos de identidades compatibles con Adobe</a> de API de administración de usuarios </p> </td> 
   <td colname="col2"> <p> Los administradores que realizan la migración a Admin Console deben configurar las <a href="https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html">API de administración de usuarios</a> incluidas en Adobe I/O para el acceso programático a las cuentas de usuario de Admin Console. </p> <p>Las API de permisos de Analytics se desactivarán cuando esté habilitado para la migración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Credenciales del servicio Web </p> </td> 
   <td colname="col2"> <p> Las credenciales del servicio web de los usuarios (y su clave secreta compartida) no estarán disponibles en Admin Console y se puede acceder a ellas haciendo clic en el usuario específico en la sección Usuarios y recursos de Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inicio de sesión único </p> </td> 
   <td colname="col2"> <p> Las configuraciones de inicio de sesión único de Analytics se eliminarán cuando haya completado la migración. Permanecerán activos durante la migración. Los clientes que utilizan el inicio de sesión único de Analytics deberían actualizar al <a href="https://helpx.adobe.com/es/enterprise/using/identity.html">Adobe Federated ID</a>. </p> <p>Analytics recomienda migrar los usuarios como Adobe ID primero para crear fácilmente las cuentas de Experience Cloud y, a continuación, convertirlas a usuarios de un solo signo federado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Descarga de grupos de permisos </p> </td> 
   <td colname="col2"> <p> La descarga de la información del grupo de permisos ya no se admitirá en las herramientas de administración de Analytics ni en Adobe Admin Console. Los clientes deben utilizar las API de administración de usuarios de adobe.io para obtener información de grupos de permisos de forma masiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fecha de creación de la cuenta </p> </td> 
   <td colname="col2"> <p>La información sobre la fecha de creación de cuentas ya no se admite en las herramientas de administración de Analytics ni en Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Correo electrónico masivo </p> </td> 
   <td colname="col2"> <p>El correo electrónico masivo a los usuarios ya no se admitirá en la Consola de administración de Analytics ni en la Consola de administración de Adobe. Los clientes pueden exportar de forma masiva las direcciones de correo electrónico de sus usuarios desde Adobe Admin Console y enviar un correo electrónico con cualquier cliente de correo electrónico que deseen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Notificación de la migración a los usuarios {#section-f3b25f672a3a4d03b0559656fd99d20a}

Es posible que desee comunicar de forma proactiva este plan de migración a los usuarios actuales. Esta es una plantilla que puede personalizar para enviar a todos sus usuarios actuales de Analytics:

Para enviar un correo electrónico a todos los usuarios, vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]** > Usuarios [de](https://marketing.adobe.com/resources/help/es_ES/reference/t_email_users.html)correo electrónico.

**Asunto:** Próximamente: nueva forma de iniciar sesión en Adobe Analytics y Adobe Experience Cloud.

**Cuerpo:** Hola, usuarios de Adobe Analytics:

Nuestra empresa empezará a migrar todas las cuentas de Adobe Analytics de [!DNL https://my.omniture.com/login/] a Adobe Experience Cloud ([experiencecloud.adobe.com](http://experiencecloud.adobe.com/)). Con esta migración, su cuenta de Adobe Analytics se actualizará para permitir el acceso a Analytics a través de Adobe Experience Cloud. Aunque el método para acceder a Analytics cambiará, se conservarán todos los permisos existentes para los grupos de informes y las herramientas.

**Próximos pasos:** Empezaremos a migrar usuarios el **INSERTAR FECHA**. Busque un mensaje de bienvenida con su nuevo inicio de sesión dirigido al ID de correo electrónico que aparece en la lista de su cuenta de Analytics. Si no ha configurado un ID [de](https://helpx.adobe.com/es/x-productkb/global/adobe-id-account-change.html) Adobe vinculado a su dirección de correo electrónico, se le pedirá que configure una cuenta.

**Recursos útiles:**

[Inicio de sesión y administración de la configuración de perfil](https://marketing.adobe.com/resources/help/es_ES/mcloud/getting-started-experience-cloud.html).

[Acerca de nubes, servicios principales y soluciones](https://marketing.adobe.com/resources/help/en_US/mcloud/solutions_capability_names.html) en Experience Cloud

Póngase en contacto con los administradores de Analytics si tiene alguna pregunta o duda.

Mejor,

Administrador de Analytics
