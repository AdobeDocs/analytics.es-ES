---
title: Variables de configuración
description: Utilice variables de configuración para determinar cómo se recopilan los datos.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '123'
ht-degree: 100%

---


# Información general de variables de configuración

Las variables de configuración controlan la manera en que se capturan y procesan los datos en los informes. No suelen contener valores de dimensión o valores de métrica.

## Establecer variables de configuración

En implementaciones de JavaScript que utilizan `AppMeasurement.js`, las variables de configuración generalmente se establecen en la parte superior del archivo JS.

En implementaciones que utilizan Adobe Experience Platform Launch, las variables de configuración generalmente se encuentran estableciendo la extensión de Adobe Analytics:

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad que desee editar.
3. Haga clic en la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en [!UICONTROL Configurar] en Adobe Analytics.

>[!IMPORTANT]
>
>Asegúrese de que todas las variables de configuración estén configuradas antes de llamar a un método de seguimiento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)). Evite establecer variables de configuración en la función [`doPlugins()`](../functions/doplugins.md).
