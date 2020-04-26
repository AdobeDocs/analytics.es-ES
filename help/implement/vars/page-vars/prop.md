---
title: prop
description: Variables personalizadas que puede utilizar en su implementación.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# prop

Las propiedades son variables personalizadas que se pueden utilizar como desee.

>[!TIP] Adobe recomienda utilizar eVars en la mayoría de los casos. En versiones anteriores de Adobe Analytics, las props y las eVars tenían ventajas y desventajas entre sí. Sin embargo, Adobe ha mejorado las eVars y ahora sirven para todos los casos prácticos de las props. Consulte [eVars](evar.md) para ver una comparación de características entre estos dos tipos de variables personalizadas.

Si su organización utiliza propiedades, asegúrese de registrar su uso y lógica en el [documento de diseño de la solución](../../prepare/solution-design.md).

## Propiedades en Adobe Experience Platform Launch

Puede establecer propiedades durante la configuración de la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Props].

Puede seleccionar una propiedad para establecer un valor o elemento de datos. También puede copiar el valor de otra variable de Analytics.

## “s.prop1 - s.prop75” en el editor de código personalizado de AppMeasurement y Launch

Cada variable prop es una cadena que contiene valores personalizados específicos de su organización. Su longitud máxima es de 100 bytes. Los valores superiores a 100 bytes se truncan automáticamente cuando se envían a Adobe.

```js
s.prop1 = "Example custom value";
```

## Props de lista

Las props de lista son una configuración aplicada a las propiedades que permite que la variable incluya varios valores en la misma visita. Si esta configuración no está habilitada o si se utiliza un delimitador incorrecto, la variable se trata como un valor único.

### Configurar props de lista

Habilite props de lista en la configuración del grupo de informes. Consulte [Variables de tráfico](/help/admin/admin/c-traffic-variables/traffic-var.md) en la guía de administración. Asegúrese de que el delimitador deseado está configurado correctamente. Adobe no proporciona un delimitador predeterminado.

>[!TIP] Los delimitadores comunes que se utilizan en las implementaciones son una coma (`,`), dos puntos (`:`), un punto y coma (`;`) o una barra vertical (`|`). Puede utilizar el delimitador que se adapte mejor a la implementación.

### Configurar props de lista

Una vez configuradas las props de lista en la configuración del grupo de informes con el delimitador deseado, no hay más diferencias de implementación que el uso del delimitador.

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

>[!IMPORTANT] Las props de lista siguen estando sujetas a la longitud máxima de 100 bytes. No es raro que las props de lista alcancen este límite, por lo que se truncan, ya que pueden contener varios valores. Utilice abreviaciones o valores abreviados si prevé que se pueda alcanzar este límite de 100 bytes.

Si establece el mismo valor más de una vez en una propiedad de lista, se anula la duplicación en sistema de informes. Espacio de trabajo de Análisis cuenta el número de visitas en las que se ve un valor y no el número de veces que existe un valor en los datos.
