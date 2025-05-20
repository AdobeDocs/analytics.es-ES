---
description: Administre los usuarios, grupos y productos de Analytics en Adobe Admin Console.
subtopic: Users and groups
title: Administración de usuarios y productos
feature: Admin Tools
exl-id: c0fbbb3a-0011-49d2-89a2-70fce11e0fb2
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: ht
source-wordcount: '254'
ht-degree: 100%

---

# Administración de usuarios y productos (heredados)

Administre los usuarios, grupos y productos de Analytics en Adobe Admin Console.

>[!IMPORTANT]
>
>La administración de usuarios y productos se ha trasladado a [Adobe Admin Console](https://helpx.adobe.com/es/enterprise/using/admin-console.html). Para empezar a administrar los permisos de usuario para los usuarios de Adobe Analytics, consulte [Analytics en Adobe Admin Console](/help/admin/admin-console/home.md).

## Recursos de ayuda para los administradores de Adobe Admin Console {#help}

| Tarea o recurso | Descripción |
| --- | --- |
| Migración de los ID de usuario de Analytics a Adobe Admin Console | Adobe va a ayudar a los administradores de Analytics a migrar los ID de usuario a Adobe Admin Console. Este proceso se realiza en oleadas. Cuando llegue la hora de migrar a los usuarios, Adobe notificará a los administradores de Analytics mediante un correo electrónico con instrucciones. Una herramienta de migración está disponible en [Analytics User Management](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html?lang=es) para simplificar esta tarea.<p>**Importante**: El día de la migración de los usuarios, los grupos de permisos anteriores se copiarán automáticamente en Adobe Admin Console. Ya no podrá invitar a nuevos usuarios ni crear grupos nuevos con las herramientas de administración de Analytics. Revise las preguntas frecuentes y la ayuda de Migración de usuarios de Analytics a Adobe Admin Console para obtener información acerca de cómo prepararse para la migración y las funciones administrativas que se ven afectadas. |
| Inicio de Adobe Admin Console | Cuando haya migrado sus cuentas de usuario, podrá administrar los usuarios y los productos en todas las soluciones desde Adobe Admin Console. Vaya a `https://adminconsole.adobe.com/enterprise/`. Consulte también [Administración de usuarios y productos de Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html?lang=es). |
| Administración de usuarios, permisos y perfiles de productos de Adobe Analytics | Consulte [Analytics en Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=es). |

<!---
## User Management Descriptions {#section_7C19842A3D4249109A9399D4DF18DE75}

The following table describes elements on the [!UICONTROL Users] tab in [!UICONTROL User Management].

<table id="table_6F81D1095EB945D8995FF971B65BA52A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins available</span> </td> 
   <td colname="col2"> The maximum number of user accounts you can create for this company. If necessary, you can contact your Account Representative or Customer Care to increase this number at no charge. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins in use</span> </td> 
   <td colname="col2"> The number of user accounts currently in use for this company. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins Remaining</span> </td> 
   <td colname="col2"> The difference between the user account maximum and the number of existing user accounts. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Add New User</span> </td> 
   <td colname="col2"> <p>Lets you add a user account to the company. This link is available only if the Number of User Logins Remaining is greater than 0. </p> <p>See <a href="/help/admin/user-management2/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Download Report</span> </td> 
   <td colname="col2">Exports the contents of the <span class="wintitle"> Users</span> table to a tab-delimited file. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Login</span> </td> 
   <td colname="col2"> <p>The user name. You can click the user name to edit the user account properties. </p> <p>See <a href="/help/admin/user-management2/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> First Name</span> </td> 
   <td colname="col2"> The user's first (given) name. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Last Name</span> </td> 
   <td colname="col2"> The user's surname (family name). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Title</span> </td> 
   <td colname="col2"> The user's job title. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Admin</span> </td> 
   <td colname="col2"> Specifies if the user account has administrative privileges. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Last Login</span> </td> 
   <td colname="col2"> Displays a timestamp of the last login for this user account. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Create Time</span> </td> 
   <td colname="col2"> Shows the date and time when the login account was created. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Expires</span> </td> 
   <td colname="col2"> Displays the account expiration account, if applicable. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Manage</span> </td> 
   <td colname="col2"> Provides links for user account management. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Edit</span> </td> 
   <td colname="col2"> <p>Edit user account settings. </p> <p>See <a href="/help/admin/user-management2/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Delete</span> </td> 
   <td colname="col2"> Delete the user account. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Transfer</span> </td> 
   <td colname="col2">Assign the privileges (permissions and resource access) of one user account to another. <p>See <a href="/help/admin/user-management2/c-user-management/t-transfer-user-accout-privileges.md"> Transfer user account privileges</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Login as this user</span> </td> 
   <td colname="col2"> <p>Allows admins to impersonate and log in as a non-admin account. Admin accounts cannot be impersonated. </p> </td> 
  </tr> 
 </tbody> 
</table>
-->