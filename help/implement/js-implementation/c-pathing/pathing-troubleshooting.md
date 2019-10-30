---
description: Lista de motivos por los que la información de control de rutas podría no registrarse y mostrarse en los informes.
keywords: Implementación de Analytics
seo-description: Lista de motivos por los que la información de control de rutas podría no registrarse y mostrarse en los informes.
seo-title: Motivos por el que el control de rutas podría no registrarse
solution: Analytics
title: Motivos por el que el control de rutas podría no registrarse
topic: Desarrollador e implementación
uuid: 9985b7f7-75ea-4c94-97a3-520f92630989
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Motivos por el que el control de rutas podría no registrarse

Lista de motivos por los que la información de control de rutas podría no registrarse y mostrarse en los informes.

* No se ha habilitado el control de rutas para esa prop en ese grupo de informes. Se habilita para cada grupo de informes específico.
* No se están pasando datos a la prop correcta.
* El control de rutas está habilitado y hay datos en la prop, pero no aparecen en los informes. Aunque los datos de [!UICONTROL sprop] pueden aparecer en 10 minutos, los datos de control de rutas no se mostrarán hasta que la sesión del visitante finalice. Termina después de 30 minutos de inactividad. Después, Analytics tarda otros 10 minutos en terminar el procesamiento de los datos de rutas para la presentación final en los informes.

Si ha comprobado todo esto y los datos siguen sin aparecer, consulte con el Servicio de atención al cliente para continuar la depuración.
