---
description: 'null'
seo-description: 'null'
seo-title: Cumplimiento de GDPR/ePrivacy y reenvío de servidor
title: Cumplimiento de GDPR/ePrivacy y reenvío de servidor
uuid: 1b90c567-3321-4dbd-a699-38c04e809fa4
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Cumplimiento de GDPR/ePrivacy y reenvío de servidor

En esta sección se explican las mejoras aplicadas recientemente en el reenvío del lado del servidor debido a la [normativa de cumplimiento de cookies de la UE](https://ec.europa.eu/ipg/basics/legal/cookies/index_en.htm), que entró en vigor el 30 de septiembre de 2017.

Server-side forwarding is used to share data from Adobe Analytics to other [!DNL Experience Cloud Solutions], such as Audience Manager, in real time. Cuando está habilitado, el reenvío del lado del servidor también permite a Analytics enviar datos automáticamente a otras soluciones de Experience Cloud. Asimismo, también permite a dichas soluciones enviar datos automáticamente a Analytics durante el proceso de recopilación de datos.

Hasta hace poco, el reenvío del lado del servidor no ofrecía la posibilidad de elegir entre eventos o visitas, ya fueran de tipo consentido o preconsentido. Desde el 1 de noviembre de 2018, usted, como responsable del tratamiento de datos (cliente de Adobe Analytics), tiene la opción de restringir datos preconsentidos a Adobe Analytics e impedir que se reenvíen a AAM. Una nueva variable de contexto de implementación le permite marcar las visitas en las que no se recibió consentimiento. Cuando esta variable está establecida, impide que dichas visitas se envíen a AAM hasta haber recibido el consentimiento.

When this new context variable, `cm.ssf=1`, exists on a hit, this hit gets flagged and does not get server-side-forwarded to AAM. Por el contrario, si esta cadena no aparece en una visita, se reenvía a AAM.

El reenvío del lado del servidor es bidireccional, lo que significa que cuando se aplica a una visita y esta se reenvía a AAM, Audience Analytics recibe de AAM información de segmento de dicha visita y la vuelve a enviar a Analytics. En consecuencia, las visitas que no se incluyan en el reenvío del lado del servidor de Analytics a AAM no se enriquecerán con la lista de ID de segmento de AAM. Así pues, habrá un subconjunto de tráfico o visitas que no recibirá información sobre ID de segmento de AAM.

## Detalles de implementación:{#section_FFA8B66085BF469FAB5365C944FE38F7}

Siga los pasos indicados en función del método de implementación.

| Método de implementación | Pasos |
|--- |--- |
| Adobe Experience Platform Launch | Si tiene instalada la extensión Adobe Analytics, agregue la siguiente definición de variable de datos de contexto al editor de código personalizado dentro de la configuración de acción de una regla: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` Nota: <br/>Nota:  Defina la variable contextdata y configúrela en 1 si un cliente no da su consentimiento para la mercadotecnia de objetivo. Set the `contextdata` variable to *0* for customers who consented to targeted marketing. |
| DTM | Agregue la definición de la variable de datos contextuales al editor de código de página personalizado: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Nota: Defina la variable de datos contextuales y establézcala en 1 si un cliente no da su consentimiento para el marketing dirigido. Establezca la variable de datos contextuales en 0 para los clientes que sí consientan el marketing dirigido. |
| AppMeasurement | Agregue la definición de la variable de datos contextuales al archivo AppMeasurement.js:  <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Nota: Defina la variable de datos contextuales y establézcala en 1 si un cliente no da su consentimiento para el marketing dirigido. Establezca la variable de datos contextuales en 0 para los clientes que sí consientan el marketing dirigido. |

## Elaboración de informes (opcional) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Puede utilizar Adobe Analytics para informar sobre la cantidad de tráfico que se basa en el consentimiento y, como resultado, se reenvía en el servidor en comparación con la cantidad de tráfico que no se basa en el consentimiento y que no se reenvía a AAM.

Para configurar este tipo de informes, asigne la nueva variable contextual a una variable de tráfico personalizado (prop) mediante reglas de procesamiento. Para ello, haga lo siguiente:

1. Implementar la variable "cm.ssf" (como se muestra arriba).
1. [Habilite el elemento prop.](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. Utilice reglas de procesamiento para asignar la variable contextual al elemento prop.

   1. Go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** , then select a report suite.
   1. Click  **[!UICONTROL Edit Report Suite]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Processing Rules]** .
   1. Haga clic en **[!UICONTROL Agregar regla.]**
   1. Under **[!UICONTROL Always Execute]**, overwrite the value of the prop you had enabled with the context variable "cm.ssf(Context Data)".
   1. Haga clic en **[!UICONTROL Guardar]**.

