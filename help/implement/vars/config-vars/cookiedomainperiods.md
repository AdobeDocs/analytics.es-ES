---
title: cookieDomainPeriods
description: Ayudar a AppMeasurement a comprender qué dominio almacenará cookies si su dominio tiene un punto en su sufijo.
feature: Variables
exl-id: c426d6a7-4521-4d50-bb7d-1664920618d8
role: Admin, Developer
source-git-commit: fe33da47c109adacb8162c7165ad4c63bd65c08d
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 43%

---


# cookieDomainPeriods

AppMeasurement determina la ubicación de la cookie mirando el sufijo de dominio y el dominio. Para dominios como `example.com`, AppMeasurement establece cookies en la ubicación correcta. Sin embargo, para otros dominios como `example.co.uk`, AppMeasurement puede establecer cookies por error en `co.uk`. La mayoría de los exploradores rechaza las cookies configuradas en este dominio inválido, lo que provoca problemas con la identificación del visitante.

La variable `cookieDomainPeriods` ayuda a AppMeasurement a determinar dónde se configuran las cookies de Analytics. Para ello, llama a que el sufijo de dominio tenga un punto adicional. Esta variable permite a AppMeasurement dar cabida al período adicional en el sufijo de dominio y configurar cookies en la ubicación correcta.

* Para dominios como `example.com` o `www.example.com`, no es necesario configurar esta variable. Si es necesario, puede establecer esta variable en `"2"`.
* Para dominios como `example.co.uk` o `www.example.co.jp`, establezca esta variable como `"3"`.


>[!IMPORTANT]
>
>No tenga en cuenta los subdominios para esta variable. Por ejemplo, no configure `cookieDomainPeriods` en la URL de ejemplo `store.toys.example.com`. AppMeasurement reconoce de forma predeterminada que las cookies deben almacenarse en `example.com`, incluso en direcciones URL con muchos subdominios.


## Períodos de dominio de cookies, cookies de terceros e identificación de visitantes heredados

Solo cuando se utiliza la identificación de visitante de Adobe Analytics heredada (en lugar del servicio de identidad de Experience Cloud recomendado), la configuración implícita o explícita de `cookieDomainPeriods` Esto puede tener implicaciones en la forma en que se identifican los visitantes, dependiendo de si las cookies de terceros están bloqueadas o no.

La siguiente tabla ilustra cuatro escenarios posibles.

| Escenario | `cookieDomainPeriods` La configuración de es ... | ¿Las cookies de terceros están bloqueadas? | Resultado al utilizar el servicio de identificación de visitantes de Adobe Analytics heredado |
|:---:|---|---|---|
| 1 | <span style="color:green">Correcto</span> | No | Los visitantes se identifican con un `s_vi` cookie, establecida del lado del servidor. |
| 2 | <span style="color:green">Correcto</span> | Sí | Los visitantes se identifican con una reserva `s_fid` cookie, establezca el lado del cliente (dominio de página de origen). |
| 3 | <span style="color:red">Incorrecto</span> | No | Los visitantes se identifican con un identificador de reserva basado en la combinación de agente de usuario y dirección IP. <br/>El AppMeasurement está obligado a establecer cookies como cookies de terceros.<br/> El `s_vi` La cookie se puede establecer cuando `cookieDomainPeriods` no se transmite correctamente. |
| 4 | <span style="color:red">Incorrecto</span> | Sí | Los visitantes se identifican con un identificador de reserva basado en la combinación de agente de usuario y dirección IP.<br/>El AppMeasurement está obligado a establecer cookies como cookies de terceros que están bloqueadas, por lo que no se establecen cookies. |

>[!CAUTION]
>
>Es posible que haya configurado inadvertidamente `cookieDomainPeriods` <span style="color:red">incorrecto</span> (dejándola en su valor predeterminado de `"2"`) al usar dominios como `example.co.uk`. Esta configuración implícita incorrecta indica que está identificando visitantes después de los escenarios 3 o 4.
>
>Configuraciones de la versión de AppMeasurement 2.26.x o posteriores `cookieDomainPeriods` automáticamente con el valor correcto, de modo que solo sean posibles los escenarios 1 o 2. Cuando se actualiza a la versión de AppMeasurement 2.26.x o posterior, mientras se identifican los visitantes de forma incorrecta (escenario 3 o 4), la actualización tiene implicaciones importantes.
>
>* Los identificadores de visitante se están restableciendo y los visitantes aparecerán como nuevos visitantes. No habrá forma de vincular la nueva actividad al identificador de visitante anterior.
>* Las cookies se configuran (por ejemplo, para el seguimiento de vínculos o el Activity Map, por ejemplo.`s_sq` cookie), lo que provoca diferencias repentinas en los informes.
>
>Al configurar correctamente `cookieDomainPeriods` Mejorará la funcionalidad de AppMeasurement y Analytics. Se recomienda comprobar si se ven afectados los cambios resultantes de actualizar la biblioteca de AppMeasurement.
>
> Consulte [Cookies de Analytics](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html?lang=es) para obtener más información sobre los usos del AppMeasurement de cookies.

## Períodos de dominio de cookies mediante el SDK web

El SDK web puede determinar el dominio de almacenamiento de cookies correcto sin esta variable.

## Períodos del dominio de cookies mediante la extensión de Adobe Analytics

Períodos de dominio es un campo en el acordeón de [!UICONTROL Cookies] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
1. Expanda el acordeón de [!UICONTROL Cookies], que muestra el campo [!UICONTROL Períodos de dominio].

Establezca este campo como `3` solo en los dominios que contengan un punto en su sufijo. De lo contrario, este campo se puede dejar en blanco.

## Puntos de dominio de cookies en el AppMeasurement de código y el editor de código personalizado de la extensión de Analytics

Puede configurar las variables `cookieDomainPeriods` en la biblioteca JavaScript de AppMeasurement o en el editor de código personalizado de la extensión de Analytics.

La variable `cookieDomainPeriods` es una cadena que generalmente se define como `"3"`, solo en los dominios que contienen un punto en su sufijo. Su valor predeterminado es `"2"`, que se adapta a la mayoría de los dominios.

```js
// Manually set cookieDomainPeriods for domains with a period in its suffix, such as www.example.co.uk
s.cookieDomainPeriods = "3";

// Detect if a URL has a domain suffix with an extra period, and set s.cookieDomainPeriods automatically
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```
