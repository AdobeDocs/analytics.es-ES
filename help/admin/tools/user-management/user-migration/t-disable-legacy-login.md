---
description: Obtenga información sobre cómo deshabilitar los inicios de sesión heredados para los usuarios de Analytics.
title: Desactivación de inicios de sesión heredados
feature: Admin Tools
exl-id: 3e619700-722d-429b-94dc-7aa162e114c0
role: Admin
TQID: https://experienceleague.adobe.com/xwLXKuaeoKB5-TSVC7FLQXdUsBEeOg-zuITMa8Z3OIo
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 185
ht-degree: 52%

---

# Desactivación de inicios de sesión heredados

Obtenga información sobre cómo deshabilitar los inicios de sesión heredados para los usuarios de Analytics.

Una vez que los usuarios hayan migrado del sistema de administración de usuarios de Analytics heredado a Adobe Admin Console, podrá desactivar sus inicios de sesión heredados. Deshabilitar los inicios de sesión heredados redirige a los usuarios al inicio de sesión de CX Enterprise si intentan utilizar el inicio de sesión heredado.

1. Abra la herramienta de migración en **[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Migración de ID de usuario]**.
1. En la sección [!DNL User Information], busque el dominio que contiene los usuarios con los que desea trabajar y, a continuación, haga clic en **[!UICONTROL Seleccionar usuarios]**.
1. Seleccione los usuarios con los inicios de sesión heredados que desea desactivar.

   ![](/help/admin/tools/user-management/user-migration/assets/user-info.png)

   Los usuarios elegibles tendrán un estado de *`Migrated`* en la columna Estado de la migración. No puede desactivar el inicio de sesión heredado de un usuario hasta que se haya migrado.
1. Haga clic en **[!UICONTROL Desactivar inicio de sesión heredado]** y, a continuación, haga clic en **[!UICONTROL Listo]**.

   Desactivar inicio de sesión heredado indica cuál de sus usuarios puede continuar utilizando el nombre de usuario y contraseña de [!DNL my.omniture.com] heredados.

   No puede deshabilitar los inicios de sesión heredados para un usuario que aún no se ha migrado. Una vez desactivado, el usuario debe utilizar su Experience Cloud ID para iniciar sesión y acceder a Analytics.
