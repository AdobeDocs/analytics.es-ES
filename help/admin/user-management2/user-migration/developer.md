---
description: API de listas afectadas por la migración de usuarios
title: API afectadas por la migración de usuarios
uuid: 9a5d43be-e146-476b-961e-49ea0a30b500
translation-type: tm+mt
source-git-commit: f2fe11eeafc7b188ff7a886847b33a82ab80e47a
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 92%

---


# API afectadas por la migración de usuarios{#apis-affected-by-the-migration}

Adobe está migrando todas las empresas de inicio de sesión de Analytics desde [!DNL my.omniture.com] a la autenticación mediante Adobe Experience Cloud. Una vez que la empresa empiece la migración, no se admitirá la creación ni la administración programática de usuarios con los métodos `GetLoginKey` y los permisos específicos de Analytics disponibles mediante las versiones 1.3 y 1.4 de la API de administración de Analytics. Estas acciones ahora se activarán en Experience Cloud mediante [!DNL adobe.io].

## Métodos de API afectados {#section-d19051ac26cc49aeb124f767c4760254}

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

## Acciones que puede realizar {#section-8b0b89a862614f729ebdbe092ce99027}

Si la empresa está utilizando estos métodos, recibirá una notificación previa a la migración a partir del 31 de marzo de 2018. La notificación se enviará, como mínimo, 30 días antes de que la empresa comience la migración a la autenticación de Experience Cloud y, en ese instante, se dejarán de admitir los métodos indicados.

Si la empresa no utiliza ninguno de estos métodos no será necesario realizar ninguna acción, excepto asegurarse de que no comienzan a usarse.

Para obtener información adicional:

* [Información general de administración de usuarios](https://helpx.adobe.com/es/enterprise/help/users.html)
* [API de administración de usuarios mediante adobe.io](https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html)
* [Foro de API de administración de usuarios](https://forums.adobe.com/community/umapi/overview)
* [Migración de acceso y administración de usuarios de Analytics a Experience Cloud](https://docs.adobe.com/content/help/es-ES/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html)

