---
description: Enumera las API afectadas por la migración de usuarios
title: API afectadas por la migración de usuarios
feature: Admin Tools
exl-id: 82d0a1cd-1e25-4157-9bb9-bba1049fdc48
role: Admin, Developer
source-git-commit: b90356050a6ff39e1688a10f6aa0af284284e2a6
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 100%

---

# API afectadas por la migración de usuarios{#apis-affected-by-the-migration}

Adobe está migrando todas las empresas de inicio de sesión de Analytics desde [!DNL my.omniture.com] a la autenticación mediante Adobe Experience Cloud. Una vez que la empresa empiece la migración, no se admitirá la creación ni la administración programática de usuarios con los métodos `GetLoginKey` y los permisos específicos de Analytics disponibles mediante las versiones 1.3 y 1.4 de la API de administración de Analytics. Estas acciones ahora se activarán en Experience Cloud mediante [!DNL adobe.io].

## Métodos de API afectados {#methods}

Los métodos siguientes en las versiones 1.3 y 1.4 de la API de administración dejarán de admitirse una vez que empiece la migración de usuarios.

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

Si la empresa está utilizando estos métodos, recibirá una notificación previa a la migración a partir del 31 de marzo de 2018. La notificación se enviará, como mínimo, 30 días antes de que la empresa comience la migración a la autenticación de Experience Cloud y, en ese instante, se dejarán de admitir los métodos indicados.

Si la empresa no utiliza ninguno de estos métodos no será necesario realizar ninguna acción, excepto asegurarse de que no comienzan a usarse.

Para obtener información adicional:

* [Información general de administración de usuarios](https://helpx.adobe.com/es/enterprise/help/users.html)
* [Foro de API de administración de usuarios](https://community.adobe.com/t5/enterprise-teams/bd-p/enterprise-and-teams)
* [Migración de acceso y administración de usuarios de Analytics a Experience Cloud](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html?lang=es)
