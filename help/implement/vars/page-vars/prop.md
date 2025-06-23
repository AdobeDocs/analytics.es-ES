---
title: prop
description: Variables personalizadas que puede utilizar en su implementación.
feature: Appmeasurement Implementation
exl-id: 0d0ff8cd-1d8c-4263-866d-e51ad66148b0
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 85%

---

# prop

*Esta página de ayuda describe cómo implementar props (propiedades). Para obtener información sobre cómo funcionan las props como dimensiones, consulte [prop](/help/components/dimensions/prop.md) en la guía del usuario de componentes.*

Las propiedades son variables personalizadas que se pueden utilizar como desee. No se mantienen más allá de la visita en la que están configuradas.

>[!TIP]
>
>Adobe recomienda utilizar [eVars](evar.md) en la mayoría de los casos. En versiones anteriores de Adobe Analytics, las props y las eVars tenían ventajas y desventajas entre sí. Sin embargo, Adobe ha mejorado las eVars hasta el punto de que ahora cumplen casi todos los casos de uso de las props.

Si tiene un [documento de diseño de soluciones](/help/implement/prepare/solution-design.md), puede asignar estas dimensiones personalizadas a valores específicos de su organización. El número de propiedades disponibles depende del contrato con Adobe. Hay disponibles hasta 75 props si su contrato con Adobe lo admite.

## Props con el SDK web

Las props se asignan a las siguientes variables:

* [Objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm._experience.analytics.customDimensions.props.prop1` - `xdm._experience.analytics.customDimensions.props.prop75` - las props de lista se especifican en un [conjunto de campos independiente](#list-props-web-sdk).
* [Objeto de datos](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.prop1` - `data.__adobe.analytics.prop75`; o `data.__adobe.analytics.c1` - `data.__adobe.analytics.c75` - las props de lista se incluyen en estos campos.

## Props con la extensión de Adobe Analytics

Puede establecer propiedades durante la configuración de la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca la lista desplegable [!UICONTROL Extension] en Adobe Analytics y [!UICONTROL Action Type] en [!UICONTROL Set Variables].
6. Busque la sección [!UICONTROL Props].

Puede establecer una propiedad a un valor o a un elemento de datos. También puede copiar el valor de otra variable de Analytics.

## s.prop1 - s.prop75 en AppMeasurement y el editor de código personalizado de la extensión de Analytics

Cada variable prop es una cadena que contiene valores personalizados específicos de su organización. Su longitud máxima es de 100 bytes. Los valores superiores a 100 bytes se truncan automáticamente cuando se envían a Adobe.

```js
s.prop1 = "Example custom value";
```

## Props de lista

Las props de lista son una configuración aplicada a las propiedades que permite que la variable incluya varios valores en la misma visita. Si esta configuración no está habilitada o si se utiliza un delimitador incorrecto, la variable se trata como un valor único.

### Configurar props de lista

Habilitar props de lista en [Variables de tráfico](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) en la configuración del grupo de informes. Asegúrese de que el delimitador deseado está configurado correctamente. Adobe no proporciona un delimitador predeterminado.

>[!TIP]
>
>Los delimitadores comunes que se utilizan en las implementaciones son una coma (`,`), dos puntos (`:`), un punto y coma (`;`) o una barra vertical (`|`). Puede utilizar el delimitador ASCII no extendido que se adapte mejor a la implementación.

### Establecer las prop de lista mediante el SDK web {#list-props-web-sdk}

Si se usa el [**objeto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), las props de lista se asignan a `xdm._experience.analytics.customDimensions.listProps.prop1.values[]` - `xdm._experience.analytics.customDimensions.listProps.prop75.values[]`. El SDK web utiliza automáticamente el delimitador correcto que aparece en la configuración del grupo de informes. Si establece el delimitador en el campo XDM (por ejemplo, `xdm._experience.analytics.customDimensions.props.prop1.delimiter`), eso anula el delimitador recuperado automáticamente de la configuración del grupo de informes y puede provocar un análisis incorrecto de la cadena prop de lista.

Si se usa el [**objeto de datos**](/help/implement/aep-edge/data-var-mapping.md), las props de lista usan los mismos campos que las props estándar y siguen la sintaxis de AppMeasurement.

### Configurar las prop de lista con la extensión Adobe Analytics y AppMeasurement

Una vez configuradas las props de lista en la configuración del grupo de informes con el delimitador deseado, no hay más diferencias de implementación que el uso del delimitador.

```js
// List prop delimited with a comma
s.prop1 = "value1,value2,value3";
```

>[!IMPORTANT]
>
>Las prop de lista siguen estando sujetas a la longitud máxima de 100 bytes. No es raro que las props de lista alcancen este límite, por lo que se truncan, ya que pueden contener varios valores. Utilice abreviaciones o valores abreviados si prevé que se pueda alcanzar este límite de 100 bytes.

Si establece el mismo valor más de una vez en una propiedad de lista, se anula la duplicación en sistema de informes. Analysis Workspace cuenta la cantidad de visitas en las que se ve un valor y no la cantidad de veces que existe un valor en los datos.
