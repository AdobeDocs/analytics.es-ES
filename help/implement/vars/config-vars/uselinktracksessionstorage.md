---
title: useLinkTrackSessionStorage
description: Almacene los datos de seguimiento de vínculos en el almacenamiento de la sesión en lugar de en una cookie.
feature: Appmeasurement Implementation
exl-id: 3295195d-bfd6-4af9-9487-dc1ea6c3da23
role: Admin, Developer
TQID: https://experienceleague.adobe.com/n2TiWJuwct2fSZ3gz8UOhX9w--yXZ35yLrxQItVOXfk
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 283
ht-degree: 86%

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

## Uso del almacenamiento de sesión de seguimiento de vínculos mediante Web SDK

Web SDK no admite esta funcionalidad.

## Uso del almacenamiento de sesión de seguimiento de vínculos con la extensión Adobe Analytics

No hay ningún campo dedicado en la extensión de Adobe Analytics para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.useLinkTrackSessionStorage en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.useLinkTrackSessionStorage` es un booleano que determina si AppMeasurement utiliza almacenamiento de sesión para los datos de seguimiento de vínculos en lugar de la cookie de `s_sq`. Su valor predeterminado es `false`. Configure esta variable en `true` si desea que AppMeasurement utilice el almacenamiento de sesión en lugar de la cookie `s_sq` para el seguimiento de vínculos y el Activity Map.

```js
s.useLinkTrackSessionStorage = true;
```
