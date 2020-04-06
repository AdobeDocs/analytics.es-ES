---
description: El reenvío de servidor está diseñado para clientes que deseen compartir datos de Analytics con otras soluciones de Experience Cloud en tiempo real. Cuando está habilitado, el reenvío del lado del servidor también permite a Analytics enviar datos automáticamente a otras soluciones de Experience Cloud. Asimismo, también permite a estas soluciones enviar datos automáticamente a Analytics durante el proceso de recopilación de datos.
solution: Audience Manager
title: Resumen del reenvío del lado del servidor
uuid: 22ddbde5-6805-4eba-8f82-62772644dcaa
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Resumen del reenvío del lado del servidor

El reenvío de servidor está diseñado para clientes que deseen compartir datos de Analytics con otras soluciones de Experience Cloud en tiempo real. Cuando está habilitado, el reenvío del lado del servidor también permite a Analytics enviar datos automáticamente a otras soluciones de Experience Cloud. Asimismo, también permite a estas soluciones enviar datos automáticamente a Analytics durante el proceso de recopilación de datos.

El reenvío del lado del servidor mejora la recopilación de datos porque:

* Reduce las llamadas desde la página. Con el reenvío del lado del servidor, los clientes de [!DNL Audience Manager] ya no tienen que utilizar DIL para la recopilación de datos, pues estos se reenvían desde Analytics. Eliminar DIL significa eliminar una llamada `"/event"`. La disminución de llamadas ayuda a mejorar los tiempos de carga de las páginas, lo que mejora la experiencia del cliente en el sitio.
* Le permite aprovechar el uso compartido de datos entre las soluciones de Experience Cloud.
* Se ajusta a las prácticas recomendadas para la implementación y la implementación del código del Administrador de Audiencias.

>[!TIP]
>
>Los clientes existentes de Audience Manager que utilicen Analytics deberían migrar al reenvío del lado del servidor. Los nuevos clientes de Adobe Analytics y Audience Manager deberían implementar el reenvío del lado del servidor (en lugar de DIL) como método predeterminado de recopilación y transferencia de datos.

>[!IMPORTANT]
>A instancias del reglamento de la UE sobre cumplimiento normativo de las cookies, los controladores de datos (clientes de Analytics) tienen ahora la opción de restringir a Adobe Analytics los datos previos al consentimiento y de impedir que se reenvíen en el lado del servidor a Adobe Audience Manager (AAM). Una nueva variable de contexto de implementación permite marcar las visitas en las que no se ha recibido el consentimiento. La variable, cuando está configurada, evita que estas visitas se envíen a AAM hasta que se reciba el consentimiento. For more information, see [GDPR_ePrivacy compliance and server-side forwarding](/help/admin/admin/c-server-side-forwarding/ssf-gdpr.md).

Para comprender la posición de su organización en cuanto a la implementación del reenvío del lado del servidor, siga estos pasos de validación:

## ![imagen step1_icon.png](assets/step1_icon.png) Verificar implementación del servicio ECID

Compruebe si el servicio Experience Cloud ID (ECID) está implementado. Para ello, consulte la [solicitud de seguimiento de Analytics](https://marketing.adobe.com/resources/help/es_ES/mcvid/mcvid-test-verify.html).

En la pestaña Solicitud, compruebe que haya un valor establecido para ECID. Esto indica que el Servicio de identidad está implementado correctamente, un requisito previo para el reenvío de lado del servidor.

* Si ve un valor para ECID, siga con el paso 2.
* Si no ve un valor para ECID, [implemente el Servicio de identidad](https://docs.adobe.com/content/help/es-ES/id-service/using/implementation/implementation-guides.html) antes de seguir con el paso 2.

## ![imagen step2_icon.png](assets/step2_icon.png) Verificar la versión de implementación de reenvío del lado del servidor

Compruebe si ya tiene implementada una versión del reenvío del lado del servidor al [inspeccionar la solicitud de seguimiento de Analytics](/help/admin/admin/c-server-side-forwarding/ssf-verify.md).

En la pestaña “Respuesta”, compruebe que la respuesta contenga datos de Audience Manager. Si ve:

* Una **respuesta JSON de Audience Manager que incluye elementos como “postbacks” o “dcs_region”**: Ya tiene habilitado algún tipo de reenvío del lado del servidor. Siga con el paso 3.
* **&quot;status&quot;:&quot;SUCCESS&quot;**: Tiene implementado el módulo Gestión de público, pero el reenvío de servidor no está configurado correctamente. Siga con el paso 3.
* Una imagen **de** 2 x 2: no tiene implementado el reenvío del lado del servidor o el módulo de administración de Audiencias. Para corregir esto:

   * **Clientes de AAM con DIL**: coordine los dos elementos siguientes en estrecha conjunción:

      1. Quite el código DIL e instale el código de página Módulo [de administración de](https://docs.adobe.com/content/help/es-ES/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.translate.html) Audiencias.
      1. Habilite el reenvío del lado del servidor en la interfaz de usuario de administración de Analytics como se describe en el paso 3. Al habilitar esta opción antes de eliminar el código DIL, se duplicado los datos y se crean llamadas al servidor facturadas adicionales al Administrador de Audiencias.
   * **Nuevos clientes** de AAM: instale el código de página Módulo [de administración de](https://docs.adobe.com/content/help/es-ES/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.translate.html) Audiencias y continúe con el paso 3. Los datos no se enviarán al Administrador de Audiencias hasta que se active el reenvío del lado del servidor en el paso 3.


## ![imagen step3_icon.png](assets/step3_icon.png) Verificación de la implementación de reenvío de lado del servidor del grupo de informes

Compruebe si el reenvío del lado del servidor está implementado en el nivel de grupo de informes, en lugar del enfoque de servidor de seguimiento heredado.

Se recomienda el reenvío del lado del servidor en el nivel de grupo de informes sobre el enfoque del servidor de seguimiento heredado, ya que puede controlar con mayor precisión qué datos se comparten desde Analytics. También es un requisito previo para esta integración de Audiencia de Analytics.

Vaya a **Analytics** > **Administración** > **Grupos de informes** > (seleccione **grupos de informes**) > **Editar configuración** > **General** > **Reenvío de servidor**. Si la casilla de verificación está:

* **Inactiva** (no puede realizar una selección o el menú no existe): Los grupos de informes seleccionados no están asignados a su organización IMS. Asegúrese de que los grupos de informes aplicables estén asignados a la organización de Experience Cloud apropiada mediante la [interfaz de asignación de grupos de informes](https://docs.adobe.com/content/help/es-ES/core-services/interface/about-core-services/report-suite-mapping.html).
* **Deshabilitado**: No tiene activado el nuevo reenvío del lado del servidor. Lea el contenido de la página y, a continuación, continúe con la activación de la función.
* **Habilitado**: Está aprovisionado para el nuevo reenvío del lado del servidor. También puede configurar esta integración de Audiencia de Analytics.

>[!NOTE] No aparecerán datos en otras soluciones de Experience Cloud, como [Audience Manager](https://docs.adobe.com/content/help/es-ES/audience-manager/user-guide/aam-home.translate.html) o [Audiencias](https://marketing.adobe.com/resources/help/es_ES/mcloud/audience_library.html), hasta que haya completado los 3 pasos. Una vez que termine, la configuración tardará varias horas en tener efecto.

