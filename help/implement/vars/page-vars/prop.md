---
title: prop
description: Variables personalizadas que puede utilizar en su implementación.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# prop

Las props son variables personalizadas que se pueden utilizar como desee.

> [!TIP] Adobe recomienda utilizar eVars en la mayoría de los casos. En versiones anteriores de Adobe Analytics, las props y las eVars tenían ventajas y desventajas entre sí. Sin embargo, Adobe ha mejorado las eVars hasta donde cumplen casi todos los casos de uso de las props. Consulte [eVars](evar.md) para ver una comparación de características entre estos dos tipos de variables personalizadas.

Si su organización utiliza props, asegúrese de registrar su uso y lógica en el documento [de diseño de la](../../prepare/solution-design.md)solución.

## Props en Adobe Experience Platform Launch

Puede establecer props durante la configuración de la extensión de Analytics (variables globales) o en reglas.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la [!UICONTROL Rules] ficha y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Actions], haga clic en una [!UICONTROL Adobe Analytics - Set Variables] acción existente o en el icono &#39;+&#39;.
5. Establezca el [!UICONTROL Extension] menú desplegable en Adobe Analytics y el valor [!UICONTROL Action Type] en [!UICONTROL Set Variables].
6. Busque la [!UICONTROL Props] sección.

Puede seleccionar una prop para establecer un valor o elemento de datos. También puede copiar el valor de otra variable de Analytics.

## s.prop1 - s.prop75 en el editor de código personalizado AppMeasurement e Launch

Cada variable prop es una cadena que contiene valores personalizados específicos de su organización. Su longitud máxima es de 100 bytes; los valores superiores a 100 bytes se truncan automáticamente cuando se envían a Adobe.

```js
s.prop1 = "Example custom value";
```

## Props de lista

Las props de lista son una configuración aplicada a las props que permite que la variable contenga varios valores en la misma visita. Si esta configuración no está habilitada o si se utiliza un delimitador incorrecto, la variable se trata como un valor único.

### Configurar props de lista

Habilite props de lista en la configuración del grupo de informes. See [Traffic variables](/help/admin/admin/c-traffic-variables/traffic-var.md) in the Admin user guide. Asegúrese de que el delimitador deseado está configurado correctamente. Adobe no proporciona un delimitador predeterminado.

> [!TIP] Los delimitadores comunes que se utilizan en las implementaciones son una coma (`,`), dos puntos (`:`), un punto y coma (`;`) o una barra vertical (`|`). Puede utilizar cualquier delimitador que se adapte mejor a la implementación.

### Configurar props de lista

Una vez configuradas las props de lista en la configuración del grupo de informes con el delimitador deseado, no hay más diferencias de implementación que el uso del delimitador.

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

> [!IMPORTANT] Las props de lista siguen estando sujetas a la longitud máxima de 100 bytes. Las props de lista son más fáciles de alcanzar este límite y se truncan, ya que pueden contener varios valores. Considere utilizar abreviaciones o valores abreviados si puede alcanzar este límite de 100 bytes.

Si establece el mismo valor más de una vez en una prop de lista, en los informes se eliminan las duplicaciones. Analysis Workspace cuenta el número de visitas en las que se ve un valor y no el número de veces que existe un valor en los datos.
