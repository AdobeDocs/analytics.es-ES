---
title: zip
description: Rellene manualmente la dimensión “Código postal” si la configuración del grupo de informes lo permite.
feature: Appmeasurement Implementation
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/dv564yEz9tChaxot0w65ZGIc1T0Jqdnp1Mua0QUbn5Y'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 275
ht-degree: 81%

---

# zip

La variable `zip` permite rellenar manualmente la dimensión “Código postal” si la [!UICONTROL opción Zip] en la configuración del grupo de informes lo permite. En versiones anteriores de Adobe Analytics, esta variable solo se podía establecer de forma manual, generalmente al introducir información de envío en una página de venta minorista. Las mejoras a Adobe Analytics permiten que esta variable se establezca automáticamente mediante los datos de ubicación geográfica. Esta variable no se mantiene más allá de la visita que se ha establecido.

>[!IMPORTANT]
>
>Asegúrese de que la [!UICONTROL opción Zip] de la configuración del grupo de informes está establecida con el valor deseado. No puede usar esta variable si [!UICONTROL Geo zip] siempre se usa. Consulte [Configuración general de la cuenta](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) en la Guía de administración para obtener más información.

## Código postal con Web SDK

El código postal está asignado a las siguientes variables:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.placeContext.geo.postalCode`
* [Objeto de datos](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.zip`

## Código postal con la extensión Adobe Analytics

Puede establecer el código postal al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca la lista desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Zip].

Puede establecer un Código postal para cualquier valor de cadena, incluidos los elementos de datos.

## s.zip en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.zip` es una cadena que generalmente contiene un código postal, pero que puede contener cualquier valor deseado de hasta 50 bytes de longitud.

```js
s.zip = "84043";
```
