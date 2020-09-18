---
title: Solución de problemas de recopilación de datos de Activity Map
description: Determinar por qué no se pueden ver los datos de Activity Map en las solicitudes de imagen
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 3%

---


# Solución de problemas de recopilación de datos de Activity Map

Si no ve datos para dimensiones de Activity Map, utilice esta página para determinar por qué.

## Confirmar la recopilación de datos mediante el depurador

En primer lugar, asegúrese de que AppMeasurement recopila correctamente los datos del Activity Map.

1. Download and install the [Adobe Experience Cloud Debugger Chrome Extension](https://docs.adobe.com/content/help/es-ES/debugger/using/experience-cloud-debugger.html).
2. Navegue hasta la página web y haga clic en un vínculo.
3. Cuando se cargue la página siguiente, abra el depurador. Valide que vea variables de datos de contexto de Activity Map entre `activitymap.` y `.activitymap`:

![Datos del depurador](assets/debugger.png)

## Posibles razones por las que no hay datos de Activity Map

Compruebe cada una de las siguientes opciones para asegurarse de que los componentes del Activity Map están presentes:

* **Versión** de AppMeasurement: El Activity Map es compatible con la versión 1.6 y posteriores. Muchos problemas de casos extremos se resuelven al actualizar a la última versión estable de AppMeasurement.
* **Módulo** Activity Map: Compruebe si el `AppMeasurement_Module_Activity_Map` módulo está presente en el `AppMeasurement.js` archivo. Si su implementación utiliza Adobe Experience Platform Launch, asegúrese de que **[!UICONTROL Habilitar ClickMap]** está marcado al configurar la extensión de Analytics en Seguimiento de **[!UICONTROL vínculos]**.
* **La`s_sq`cookie**: El Activity Map depende de la `s_sq` cookie para la recopilación de datos.
   * Asegúrese de que la `cookieDomainPeriods` variable está correctamente configurada, especialmente para dominios regionales como `*.co.uk` o `*.co.jp`.
   * Asegúrese de que la `linkInternalFilters` variable está configurada en los valores deseados. Si un vínculo en el que se hizo clic no coincide con los filtros internos, el Activity Map lo considera un vínculo de salida y no recopila datos.
* **Superposición de Activity Map en ejecución**: AppMeasurement no rastrea los datos de clics de la página web cuando la superposición de Activity Map está habilitada.
