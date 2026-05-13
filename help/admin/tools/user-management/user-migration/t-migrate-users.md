---
description: Migre usuarios del sistema de administración de usuarios de Analytics heredado a Admin Console.
title: Migración de cuentas de usuarios de Analytics para Adobe ID
feature: Admin Tools
exl-id: 198367a1-8156-4cc3-af8a-d92c61699eda
role: Admin
TQID: https://experienceleague.adobe.com/bD-qiEI3KbDBNe4aO01-MqzjoZ-OMcGAnd9vnMTBmZs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: d124af73-4061-4b84-9063-ae2b60f2c1f3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 409
ht-degree: 78%

---

# Migración de cuentas de usuarios de Analytics para Adobe ID

Migre usuarios del sistema de administración de usuarios de Analytics heredado a Admin Console.

>[!NOTE]
>
>Si un administrador que no ha iniciado sesión mediante Experience Cloud intenta acceder a la herramienta de migración de ID de usuario, se redirigirá a la página de inicio de sesión de Experience Cloud.

1. Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Migración de ID de usuario]**.

   ![](/help/admin/tools/user-management/user-migration/assets/migration-progress.png)

   La página Migración de ID de usuario tiene dos secciones: *Progreso de la migración* e *Información del usuario*.

## Progreso de migración

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
      <td colname="col2"> <p>Los usuarios aceptaron la invitación. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Inicio de sesión heredado desactivado </p> </td> 
      <td colname="col2"> <p>El inicio de sesión heredado con un ID de empresa está desactivado. Los usuarios ahora accederán a Experience Cloud con su Adobe ID o Enterprise ID. Cuando todos los usuarios hayan llegado a esta fase, habrá completado la migración. </p> <p>En la migración, el inicio de sesión heredado está desactivado. Los usuarios son redirigidos a <span class="filepath"> experiencecloud.adobe.com</span> y deben iniciar sesión con el Adobe ID o Enterprise ID. </p> </td> 
   </tr> 
   </tbody> 
   </table>

## Información del usuario

Información del usuario describe los usuarios de su organización, separados por nombre de dominio.

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
   <td colname="col2"> <p>Los dominios son específicos de los ID de correo electrónico de la base de usuarios actual de Analytics. Un dominio solo lo puede reivindicar una única organización, y son los administradores del sistema los únicos que pueden hacerlo. Para obtener más información, consulte <a href="https://helpx.adobe.com/es/enterprise/help/request-access-to-claimed-domain.html">Solicitar acceso a un dominio reivindicado</a>. </p> </td> 
</tr> 
<tr> 
   <td colname="col1"> <p>Dominio reclamado </p> </td> 
   <td colname="col2"> <p>Si desea migrar usuarios como Enterprise ID o Federated ID, debe ser administrador del sistema y reclamar primero un dominio disponible mediante Adobe Admin Console antes de migrar usuarios. Obtenga más información <a href="https://helpx.adobe.com/es/enterprise/using/identity.html">aquí</a>. </p> <p>Si no desea reclamar dominios para Enterprise ID o Federated ID, omita este paso y migre a los usuarios como Adobe ID. Obtenga más información sobre tipos de ID <a href="https://helpx.adobe.com/es/enterprise/using/identity.html">aquí</a>. </p> </td> 
</tr> 
</tbody> 
</table>

1. Busque el dominio que contiene los ID de usuario que desea migrar y a continuación, en **[!UICONTROL Requiere migración]**, haga clic en **[!UICONTROL Seleccionar usuarios]**.
1. En la página [!DNL Users], seleccione aquellos que desea migrar y, a continuación, haga clic en **[!UICONTROL Migrar]**.

   Al hacer clic en **[!UICONTROL Migrar]**, los usuarios reciben una invitación (migración iniciada) que deben aceptar. Esta acción mueve el ID de usuario a Migración completada. Entonces puede desactivar su acceso heredado a `[!DNL my.omniture.com].`

   ![](/help/admin/tools/user-management/user-migration/assets/user-info.png)

1. Especifique el tipo de ID con el que desea migrar a los usuarios (Adobe ID o Enterprise ID)

   Después de migrar los usuarios, el estado de la columna Estado de la migración pasa de *`Not Initiated`* a *`Migrated`*.

   Si se muestra *`Failed`*, pase el puntero por encima del icono para ver una descripción de la causa del error de migración.
