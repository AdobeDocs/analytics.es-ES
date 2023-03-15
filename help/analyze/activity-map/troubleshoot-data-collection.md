---
title: Solucionar problemas de recopilación de datos del Activity Map
description: Determine por qué no puede ver datos del Activity Map en las solicitudes de imagen
feature: Activity Map
role: User, Admin
exl-id: 7f9e06ba-4040-483b-b18b-cdfe85bca486
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# Solucionar problemas de recopilación de datos del Activity Map

Si no ve datos para dimensiones de Activity Map, utilice esta página para determinar por qué.

## Confirmar la recopilación de datos con el depurador

En primer lugar, asegúrese de que AppMeasurement recopila correctamente los datos del Activity Map.

1. Descargue e instale [Extensión de Chrome de Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=es).
2. Vaya a la página web y, a continuación, haga clic en un vínculo.
3. Cuando se cargue la página siguiente, abra el depurador. Compruebe que ve variables de datos de contexto Activity Map entre medias `activitymap.` y `.activitymap`:

![Datos de Debugger](assets/debugger.png)

## Posibles motivos por los que no hay datos de Activity Map

Compruebe cada una de las siguientes opciones para asegurarse de que los componentes del Activity Map están presentes:

* **Versión de AppMeasurement**: el Activity Map es compatible con v1.6 y versiones posteriores. Muchos problemas de casos extremos se resuelven al actualizar a la última versión estable de AppMeasurement.
* **módulo del Activity Map**: Compruebe si la variable `AppMeasurement_Module_Activity_Map` El módulo está presente en su `AppMeasurement.js` archivo. Si su implementación utiliza Adobe Experience Platform para recopilar datos, asegúrese de que **[!UICONTROL Habilitar ClickMap]** se selecciona al configurar la extensión de Analytics en **[!UICONTROL Seguimiento de vínculos]**.
* **El `s_sq` cookie**: el Activity Map depende del `s_sq` cookie para la recopilación de datos.
   * Asegúrese de que la variable `cookieDomainPeriods` está correctamente configurada, especialmente para dominios regionales como `*.co.uk` o `*.co.jp`.
   * Asegúrese de que la variable `linkInternalFilters` se establece en los valores deseados. Si un vínculo en el que se hizo clic no coincide con los filtros internos, el Activity Map lo considera un vínculo de salida y no recopila datos.
* **superposición de Activity Map en ejecución**: AppMeasurement no realiza el seguimiento de los datos de clics de la página web cuando la superposición de Activity Map está habilitada.
