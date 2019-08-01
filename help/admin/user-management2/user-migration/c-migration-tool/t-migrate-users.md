---
description: Migre usuarios del sistema de administración de usuarios de Analytics heredado a Admin Console.
seo-description: Migre usuarios del sistema de administración de usuarios de Analytics heredado a Admin Console.
seo-title: Migración de cuentas de usuarios de Analytics para Adobe ID
title: Migración de cuentas de usuarios de Analytics para Adobe ID
uuid: 734 e 9 f 14-ef 8 d -44 de -8 ff 3-3 ee 6 dfe 0 a 214
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2fcd72e6c61f8004268e583b934e9cf474e5e44f

---


# Migración de cuentas de usuarios de Analytics para Adobe ID{#migrate-analytics-user-accounts-for-adobe-ids}

Migre usuarios del sistema de administración de usuarios de Analytics heredado a Admin Console.

## Migración de cuentas de usuarios de Analytics para Adobe ID {#task-f3355f3b14a340feae58cfa04c0ba1c9}

Migre usuarios del sistema de administración de usuarios de Analytics heredado a Admin Console.

>[!NOTE]
>
>Si un administrador que no ha iniciado sesión mediante Experience Cloud intenta acceder a la herramienta de migración de ID de usuario, se le redirigirá a la página de inicio de sesión de Experience Cloud.

**Para migrar usuarios de Analytics:**

1. Navegue a **Analytics** &gt; **[!UICONTROL Administración]** &gt; **[!UICONTROL Migración de ID de usuario]**.

   ![](assets/migration-progress.png)

   La página Migración de ID de usuario tiene dos secciones: *Progreso de migración* e *Información de usuario*.

   **Progreso de migración**

<table id="table_F9F1CFF762C745E198CB075A02BA2DDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Fase </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Migraciones completadas </p> </td> 
   <td colname="col2"> <p>Los usuarios han aceptado la invitación. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Inicio de sesión heredado desactivado </p> </td> 
   <td colname="col2"> <p>El inicio de sesión heredado que utiliza un ID de empresa se ha desactivado. Ahora, los usuarios accederán a Experience Cloud mediante el Adobe ID o Enterprise ID. Cuando todos los usuarios hayan llegado a esta fase, habrá completado la migración. </p> <p>En la migración, el inicio de sesión heredado está deshabilitado. Users are redirected to <span class="filepath"> experiencecloud.adobe.com</span> and must log in using the Adobe ID or Enterprise ID. </p> <p>See <a href="../c-migration-tool/t-disable-legacy-login.md#task-c9262e469814473c8a3ff3971c95570b" format="dita" scope="local"> Disable Legacy Logins</a> for more information. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Información de usuario**

Información de usuario muestra a los usuarios de la organización separados por nombre de dominio.

<table id="table_3822E27AF81E4A188562FEB5131548A5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Dominio </p> </td> 
   <td colname="col2"> <p>Los dominios son específicos de los ID de correo electrónico de la base de usuarios de Analytics actual. Un dominio solo lo puede reivindicar una única organización, y son los administradores del sistema los únicos que pueden hacerlo. Para obtener más información, consulte <a href="https://helpx.adobe.com/enterprise/help/request-access-to-claimed-domain.html" format="html" scope="external">Solicitar acceso a un dominio reivindicado</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio reclamado </p> </td> 
   <td colname="col2"> <p>Si desea migrar usuarios como Enterprise ID o Federated ID, debe ser administrador del sistema y reclamar primero un dominio disponible mediante Admin Console. Obtenga más información <a href="https://helpx.adobe.com/enterprise/help/identity.html" format="html" scope="external">aquí</a>. </p> <p>Si no desea reclamar dominios para Enterprise ID o Federated ID, omita este paso y migre a los usuarios como Adobe ID. Obtenga más información sobre tipos de ID <a href="https://helpx.adobe.com/enterprise/help/identity.html" format="html" scope="external">aquí</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Locate the domain containing the user IDs you want to migrate, then, under **[!UICONTROL Requiring Migration]**, click **[!UICONTROL Select Users]**.
1. On the [!DNL Users] page, select the users you want to migrate, then click **[!UICONTROL Migrate]**.

   When you click **[!UICONTROL Migrate]**, users receive an invitation (Migration Initiated) and must accept it. Esta acción mueve el ID de usuario a Migración completada. Entonces puede desactivar su acceso heredado a [!DNL my.omniture.com].

   ![](assets/user-info.png)

1. Especifique el tipo de ID con el que desea migrar a los usuarios ([Adobe ID o Enterprise ID](https://helpx.adobe.com/enterprise/help/identity.html)).

   After migrating users, the status under the column Migration Status changes from *`Not Initiated`* to *`Migrated`*.

   If *`Failed`* displays, hover over the icon for a description about why the migration failed.
