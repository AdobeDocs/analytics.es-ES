---
description: Instrucciones sobre cómo los administradores pueden activar el acceso a los informes de Data Warehouse para un grupo de usuarios.
title: Añadir un grupo de usuarios de Data Warehouse
feature: Data Warehouse
uuid: d89294db-caa3-4044-b70d-65b512b0dc1c
exl-id: 8737ab60-2ad1-4795-808b-d0200078a333
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 100%

---

# Añadir un grupo de usuarios de Data Warehouse

Instrucciones sobre cómo los administradores pueden activar el acceso a los informes de Data Warehouse para un grupo de usuarios.

1. Haga clic en **[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Administración de usuarios]**.
1. Haga clic en **[!UICONTROL Editar grupos]**.
1. Haga clic en **[!UICONTROL Agregar nuevo grupo de usuarios]**.
1. En la sección **[!UICONTROL Definir grupo de usuarios]**, escriba un nombre en el campo Nombre del grupo. Proporcione la información de grupo siguiente:

   Por ejemplo: `Data Warehouse Access`.
1. Escriba una descripción en el campo **[!UICONTROL Descripción del grupo.]**
1. En la sección **[!UICONTROL Acceso al grupo de informes]**, seleccione los grupos de informes a los que deben tener acceso los miembros del grupo.
1. En [!UICONTROL Herramientas], habilite **[!UICONTROL Todas las herramientas]**.

   Si lo prefiere, haga clic en **[!UICONTROL Personalizar]** y active **[!UICONTROL Informe de Data Warehouse personalizado]**.

1. En [!UICONTROL Asignar inicios de sesión del usuario], agregue los Inicios de sesión del usuario que desee.
1. Haga clic en **[!UICONTROL Guardar grupo]**.

   La próxima vez que los usuarios añadidos a este grupo inicien sesión, verán la opción de Data Warehouse incorporada al menú [!UICONTROL Reports &amp; Analytics].

   >[!NOTE]
   >
   >Si se detecta algún conflicto en los permisos (como un usuario asignado a dos grupos, si uno de ellos deniega el acceso a una función y el otro lo concede), el sistema restringirá el permiso. Puede que sea necesario quitar de esos grupos a los usuarios pertenecientes a grupos que denieguen el acceso a Data Warehouse.

>[!MORELIKETHIS]
>
>* [Grupos](/help/admin/user-management2/c-user-groups/groups.md)

