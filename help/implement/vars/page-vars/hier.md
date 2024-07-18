---
title: hier
description: (Retirado) Implementar variables de jerarquía en Adobe Analytics.
feature: Variables
exl-id: 72bdab8f-a001-4ada-b5e2-453a8e3f24a6
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 93%

---

# hier

>[!IMPORTANT]
>
>Esta variable desaparece y no es una dimensión disponible en Analysis Workspace. Adobe recomienda usar [eVars](evar.md) y clasificaciones en su lugar.

Las variables de jerarquía son variables personalizadas que permiten ver la estructura de un sitio. Adobe admite hasta 5 variables de jerarquía en la implementación.

Esta variable resulta útil para los sitios que tienen más de tres niveles en la estructura del sitio. Por ejemplo: un sitio de medios puede tener 4 niveles en la sección Deportes: `Sports`, `Local Sports`, `Baseball`, y `Team name`. Si alguien visita la página de béisbol, tanto deportes como deportes locales y béisbol reflejarán esa visita.

Antes de usar jerarquías en la implementación, asegúrese de configurar cada jerarquía en la configuración del grupo de informes.

## Jerarquías que usan el SDK web

Las jerarquías son [asignadas para Adobe Analytics](/help/implement/aep-edge/xdm-var-mapping.md) en los campos XDM de `xdm._experience.analytics.customDimensions.hierarchies.hier1` a `xdm._experience.analytics.customDimensions.hierarchies.hier5`.

## Jerarquías que usan la extensión Adobe Analytics

Puede establecer jerarquías al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) usando sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca la lista desplegable [!UICONTROL Extension] en Adobe Analytics y [!UICONTROL Action Type] en [!UICONTROL Set Variables].
6. Busque la sección [!UICONTROL Jerarquía].

Puede establecer un valor de jerarquía en una cadena estática o hacer referencia a un elemento de datos. También puede establecer el delimitador que desee. Asegúrese de que el delimitador que ha establecido aquí coincide con el conjunto de delimitadores de la configuración del grupo de informes.

## s.hier1 - s.hier5 en el editor de código personalizado de la extensión de Analytics y AppMeasurement

Cada jerarquía es una cadena que contiene valores personalizados específicos de su organización. Su longitud máxima es de 255 bytes; los valores superiores a 255 bytes se truncan automáticamente cuando se envían a Adobe.

Asegúrese de que ninguno de los nombres de sección contenga un delimitador. Por ejemplo, si llama a una de las secciones `Coach Griffin, Jim`, elija un delimitador que no sea una coma. El límite total de variables es de 255 bytes. Los delimitadores pueden constar de varios caracteres, como `||` o `/|\`, que tienen menos probabilidades de aparecer en los valores de las variables.

```js
s.hier1 = "Toys|Boys 6+|Legos|Super Block Tub";

s.hier3 = "Sports/Local Sports/Baseball";
```
