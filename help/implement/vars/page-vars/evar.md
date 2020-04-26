---
title: eVar
description: Variables personalizadas que puede utilizar en su implementación.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# eVar

*Esta página de ayuda describe cómo implementar eVars. Para obtener información sobre cómo funcionan las eVars como dimensiones, consulte[eVars](../../../components/c-variables/dimensionslist/reports-conversion.md)en la guía del usuario Componentes.*

Las eVars son variables personalizadas que se pueden utilizar como desee.

>[!TIP] Adobe recomienda usar eVars en lugar de props en la mayoría de los casos. En versiones anteriores de Adobe Analytics, las props y las eVars tenían ventajas y desventajas entre sí. Sin embargo, Adobe ha mejorado las eVars y ahora sirven para todos los casos prácticos de las props.

Asegúrese de registrar cómo utiliza cada eVar y su lógica en el [documento de diseño de la solución](../../prepare/solution-design.md).

## Configurar eVars en la configuración del grupo de informes

Antes de usar eVars en la implementación, asegúrese de configurar cada eVar en la configuración del grupo de informes. Consulte [Variables de conversión](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) en la guía de administración.

## eVars en Adobe Experience Platform Launch

Puede establecer eVars al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL eVars].

Puede seleccionar una eVar para establecer un valor o elemento de datos. También puede copiar el valor de otra variable de Analytics.

## s.eVar1 - s.eVar250 en el editor de código personalizado de AppMeasurement y Launch

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

Si se especifican más de dos decimales, el contador de eVar redondea a dos decimales. Un contador de eVar no puede contener números negativos.

>[!IMPORTANT] Primero debe configurar las eVars en &#39;Contador&#39; en la Consola de administración antes de utilizar las eVars de contador. Consulte [Variables de conversión](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) en la guía de administración.

## Ventajas exclusivas para props o eVars

En la versión actual de Adobe Analytics, las props y las eVars son variables personalizadas con capacidades similares. Sin embargo, tienen varias diferencias importantes:

* Los datos de las props están disponibles en los informes en cuestión de minutos. Las eVars pueden necesitar hasta más de 30 minutos para aparecer en los sistemas de informes.
* Las props tienen un límite de 100 bytes en los informes. Las eVars tienen un límite de 255 bytes.
* Las props pueden convertirse en props de lista, que aceptan varios valores en la misma visita. Las variables de lista son una variable independiente y sólo hay tres variables de lista disponibles.
* De forma predeterminada, las props no persisten más allá de la visita que están configuradas. Las eVars tienen una fecha de caducidad personalizada, lo que permite determinar cuándo una eVar deja de obtener crédito por un evento subsiguiente. Sin embargo, si utiliza el procesamiento [del tiempo de los](../../../components/vrs/vrs-report-time-processing.md)informes, tanto las propiedades como las eVars pueden utilizar un modelo de atribución personalizado.
