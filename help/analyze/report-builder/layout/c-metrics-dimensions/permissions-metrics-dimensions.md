---
description: Report Builder de Adobe incluye ahora una configuración de permisos análoga a la de las Herramientas de administración de Analytics.
title: Permisos de acceso del usuario para dimensiones y métricas
topic: Report builder
uuid: b561407d-c4fa-4f1e-8b16-5ca46fcbf36f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Permisos de acceso del usuario para dimensiones y métricas

Report Builder de Adobe incluye ahora una configuración de permisos análoga a la de las Herramientas de administración de Analytics.

Es posible que haya creado libros anteriormente con solicitudes dirigidas a dimensiones y métricas a las que no tiene acceso al no ser administrador. Estos permisos ahora son obligatorios.

Por ejemplo, si actualiza una solicitud que incluye dimensiones o métricas a las cuales no tiene acceso, obtendrá un error de permiso restringido:

![](assets/arb_restrc_perm.png)

Siga estas instrucciones para **cada uno** de los libros de Report Builder que mantiene:

1. Abra el libro.
1. Actualice todas las solicitudes.
1. If you get prompted with a User Access Permission error, click **[!UICONTROL Open CSV File]** to get access to the list of restricted permissions errors.
1. Cree un archivo “AllRestrictedPermissionErrors.xlsx” y copie/pegue la lista de errores de permisos restringidos del archivo CSV en este archivo.
1. Cierre el libro de Report Builder.

Una vez que haya procesado todos los libros, debe tener una lista completa de errores de permisos restringidos en “AllRestrictedPermissionErrors.xlsx”. Envíe esta lista a su administrador de acceso del usuario de Adobe Analytics y solicítele que le conceda acceso a las métricas y dimensiones.
