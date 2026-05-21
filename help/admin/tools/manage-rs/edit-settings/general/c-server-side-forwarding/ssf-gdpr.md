---
description: Explica las mejoras en el reenvío del lado del servidor que se han debido a la normativa de cumplimiento de cookies de la UE.
title: Cumplimiento de la privacidad en línea y del RGPD y reenvío del lado del servidor
feature: Report Suite Settings
exl-id: 54e43a16-8f15-4ee8-9aa2-579af30be2c9
role: Admin
TQID: https://experienceleague.adobe.com/Q4HJtRLxJvr4fy7bF5jxCW2FLH5sdKCU6rAUzN0yNv0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: c2ae876122715b4fa6367326dc23479dd9648021
workflow-type: tm+mt
source-wordcount: 588
ht-degree: 40%

---

# Cumplimiento de la privacidad en línea y del RGPD y reenvío del lado del servidor

En esta sección se explican las mejoras aplicadas en el reenvío del lado del servidor debido a la [normativa de cumplimiento de cookies de la UE](https://wikis.ec.europa.eu/display/WEBGUIDE/04.+Cookies+and+similar+technologies), que entró en vigor el 30 de septiembre de 2017.

El reenvío del lado del servidor se utiliza para compartir en tiempo real datos de Adobe Analytics con otras soluciones empresariales de CX, como Audience Manager. Cuando está habilitado, el reenvío del lado del servidor también permite a Analytics enviar datos automáticamente a otras soluciones de CX Enterprise y enviar datos automáticamente a Analytics durante el proceso de recopilación de datos.

Anteriormente, el reenvío del lado del servidor no tenía una forma de delinear entre el consentimiento y los eventos/visitas previos al consentimiento. A partir del 1 de noviembre de 2018, usted como responsable del tratamiento de datos (cliente de Adobe Analytics) tendrá la opción de restringir a Adobe Analytics los datos previos al consentimiento y de evitar que se reenvíen a Adobe Audience Manager. Una nueva variable de contexto de implementación le permite marcar las visitas en las que no se recibió consentimiento. Cuando esta variable está establecida, impide que dichas visitas se envíen a Adobe Audience Manager hasta haber recibido el consentimiento.

Cuando esta nueva variable contextual, `cm.ssf=1`, existe en una visita, esta se marca y no se reenvía del lado del servidor a Adobe Audience Manager. Por el contrario, si esta cadena no aparece en una visita, la visita se reenvía a Adobe Audience Manager.

El reenvío del lado del servidor es bidireccional, lo que significa que cuando se aplica a una visita y esa visita se reenvía a Adobe Audience Manager, Audience Analytics recibe información del segmento para esa visita de Adobe Audience Manager y la envía de vuelta a Analytics. Como resultado, las visitas que no se reenvíen del lado del servidor de Analytics a Adobe Audience Manager no se ampliarán con la lista de ID de segmento de Adobe Audience Manager. Por lo tanto, habrá un subconjunto de tráfico/visitas que no obtendrá información de ID de segmento de Adobe Audience Manager.

## Detalles de implementación {#section_FFA8B66085BF469FAB5365C944FE38F7}

Según el método de implementación, siga estos pasos.

| Método de implementación | Pasos |
|--- |--- |
| Etiquetas en Adobe Experience Platform | Si tiene instalada la extensión de Adobe Analytics, agregue la siguiente definición de variable de datos de contexto al editor de código personalizado dentro de la configuración de acción de una regla: <br/>`s.contextData['cm.ssf'] = '1'` <br/>Nota: Defina la variable de datos contextuales y establézcala en 1 si un cliente no da su consentimiento para el marketing segmentado. Establezca la variable `contextdata` en *0* para los clientes que consientan el marketing dirigido. |
| AppMeasurement | Agregue la definición de la variable de datos contextuales al archivo AppMeasurement.js: <br/>`s.contextData['cm.ssf'] = '1'` <br/>Nota: Defina la variable de datos contextuales y establézcala en 1 si un cliente no da su consentimiento para el marketing dirigido. Establezca la variable de datos contextuales en 0 para los clientes que sí consientan el marketing dirigido. |

## Creación de informes (opcional) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Puede utilizar Adobe Analytics para generar informes sobre el volumen de su tráfico consentido y que, como resultado, se ha reenviado del lado del servidor. De este modo, puede compararlo con el volumen de su tráfico no consentido y que, de igual manera, no se ha reenviado a Adobe Audience Manager.

Para configurar este tipo de informes, asigne la nueva variable de contexto a una variable de tráfico personalizada (prop) mediante reglas de procesamiento. Para ello

1. Implemente la variable “cm.ssf” tal como se ha indicado anteriormente.
1. [Habilitar la propiedad.](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)
1. Utilice reglas de procesamiento para asignar la variable de contexto a la prop.

   1. Vaya a **[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]** y seleccione un grupo de informes.
   1. Haga clic en **[!UICONTROL Editar grupo de informes]** > **[!UICONTROL General]** > **[!UICONTROL Reglas de procesamiento]**.
   1. Haga clic en **[!UICONTROL Agregar regla]**.
   1. En **[!UICONTROL Ejecutar siempre]**, sobrescriba el valor del elemento prop que ha habilitado por la variable de contexto “cm.ssf(Context Data)”.
   1. Haga clic en **[!UICONTROL Guardar]**.
