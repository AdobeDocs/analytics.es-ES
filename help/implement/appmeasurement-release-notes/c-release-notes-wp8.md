---
description: 'null'
seo-description: 'null'
seo-title: Windows Phone 8
solution: Analytics,Experience Cloud
subtopic: Notas de la versión
title: Windows Phone 8
topic: Desarrollador e implementación
uuid: 7378969a-d219-42bf-9750-141acc9e4b7d
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Windows Phone 8{#windows-phone}

>[!NOTE]
>
>Para encontrar la versión actual de la biblioteca, active el registro de depuración.

Mobile library [downloads](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) are available on [!DNL Developer Connection].

>[!NOTE]
>
>The [!DNL Windows] Phone 8 SDK is replaced by the [Windows 8.1 Universal App Store](../appmeasurement-release-notes/c-release-notes-winu.md) SDK. Este SDK no se va a desarrollar más.

## Versión 3.0.4 {#section_51A8A53CDFB24F6F9D882E9C30ECDB49}

Fecha de versión: **21 de agosto de 2013**

* Las claves de datos de contexto ahora permiten barras bajas.

## Versión 3.0.5 {#section_DFE58939E33C447FBBF8B04E612A96B5}

Fecha de versión: **22 de mayo de 2013**

* Correcciones de errores y mejoras de rendimiento.

## Versión 3.0.4 {#section_F303B6E5955248CF8BDA6C7CB994BAD5}

Fecha de versión: **18 de abril de 2013**

* Se ha solucionado un problema que, en ocasiones, producía un cálculo incorrecto de la duración de la sesión anterior.

## Versión 3.0.3 {#section_0159586C3EC94865A485A8E586862DF6}

Fecha de versión: **21 de marzo de 2013**

* Se ha solucionado un problema de localización con objetos `DateTime`.

## Versión 3.0.2 {#section_296C375729EA4474BDF3FD6ADD4BEAFB}

Fecha de versión: **26 de febrero de 2013**

* `ADMS_Measurement.visitorID` ahora se rellena previamente con el valor predeterminado.
* Se ha solucionado un error que, algunas veces, causaba respuestas automáticas desde la caché.

## Versión 3.0.1 {#section_5865E881249441ADBB03A9637548650F}

Fecha de versión: **21 de febrero de 2013**

* Ya no es necesario configurar un `offlineThrottleDelay` obsoleto gracias a la optimización de los procesos. La configuración aún existe para preservar la compatibilidad con versiones anteriores, pero ya no tiene ningún efecto.
* `DayOfWeek` se basa ahora en 1, iniciando en domingo para coincidir con los valores recopilados en otras plataformas.
* Se ha solucionado un problema con el almacenamiento sin conexión que a veces hacía que la aplicación se bloquease.

