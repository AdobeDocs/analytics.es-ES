---
description: El reenvío del lado del servidor se diseñó para los clientes que desean compartir en tiempo real datos de Analytics con otras soluciones de Experience Cloud. Cuando está habilitado, el reenvío del lado del servidor también permite a Analytics enviar datos automáticamente a otras soluciones de Experience Cloud, y a dichas soluciones enviar datos automáticamente a Analytics durante el proceso de recopilación de datos.
seo-description: El reenvío del lado del servidor se diseñó para los clientes que desean compartir en tiempo real datos de Analytics con otras soluciones de Experience Cloud. Cuando está habilitado, el reenvío del lado del servidor también permite a Analytics enviar datos automáticamente a otras soluciones de Experience Cloud, y a dichas soluciones enviar datos automáticamente a Analytics durante el proceso de recopilación de datos.
seo-title: Descripción general del reenvío del lado del servidor
solution: Audience Manager
title: Descripción general del reenvío del lado del servidor
uuid: 22 ddbde 5-6805-4 eba -8 f 82-62772644 dcaa
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Descripción general del reenvío del lado del servidor

El reenvío del lado del servidor se diseñó para los clientes que desean compartir en tiempo real datos de Analytics con otras soluciones de Experience Cloud. Cuando está habilitado, el reenvío del lado del servidor también permite a Analytics enviar datos automáticamente a otras soluciones de Experience Cloud, y a dichas soluciones enviar datos automáticamente a Analytics durante el proceso de recopilación de datos.

El reenvío del lado del servidor mejora la recopilación de datos porque:

* Reduce las llamadas desde la página. With server-side forwarding, [!DNL Audience Manager] customers no longer need to use DIL for data collection because it is being forwarded from Analytics. Removing DIL means eliminating an `"/event"` call. La reducción de llamadas ayuda a mejorar el tiempo de carga de las páginas, lo que mejora la experiencia del cliente con su sitio.
* Le permite aprovechar el uso compartido de datos entre soluciones de Experience Cloud.
* Se conforma a las prácticas recomendadas para la implementación de código de Audience Manager.

>[!TIP]
>
>Los clientes actuales de Audience Manager que utilicen Analytics deberían migrar al reenvío de servidor. Los nuevos clientes de Adobe Analytics y Audience Manager deberían implementar el reenvío del lado del servidor (en lugar de DIL) como método predeterminado de recopilación y transferencia de datos.

>[!IMPORTANT]
>A instancias del reglamento de la UE sobre cumplimiento normativo de las cookies, los controladores de datos (clientes de Analytics) tienen ahora la opción de restringir a Adobe Analytics los datos previos al consentimiento y de impedir que se reenvíen en el lado del servidor a Adobe Audience Manager (AAM). Una nueva variable de contexto de implementación le permite marcar las visitas en las que no se recibió consentimiento. Cuando esta variable está establecida, impide que dichas visitas se envíen a AAM hasta haber recibido el consentimiento. Para obtener más información, consulte RGPD_ePrivacy cumplimiento y reenvío del lado del servidor.

Para comprender la posición de su organización en cuanto a la implementación del reenvío del lado del servidor, siga estos pasos de validación:

## ![Paso 1_ icon. png Imagen](assets/step1_icon.png) Verificación de la implementación del servicio MID

Compruebe si el servicio Experience Cloud ID (MID) está implementado. Para ello, consulte la [solicitud de seguimiento de Analytics](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-test-verify.html).

En la pestaña Solicitud, compruebe que haya un valor establecido para MID. Esto indica que el servicio de identidad se implementa correctamente, que es un requisito previo para el reenvío de servidor.

* Si ve un valor para MID, siga con el paso 2.
* If you do not see a MID value, [implement Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-implementation-guides.html) before proceeding to step 2.

## ![Paso 2_ icon. png Imagen](assets/step2_icon.png) Verificación de la versión de implementación del reenvío del lado del servidor

Verify whether you already have a version of server-side forwarding implemented, by [inspecting the Analytics tracking request](../../../admin/admin/c-server-side-forwarding/ssf-verify.md).

En la pestaña “Respuesta”, compruebe que la respuesta contenga datos de Audience Manager. Si ve:

* Una **respuesta JSON de Audience Manager que incluye elementos como “postbacks” o “dcs_region”**: ya tiene habilitado algún tipo de reenvío del lado del servidor. Siga con el paso 3.
* **"status":"SUCCESS"**: tiene implementado el módulo Gestión de público, pero el reenvío de servidor no está configurado correctamente. Siga con el paso 3.
* Una **imagen 2 x 2**: no tiene implementado el reenvío del lado del servidor o el módulo Gestión de público. Para corregir esto:

   * **Clientes de AAM con DIL**: se deben realizar los dos pasos siguientes en un breve tiempo:

      1. Elimine el código DIL e instale el código de página [Módulo Gestión de público](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html).
      1. Habilite el reenvío del lado del servidor en la interfaz de Administración de Analytics como se describe en el paso 3. Habilitar este ajuste antes de eliminar el código DIL duplica datos y crea llamadas de servidor facturables adicionales a Audience Manager.
   * **Nuevos clientes de AAM**: instale el código de página [Módulo Gestión de público](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html) y siga con el paso 3. No se enviarán datos a Audience Manager hasta que se active el reenvío del lado del servidor en el paso 3.


## ![Paso 3_ icon. png Imagen](assets/step3_icon.png) Verificación de la implementación del reenvío del lado del servidor del grupo de informes

Compruebe si tiene implementado el reenvío del lado del servidor en el nivel de grupo de informes, en vez del antiguo enfoque del servidor de seguimiento.

Se recomienda el reenvío del lado del servidor en el nivel de grupo de informes sobre el sistema anterior de servidor de seguimiento porque el primero permite controlar con mayor precisión los datos que se comparten desde Analytics. Esto también es un requisito previo para esta integración de Audience Analytics.

Go to **Analytics** &gt; **Admin** &gt; **Report Suites** &gt; (select **report suites**) &gt; **Edit Settings** &gt; **General** &gt; **Server Side Forwarding**. Si la casilla de verificación está:

* **Inactiva** (no puede realizar una selección o el menú no existe): los grupos de informes seleccionados no están asignados a su organización IMS. Asegúrese de que los grupos de informes aplicables estén asignados a la organización IMS apropiada mediante la [interfaz de asignación de grupos de informes](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).
* **Deshabilitada**: no tiene activado el nuevo reenvío del lado del servidor. Lea el contenido de la página y habilite esta función.
* **Habilitada**: ya está aprovisionado para el nuevo reenvío del lado del servidor. También puede configurar esta integración de Audience Analytics.

<!-- Meike, check Report Suite Mapping UI link above -->

>[!NOTE]
>
>Data will not appear in other Experience Cloud solutions, such as [Audience Manager](https://marketing.adobe.com/resources/help/en_US/aam/c_aam_home.html) or [Audiences](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html) until all 3 steps are complete. Una vez que termine, la configuración tardará varias horas en tener efecto.

