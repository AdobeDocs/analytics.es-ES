---
description: Report Builder de Adobe incluye ahora una configuración de permisos análoga a la de las Herramientas de administración de Analytics.
title: Permisos de acceso del usuario para dimensiones y métricas
uuid: b561407d-c4fa-4f1e-8b16-5ca46fcbf36f
feature: Report Builder
role: User, Admin
exl-id: 53cfdcf4-31c3-40ab-aca4-8f0f9be6fe13
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '228'
ht-degree: 71%

---

# Permisos de acceso del usuario para dimensiones y métricas

Adobe Report Builder presenta una configuración de permisos similar a la de las Herramientas de administración de Analytics.

Es posible que haya creado libros anteriormente con solicitudes dirigidas a dimensiones y métricas a las que no tiene acceso al no ser administrador. Estos permisos ahora son obligatorios.

Por ejemplo, si actualiza una solicitud que incluye dimensiones o métricas a las que no tiene acceso, obtendrá un error de permiso restringido. El mensaje de error indica que una solicitud no está disponible para su cuenta de usuario debido a permisos administrativos.

![Captura de pantalla que muestra el mensaje de error de permisos restringidos.](assets/arb_restrc_perm.png)

Siga estas instrucciones para **cada uno** de los libros de Report Builder que mantiene:

1. Abra el libro.
1. Actualice todas las solicitudes.
1. Si le aparece un error de permisos de acceso de usuario, haga clic en **[!UICONTROL Abrir archivo CSV]** para obtener acceso a la lista de errores de permisos restringidos.
1. Cree un archivo “AllRestrictedPermissionErrors.xlsx” y copie/pegue la lista de errores de permisos restringidos del archivo CSV en este archivo.
1. Cierre el libro de Report Builder.

Una vez que haya procesado todos los libros, debe tener una lista completa de errores de permisos restringidos en “AllRestrictedPermissionErrors.xlsx”. Envíe esta lista a su administrador de acceso del usuario de Adobe Analytics y solicítele que le conceda acceso a las métricas y dimensiones.
