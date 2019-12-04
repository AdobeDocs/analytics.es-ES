---
description: El reenvío del lado del servidor se diseñó para los clientes que desean compartir en tiempo real datos de Analytics con otras soluciones de Experience Cloud. Cuando está habilitado, el reenvío del lado del servidor también permite a Analytics enviar datos automáticamente a otras soluciones de Experience Cloud. Asimismo, también permite a estas soluciones enviar datos automáticamente a Analytics durante el proceso de recopilación de datos.
solution: Audience Manager
title: Resumen del reenvío del lado del servidor
uuid: 22ddbde5-6805-4eba-8f82-62772644dcaa
translation-type: tm+mt
source-git-commit: b7ef2f8b097540799a19c3964dfc64d59babd4a6

---


# Resumen del reenvío del lado del servidor

El reenvío del lado del servidor se diseñó para los clientes que desean compartir en tiempo real datos de Analytics con otras soluciones de Experience Cloud. Cuando está habilitado, el reenvío del lado del servidor también permite a Analytics enviar datos automáticamente a otras soluciones de Experience Cloud. Asimismo, también permite a estas soluciones enviar datos automáticamente a Analytics durante el proceso de recopilación de datos.

El reenvío del lado del servidor mejora la recopilación de datos porque:

* Reduce las llamadas desde la página. Con el reenvío del lado del servidor, los clientes de [!DNL Audience Manager] ya no tienen que utilizar DIL para la recopilación de datos, pues estos se reenvían desde Analytics. Eliminar DIL significa eliminar una llamada `"/event"`. La reducción de llamadas ayuda a mejorar el tiempo de carga de las páginas, lo que mejora la experiencia del cliente con su sitio.
* Le permite aprovechar el uso compartido de datos entre soluciones de Experience Cloud.
* Se conforma a las prácticas recomendadas para la implementación de código de Audience Manager.

>[!TIP]
>
>Los clientes existentes de Audience Manager que utilicen Analytics deberían migrar al reenvío del lado del servidor. Los nuevos clientes de Adobe Analytics y Audience Manager deberían implementar el reenvío del lado del servidor (en lugar de DIL) como método predeterminado de recopilación y transferencia de datos.

>[!IMPORTANT]
>A instancias del reglamento de la UE sobre cumplimiento normativo de las cookies, los controladores de datos (clientes de Analytics) tienen ahora la opción de restringir a Adobe Analytics los datos previos al consentimiento y de impedir que se reenvíen en el lado del servidor a Adobe Audience Manager (AAM). Una nueva variable de contexto de implementación le permite marcar las visitas en las que no se recibió consentimiento. Cuando esta variable está establecida, impide que dichas visitas se envíen a AAM hasta haber recibido el consentimiento. Para obtener más información, consulte [RGPD_ePrivacy cumplimiento y reenvío del lado del servidor](/help/admin/admin/c-server-side-forwarding/ssf-gdpr.md).

Para comprender la posición de su organización en cuanto a la implementación del reenvío del lado del servidor, siga estos pasos de validación:

## ![step1_icon.png image](assets/step1_icon.png) Comprobación de la implementación del servicio ECID

Verify whether Experience Cloud ID (ECID) service is implemented, by inspecting the [Analytics tracking request](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-test-verify.html).

En la ficha Solicitud, compruebe que se está estableciendo un valor ECID. Esto indica que el Servicio de identidad está implementado correctamente, un requisito previo para el reenvío de lado del servidor.

* Si ve un valor ECID, continúe con el paso 2.
* If you do not see an ECID value, [implement Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html) before proceeding to step 2.

## ![imagen step2_icon.png](assets/step2_icon.png) Verificar la versión de implementación de reenvío del lado del servidor

Compruebe si ya tiene implementada una versión del reenvío del lado del servidor al [inspeccionar la solicitud de seguimiento de Analytics](/help/admin/admin/c-server-side-forwarding/ssf-verify.md).

En la pestaña “Respuesta”, compruebe que la respuesta contenga datos de Audience Manager. Si ve:

* Una **respuesta JSON de Audience Manager que incluye elementos como “postbacks” o “dcs_region”**: Ya tiene habilitado algún tipo de reenvío del lado del servidor. Siga con el paso 3.
* **"status":"SUCCESS"**: Tiene implementado el módulo Gestión de público, pero el reenvío de servidor no está configurado correctamente. Siga con el paso 3.
* Una **imagen 2 x 2**: no tiene implementado el reenvío del lado del servidor o el módulo Gestión de público. Para corregir esto:

   * **Clientes de AAM con DIL**: se deben realizar los dos pasos siguientes en un breve tiempo:

      1. Elimine el código DIL e instale el código de página [Módulo Gestión de público](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html).
      1. Habilite el reenvío del lado del servidor en la interfaz de Administración de Analytics como se describe en el paso 3. Habilitar este ajuste antes de eliminar el código DIL duplica datos y crea llamadas de servidor facturables adicionales a Audience Manager.
   * **Nuevos clientes de AAM**: instale el código de página [Módulo Gestión de público](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html) y siga con el paso 3. No se enviarán datos a Audience Manager hasta que se active el reenvío del lado del servidor en el paso 3.


## ![imagen step3_icon.png](assets/step3_icon.png) Verificación de la implementación de reenvío de lado del servidor del grupo de informes

Compruebe si tiene implementado el reenvío del lado del servidor en el nivel de grupo de informes, en vez del antiguo enfoque del servidor de seguimiento.

Se recomienda el reenvío del lado del servidor en el nivel de grupo de informes sobre el sistema anterior de servidor de seguimiento porque el primero permite controlar con mayor precisión los datos que se comparten desde Analytics. Esto también es un requisito previo para esta integración de Audience Analytics.

Vaya a **Analytics** &gt; **Administración** &gt; **Grupos de informes** &gt; (seleccione **grupos de informes**) &gt; **Editar configuración** &gt; **General** &gt; **Reenvío de servidor**. Si la casilla de verificación está:

* **Inactivo** (no puede realizar una selección o el menú no existe): no tiene asignados los grupos de informes seleccionados a su organización de IMS. Asegúrese de que los grupos de informes aplicables están asignados a la organización adecuada de Experience Cloud mediante la interfaz de usuario [de asignación de grupos de](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html)informes.
* **Deshabilitada**: no tiene activado el nuevo reenvío del lado del servidor. Lea el contenido de la página y habilite esta función.
* **Habilitada**: ya está aprovisionado para el nuevo reenvío del lado del servidor. También puede configurar esta integración de Audience Analytics.

> [!NOTE] No aparecerán datos en otras soluciones de Experience Cloud, como [Audience Manager](https://marketing.adobe.com/resources/help/en_US/aam/c_aam_home.html) o [Audiencias](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html), hasta que haya completado los 3 pasos. Una vez que termine, la configuración tardará varias horas en tener efecto.

