---
description: Enumera las API afectadas por la migración de usuarios
title: API afectadas por la migración de usuarios
feature: Admin Tools
exl-id: 82d0a1cd-1e25-4157-9bb9-bba1049fdc48
role: Admin, Developer
TQID: https://experienceleague.adobe.com/vrfYIoa98hEoUVW17cwOLWTPk-3MIRS2wwLPB-ZB5DA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 232
ht-degree: 44%

---

# API afectadas por la migración de usuarios{#apis-affected-by-the-migration}

Adobe está migrando todas las empresas de inicio de sesión de Analytics desde [!DNL my.omniture.com] a la autenticación mediante Adobe Experience Cloud. Una vez que la empresa empiece la migración, no se admitirá la creación ni la administración programática de usuarios con los métodos `GetLoginKey` y los permisos específicos de Analytics disponibles mediante las versiones 1.3 y 1.4 de la API de administración de Analytics. Estas acciones ahora se habilitarán en Experience Cloud mediante [!DNL adobe.io].

## Métodos de API afectados {#methods}

Los siguientes métodos de API en las versiones 1.3 y 1.4 de la API de administración ya no serán compatibles una vez que inicie la migración de usuarios:

* Company.GetLoginKey
* Permissions.AddLogin
* Permissions.Authenticate
* Permissions.DeleteGroup
* Permissions.DeleteLogin
* Permissions.GetGroup
* Permissions.GetGroups
* Permissions.GetLogin
* Permissions.GetLogins
* Permissions.GetReportSuiteGroups
* Permissions.RemoveLoginSegment
* Permissions.SaveGroup
* Permissions.SaveLogin
* Permissions.GetLoginSegment

## Acciones que puede realizar {#actions}

Si su empresa utiliza actualmente estos métodos, busque una notificación previa a la migración a partir del 31 de marzo de 2018. La notificación se enviará al menos 30 días antes de que su empresa empiece la migración a la autenticación de Experience Cloud y, en ese momento, estos métodos dejarán de ser compatibles.

Si su empresa no utiliza ninguno de estos métodos, no se requiere ninguna acción aparte de garantizar que no comience a utilizar estos métodos.

Para obtener más información:

* [Información general de administración de usuarios](https://helpx.adobe.com/es/enterprise/help/users.html)
* [Foro de API de administración de usuarios](https://community.adobe.com/t5/enterprise-teams/bd-p/enterprise-and-teams)
* [Migración de la administración y el acceso de los usuarios de Analytics a Experience Cloud](/help/admin/tools/user-management/user-migration/c-migration-tool.md)
