---
description: Instrucciones sobre cómo los administradores pueden activar el acceso a los informes del Data Warehouse para un grupo de usuarios.
seo-description: Instrucciones sobre cómo los administradores pueden activar el acceso a los informes del Data Warehouse para un grupo de usuarios.
seo-title: Añadir un grupo de usuarios del Data Warehouse
solution: Analytics
title: Añadir un grupo de usuarios del Data Warehouse
topic: Data Warehouse
uuid: d 89294 db-caa 3-4044-b 70 d -65 b 512 b 0 dc 1 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Añadir un grupo de usuarios del Data Warehouse

Instrucciones sobre cómo los administradores pueden activar el acceso a los informes del Data Warehouse para un grupo de usuarios.

1. Click **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]**.
1. Click **[!UICONTROL Edit Groups]**.
1. Click **[!UICONTROL Add New User Group]**.
1. In the **[!UICONTROL Define User Group]** section, type a name in the Group Name field. Proporcione la información de grupo siguiente:

   Por ejemplo, `Data Warehouse Access`.
1. Type a description in the **[!UICONTROL Group Description]** field.
1. En la sección **Acceso a grupos de informes**, seleccione los grupos de informes a los que desea que puedan acceder los miembros del grupo.
1. En [!UICONTROL Herramientas]**, habilite[!UICONTROL Todas las herramientas]**.

   Si lo prefiere, haga clic en **[!UICONTROL Personalizar]** y active **[!UICONTROL Informe del Data Warehouse personalizado]**.

1. En [!UICONTROL Asignar inicios de sesión del usuario], agregue los Inicios de sesión del usuario que desee.
1. Click **[!UICONTROL Save Group]**.

   La próxima vez que los usuarios añadidos a este grupo inicien sesión, verán la opción del Data Warehouse incorporada al menú [!UICONTROL Reports &amp; Analytics].

   >[!NOTE]
   >
   >En caso de conflicto de permisos (como un usuario asignado a dos grupos, uno de los cuales deniega el acceso a una función y otro otorga ese mismo acceso), el sistema restringe el permiso. Puede que sea necesario quitar de esos grupos a los usuarios pertenecientes a grupos que denieguen el acceso al Data Warehouse.

>[!MORE_LIKE_THIS]
>
>* [Grupos](/help/admin/user-management2/c-user-groups/groups.md)

