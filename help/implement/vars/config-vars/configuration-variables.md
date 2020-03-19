---
title: Variables de configuración
description: Utilice variables de configuración para determinar cómo se recopilan los datos.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Información general de variables de configuración

Las variables de configuración controlan la manera en que se capturan y procesan los datos en los informes. No suelen contener valores de dimensión o métrica.

## Configuración de variables de configuración

En implementaciones de JavaScript que utilizan `AppMeasurement.js`, las variables de configuración generalmente se establecen en la parte superior del archivo JS.

En implementaciones que utilizan Adobe Experience Platform Launch, las variables de configuración generalmente se encuentran configurando la extensión de Adobe Analytics:

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad que desee editar.
3. Click the [!UICONTROL Extensions] tab, then Click [!UICONTROL Configure] under Adobe Analytics.

> [!IMPORTANT] Asegúrese de que todas las variables de configuración estén configuradas antes de llamar a un método de seguimiento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)). Evite configurar variables de configuración en la [`doPlugins()`](../functions/doplugins.md) función.
