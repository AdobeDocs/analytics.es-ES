---
description: 'null'
solution: Analytics,Experience Cloud
subtopic: Release notes
title: Mac OS X
topic: Developer and implementation
uuid: d5e46c86-2d00-4a18-8eee-dcaf082761af
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Mac OS X{#mac-os-x}

>[!IMPORTANT]
>
>Estos SDK han quedado obsoletos y Adobe ya no los admite ni distribuye.

> [!NOTE] Para saber la versión de la biblioteca actual, active los registros de depuración.

Mobile library [downloads](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) are available on [!DNL Developer Connection].

## Versión 3.2.2 {#section_90CCB6A33C5041FA9CBAF6E8B7F3915F}

Fecha de versión: **30 de enero de 2014**

* Se ha resuelto un problema que producía promedios de larga duración de sesión si un dispositivo tenía una configuración de tiempo incorrecta.

## Versión 3.2.1 {#section_0354BDA5B77242058740CE7B6AEF2FEE}

Fecha de versión: **16 de agosto de 2013**

* Optimizado mediante la eliminación de código no utilizado.
* Se ha solucionado un posible bloqueo que se podía producir cuando clearVars se utilizaba en un escenario de subprocesos.

## Versión 3.2 {#section_B85E2904C769461BA8B062AAA0534F9B}

Fecha de versión: **5 de agosto de 2013**

* Se ha agregado compatibilidad con Adobe Audience Manager.
* Los datos del ciclo de vida ahora se enviarán con solicitudes mbox de [!DNL Target].

## Versión 3.1.7 {#section_EC59B76EE3A343D5921E906EB0A8DB49}

Fecha de versión: **23 mayo de 2013**

* Se ha agregado código para evitar que se envíen demasiadas visitas de ciclo de vida a través de notificaciones de ubicación y de Newsstand que inician una aplicación.

## Versión 3.1.6 {#section_DAEB9DDF3A1242CEBF21F4E5AF742D68}

Fecha de versión: **18 de abril de 2013**

* Se ha solucionado un problema que, en ocasiones, producía un cálculo incorrecto de la duración de la sesión anterior.

## Versión 3.1.5 {#section_620AA594868F47619A514AF3C1EAC93B}

Fecha de versión: **21 de marzo de 2013**

* `ADMS_Measurement.visitorID` ahora se rellena previamente con el valor predeterminado.

## Versión 3.1.4 {#section_23E5968C1EC748F7A266D6A5682A1B5F}

Fecha de versión: **febrero de 2013**

Versión inicial. Esta versión se basa en el código de base [!DNL iOS] 3.1.4, de modo que el número de versión inicial se estableció para que coincidiese con [!DNL iOS].
