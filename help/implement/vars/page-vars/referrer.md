---
title: referrer
description: Omisión del referente registrado automáticamente para una visita.
feature: Appmeasurement Implementation
exl-id: 09a76de9-0689-424a-aead-3fdff1709fd9
role: Admin, Developer
TQID: https://experienceleague.adobe.com/YsYfgjFNDiJoQbvPU-XoB6bQt2IAriP1qmkOqc2lFDk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 85%

---

# referrer

La variable `referrer` omite el referente registrado automáticamente en los informes. Esta variable es útil en situaciones en las que el referente podría perderse, como, por ejemplo, durante redirecciones o reenvíos temporales del visitante a un procesador de pagos. Esta variable ayuda a rellenar las dimensiones “Referente” y “Dominio de referencia”.

## Referente mediante Web SDK

El referente se asigna a las siguientes variables:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webReferrer.URL`
* [Objeto de datos](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.referrer`

Web SDK incluye automáticamente `web.webReferrer.URL` en cada evento enviado, si está disponible.

## Referente con la extensión de Adobe Analytics

Puede establecer el referente al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca la lista desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Referente].

Puede establecer el referente en cualquier valor de cadena, incluidos los elementos de datos.

## s.referrer en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.referrer` es una cadena que contiene la dirección URL de la página anterior. Esta variable puede almacenar un máximo de 255 bytes. Los valores mayores a 255 bytes se truncan. AppMeasurement establece automáticamente esta variable en `document.referrer`. No es necesario configurar esta variable a menos que desee anular el valor registrado automáticamente.

```js
s.referrer = "https://example.com";
```

Si utiliza la `digitalData` [capa de datos](../../prepare/data-layer.md):

```js
s.referrer = digitalData.page.pageInfo.referringURL;
```

>[!CAUTION]
>
>Evite establecer esta variable en valores que no sean URL. No elimine el protocolo de la dirección URL.

## Ejemplo

Muchas empresas se ocupan de las implementaciones en torno a las redirecciones. Puede aprovechar la utilidad [`Util.getQueryParam()`](../functions/util-getqueryparam.md) para obtener el referente de la dirección URL si el sitio lo aloja. Compruebe que la dirección URL codifique los valores incluidos en la cadena de consulta.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
