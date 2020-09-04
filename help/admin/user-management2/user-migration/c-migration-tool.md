---
description: Todo lo que debe saber sobre la migración de ID de usuario de Analytics a Admin Console en Adobe Experience Cloud.
title: Migración de usuarios de Analytics a Admin Console
uuid: 7d020713-693b-4945-aa52-3669a631aacb
translation-type: tm+mt
source-git-commit: 82cf5ddfd4d18af09c2dbedba20514e4b643a94b
workflow-type: tm+mt
source-wordcount: '3131'
ht-degree: 99%

---


# Migración de usuarios de Analytics a Admin Console {#analytics-user-migration-to-the-admin-console}

Todo lo que debe saber sobre la migración de ID de usuario de Analytics a Admin Console en Adobe Experience Cloud.

Para obtener ayuda en general sobre los temas relacionados con Admin Console (no con la migración de Analytics), consulte la [guía del usuario de Admin Console](https://helpx.adobe.com/es/enterprise/administering/user-guide.html).

Después de migrar, puede [administrar los usuarios y productos de Experience Cloud](https://docs.adobe.com/content/help/es-ES/core-services/interface/manage-users-and-products/admin-getting-started.html) en Admin Console.

## ¿Qué es la migración de ID de usuario de Analytics? {#section-adbe49aba10c4e62afa836a97894107c}

La migración de ID de usuarios de Analytics permite a los administradores migrar fácilmente las cuentas de usuario de Administración de usuarios de Analytics a Admin Console de Adobe. Una vez que se haya migrado los usuarios, estos podrán acceder a las soluciones y a los servicios principales disponibles en Experience Cloud. La migración se está poniendo a disposición de los clientes por fases.

Entre las ventajas de usar Admin Console se incluyen:

<table id="table_E4465796E224474680D750CAC5434ED3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ventaja </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Inicio de sesión único </p> </td> 
   <td colname="col2"> <p>Los usuarios de Analytics pueden iniciar sesión en Experience Cloud y en todas las soluciones mediante el uso del Adobe ID o Enterprise ID. Este inicio de sesión permite acceder a soluciones integradas y servicios principales en Experience Cloud. </p> <p>Tras la migración, los usuarios que intenten iniciar sesión con los accesos heredados (<span class="filepath">my.omniture.com</span> y <span class="filepath">sc.omniture.com</span>) se redirigen a <span class="filepath"> experiencecloud.adobe.com</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Administrar la identidad y los permisos de usuarios </p> </td> 
   <td colname="col2"> <p>Los administradores de Analytics solo pueden administrar usuarios y permisos en <a href="http://adminconsole.adobe.com/enterprise/">Admin Console</a> (http://adminconsole.adobe.com/enterprise/). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Administrar los productos y servicios principales </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">Invitar a nuevos usuarios </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">Crear perfiles de producto </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">Otorgar permisos de usuario para productos y servicios específicos </li> 
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
   <th colname="col1" class="entry"> Pregunta/tarea </th> 
   <th colname="col2" class="entry"> Respuesta </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Soy administrador de Analytics y he recibido un correo electrónico previo a la migración. ¿Qué debo hacer en primer lugar? </p> </td> 
   <td colname="col2"> <p>Compruebe que dispone de un Adobe ID y que puede acceder a <a href="https://adminconsole.adobe.com/enterprise/">Admin Console de Experience Cloud</a>. </p> <p>Si no lo tiene, póngase en contacto con el <a href="https://helpx.adobe.com/es/marketing-cloud/contact-support.html">servicio de atención al cliente de Adobe</a> (primero, debe ponerse en contacto con el administrador del sistema o del producto, quien puede dirigirle a la organización correcta). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Integraciones de AEM con Analytics </p> </td> 
   <td colname="col2"> <p> Los usuarios de AEM con una integración con Analytics deberán cambiar su configuración para usar el secreto compartido de Analytics en lugar de la contraseña. </p> <p> Debe hacerlo antes de que se active la migración. Una vez que se desactive la migración, la contraseña que se configuró originalmente ya no será válida. </p> <p><b>Para obtener el secreto compartido de Analytics</b> </p> <p> El secreto compartido se puede obtener en Analytics (<span class="uicontrol">Analytics</span> &gt; <span class="uicontrol">Administración de usuarios</span>) y es diferente para cada usuario. </p> <p><b>Para actualizar la configuración de AEM con el secreto compartido</b> </p> <p>Consulte <a href="https://helpx.adobe.com/es/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html">Connecting to Adobe Analytics and Creating Frameworks</a> (Conexión a Adobe Analytics y creación de módulos). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Actualizar el Report Builder </p> </td> 
   <td colname="col2"> <p> <p>Importante: Actualice la instalación del <a href="https://docs.adobe.com/content/help/es-ES/analytics/analyze/report-builder/report-builder-setup/t-install-arb.html">Report Builder</a> a la versión más reciente. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Cuándo empieza la migración? </p> </td> 
   <td colname="col2"> <p>Adobe notificará por correo electrónico a los administradores de Analytics instrucciones sobre el comienzo de la migración. </p> <p>Las migraciones a Admin Console se producirán por etapas. El día de la migración, Adobe notifica a los administradores de Analytics y les otorga acceso a la herramienta de migración. Una vez que una empresa de inicio de sesión cumpla los criterios definidos para cada etapa de la migración, Adobe: </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">Definirá las fechas de inicio y finalización de la migración de la empresa. </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">Enviará una notificación por correo electrónico a los administradores de Analytics actuales de la empresa unos 30 días antes de la migración. </li> 
     <li id="li_476265B24CE2404B995201170C75D674">Mostrará una notificación en el producto para informar a los administradores de la fecha de inicio de la migración. </li> 
    </ul> <p> El día de la migración, los grupos de permisos anteriores se copiarán automáticamente en Admin Console. Ya no podrá invitar a nuevos usuarios ni crear grupos nuevos en las herramientas de administración de Analytics. </p> <p>Después de la migración: </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">Los administradores utilizarán Admin Console para administrar los usuarios y permisos de Analytics. (Ya no tendrá que utilizar la interfaz de administración de usuarios de Analytics &gt; Administración &gt; Administración de usuarios). </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">Los usuarios accederán a Analytics con su Adobe ID o Enterprise ID a través de Experience Cloud, en lugar de usar <span class="filepath">my.omniture.com</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Qué ocurrirá en la fecha de inicio de la migración? </p> </td> 
   <td colname="col2"> <p>En la fecha de inicio de la migración, a las 10:00 horas UTC: </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">Los grupos de permisos existentes de Analytics se replicarán automáticamente en Admin Console como perfiles de productos. Incluirán su descripción y permisos granulares en grupos de informes, métricas, dimensiones y herramientas de Analytics y de grupos de informes. </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">Si alguno de los usuarios de Analytics actuales se creó en Admin Console (es decir, tiene un Adobe ID/Enterprise ID vinculado), se añadirá al perfil de producto correspondiente en Admin Console. </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">La sección Administración de usuarios de la ficha Administración de Analytics pasará a ser de <span class="term"> solo lectura</span>. Aquí ya no podrá crear nuevos usuarios ni grupos de permisos, por lo que deberá realizar estas funciones en Admin Console. Consulte <a href="/help/admin/user-management2/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56">Funciones de Analytics no soportadas en Admin Console</a> para obtener más información. </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">Como administrador, se le otorgará acceso a la herramienta <a href="https://docs.adobe.com/content/help/en/analytics/admin/user-product-management/user-management/migrate-users/t-migrate-users.html">Migración de ID de usuario</a>. Además, aparece una notificación en el producto que incluye la fecha de finalización de la migración (suele ser en un plazo de 60 días) junto con vínculos a contenido de ayuda y preguntas frecuentes. </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">Se le otorgará acceso a la ficha Permisos de Admin Console, donde puede crear perfiles de producto con las opciones granulares que ya conoce en Analytics. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Cómo puedo migrar los ID de usuario? </p> </td> 
   <td colname="col2"> <p> Haga clic en <a href="/help/admin/user-management2/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9"> Migrar ID de usuario</a> en la página Administración, dentro de Administración de usuarios. Utilice la herramienta para añadir usuarios a perfiles de productos en Admin Console (replicados de los grupos de permisos en Analytics). Puede migrar ID de usuario a su propio ritmo. </p> <p>Se necesitan privilegios de administración. Una vez que la migración haya terminado, no se puede revertir. </p> <p>En la fecha de fin de la migración, el acceso <span class="filepath">my.omniture.com</span> se desactivará para los usuarios de la empresa de inicio de sesión. Los usuarios (incluidos aquellos que aún no se han migrado) se redirigirán para que inicien sesión mediante la nueva URL de Experience Cloud (<span class="filepath">experiencecloud.adobe.com</span>). </p> <p>Nota: Adobe recomienda aprovechar la oportunidad para realizar una auditoría de los usuarios y grupos antes de llevar a cabo la migración. Elimine las cuentas antiguas y sin utilizar, o bien las cuentas que ya no deben tener acceso al producto (como las de los empleados que ya no pertenecen a la organización). </p> <p>Tema relacionado: <a href="/help/admin/user-management2/user-migration/migrate-enterprise.md"> Migrar cuentas de usuario de Analytics para Enterprise ID y Federated ID</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Afectará la migración a la implementación de Analytics o a la forma en que se recopilan los datos? </p> </td> 
   <td colname="col2"> <p>No. </p> <p>La herramienta de migración tiene como objetivo ayudarle con la transición de ID de usuario y permisos de la administración de usuarios de Analytics a <a href="https://adminconsole.adobe.com/enterprise/">Admin Console de Experience Cloud</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Cómo se lleva a cabo el proceso de migración? </p> </td> 
   <td colname="col2"> <p>Todos los administradores de Analytics actuales recibirán una notificación previa por correo electrónico cuatro semanas antes de la migración (la fecha de inicio real aparecerá en la interfaz de Analytics). </p> <p>Una vez que empiece la migración, los administradores dispondrán de 60 días para completar el proceso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Puedo adelantar la migración? </p> </td> 
   <td colname="col2"> <p>Sí. Sin embargo, Adobe le recomienda que aproveche el tiempo previo a la migración para: </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">Comprobar que es administrador de productos de Analytics en Admin Console. </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">Comunicar a la base de usuarios que la experiencia de inicio de sesión cambiará en el momento en que empiece la migración. </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">Auditar los usuarios y permisos actuales y realizar actividades de limpieza. </li> 
    </ul> <p>Para adelantar la migración, póngase en contacto con el administrador de éxitos del cliente en el <a href="https://helpx.adobe.com/es/marketing-cloud/contact-support.html">servicio de atención al cliente de Adobe</a> y envíe una solicitud para adelantar la fecha de inicio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Soy administrador de Analytics, pero no tengo acceso a Admin Console. ¿Quién puede ayudarme a obtener acceso a Admin Console? </p> </td> 
   <td colname="col2"> <p>Cualquier administrador de sistemas o productos que tenga acceso a Admin Console en su organización podrá proporcionarle acceso. Si no sabe con seguridad qué persona de su organización dispone de privilegios de administrador en la consola, póngase en contacto con el <a href="https://helpx.adobe.com/es/marketing-cloud/contact-support.html">servicio de atención al cliente de Adobe</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Puedo posponer la fecha de inicio de la migración? </p> </td> 
   <td colname="col2"> <p>Sí. Póngase en contacto con el <a href="https://helpx.adobe.com/es/marketing-cloud/contact-support.html">servicio de atención al cliente de Adobe</a>. </p><p>Consulte a continuación una descripción de los cambios en la Administración de usuarios y permisos de Analytics actual en la fecha de inicio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ahora que mi empresa está migrando a Admin Console, ¿dónde puedo crear usuarios y grupos de permisos nuevos antes de la fecha de inicio de la migración? </p> </td> 
   <td colname="col2"> <p>Antes de la fecha de inicio de la migración, puede crear usuarios en Admin Console o en Analytics &gt; Administración de usuarios. </p> <p>Una vez que empiece la migración, solo podrá crear usuarios y grupos de permisos en Admin Console. </p><p>consulte la sección Migración a continuación para obtener más detalles sobre lo que sucede en la fecha de inicio de la migración. </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> ¿Cuándo puedo implementar el inicio de sesión único mediante el uso de Federated ID? </p> </td> 
   <td colname="col2"> <p> Próximamente habrá disponible una herramienta en Admin Console que le permitirá cambiar los tipos de ID de Adobe ID a Federated ID. Durante la migración, no puede migrar usuarios como Federated ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Aspectos a tener en cuenta durante la migración (preguntas frecuentes) {#section-d394524aa6d046d79025bbd7499792bc}

Información importante sobre el proceso de migración y su impacto en la administración de los usuarios actuales.

<table id="table_0E37BB1DEA6143F0B5F4E861FCFA7189"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pregunta </th> 
   <th colname="col2" class="entry"> Respuesta </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>¿Cómo se replican los grupos de permisos en Admin Console? ¿Qué ocurre con mis usuarios? </p> </td> 
   <td colname="col2"> <p>Un grupo de Analytics migrado se conoce como <i>perfil de producto</i> en Admin Console. La configuración de los permisos del grupo original se mantiene en la migración. Sin embargo, los usuarios asignados al grupo no se migran. Si un usuario que pertenece a dicho grupo se migra mediante la herramienta de migración, tal usuario se asigna al perfil de producto. </p> <p>Por ejemplo, el grupo de permisos Operaciones de la Costa Oeste, que otorgaba a sus miembros acceso al Report Builder y Analysis Workspace (con determinados grupos de informes, métricas y dimensiones), se convertirá en un perfil de producto Operaciones de la Costa Oeste. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Puedo delegar la tarea de la migración en otro administrador? </p> </td> 
   <td colname="col2"> <p>Una vez que comience la migración, cualquier administrador que acceda a la instancia de Analytics mediante Experience Cloud puede utilizar la herramienta de migración para empezar (o seguir) con la migración de usuarios. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Puedo actualizar la pertenencia a los grupos de permisos para los usuarios que no se han migrado? </p> </td> 
   <td colname="col2"> <p>Sí. Puede cambiar la pertenencia a los grupos de los usuarios no migrados en la sección Administración de usuarios de Analytics. </p><p>A la espera de una aclaración de Ashok sobre dónde se ha hecho eso. </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Puedo crear usuarios y grupos de permisos en Analytics una vez que empiece la migración y, a continuación, utilizar la herramienta de migración para moverlos a Admin Console? </p> </td> 
   <td colname="col2"> <p> No. Una vez que empiece la migración, los usuarios y grupos de permisos nuevos (denominados perfiles de producto en Admin Console) se deben crear en Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Tendrían los usuarios que yo migre con la herramienta de migración los mismos permisos que tenían asignados en Analytics? </p> </td> 
   <td colname="col2"> <p>Sí. Los usuarios migrados con la herramienta conservarán los permisos que tienen actualmente en Analytics. Además, mantendrán el acceso a los recursos de Analytics (como segmentos, proyectos y métricas calculadas, entre otros) cuando accedan a Analytics mediante Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Siguen teniendo acceso a Analytics los usuarios migrados a Admin Console mediante <span class="filepath">my.omniture.com</span>? </p> </td> 
   <td colname="col2"> <p>Sí. Los usuarios migrados seguirán teniendo acceso a Analytics con el nombre de usuario y la contraseña existentes mediante <span class="filepath">my.omniture.com</span> hasta la fecha de fin de la migración, a menos que desactive el acceso de inicio de sesión heredado a través de la herramienta de migración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dos o más de mis usuarios tienen el mismo ID de correo electrónico en el registro de Analytics. ¿Qué ocurre si los migro? </p> </td> 
   <td colname="col2"> <p>Puesto que las cuentas de usuario de Admin Console requieren ID de correo electrónico exclusivos, aparecerá un error de ID de correo electrónico duplicado al intentar migrar más de uno de estos usuarios. Puede actualizar los ID de correo electrónico de los usuarios no migrados en la sección Administración de usuarios (heredada) antes de volver a intentar realizar la migración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> ¿Qué debo hacer después de migrar los usuarios? </p> </td> 
   <td colname="col2"> <p>Desactive el acceso de inicio de sesión heredado a <span class="filepath">my.omniture.com</span>. No podrá desactivar ningún inicio de sesión heredado hasta que se hayan migrado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Puedo realizar un seguimiento del proceso de migración? </p> </td> 
   <td colname="col2"> <p>La herramienta de migración incluye un panel de control que muestra cuántos usuarios se han migrado correctamente y cuántos de ellos tienen el inicio de sesión heredado desactivado. </p> <p> Idealmente, habrá migrado correctamente la empresa de inicio de sesión a Admin Console cuando el 100 % de los usuarios hayan realizado la migración y tengan los inicios de sesión heredados desactivados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Necesito administrar usuarios y permisos durante la migración. ¿Qué herramienta puedo utilizar para realizar esta tarea? </p> </td> 
   <td colname="col2"> <p>Una vez que comience la migración, podrá utilizar Admin Console para crear y administrar usuarios y perfiles de producto nuevos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Qué experimentan mis usuarios durante la migración con la herramienta? </p> </td> 
   <td colname="col2"> <p>Recibirán un correo electrónico de bienvenida dirigido al ID de correo electrónico del registro de usuario de Analytics, en el que se les notificará la nueva forma de acceder a Analytics a través de Experience Cloud. Si no disponen de un Adobe ID existente, se les solicitará que creen uno para poder acceder a la solución mediante el uso de dicho ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Puedo utilizar API para migrar mis usuarios en lugar de usar la herramienta de migración? </p> </td> 
   <td colname="col2"> <p>No. Debe utilizar la herramienta de migración para asegurarse de que todos los usuarios existentes se migran a Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Qué funciones de administración de usuarios de Analytics no están disponibles en Admin Console? </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">Transferencia de recursos </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">Caducidad de usuarios </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">Registros de usuarios </li> 
    </ul> <p>Estos seguirán estando disponibles en la administración de usuarios de Analytics. </p> <p>Consulte <a href="/help/admin/user-management2/user-migration/c-migration-tool.md">Funciones de Analytics no soportadas en Admin Console</a> para obtener más información. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hemos creado varias configuraciones en Admin Console y las hemos asignado a grupos de permisos de Analytics. ¿Qué pasará con esas configuraciones una vez que empiece la migración? </p> </td> 
   <td colname="col2"> <p>Los grupos de permisos de Analytics se recrean en Admin Console como perfiles de producto, al igual que el resto de los grupos. Esto significa que verá dos perfiles de producto en la consola que, básicamente, tienen permisos duplicados. Puede eliminar los perfiles de producto duplicados de Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Cuál es el siguiente paso después de migrar los usuarios? </p> </td> 
   <td colname="col2"> <p>Una vez que haya migrado un usuario o un conjunto de usuarios, el siguiente paso consiste en desactivar el inicio de sesión heredado de <span class="filepath">my.omniture.com</span>. Para ello, puede seleccionar los usuarios en la herramienta de migración y hacer clic en la opción contextual "Desactivar inicio de sesión heredado" que aparece en la parte superior de la pantalla. Tenga en cuenta que esta opción solo está visible al seleccionar un usuario o conjunto de usuarios que se hayan migrado correctamente a Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Qué ocurre en la fecha de fin de la migración? </p> </td> 
   <td colname="col2"> <p>Una vez pasada la fecha del fin de la migración (60 días desde el inicio de esta), todos los usuarios de la empresa de inicio de sesión se redirigirán al inicio de sesión a través de la página de inicio de sesión de Experience Cloud con sus Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>No he podido migrar todos los usuarios antes de la fecha de fin de la migración. ¿Perderán los usuarios no migrados el acceso a Analytics? </p> </td> 
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
   <td colname="col2"> <p> En Analytics, un usuario eliminado se establece como <span class="term"> ha expirado</span>, pero la cuenta sigue existiendo. Al preservar la cuenta es posible transferir recursos, como, por ejemplo, segmentos, métricas calculadas, informes programados, proyectos, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caducidades de cuenta </p> </td> 
   <td colname="col2"> <p> Puede establecer manualmente una fecha de caducidad de cuenta en Analytics con Herramientas de administración. Una vez cumplida la fecha de caducidad, el usuario no podrá acceder a Analytics, pero su cuenta de usuario de Experience Cloud (por ejemplo, Adobe ID, Enterprise ID, Federated ID, etc.) no caducará. El usuario podrá iniciar sesión en Experience Cloud, pero no podrá hacer clic en Analytics. </p> </td> 
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
   <td colname="col2"> <p> Los administradores que realicen la migración a Admin Console ya no podrán utilizar la función “Iniciar sesión como” para acceder a cuentas de usuario que no son de administración migradas a Admin Console. Esta función se va a dejar de utilizar con Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caducidad de usuarios y transferencia de recursos </p> </td> 
   <td colname="col2"> <p> Admin Console no soporta la caducidad de usuarios ni la transferencia de recursos. Los administradores utilizarán la sección Usuarios y activos de Analytics en Herramientas de administración para aplicar ambas funciones. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Último acceso (último inicio de sesión) </p> </td> 
   <td colname="col2"> <p> Los detalles sobre la fecha y hora del último inicio de sesión de los usuarios estarán disponibles en el vínculo Usuarios y activos de Analytics y no en Admin Console. La fecha del último inicio de sesión en Analytics especifica cuándo accedieron realmente los usuarios a Analytics desde Experience Cloud, pero no refleja la fecha/hora en la que iniciaron sesión en Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://helpx.adobe.com/es/enterprise/using/identity.html">Tipos de identidades compatibles con Adobe</a> de API de administración de usuarios </p> </td> 
   <td colname="col2"> <p> Los administradores que realizan la migración a Admin Console deben configurar las <a href="https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html">API de administración de usuarios</a> incluidas en Adobe I/O para el acceso programático a las cuentas de usuario de Admin Console. </p> <p>Las API de permisos de Analytics se desactivarán cuando se habilite su migración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Credenciales del servicio web </p> </td> 
   <td colname="col2"> <p> Las credenciales del servicio web de los usuarios (y el secreto compartido) no estarán disponibles en Admin Console. Para acceder a ellas, haga clic en el usuario específico en la sección Usuarios y activos de Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inicio de sesión único </p> </td> 
   <td colname="col2"> <p> Las configuraciones de inicio de sesión único de Analytics se eliminarán al terminar la migración. No obstante, permanecerán activas durante la migración. Los clientes que utilizan el inicio de sesión único de Analytics deberían actualizar al <a href="https://helpx.adobe.com/es/enterprise/using/identity.html">Adobe Federated ID</a>. </p> <p>Analytics recomienda migrar los usuarios como Adobe ID en primer lugar para crear fácilmente las cuentas de Experience Cloud y, a continuación, convertir dichas cuentas en usuarios de inicio de sesión federado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Descarga de grupos de permisos </p> </td> 
   <td colname="col2"> <p> La descarga de información de grupos de permisos ya no estará disponible en las herramientas de administración de Analytics ni en Admin Console de Adobe. Los clientes deberían utilizar las API de administración de usuarios de adobe.io para obtener información de grupos de permisos por lotes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Fecha de creación de cuentas </p> </td> 
   <td colname="col2"> <p>La información sobre la fecha de creación de las cuentas ya no está disponible en las herramientas de administración de Analytics ni en Admin Console de Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Correo electrónico masivo </p> </td> 
   <td colname="col2"> <p>El envío de correo electrónico masivo a usuarios ya no estará disponible en Admin Console de Analytics ni de Adobe. Los clientes pueden exportar por lotes las direcciones de correo electrónico de los usuarios de Admin Console de Adobe y enviar un correo electrónico mediante el uso del cliente de correo que deseen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Notificación de la migración a los usuarios {#section-f3b25f672a3a4d03b0559656fd99d20a}

Puede que desee comunicar de forma proactiva el plan de migración a los usuarios actuales. A continuación, tiene una plantilla que puede personalizar para enviarla a todos los usuarios actuales de Analytics:

Para enviar un correo electrónico a todos los usuarios, navegue a **[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Administración de usuarios]** > [Enviar correo electrónico a usuarios](https://docs.adobe.com/help/en/analytics/admin/user-product-management/t-email-users.html).

**Asunto:** Próximamente: nueva forma de iniciar sesión en Adobe Analytics y Adobe Experience Cloud.

**Cuerpo:** Hola, usuarios de Adobe Analytics:

Nuestra empresa empezará a migrar todas las cuentas de Adobe Analytics de [!DNL https://my.omniture.com/login/] a Adobe Experience Cloud ([experiencecloud.adobe.com](http://experiencecloud.adobe.com/)). Con esta migración, su cuenta de Adobe Analytics se actualizará para permitir el acceso a Analytics mediante Adobe Experience Cloud. Aunque el método de acceso a Analytics va a cambiar, se mantendrán los permisos existentes para grupos de informes y herramientas.

**Próximos pasos:** Empezaremos a migrar usuarios el **INSERTAR FECHA**. Recibirá en el ID de correo electrónico que se muestra en su cuenta de Analytics un mensaje de bienvenida con el nuevo inicio de sesión. Si no ha configurado un [Adobe ID](https://helpx.adobe.com/es/x-productkb/global/adobe-id-account-change.html) vinculado a la dirección de correo electrónico, se le solicitará que configure una cuenta.

**Recursos de utilidad:**

[Inicio de sesión y administración de la configuración de perfil](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/getting-started-experience-cloud.html).

Póngase en contacto con los administradores de Analytics en caso de que tenga alguna duda o pregunta.

Saludos,

Administrador de Analytics
