---
title: trackingServerSecure
description: Dominio utilizado para enviar datos a Adobe a través de HTTPS.
feature: Appmeasurement Implementation
exl-id: d5b112f9-f3f6-43ac-8ee5-d9ad8062e380
role: Admin, Developer
source-git-commit: 7918b18e73618368543a996ca121b64b7afb33ab
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 13%

---

# trackingServerSecure

La variable `trackingServerSecure` determina el dominio que utiliza AppMeasurement para enviar datos a Adobe a través de HTTPS. Si esta variable no se define correctamente, la implementación puede experimentar una pérdida de datos.

Antes del [servicio de identidad de Adobe Experience Cloud](https://experienceleague.adobe.com/es/docs/id-service/using/home), esta variable también determinaba dónde se configuraban las cookies de terceros. Adobe recomienda encarecidamente utilizar el servicio de ID en todas las implementaciones siempre que sea posible.

## Dominio de Edge que utiliza la extensión de Web SDK

Web SDK usa [!UICONTROL dominio de Edge] para administrar tanto el servidor de seguimiento como el servidor de seguimiento seguro. Puede establecer el valor [!UICONTROL dominio de Edge] deseado al configurar la extensión de Web SDK.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Seleccione la propiedad de etiquetas que desee.
1. Vaya a la pestaña [!UICONTROL Extensions] y, a continuación, seleccione el botón **[!UICONTROL Configure]** en [!UICONTROL Adobe Experience Platform Web SDK].
1. Establezca el campo de texto **[!UICONTROL dominio de Edge]** deseado.

Consulte [Configurar la extensión de Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=es) en la documentación de Web SDK para obtener más información.

>[!TIP]
>
>Si su organización se desplaza a Web SDK desde una implementación de extensión de AppMeasurement o Analytics, este campo puede utilizar el mismo valor contenido en `trackingServerSecure` (o `trackingServer`).

## Dominio de Edge que implementa manualmente Web SDK

Configure SDK usando [`edgeDomain`](https://experienceleague.adobe.com/es/docs/experience-platform/web-sdk/commands/configure/edgedomain). El campo es una cadena que determina el dominio al que se envían los datos.

```json
alloy("configure", {
  "edgeDomain": "data.example.com"
});
```

## Servidor de seguimiento SSL con la extensión de Adobe Analytics

[!UICONTROL El servidor de seguimiento SSL] es un campo del acordeón [!UICONTROL General] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Seleccione la propiedad de etiquetas que desee.
1. Vaya a la pestaña [!UICONTROL Extensions] y, a continuación, seleccione el botón **[!UICONTROL Configure]** en Adobe Analytics.
1. Expanda el acordeón [!UICONTROL General], que muestra el campo [!UICONTROL Servidor de seguimiento SSL].

Si este campo se deja en blanco, el valor predeterminado es [!UICONTROL Servidor de seguimiento]. Si tanto [!UICONTROL Servidor de seguimiento SSL] como [!UICONTROL Servidor de seguimiento] están en blanco, el valor predeterminado es `[rsid].data.adobedc.net`.

## s.trackingServerSecure en AppMeasurement y el editor de código personalizado de la extensión de Analytics

La variable `s.trackingServerSecure` es una cadena que contiene el dominio para enviar datos a Adobe. Es solo de dominio; omita el protocolo, la ruta, el puerto y las barras diagonales. Si esta variable está en blanco, utiliza el valor de la variable `s.trackingServer`. Si tanto `s.trackingServerSecure` como `s.trackingServer` están en blanco, el valor predeterminado es `[rsid].2o7.net`.

```js
// Example value when participating in the Adobe-managed certificate program
s.trackingServerSecure = "data.example.com";

// Example value sending data directly to Adobe
s.trackingServerSecure = "example.data.adobedc.net";
```

## Consideraciones que determinan el valor de `trackingServerSecure`

El valor que use para `trackingServerSecure` (o `edgeDomain`) depende de varios factores:

* Su participación en el [programa de certificados administrados por Adobe](https://experienceleague.adobe.com/es/docs/core-services/interface/data-collection/adobe-managed-cert)
* Si tiene implementado y configurado correctamente el [servicio de identidad de Adobe Experience Cloud](https://experienceleague.adobe.com/es/docs/id-service/using/home)

**Si su organización participa en el programa de certificados administrado por Adobe**, establezca el valor en el dominio de origen seleccionado al configurar el certificado. Normalmente, este valor es un subdominio propiedad de su organización. Por ejemplo, `data.example.com`. Los registros CNAME de su organización redirigen esos datos a Adobe.

**Si no participa en el programa de certificación**, establezca el valor en un subdominio de `data.adobedc.net`. Adobe recomienda utilizar el ID de empresa de su organización para mantener la coherencia. Por ejemplo, `example.data.adobedc.net`. Siga estos pasos para determinar el ID de empresa:

1. Inicie sesión en [experience.adobe.com](https://experience.adobe.com) con sus credenciales de Adobe ID.
1. En cualquier lugar de la interfaz de Experience Cloud, presione `[Cmd]` + `[I]` (iOS) o `[Ctrl]` + `[I]` (Windows).
1. Aparece un **[!UICONTROL depurador de datos de usuario]**. Seleccione la ficha **[!UICONTROL Organizaciones asignadas]**.
1. Expanda la organización IMS deseada.
1. Busque el campo **[!UICONTROL Inquilino]**. Este valor es el subdominio recomendado de `data.adobedc.net` para usar.

>[!NOTE]
>
>No utilice subdominios más profundos que `example.data.adobedc.net`. Por ejemplo, `custom.example.data.adobedc.net` no es un servidor de seguimiento válido.

Las implementaciones más antiguas pueden tener valores como `sc.omtrdc.net` o `2o7.net`. Estos se utilizaban principalmente en versiones anteriores de Adobe Analytics y siguen siendo válidos.

Adobe recomienda encarecidamente mantener esta información en [documento de diseño de la solución](../../prepare/solution-design.md) para mantener la coherencia en toda su organización.

## Ramificaciones por no utilizar el servicio de ID de visitante

Adobe recomienda encarecidamente usar el [servicio de identidad de Adobe Experience Cloud](https://experienceleague.adobe.com/es/docs/id-service/using/home) en todas las implementaciones. El servicio de ID se puede implementar de varias formas diferentes:

* Las implementaciones manuales de AppMeasurement utilizan `VisitorAPI.js` y llaman al método `getInstance`. Consulte [Implementar el servicio de identidad de Experience Cloud para Analytics](https://experienceleague.adobe.com/es/docs/id-service/using/implementation/setup-analytics) para obtener más información.
* Las implementaciones que usan la extensión de etiquetas de Adobe Analytics usan la [extensión de etiqueta de servicio Adobe Experience Cloud ID](https://experienceleague.adobe.com/es/docs/experience-platform/tags/extensions/client/id-service/overview). Una vez añadida, no se requiere ninguna configuración adicional.
* Las implementaciones que utilizan cualquier formulario de Web SDK (`alloy.js` o la extensión de etiquetas de Web SDK) ya tienen el servicio de ID habilitado de forma nativa. No se requiere ninguna configuración aparte de establecer el valor `edgeDomain`.

**Si su implementación no utiliza el servicio de identidad**, tenga en cuenta los siguientes impactos en su implementación:

* Si no utiliza el servicio de identidad, `trackingServerSecure` determina la ubicación de la cookie. La configuración de esta variable en un dominio de terceros obliga a AppMeasurement a utilizar una cookie de reserva, ya que la mayoría de los exploradores modernos rechazan las cookies de terceros.
* El seguimiento de vínculos internos y Activity Map pueden ser menos fiables.
