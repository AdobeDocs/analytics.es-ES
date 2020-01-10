---
description: 'null'
solution: Analytics,Experience Cloud
subtopic: Release notes
title: WinRT para Windows 8
topic: Developer and implementation
uuid: cec19d63-114c-4ef6-a55e-db6aad4e948b
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# WinRT para Windows 8{#winrt-for-windows}

>[!NOTE]
>
>Para saber la versión de la biblioteca actual, active los registros de depuración.

Las [descargas](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) de biblioteca móvil están disponibles en [!DNL Developer Connection].

>[!NOTE]
>
>[!DNL WinRT] para el SDK 8 de [!DNL Windows] se ha sustituido con el SDK de [Universal App Store para Windows 8.1](../appmeasurement-release-notes/c-release-notes-winu.md). Este SDK no se va a desarrollar más.

## Versión 4.0 {#section_248BF5A38F1843A5BCF6DBD62A5D3D59}

Fecha de versión: **17 de junio de 2014**

Nueva versión con nuevas funciones, entre las que se incluyen la localización geográfica, el valor de duración, las acciones temporizadas y la compatibilidad con la inclusión.

## Versión 3.1.1 {#section_6E925545B72240BB816DA2333CA93E46}

Fecha de versión: **22 de mayo de 2014**

Correcciones de errores y mejoras de rendimiento.

## Versión 3.1.0 {#section_F9059928B6FE43C99322A0DA35EB85C3}

Fecha de versión: **17 de octubre de 2013**

* [!DNL Windows]Compatibilidad con 8.1

## Versión 3.0.5 {#section_8F163FF1E88142F180091A88C9FD9D12}

Fecha de versión: **18 de abril de 2013**

* Se ha solucionado un problema que, en ocasiones, producía un cálculo incorrecto de la duración de la sesión anterior.

## Versión 3.0.4 {#section_FD242F9BA3D1481090E45998883E4CDD}

Fecha de versión: **21 de marzo de 2013**

* `ADMS_Measurement.visitorID` ahora se rellena previamente con el valor predeterminado.
* Se ha solucionado un problema relacionado con la recuperación de información del dispositivo.

## Versión 3.0.3 {#section_5865E881249441ADBB03A9637548650F}

Fecha de versión: **21 de febrero de 2013**

* Ya no es necesario configurar un `offlineThrottleDelay` obsoleto gracias a la optimización de los procesos. La configuración aún existe para preservar la compatibilidad con versiones anteriores, pero ya no tiene ningún efecto.
* `DayOfWeek` se basa ahora en 1, iniciando en domingo para coincidir con los valores recopilados en otras plataformas.
* Se ha agregado la suscripción automática para los oyentes de los eventos en TrackingHelper.js para racionalizar el seguimiento del ciclo vital.

## Versión 3.0.2 {#section_CCFAE5A29FB14DAD9A9F14FE8EE09B75}

Fecha de versión: **noviembre de 2012**

* La resolución de pantalla ahora se recopila con precisión para plataformas C#, C++ y HTML5/WinJS.
* La clase `ADMS_Churn` es ahora interna. Para realizar prácticas recomendadas en el seguimiento del ciclo de vida de la aplicación, utilice las siguientes llamadas:

   ```
   public void ADMS_Measurement.StartSession(); 
   public void ADMS_Measurement.StopSession();
   ```

* Se ha agregado la variable `public double maxSessionLength` a `ADMS_Measurement` para permitirle establecer una duración máxima de sesión para la sesión del usuario anterior. Si la longitud de sesión registrada supera el máximo, se enviará la duración máxima de sesión. El valor predeterminado de `maxSessionLength` es 3600 (segundos).
* Se ha agregado una variable de configuración de `lifecycleSessionTimeout` que le permite especificar el tiempo, en segundos, que debe pasar entre inicios de la aplicación antes de que el inicio se considere una nueva sesión.
* Se ha agregado una métrica nueva de longitud de la sesión anterior a las métricas del ciclo vital.
* Se ha actualizado TrackingHelper para una mayor claridad.
* Se ha corregido un error en el módulo multimedia.

## Versión 3.0.1 {#section_EA2E5F8550C348BDB948A9236BD35619}

**octubre de 2012**

Versión inicial.
