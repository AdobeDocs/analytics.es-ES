---
title: eVar
description: Variables personalizadas que puede utilizar en su implementación.
translation-type: tm+mt
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# eVar

Las eVars son variables personalizadas que se pueden utilizar como desee.

> [!TIP] Adobe recomienda usar eVars sobre props en la mayoría de los casos. En versiones anteriores de Adobe Analytics, las props y las eVars tenían ventajas y desventajas entre sí. Sin embargo, Adobe ha mejorado las eVars hasta donde cumplen casi todos los casos de uso de las props.

Asegúrese de registrar cómo utiliza cada eVar y su lógica en el documento [de diseño de la](../../prepare/solution-design.md)solución.

## Configurar eVars en la configuración del grupo de informes

Antes de usar eVars en la implementación, asegúrese de configurar cada eVar en la configuración del grupo de informes. See [Conversion variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin guide.

## eVars en Adobe Experience Platform Launch

Puede establecer eVars al configurar la extensión de Analytics (variables globales) o en reglas.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics - Establecer variables] o haga clic en el icono &#39;+&#39;.
5. Defina el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el tipo [!UICONTROL de] acción en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL eVars] .

Puede seleccionar una eVar para establecer un valor o elemento de datos. También puede copiar el valor de otra variable de Analytics.

## s.eVar1 - s.eVar250 en el editor de código personalizado AppMeasurement e Launch

Cada eVar es una cadena que contiene valores personalizados específicos de su organización. Su longitud máxima es de 255 bytes; los valores superiores a 255 bytes se truncan automáticamente cuando se envían a Adobe.

```js
s.eVar1 = "Example custom value";
```

## eVars de contador

Los valores de eVar generalmente contienen un valor de cadena. Sin embargo, puede configurar las eVars para que contengan un contador. Por ejemplo: desea contar el número de búsquedas internas realizadas antes de una compra. En lugar de establecer un valor de texto, se usaría la siguiente sintaxis:

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

Si se especifican más de dos decimales, el contador de eVar redondea a dos decimales. Un contador eVar no puede contener números negativos.

## Ventajas exclusivas para las props o las eVars

En la versión actual de Adobe Analytics, las props y las eVars son variables personalizadas con capacidades similares. Sin embargo, tienen varias diferencias importantes:

* Los datos de las props están disponibles en los informes en cuestión de minutos. Las eVars pueden tardar hasta 30 minutos en aparecer en los informes.
* Las props tienen un límite de 100 bytes en los informes. Las eVars tienen un límite de 255 bytes.
* Las props pueden convertirse en props de lista, que aceptan varios valores en la misma visita. Las variables de lista son una variable independiente y sólo hay tres variables de lista disponibles.
* De forma predeterminada, las props no persisten más allá de la visita que están configuradas. Las eVars tienen caducidad personalizada, lo que permite determinar cuándo una eVar ya no obtiene crédito por un evento subsiguiente. Si utiliza el procesamiento [del tiempo del](../../../components/vrs/vrs-report-time-processing.md)informe, tanto las props como las eVars pueden utilizar cualquier modelo de atribución que desee.
