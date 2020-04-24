---
description: Instrucciones sobre cómo los administradores pueden activar el acceso a los informes de Data Warehouse para un grupo de usuarios.
title: Añadir un grupo de usuarios de Data Warehouse
topic: Data warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Añadir un grupo de usuarios de Data Warehouse

Instrucciones sobre cómo los administradores pueden activar el acceso a los informes de Data Warehouse para un grupo de usuarios.

1. Haga clic **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]**.
1. Haga clic en **[!UICONTROL Edit Groups]**.
1. Haga clic en **[!UICONTROL Add New User Group]**.
1. In the **[!UICONTROL Define User Group]** section, type a name in the Group Name field. Proporcione la información de grupo siguiente:

   Por ejemplo: `Data Warehouse Access`.
1. Escriba una descripción en el **[!UICONTROL Group Description]** campo.
1. In the **[!UICONTROL Report Suite Access]** section, select the report suites that you want group members to be able to access.
1. En [!UICONTROL Tools], active **[!UICONTROL All Tools]**.

   Como alternativa, haga clic en **[!UICONTROL Customize]** y, a continuación, habilite **[!UICONTROL Custom Data Warehouse Report]**.

1. En [!UICONTROL Assign User Logins], agregue los inicios de sesión de usuario deseados.
1. Haga clic en **[!UICONTROL Save Group]**.

   La próxima vez que los usuarios añadidos a este grupo inicien sesión, verán la opción de Data Warehouse incorporada al menú [!UICONTROL Reports & Analytics].

   >[!NOTE]
   >
   >Si se detecta algún conflicto en los permisos (como un usuario asignado a dos grupos, si uno de ellos deniega el acceso a una función y el otro lo concede), el sistema restringirá el permiso. Puede que sea necesario quitar de esos grupos a los usuarios pertenecientes a grupos que denieguen el acceso a Data Warehouse.

>[!MORELIKETHIS]
>
>* [Grupos](/help/admin/user-management2/c-user-groups/groups.md)

