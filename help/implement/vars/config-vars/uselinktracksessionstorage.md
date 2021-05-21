---
title: useLinkTrackSessionStorage
description: Almacene los datos de seguimiento de vínculos en el almacenamiento de la sesión en lugar de en una cookie.
exl-id: 3295195d-bfd6-4af9-9487-dc1ea6c3da23
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '261'
ht-degree: 100%

---

# useLinkTrackSessionStorage

Si su organización utiliza el seguimiento de vínculos, AppMeasurement utiliza la cookie `s_sq` para pasar información entre visitas. Algunas configuraciones de sitio web entran en conflicto con esta cookie. Si desea usar el almacenamiento de sesión del explorador para el seguimiento de vínculos y los datos del Activity Map en lugar de una cookie, habilite esta variable.

El uso del almacenamiento de sesión de un explorador para el seguimiento de vínculos tiene varias limitaciones:

* El almacenamiento de sesión no funciona entre protocolos. Por ejemplo, tiene una página servida a través de HTTP y la siguiente a través de HTTPS. AppMeasurement no puede acceder a los datos de seguimiento de vínculos en el almacenamiento de la sesión debido a las diferencias de protocolo.
* El almacenamiento de sesión no funciona entre subdominios. Por ejemplo, un visitante se desplaza a `store.example.com` y luego, a `toys.example.com`. AppMeasurement no puede acceder a los datos de seguimiento de vínculos en el almacenamiento de la sesión debido a las diferencias de subdominio.

>[!TIP]
>
>La implementación más confiable que utiliza el almacenamiento de sesión para el seguimiento de vínculos entrega todo el contenido a través de HTTPS en un solo subdominio.

AppMeasurement elimina los datos del seguimiento de vínculos de almacenamiento de sesión después de enviar una visita a Adobe. También caduca automáticamente cuando se cierra la pestaña del explorador.

## Uso del almacenamiento de sesión de seguimiento de vínculos en Adobe Experience Platform Launch

No hay un campo específico en Launch para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.useLinkTrackSessionStorage en el editor de código personalizado de AppMeasurement y Launch

La variable `s.useLinkTrackSessionStorage` es un booleano que determina si AppMeasurement utiliza almacenamiento de sesión para los datos de seguimiento de vínculos en lugar de la cookie de `s_sq`. Su valor predeterminado es `false`. Configure esta variable en `true` si desea que AppMeasurement utilice el almacenamiento de sesión en lugar de la cookie `s_sq` para el seguimiento de vínculos y el Activity Map.

```js
s.useLinkTrackSessionStorage = true;
```
