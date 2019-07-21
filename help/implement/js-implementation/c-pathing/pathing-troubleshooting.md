---
description: Lista de motivos por los que la información de control de rutas podría no registrarse y mostrarse en los informes.
keywords: Implementación de Analytics
seo-description: Lista de motivos por los que la información de control de rutas podría no registrarse y mostrarse en los informes.
seo-title: Razones por las que las rutas no se pueden registrar
solution: Analytics
title: Razones por las que las rutas no se pueden registrar
topic: Desarrollador e implementación
uuid: 9985 b 7 f 7-75 ea -4 c 94-97 a 3-520 f 92630989
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Razones por las que las rutas no se pueden registrar

Lista de motivos por los que la información de control de rutas podría no registrarse y mostrarse en los informes.

* No se ha habilitado el control de rutas para esa prop en ese grupo de informes. Se habilita para cada grupo de informes específico.
* No se están pasando datos a la prop correcta.
* El control de rutas está habilitado y hay datos en la prop, pero no aparecen en los informes. Aunque los datos de [!UICONTROL sprop] pueden aparecer en 10 minutos, los datos de control de rutas no se mostrarán hasta que la sesión del visitante finalice. Termina después de 30 minutos de inactividad. Después, Analytics tarda otros 10 minutos en terminar el procesamiento de los datos de rutas para la presentación final en los informes.

Si ha comprobado todo esto y los datos siguen sin aparecer, consulte con el Servicio de atención al cliente para continuar la depuración.
