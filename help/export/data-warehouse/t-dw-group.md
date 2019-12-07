---
description: Instrucciones sobre cómo los administradores pueden activar el acceso a los informes del Data Warehouse para un grupo de usuarios.
title: Añadir un grupo de usuarios del Data Warehouse
topic: Data warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Añadir un grupo de usuarios del Data Warehouse

Instrucciones sobre cómo los administradores pueden activar el acceso a los informes del Data Warehouse para un grupo de usuarios.

1. Haga clic en **[!UICONTROL Analytics]** &gt; **[!UICONTROL Administración]** &gt; **[!UICONTROL Administración de usuario]**.
1. Click **[!UICONTROL Edit Groups]**.
1. Click **[!UICONTROL Add New User Group]**.
1. In the **[!UICONTROL Define User Group]** section, type a name in the Group Name field. Proporcione la información de grupo siguiente:

   Por ejemplo, `Data Warehouse Access`.
1. Type a description in the **[!UICONTROL Group Description]** field.
1. En la sección **Acceso a grupos de informes**, seleccione los grupos de informes a los que desea que puedan acceder los miembros del grupo.
1. En [!UICONTROL Herramientas]**, habilite[!UICONTROL Todas las herramientas]**.

   Si lo prefiere, haga clic en **[!UICONTROL Personalizar]** y active **[!UICONTROL Informe del Data Warehouse personalizado]**.

1. En [!UICONTROL Asignar inicios de sesión del usuario], agregue los Inicios de sesión del usuario que desee.
1. Haga clic en **[!UICONTROL Guardar grupo]**.

   La próxima vez que los usuarios añadidos a este grupo inicien sesión, verán la opción del Data Warehouse incorporada al menú [!UICONTROL Reports &amp; Analytics].

   >[!NOTE]
   >
   >En caso de conflicto de permisos (como un usuario asignado a dos grupos, uno de los cuales niega el acceso a una función y el otro concede el mismo acceso), el sistema restringirá el permiso. Puede que sea necesario quitar de esos grupos a los usuarios pertenecientes a grupos que denieguen el acceso al Data Warehouse.

>[!MORELIKETHIS]
>
>* [Grupos](/help/admin/user-management2/c-user-groups/groups.md)

