---
title: Variables de configuración
description: Utilice variables de configuración para determinar cómo se recopilan los datos.
feature: Variables
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '123'
ht-degree: 65%

---

# Información general de variables de configuración

Las variables de configuración controlan la manera en que se capturan y procesan los datos en los informes. No suelen contener valores de dimensión o valores de métrica.

## Establecer variables de configuración

En implementaciones que utilizan la extensión del SDK web o la extensión de Analytics, las variables de configuración generalmente se encuentran en la configuración de la extensión:

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Haga clic en la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en [!UICONTROL Configurar] en la extensión.

En implementaciones de JavaScript que utilizan `AppMeasurement.js`, las variables de configuración generalmente se establecen en la parte superior del archivo JS.

>[!IMPORTANT]
>
>Asegúrese de que todas las variables de configuración estén establecidas antes de llamar a un método de seguimiento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)). Evite establecer variables de configuración en la función [`doPlugins()`](../functions/doplugins.md).
