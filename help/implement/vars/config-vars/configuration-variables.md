---
title: Variables de configuración
description: Utilice variables de configuración para determinar cómo se recopilan los datos.
feature: Variables
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '125'
ht-degree: 100%

---

# Información general de variables de configuración

Las variables de configuración controlan la manera en que se capturan y procesan los datos en los informes. No suelen contener valores de dimensión o valores de métrica.

## Establecer variables de configuración

En implementaciones de JavaScript que utilizan `AppMeasurement.js`, las variables de configuración generalmente se establecen en la parte superior del archivo JS.

En implementaciones que utilizan etiquetas de Adobe Experience Platform, las variables de configuración generalmente se encuentran ajustando la extensión de Adobe Analytics:

1. Inicie sesión en la [IU de recopilación de datos](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad que desee editar.
1. Haga clic en la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en [!UICONTROL Configurar] en Adobe Analytics.

>[!IMPORTANT]
>
>Asegúrese de que todas las variables de configuración estén configuradas antes de llamar a un método de seguimiento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)). Evite establecer variables de configuración en la función [`doPlugins()`](../functions/doplugins.md).
