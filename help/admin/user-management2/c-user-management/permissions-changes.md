---
description: 'null'
keywords: grupos; permisos
seo-description: 'null'
seo-title: Cambios en los permisos de usuario y grupo
solution: Analytics
subtopic: Usuarios y grupos
title: Cambios en los permisos de usuario y grupo
topic: Herramientas de administración
uuid: 94 f 2727 b -17 e 4-4003-a 222-35 c 821 d 6959 e
translation-type: tm+mt
source-git-commit: 0837416ae67936fbf81af2b7051a7ed9f522f5b5

---


# Cambios en los permisos de usuario y grupo

>[!IMPORTANT]
>
>User and product management is moving to the [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Adobe le avisará cuando deba migrar a sus usuarios. After all customers have migrated, help content for **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin Tools]** &gt; **[!UICONTROL User Management]** will be retired.

## ¿Qué ha cambiado?{#section_2C205DE94155441B9E9D3E4C46CCF2EE}

**[!UICONTROL Administración]** &gt; **[!UICONTROL Administración]** de usuarios &gt; **[!UICONTROL Grupos]**

>[!NOTE]
>
>Debido al gran número de combinaciones de permisos posibles, no podemos proporcionar documentación que describa todos los métodos API que se pueden utilizar en cada combinación de permisos. Por lo general, los usuarios no administradores a los que se les otorga acceso a Servicios Web tendrán acceso de solo lectura a los métodos API. Por lo tanto, no tendrán acceso de escritura en los métodos.

Debido a que la API y la interfaz utilizan el mismo sistema para dar permisos, los permisos que un administrador de la interfaz (Adobe Admin Console) haya concedido a un usuario que no es administrador determinado serán los mismos que este tendrá en la API.

<table id="table_D1DB0DE37752450BBCCA44DB760BB505"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Mejora </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p id="reportaccess">Cambios en <span class="uicontrol">Acceso a informes</span> (personalizar grupos) </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Agregar nuevo grupo</span> &gt; <span class="uicontrol">Acceso a informes</span> </p> <p>La sección <span class="wintitle">Acceso a informes</span> en la página <span class="wintitle">Definir grupo de usuarios</span> se ha optimizado para cuatro categorías, lo que permite personalizar permisos a nivel granular. </p> <p><img  src="assets/report-access.png" id="image_CB83E5C7DB4343619421A1FAA61478D0"> </img> </p> <p>Elementos anteriormente en </p> 
    <ul id="ul_16D5EF18D57D4608AEEDEC40D90D8828"> 
     <li id="li_F29E84C6228A464C8807F09205AEAAC6"> <p> <a href="../../../admin/user-management2/c-customize-report-access/groups-analytics-tools.md#concept_C4383A6C0F5E4130875FDD3756F2E2FC" format="dita" scope="local"> Herramientas de Analytics</a>: habilite permisos de usuario para elementos de General (facturación, registros, etc.), Administración de la empresa, Herramientas, Acceso a servicio Web, Report Builder e integración de Data Connectors. </p> <p> <b>Nota</b>: Las configuraciones de empresa de la categoría Personalizar Admin Console se han trasladado a las herramientas de Analytics. </p> </li> 
     <li id="li_A6EB788162A2455E94CE54B9279A854D"> <p> <a href="../../../admin/user-management2/c-customize-report-access/groups-report-suite-tools.md#concept_C94E9864349B428AB9CCE0CA4B0A40FF" format="dita" scope="local"> Herramientas del grupo de informes</a>: habilite permisos de usuario para Servicios Web, Administración de grupos de informes, Herramientas e informes y Elementos de tablero. </p> </li> 
     <li id="li_EDB0255E009B4F1CAFAF53966B41363C"> <p> <a href="../../../admin/user-management2/c-customize-report-access/groups-metrics.md#concept_05D54436430E4320A48C7C685D337FBE" format="dita" scope="local"> Métricas</a>: habilite permisos para tráfico, conversión, eventos personalizados, eventos de soluciones, reconocimiento de contenido, etc. </p> </li> 
     <li id="li_8DAE87D1DEF54803A9C6FE31C01F0FB0"> <p> <a href="../../../admin/user-management2/c-customize-report-access/groups-dimensions.md#concept_68B36161345341369B6D01DC7DD42A22" format="dita" scope="local"> Dimensiones</a>: personalice el acceso de los usuarios a nivel granular con eVars, informes de tráfico, informes de soluciones e informes de rutas. </p> </li> 
    </ul> <p>Por ejemplo, puede crear un grupo con acceso a varias herramientas de Analytics (<span class="wintitle">Analysis Workspace</span>, <span class="wintitle">Reports &amp; Analytics</span> y <span class="wintitle">Report Builder</span>), con permiso para métricas y dimensiones concretas (incluidas eVars) y funciones como la creación de segmentos o métricas calculadas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cambios en los grupos predefinidos </p> </td> 
   <td colname="col2"> <p> <b>Acceso de administrador:</b> los grupos predefinidos ya no son obligatorios para los administradores. Los administradores ahora tienen acceso a todos los elementos (herramientas, dimensiones y métricas), al igual que a Acceso a servicio Web, Report Builder, Activity Map y Ad Hoc Analysis. </p> <p>En adelante, el objetivo de los grupos será conceder acceso a los usuarios que no son administradores, o restringirlo. </p> <p> <b>Grupos personalizados:</b> los grupos personalizados han reemplazado a los grupos predefinidos. Los grupos predefinidos existentes se migrarán a grupos personalizados; el nombre del grupo se mantendrá. Se conservarán los grupos personalizados que se hayan podido crear, incluida su configuración. No obstante, observará que la ubicación de los ajustes de configuración ha cambiado. Por ejemplo, los ajustes de configuración de la empresa (en Admin Console personalizado) están ahora en <a href="../../../admin/user-management2/c-customize-report-access/groups-analytics-tools.md#concept_C4383A6C0F5E4130875FDD3756F2E2FC" format="dita" scope="local"> Personalizar herramientas de Analytics</a>. </p> <p> Users belonging to <span class="term"> All Report Access</span> have been migrated to a custom group with access to: </p> 
    <ul id="ul_696A9243F5FD4AF187352C2F4B1CFDC2"> 
     <li id="li_683A0A3BB7214CFFBC61D5A4CD237F48">Todas las dimensiones </li> 
     <li id="li_D8FDBF6A32224731AB706315DEA0A03E">Todas las métricas </li> 
     <li id="li_65ABE5C95D43444D88E63EE95C9AED05">Todos los grupos de informes </li> 
     <li id="li_7ED1505590144B38B3B9851BAA6BBB49">Permiso de informes de canal </li> 
     <li id="li_F718FE1FCF9A4B05AB933CA3F105F3EC">Permiso de informes de detección de anomalías </li> 
     <li id="li_527BD52007E846FE8B5F71AB3C12F695">Permiso de informes en tiempo real </li> 
     <li id="li_AFFB58C7FB644AC8A85E2D76BA7D51F5">Permiso de acceso a Analysis Workspace </li> 
    </ul> <p>Los administradores pueden eliminar los grupos personalizados y también crear los suyos propios, ya que todos los ajustes de configuración que antes estaban disponibles en grupos predefinidos se pueden personalizar bajo el ajuste <span class="wintitle">Acceso a informes</span>, en <a href="../c-user-groups/groups.md" format="dita" scope="local">Definir grupos de usuarios</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Permisos en el nivel de dimensión </p> </td> 
   <td colname="col2"> <p>Puede personalizar permisos para incluir o excluir el acceso a dimensiones (además del acceso a métricas). </p> 
    <ul id="ul_DA5A54223673474E9151AF979DA50659"> 
     <li id="li_C3E82F7BC07A4F2F83A85D3D511292CC"> <p>Se han migrado automáticamente a las nuevas categorías todas las dimensiones y métricas actuales dentro de grupos personalizados. Si un grupo existente tiene métricas habilitadas, se le asignarán todas las dimensiones que puedan recibir permisos por primera vez (eVars y según el contenido) y métricas de forma predeterminada. </p> </li> 
     <li id="li_CC56F9181CC14AB59318628E72F2E8C9"> Permisos del Importador de clasificaciones (anteriormente, SAINT): el acceso a las clasificaciones viene determinado por el acceso a la <a href="https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html" format="html" scope="external">variable</a> en la cual se basa la clasificación. </li> 
    </ul> <p>See <a href="../../../admin/user-management2/c-customize-report-access/groups-dimensions.md#concept_68B36161345341369B6D01DC7DD42A22" format="dita" scope="local"> Customize Dimension Permissions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Admin Console </p> </td> 
   <td colname="col2"> <p>Solo se recomienda para clientes nuevos o clientes cuyas empresas estén <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/core_services.html" format="html" scope="external">aprovisionadas en Experience Cloud</a>. Se ha planificado la migración de los clientes existentes de <span class="keyword">Analytics</span> al sistema de administración de identidades de <span class="keyword">Experience Cloud</span>. </p> <p>More information is available in <a href="https://helpx.adobe.com/enterprise/using/manage-permissions-and-roles.html" format="html" scope="external"> Manage product permissions in the Admin Console</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Preguntas más frecuentes sobre cambios en permisos {#section_02809EFC95054B40A089E6C6E4FACA13}

Aquí incluimos información importante sobre actualizaciones nuevas y planificadas y cómo afectarán a su entorno administrativo.

<table id="table_1E93F45C66E841E6882FB602509F30A3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pregunta </th> 
   <th colname="col2" class="entry"> Respuesta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1">¿Qué cambios se han producido en los permisos en la versión de <b>julio de 2016</b>? </td> 
   <td colname="col2"> <p> <b>Acceso a todos los grupos de informes</b> </p> <p>A la hora de añadir grupos de informes que incluir en un grupo, puede especificar <span class="uicontrol">Acceso a todos los grupos de informes</span>. Esta opción aplica permisos de grupo a todos los grupos de informes actuales o futuros. </p> <p>Para habilitar esta función, vaya a <span class="uicontrol">Administración de usuarios</span> &gt; <span class="uicontrol">Grupos</span> &gt; <span class="uicontrol">Añadir nuevo grupo de usuarios</span> y seleccione <span class="uicontrol">Acceso a todos los grupos de informes</span>. </p> <p><img placement="break"  src="assets/all-report-suites.png" width="300px" id="image_9E814D412E87484C940F1100D6DE2B0F" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Debería utilizar Admin Console para administrar usuarios o la administración de usuarios de Analytics existente? </p> </td> 
   <td colname="col2"> <p>Los cambios realizados en Analytics &gt; Administración &gt; Administración de usuarios no se reflejan en la Consola de administración. Por lo tanto, solo deben seguir haciendo esto los clientes nuevos que ya utilicen la Consola de administración para la administración de usuarios y grupos. Se ha planificado la migración de la administración de grupos de Analytics existente a Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Qué cambios se realizaron en la versión de <b>octubre de 2016</b> en cuanto a permisos? </p> </td> 
   <td colname="col2"> <p>Se implementaron las siguientes mejoras con respecto a la interfaz de <span class="wintitle">Herramientas de administración</span>: </p> <p> 
     <ul id="ul_2A31E8DC17A94B7FABDBA9C87C3947EF"> 
      <li id="li_AE2ECCA01CC64D30B109BE74379EE474">Permission changes as described in <a href="../../../admin/user-management2/c-user-management/permissions-changes.md#concept_86581595B86B47D5B8F90282FC3E31EF" format="dita" scope="local"> Administrative Changes - Fall 2016</a>. </li> 
      <li id="li_33CB2B6A2E5F45BE97CC5E0983AF280E">Se han eliminado los informes de tráfico obsoletos que ya no estaban en el menú. </li> 
      <li id="li_57234CF27E1D405987DE89312CD62C52">Permisos de clasificaciones: El acceso a las clasificaciones vendrá determinado por el acceso a la variable para la cual es la clasificación. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Tengo que hacer algo para migrar usuarios? </p> </td> 
   <td colname="col2"> <p>No, las migraciones de permisos se producirán de manera transparente. </p> <p> 
     <ul id="ul_654F85286EC04416B3E0BA725EBE10AD"> 
      <li id="li_8050B8941F794103B82A0ADF0930D216">Todos los informes de tráfico actuales en un grupo personalizado se migrarán automáticamente a la nueva categoría de dimensión. </li> 
      <li id="li_B97079DB29A346B98D066F11AB7F94AF">Si un grupo personalizado tiene métricas habilitadas, se le asignarán automáticamente todas las dimensiones que puedan recibir permisos por primera vez (variables eVars y de soluciones). </li> 
      <li id="li_F1219EF490DA473BA15F2B215F2995AE"> A los grupos personalizados que tengan al menos una métrica se les otorgará automáticamente acceso a todas las dimensiones eVars y otras dimensiones según contenido, <b>excepto</b> a las dimensiones de tráfico que acaben de quedar disponibles (antes informes de tráfico). </li> 
      <li id="li_F494CE6144A04A6199CFBBA1D7BEA32B">Cada grupo predefinido cambiará a un permiso. Estos nuevos permisos se agregarán a una nueva categoría <span class="uicontrol">Herramientas de Analytics</span>. </li> 
      <li id="li_2FCD9254FC3C4FD7871EEF9453E5CE1E">A cada uno de los grupos personalizados con métricas se le añadirán todos los eventos de soluciones de Analytics que se agreguen como métricas nuevas. </li> 
      <li id="li_34C4560769B64F28A4E83BAE71065DCC">Todos los usuarios que antes estaban en Acceso a todos los informes se agregarán al nuevo grupo personalizado. Acceso a todos los informes dejará de existir. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>¿Qué no va a cambiar? </p> </td> 
   <td colname="col2"> <p>Seguirán sin poderse asignar permisos a los atributos de visitantes. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Referencia rápida para permisos {#section_A3FDD8259F524B21A5489833533D1B28}

En la tabla siguiente se muestran distintas tareas y dónde pueden llevarse a cabo (dependiendo del estado de la empresa).

>[!NOTE]
>
>A *`migrated user`* and *`Experience Cloud user`* refer to users who have accepted an email invitation to join the Experience Cloud. Si no se acepta la invitación por correo electrónico, los usuarios seguirán siendo usuarios de Analytics y no pueden administrarse en Admin Console. (Una excepción es cuando se produce la migración mediante [un Federated ID o un Enterprise ID](https://helpx.adobe.com/enterprise/using/set-up-identity.html). En este caso, el usuario se migra cuando el administrador migra a los usuarios uno a uno).

<table id="table_B68FD00FC5D24823A86BB69558C0327C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tarea </th> 
   <th colname="col2" class="entry"> Empresa de inicio de sesión sin haber migrado </th> 
   <th colname="col3" class="entry"> Empresa en proceso de migración </th> 
   <th colname="col4" class="entry"> Empresa de inicio de sesión después de completar su migración </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Crear un usuario </td> 
   <td colname="col2"> <p>Admin Console (creating a user and adding him or her to an Analytics <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html" format="html" scope="external"> product configuration</a> also creates the user account in Analytics). </p> <p> <a href="../../../admin/user-management2/c-user-management/t-add-user-account.md#task_60F86F36CB86446699EA7C7E5FB03EA7" format="dita" scope="local"> Herramientas de administración</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://adminconsole.adobe.com/enterprise/" format="http" scope="external"> Consola de administración</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://adminconsole.adobe.com/enterprise/" format="http" scope="external"> Consola de administración</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Editar un usuario </td> 
   <td colname="col2"> <p> <a href="../../../admin/user-management2/c-user-management/t-add-user-account.md#task_60F86F36CB86446699EA7C7E5FB03EA7" format="dita" scope="local"> Herramientas de administración</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://adminconsole.adobe.com/enterprise/" format="http" scope="external"> Consola de administración</a> </p> <p> Herramientas de administración: la edición en las herramientas de administración para usuarios migrados se limita a la administración de claves de API y a eliminar o transferir recursos. </p> </td> 
   <td colname="col4"> <p> <a href="https://adminconsole.adobe.com/enterprise/" format="http" scope="external"> Consola de administración</a> </p> <p> Herramientas de administración: la edición se limita a la administración de claves de API y a eliminar y transferir recursos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eliminar un usuario </td> 
   <td colname="col2"> <p>Consola de administración: para usuarios de Experience Cloud </p> <p>Herramientas de administración: para todos los usuarios, pero para los usuarios de Experience Cloud solo elimina el usuario de Analytics asignado, no la cuenta de Experience Cloud. </p> </td> 
   <td colname="col3"> <p>Consola de administración: para usuarios migrados. </p> <p>Herramientas de administración: para usuarios solo de Analytics. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> <p> Herramientas de administración: tras eliminar un usuario de Experience Cloud o desvincular su cuenta en Admin Console, puede eliminar el inicio de sesión de Analytics desde las herramientas de administración. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Iniciar sesión en Analytics </td> 
   <td colname="col2"> <p> <b>Experience Cloud: </b> <span class="filepath"> marketing.adobe.com</span>. Solo disponible para usuarios de Experience Cloud. </p> <p> <b>Analytics (heredado):</b> <span class="filepath">sc.omniture.com</span>. Para usuarios solo de Analytics y para usuarios de Experience Cloud con sus credenciales de Analytics </p> </td> 
   <td colname="col3"> <p> <span class="filepath">marketing.adobe.com</span>: solo disponible para usuarios de Experience Cloud. </p> <p> <span class="filepath"> sc.omniture.com</span>: para usuarios solo de Analytics y para usuarios de Experience Cloud con sus credenciales de Analytics. </p> <p>Durante el proceso de migración, los administradores pueden deshabilitar la capacidad de inicio de sesión en <span class="filepath">omniture.com</span> para usuarios concretos. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Crear un grupo </td> 
   <td colname="col2"> <p>Consola de administración: cuando se crea un grupo en la Consola de administración, un grupo asignado en Analytics aparecerá en las Herramientas de administración, pero este grupo asignado no puede cambiar su nombre de las Herramientas de administración, ni se puede eliminar de las Herramientas de administración. </p> <p>Herramientas de administración. </p> </td> 
   <td colname="col3"> <p>Admin Console (<a href="https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html" format="html" scope="external"> create product configuration</a>) </p> </td> 
   <td colname="col4"> <p>Admin Console (<a href="https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html" format="html" scope="external"> create product configuration</a>) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Editar usuarios en un grupo </td> 
   <td colname="col2"> <p>Consola de administración: Solo para usuarios de Experience Cloud </p> <p>Herramientas de administración: desde las herramientas de administración se puede editar la pertenencia de los usuarios solo de Analytics y de los usuarios de Experience Cloud a grupos. Sin embargo, si un usuario de Experience Cloud forma parte de un grupo en la Consola de administración, no se puede eliminar del grupo en Herramientas de administración. </p> </td> 
   <td colname="col3"> <p>Consola de administración: solo usuarios de Experience Cloud </p> <p> Herramientas de administración: en las herramientas de administración se siguen pudiendo agregar o eliminar de los grupos los inicios de sesión solo en Analytics. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Editar permisos para un grupo </td> 
   <td colname="col2"> <p>Consola de administración: Puede editar grupos creados en Admin Console. </p> <p>Herramientas de administración: puede editar permisos para cualquier grupo. </p> </td> 
   <td colname="col3"> <p>Consola de administración </p> </td> 
   <td colname="col4"> <p>Consola de administración </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eliminar un grupo </td> 
   <td colname="col2"> <p>Consola de administración: Solo puede eliminar grupos creados en Admin Console. </p> <p>Herramientas de administración: puede eliminar solo los grupos creados desde las herramientas de administración. </p> </td> 
   <td colname="col3"> <p>Consola de administración </p> </td> 
   <td colname="col4"> <p>Consola de administración </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cambiar el estado de administración de un usuario </td> 
   <td colname="col2"> <p>Admin Console: solo para usuarios de Experience Cloud. </p> <p>Herramientas de administración </p> </td> 
   <td colname="col3"> <p>Admin Console: solo para usuarios de Experience Cloud. </p> <p>Herramientas de administración: solo para usuarios de Analytics. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
 </tbody> 
</table>
