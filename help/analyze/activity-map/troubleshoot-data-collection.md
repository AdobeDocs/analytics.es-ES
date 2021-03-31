---
title: Solución de problemas de la recopilación de datos del Activity Map
description: Determinar por qué no se pueden ver los datos del Activity Map en las solicitudes de imagen
feature: Activity Map
role: Profesional empresarial, administrador
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 3%

---


# Solución de problemas de la recopilación de datos del Activity Map

Si no ve datos para dimensiones de Activity Map, utilice esta página para determinar por qué.

## Confirmar la recopilación de datos con el depurador

En primer lugar, asegúrese de que AppMeasurement recopila correctamente los datos del Activity Map.

1. Descargue e instale la [extensión de Chrome de Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/es-ES/debugger/using/experience-cloud-debugger.html).
2. Vaya a la página web y, a continuación, haga clic en un vínculo.
3. Cuando se cargue la página siguiente, abra el depurador. Compruebe que ve variables de datos de contexto de Activity Map entre `activitymap.` y `.activitymap`:

![Datos de Debugger](assets/debugger.png)

## Motivos posibles por los que no están presentes los datos del Activity Map

Compruebe cada una de las siguientes opciones para asegurarse de que los componentes del Activity Map están presentes:

* **Versión** de AppMeasurement: Activity Map compatible con la versión 1.6 y posteriores. Muchos problemas de casos extremos se resuelven al actualizar a la última versión estable de AppMeasurement.
* **módulo** Activity Map: Compruebe si el  `AppMeasurement_Module_Activity_Map` módulo está presente en el  `AppMeasurement.js` archivo . Si la implementación utiliza Adobe Experience Platform Launch, asegúrese de que **[!UICONTROL Enable ClickMap]** esté marcado al configurar la extensión de Analytics en **[!UICONTROL Link tracking]**.
* **La  `s_sq` cookie**: El Activity Map depende de la  `s_sq` cookie para la recopilación de datos.
   * Asegúrese de que la variable `cookieDomainPeriods` esté correctamente configurada, especialmente para dominios regionales como `*.co.uk` o `*.co.jp`.
   * Asegúrese de que la variable `linkInternalFilters` está configurada con los valores deseados. Si un vínculo en el que se hizo clic no coincide con los filtros internos, el Activity Map lo considera un vínculo de salida y no recopila datos.
* **Superposición de Activity Map en ejecución**: AppMeasurement no rastrea datos de clics de la página web cuando la superposición del Activity Map está habilitada.
