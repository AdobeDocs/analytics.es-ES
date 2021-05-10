---
description: Explica las mejoras en el reenvío del lado del servidor que se han debido a la normativa de cumplimiento de cookies de la UE.
title: Cumplimiento de la privacidad en línea y del RGPD y reenvío del lado del servidor
uuid: 1b90c567-3321-4dbd-a699-38c04e809fa4
exl-id: 54e43a16-8f15-4ee8-9aa2-579af30be2c9
translation-type: tm+mt
source-git-commit: f3eb3c024a80d0b65729929960173f8b3a4267b0
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 90%

---

# Cumplimiento de la privacidad en línea y del RGPD y reenvío del lado del servidor

En esta sección se explican las mejoras en el reenvío del lado del servidor que se debieron a la [normativa de cumplimiento de cookies de la UE](https://ec.europa.eu/ipg/basics/legal/cookies/index_en.htm), que entró en vigor el 30 de septiembre de 2017.

El reenvío del lado del servidor se utiliza para compartir en tiempo real datos de Adobe Analytics con otras soluciones de [!DNL Experience Cloud Solutions], como Audience Manager. Cuando está habilitado, el reenvío del lado del servidor también permite a Analytics enviar datos automáticamente a otras soluciones de Experience Cloud. Asimismo, también permite a estas soluciones enviar datos automáticamente a Analytics durante el proceso de recopilación de datos.

Anteriormente, el reenvío del lado del servidor no tenía una forma de delimitar entre eventos/visitas de consentimiento y previos al consentimiento. Desde el 1 de noviembre de 2018, usted, como responsable del tratamiento de datos (cliente de Adobe Analytics), tiene la opción de restringir datos preconsentidos a Adobe Analytics e impedir que se reenvíen a AAM. Una nueva variable de contexto de implementación le permite marcar las visitas en las que no se recibió consentimiento. Cuando esta variable está establecida, impide que dichas visitas se envíen a AAM hasta haber recibido el consentimiento.

Si esta nueva variable contextual, `cm.ssf=1`, existe en una visita, esta se marca y no se incluye en el reenvío del lado del servidor a AAM. Por el contrario, si esta cadena no aparece en una visita, se reenvía a AAM.

El reenvío del lado del servidor es bidireccional, lo que significa que cuando se aplica a una visita y esta se reenvía a AAM, Audience Analytics recibe de AAM información de segmento de dicha visita y la vuelve a enviar a Analytics. En consecuencia, las visitas que no se incluyan en el reenvío del lado del servidor de Analytics a AAM no se enriquecerán con la lista de ID de segmento de AAM. Así pues, habrá un subconjunto de tráfico o visitas que no recibirá información sobre ID de segmento de AAM.

## Detalles de implementación: {#section_FFA8B66085BF469FAB5365C944FE38F7}

Siga los pasos indicados en función del método de implementación.

| Método de implementación | Pasos |
|--- |--- |
| Adobe Experience Platform Launch | Si tiene instalada la extensión Adobe Analytics, agregue la siguiente definición de variable de datos de contexto al editor de código personalizado dentro de la configuración de acción de una regla: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' `<br/> Nota:  Defina la variable de datos contextuales y establézcala en 1 si un cliente no da su consentimiento para el marketing segmentado. Establezca la variable `contextdata` en *0* para los clientes que consientan el marketing segmentado. |
| AppMeasurement | Agregue la definición de la variable de datos contextuales al archivo AppMeasurement.js:  <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Nota: Defina la variable de datos contextuales y establézcala en 1 si un cliente no da su consentimiento para el marketing dirigido. Establezca la variable de datos contextuales en 0 para los clientes que sí consientan el marketing dirigido. |

## Elaboración de informes (opcional) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Puede usar Adobe Analytics para generar informes sobre el volumen de su tráfico consentido y que, por lo tanto, se ha incluido en el reenvío del lado del servidor. De este modo, puede compararlo con el volumen de su tráfico no consentido y que, de igual manera, no se ha reenviado a AAM.

Para configurar este tipo de informes, asigne la nueva variable contextual a una variable de tráfico personalizado (prop) mediante reglas de procesamiento. Para ello, haga lo siguiente:

1. Implemente la variable “cm.ssf” tal como se ha indicado anteriormente.
1. [Habilite el elemento prop.](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. Utilice reglas de procesamiento para asignar la variable contextual al elemento prop.

   1. Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]** y seleccione un grupo de informes.
   1. Haga clic en **[!UICONTROL Editar grupo de informes]** > **[!UICONTROL General]** > **[!UICONTROL Reglas de procesamiento]**.
   1. Haga clic en **[!UICONTROL Agregar regla]**.
   1. En **[!UICONTROL Ejecutar siempre]**, sobrescriba el valor del elemento prop que ha activado por la variable de contexto “cm.ssf(Context Data)”.
   1. Haga clic en **[!UICONTROL Guardar]**.
