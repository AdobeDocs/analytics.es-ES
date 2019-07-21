---
description: El Creador de informes de Adobe incluye ahora una configuración de permisos análoga a la de las Herramientas de administración de Analytics.
seo-description: El Creador de informes de Adobe incluye ahora una configuración de permisos análoga a la de las Herramientas de administración de Analytics.
seo-title: Permisos de acceso de usuario para dimensiones y métricas
solution: Analytics
title: Permisos de acceso de usuario para dimensiones y métricas
topic: Creador de informes
uuid: b 561407 d-c 4 fa -4 f 1 e -8 b 16-5 ca 46 fcbf 36 f
translation-type: tm+mt
source-git-commit: d75c58caf1220031fa36483a0ad50ea6f7be7c39

---


# Permisos de acceso de usuario para dimensiones y métricas

El Creador de informes de Adobe incluye ahora una configuración de permisos análoga a la de las Herramientas de administración de Analytics.

Es posible que haya creado libros anteriormente con solicitudes dirigidas a dimensiones y métricas a las que no tiene acceso al no ser administrador. Estos permisos ahora son obligatorios.

Por ejemplo, si actualiza una solicitud que incluye dimensiones o métricas a las cuales no tiene acceso, obtendrá un error de permiso restringido:

![](assets/arb_restrc_perm.png)

Siga estas instrucciones para **cada uno** de los libros del Creador de informes que mantiene:

1. Abra el libro.
1. Actualice todas las solicitudes.
1. Si le aparece un error de permisos de acceso de usuario, haga clic en **[!UICONTROL Abrir archivo CSV]para obtener acceso a la lista de errores de permisos restringidos.**
1. Cree un archivo "AllRestrictedPermissionErrors.xlsx" y copie/pegue la lista de errores de permisos restringidos del archivo CSV en este archivo.
1. Cierre el libro del Creador de informes.

Una vez que haya procesado todos los libros, debe tener una lista completa de errores de permisos restringidos en "AllRestrictedPermissionErrors.xlsx". Envíe esta lista a su administrador de acceso del usuario de Adobe Analytics y solicítele que le conceda acceso a las métricas y dimensiones.
