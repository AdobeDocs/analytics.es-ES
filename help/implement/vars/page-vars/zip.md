---
title: zip
description: Rellene manualmente la dimensión “Código postal” si la configuración del grupo de informes lo permite.
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '243'
ht-degree: 100%

---

# zip

La variable `zip` permite rellenar manualmente la dimensión “Código postal” si la [!UICONTROL opción Zip] en la configuración del grupo de informes lo permite. En versiones anteriores de Adobe Analytics, esta variable solo se podía establecer de forma manual, generalmente al introducir información de envío en una página de venta minorista. Las mejoras a Adobe Analytics permiten que esta variable se establezca automáticamente mediante los datos de ubicación geográfica. Esta variable no se mantiene más allá de la visita que se ha establecido.

>[!IMPORTANT]
>
>Asegúrese de que la [!UICONTROL opción Zip] de la configuración del grupo de informes está establecida con el valor deseado. No puede utilizar esta variable si siempre se utiliza [!UICONTROL geo zip]. Consulte [Configuración general de la cuenta](/help/admin/admin/general-acct-settings-admin.md) en la Guía de administración para obtener más información.

## Código postal en Adobe Experience Platform Launch

Puede establecer el código postal al configurar la extensión Analytics (variables globales) o en reglas.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Zip].

Puede establecer un Código postal para cualquier valor de cadena, incluidos los elementos de datos.

## s.zip en AppMeasurement y el editor de código personalizado de Launch

La variable `s.zip` es una cadena que generalmente contiene un código postal, pero que puede contener cualquier valor deseado de hasta 50 bytes de longitud.

```js
s.zip = "84043";
```
