---
title: zip
description: Rellene manualmente la dimensión “Código postal” si la configuración del grupo de informes lo permite.
feature: Variables
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 75%

---

# zip

La variable `zip` permite rellenar manualmente la dimensión “Código postal” si la [!UICONTROL opción Zip] en la configuración del grupo de informes lo permite. En versiones anteriores de Adobe Analytics, esta variable solo se podía establecer de forma manual, generalmente al introducir información de envío en una página de venta minorista. Las mejoras a Adobe Analytics permiten que esta variable se establezca automáticamente mediante los datos de ubicación geográfica. Esta variable no se mantiene más allá de la visita que se ha establecido.

>[!IMPORTANT]
>
>Asegúrese de que la [!UICONTROL opción Zip] de la configuración del grupo de informes está establecida con el valor deseado. No puede usar esta variable si [!UICONTROL Geo zip] siempre se usa. Consulte [Configuración general de la cuenta](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) en la Guía de administración para obtener más información.

## Código postal con el SDK web

El código postal está asignado a las siguientes variables:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.placeContext.geo.postalCode`
* [Objeto de datos](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.zip`

## Código postal con la extensión Adobe Analytics

Puede establecer el código postal al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca la lista desplegable [!UICONTROL Extension] en Adobe Analytics y [!UICONTROL Action Type] en [!UICONTROL Set Variables].
6. Busque la sección [!UICONTROL Zip].

Puede establecer un Código postal para cualquier valor de cadena, incluidos los elementos de datos.

## s.zip en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.zip` es una cadena que generalmente contiene un código postal, pero que puede contener cualquier valor deseado de hasta 50 bytes de longitud.

```js
s.zip = "84043";
```
