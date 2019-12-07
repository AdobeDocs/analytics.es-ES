---
description: Lista de motivos por los que la información de control de rutas podría no registrarse y mostrarse en los informes.
keywords: Analytics Implementation
title: Motivos por el que el control de rutas podría no registrarse
topic: Developer and implementation
uuid: 9985b7f7-75ea-4c94-97a3-520f92630989
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Motivos por el que el control de rutas podría no registrarse

Lista de motivos por los que la información de control de rutas podría no registrarse y mostrarse en los informes.

* No se ha habilitado el control de rutas para esa prop en ese grupo de informes. Se habilita para cada grupo de informes específico.
* No se están pasando datos a la prop correcta.
* El control de rutas está habilitado y hay datos en la prop, pero no aparecen en los informes. Aunque los datos de [!UICONTROL sprop] pueden aparecer en 10 minutos, los datos de control de rutas no se mostrarán hasta que la sesión del visitante finalice. Termina después de 30 minutos de inactividad. Después, Analytics tarda otros 10 minutos en terminar el procesamiento de los datos de rutas para la presentación final en los informes.

Si ha comprobado todo esto y los datos siguen sin aparecer, consulte con el Servicio de atención al cliente para continuar la depuración.
