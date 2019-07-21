---
description: 'null'
seo-description: 'null'
seo-title: CDPR, cumplimiento de la privacidad y reenvío de servidor
title: CDPR, cumplimiento de la privacidad y reenvío de servidor
uuid: 1 b 90 c 567-3321-4 dbd-a 699-38 c 04 e 809 fa 4
translation-type: tm+mt
source-git-commit: 26c3cc9895c27d6abc452e0a4636771fb2415fb3

---


# CDPR, cumplimiento de la privacidad y reenvío de servidor

En esta sección se explican las mejoras aplicadas recientemente en el reenvío del lado del servidor debido a la [normativa de cumplimiento de cookies de la UE](https://ec.europa.eu/ipg/basics/legal/cookies/index_en.htm), que entró en vigor el 30 de septiembre de 2017.

Server-side forwarding is used to share data from Adobe Analytics to other [!DNL Experience Cloud Solutions], such as Audience Manager, in real time. Cuando está habilitado, el reenvío del lado del servidor también permite a Analytics enviar datos automáticamente a otras soluciones de Experience Cloud. Asimismo, también permite a dichas soluciones enviar datos automáticamente a Analytics durante el proceso de recopilación de datos.

Hasta hace poco, el reenvío del lado del servidor no ofrecía la posibilidad de elegir entre eventos o visitas, ya fueran de tipo consentido o preconsentido. Desde el 1 de noviembre de 2018, usted, como responsable del tratamiento de datos (cliente de Adobe Analytics), tiene la opción de restringir datos preconsentidos a Adobe Analytics e impedir que se reenvíen a AAM. Una nueva variable de contexto de implementación le permite marcar las visitas en las que no se recibió consentimiento. Cuando esta variable está establecida, impide que dichas visitas se envíen a AAM hasta haber recibido el consentimiento.

When this new context variable, `cm.ssf=1`, exists on a hit, this hit gets flagged and does not get server-side-forwarded to AAM. Por el contrario, si esta cadena no aparece en una visita, se reenvía a AAM.

El reenvío del lado del servidor es bidireccional, lo que significa que cuando se aplica a una visita y esta se reenvía a AAM, Audience Analytics recibe de AAM información de segmento de dicha visita y la vuelve a enviar a Analytics. En consecuencia, las visitas que no se incluyan en el reenvío del lado del servidor de Analytics a AAM no se enriquecerán con la lista de ID de segmento de AAM. Así pues, habrá un subconjunto de tráfico o visitas que no recibirá información sobre ID de segmento de AAM.

## Detalles de implementación: {#section_FFA8B66085BF469FAB5365C944FE38F7}

Siga los pasos indicados en función del método de implementación.

| Método de implementación | Pasos |
|--- |--- |
| Lanzamiento de Plataforma de Adobe Experience | Assuming you have the Adobe Analytics extension installed, add the following context data variable definition to the custom code editor within the Action configuration of a Rule: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Note:  Define the contextdata variable and set it to 1 if a customer does not consent to targeted marketing. Set the `contextdata` variable to *0* for customers who consented to targeted marketing. |
| DTM | Agregue la definición de la variable de datos contextuales al editor de código de página personalizado: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Nota: Defina la variable de datos contextuales y establézcala en 1 si un cliente no da su consentimiento para el marketing dirigido. Establezca la variable de datos contextuales en 0 para los clientes que sí consientan el marketing dirigido. |
| AppMeasurement | Agregue la definición de la variable de datos contextuales al archivo AppMeasurement.js:  <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Nota: Defina la variable de datos contextuales y establézcala en 1 si un cliente no da su consentimiento para el marketing dirigido. Establezca la variable de datos contextuales en 0 para los clientes que sí consientan el marketing dirigido. |

## Elaboración de informes (opcional) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Puede usar Adobe Analytics para generar informes sobre el volumen de su tráfico consentido y que, por lo tanto, se ha incluido en el reenvío del lado del servidor. De este modo, puede compararlo con el volumen de su tráfico no consentido y que, de igual manera, no se ha reenviado a AAM.

Para configurar este tipo de informes, asigne la nueva variable contextual a una variable de tráfico personalizado (prop) mediante reglas de procesamiento. Para ello, haga lo siguiente:

1. Implemente la variable “cm.ssf” tal como se ha indicado anteriormente.
1. [Habilite el elemento prop.](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. Utilice reglas de procesamiento para asignar la variable contextual al elemento prop.

   1. Go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** , then select a report suite.
   1. Click  **[!UICONTROL Edit Report Suite]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Processing Rules]** .
   1. Haga clic en **[!UICONTROL Agregar regla.]**
   1. Under **[!UICONTROL Always Execute]**, overwrite the value of the prop you had enabled with the context variable “cm.ssf(Context Data)”.
   1. Haga clic en **[!UICONTROL Guardar]**.

