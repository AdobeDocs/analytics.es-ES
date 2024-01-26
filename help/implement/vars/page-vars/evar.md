---
title: eVar (variable)
description: Variables personalizadas que puede utilizar en su implementación.
feature: Variables
exl-id: f89457b2-4186-4276-8637-9992070e3a73
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 96%

---

# eVar

*Esta página de ayuda describe cómo implementar eVars. Para obtener información sobre cómo funcionan las eVars como dimensiones, consulte [eVars](/help/components/dimensions/evar.md) en la guía del usuario de Componentes.*

Las eVars son variables personalizadas que se pueden utilizar como desee. Si tiene un [documento de diseño de solución](/help/implement/prepare/solution-design.md), la mayoría de las dimensiones específicas de su organización terminan como eVars. De forma predeterminada, las eVars persisten más allá de la visita en la que están configuradas. Puede personalizar su caducidad y asignación en [Variables de conversión](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) en la configuración del grupo de informes.

El número de eVars disponibles depende del contrato con Adobe. Hay disponibles hasta 250 eVars si su contrato con Adobe lo permite.

## Configurar eVars en la configuración del grupo de informes

Antes de usar eVars en la implementación, asegúrese de configurar cada eVar en la configuración del grupo de informes. Consulte [Variables de conversión](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) en la guía de administración.

## eVars con el SDK web

Las eVars se [asignan para Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=es) en los campos XDM `_experience.analytics.customDimensions.eVars.eVar1` a `_experience.analytics.customDimensions.eVars.eVar250`.

## eVars con la extensión de Adobe Analytics

Puede establecer eVars al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Configure las variables [!UICONTROL Extensión] lista desplegable para Adobe Analytics y la variable [!UICONTROL Tipo de acción] hasta [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL eVars].

Puede establecer una eVar en un valor o en un elemento de datos. También puede copiar el valor de otra variable de Analytics.

## s.eVar1 - s.eVar250 en AppMeasurement y el editor de código personalizado de la extensión de Analytics

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

>[!IMPORTANT]
>
>Primero debe configurar las eVars en &#39;Contador&#39; en Admin Console antes de usar las eVars de contador. Consulte [Variables de conversión](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md) en la guía de administración.
