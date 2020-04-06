---
title: useLinkTrackSessionStorage
description: Almacene los datos de seguimiento de vínculos en el almacenamiento de la sesión en lugar de en una cookie.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# useLinkTrackSessionStorage

Si su organización utiliza el seguimiento de vínculos, AppMeasurement utiliza la `s_sq` cookie para pasar información entre visitas. Algunas configuraciones de sitio web entran en conflicto con esta cookie. Si desea utilizar el almacenamiento de sesión del explorador para el seguimiento de vínculos y los datos del mapa de Actividad en lugar de una cookie, habilite esta variable.

El uso del almacenamiento de sesión de un explorador para el seguimiento de vínculos tiene varias limitaciones:

* El almacenamiento de sesión no funciona entre protocolos. Por ejemplo, tiene una página servida a través de HTTP y la siguiente a través de HTTPS. AppMeasurement no puede acceder a los datos de seguimiento de vínculos en el almacenamiento de la sesión debido a diferencias de protocolo.
* El almacenamiento de sesión no funciona entre subdominios. Por ejemplo, un visitante se desplaza a `store.example.com`y luego se desplaza a `toys.example.com`. AppMeasurement no puede acceder a los datos de seguimiento de vínculos en el almacenamiento de sesión debido a subdominios diferentes.

>[!TIP] La implementación más confiable que utiliza el almacenamiento de sesión para el seguimiento de vínculos sirve todo el contenido a través de HTTPS en un solo subdominio.

AppMeasurement elimina los datos del seguimiento de vínculos de almacenamiento de sesión después de enviar una visita a Adobe. También caduca automáticamente cuando se cierra la ficha del explorador.

## Uso del almacenamiento de sesión de seguimiento de vínculos en Adobe Experience Platform Launch

No hay un campo específico en Launch para utilizar esta variable. Utilice el editor de código personalizado, según la sintaxis de AppMeasurement.

## s.useLinkTrackSessionStorage en AppMeasurement e inicie el editor de código personalizado

La `s.useLinkTrackSessionStorage` variable es un booleano que determina si AppMeasurement utiliza almacenamiento de sesión para los datos de seguimiento de vínculos en lugar de la `s_sq` cookie. Su valor predeterminado es `false`. Configure esta variable en `true` si desea que AppMeasurement utilice el almacenamiento de sesión en lugar de la `s_sq` cookie para el seguimiento de vínculos y el mapa de Actividad.

```js
s.useLinkTrackSessionStorage = true;
```
