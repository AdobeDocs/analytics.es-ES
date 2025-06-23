---
description: El reenvío del lado del servidor se diseñó para los clientes que desean compartir en tiempo real datos de Analytics con otras soluciones de Experience Cloud. Cuando está habilitado, el reenvío del lado del servidor también permite a Analytics enviar datos automáticamente a otras soluciones de Experience Cloud. Asimismo, también permite a estas soluciones enviar datos automáticamente a Analytics durante el proceso de recopilación de datos.
solution: Analytics
title: Resumen del reenvío del lado del servidor
feature: Report Suite Settings
exl-id: e3cd72d2-9588-4770-a7c2-64b13a1e9519
role: Admin
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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
>A instancias del reglamento de la UE sobre cumplimiento normativo de las cookies, los controladores de datos (clientes de Analytics) tienen ahora la opción de restringir a Adobe Analytics los datos previos al consentimiento y de impedir que se reenvíen en el lado del servidor a Adobe Audience Manager. Una nueva variable de contexto de implementación le permite marcar las visitas en las que no se recibió consentimiento. Cuando esta variable está establecida, impide que dichas visitas se envíen a Adobe Audience Manager hasta haber recibido el consentimiento. Para obtener más información, consulte [RGPD_ePrivacy cumplimiento y reenvío del lado del servidor](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md).

Para comprender la posición de su organización en cuanto a la implementación del reenvío del lado del servidor, siga estos pasos de validación:

## ![imagen step1_icon.png](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step1_icon.png) Verificar implementación del servicio ECID

Compruebe si el servicio Experience Cloud ID (ECID) está implementado. Para ello, consulte la [solicitud de seguimiento de Analytics](https://experienceleague.adobe.com/docs/id-service/using/implementation/test-verify.html?lang=es).

En la pestaña Solicitud, compruebe que haya un valor establecido para ECID. Esto indica que el Servicio de identidad está implementado correctamente, un requisito previo para el reenvío de lado del servidor.

* Si ve un valor para ECID, siga con el paso 2.
* Si no ve un valor para ECID, [implemente el Servicio de identidad](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html?lang=es) antes de seguir con el paso 2.

## ![imagen step2_icon.png](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step2_icon.png) Verificar la versión de implementación de reenvío del lado del servidor

Compruebe si ya tiene implementada una versión del reenvío del lado del servidor al [inspeccionar la solicitud de seguimiento de Analytics](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md).

En la pestaña “Respuesta”, compruebe que la respuesta contenga datos de Audience Manager. Si ve:

* Una **respuesta JSON de Audience Manager que incluye elementos como “postbacks” o “dcs_region”**: Ya tiene habilitado algún tipo de reenvío del lado del servidor. Siga con el paso 3.
* **&quot;status&quot;:&quot;SUCCESS&quot;**: Tiene implementado el módulo Gestión de público, pero el reenvío de servidor no está configurado correctamente. Siga con el paso 3.
* Una **imagen 2 x 2**: no tiene implementado el reenvío del lado del servidor o el módulo Gestión de público. Para corregir esto:

   * **Clientes de Adobe Audience Manager con DIL**: se deben realizar los dos pasos siguientes en un breve tiempo:

      1. Elimine el código DIL e instale el código de página [Módulo Gestión de público](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=es).
      1. Habilite el reenvío del lado del servidor en la interfaz de Administración de Analytics como se describe en el paso 3. Habilitar este ajuste antes de eliminar el código DIL duplica datos y crea llamadas de servidor facturables adicionales a Audience Manager.

   * **Nuevos clientes de Adobe Audience Manager**: instale el código de la página del [módulo Gestión de público](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=es) y siga con el paso 3. No se enviarán datos a Audience Manager hasta que se active el reenvío del lado del servidor en el paso 3.

## ![imagen step3_icon.png](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/step3_icon.png) Verificación de la implementación de reenvío de lado del servidor del grupo de informes

Compruebe si tiene implementado el reenvío del lado del servidor en el nivel de grupo de informes, en vez del antiguo enfoque del servidor de seguimiento.

Se recomienda el reenvío del lado del servidor en el nivel de grupo de informes sobre el sistema anterior de servidor de seguimiento porque el primero permite controlar con mayor precisión los datos que se comparten desde Analytics. Esto también es un requisito previo para esta integración de Audience Analytics.

Vaya a **Analytics** > **Administración** > **Grupos de informes** > (seleccione **grupos de informes**) > **Editar configuración** > **General** > **Reenvío de servidor**. Si la casilla de verificación está:

* **Inactivo** (no puede realizar una selección o el menú no existe): los grupos de informes seleccionados no están asignados a un ID de organización. Póngase en contacto con el Servicio de atención al cliente para asegurarse de que el grupo de informes está asignado correctamente.
* **Deshabilitada**: no tiene activado el nuevo reenvío del lado del servidor. Lea el contenido de la página y habilite esta función.
* **Habilitada**: ya está aprovisionado para el nuevo reenvío del lado del servidor. También puede configurar esta integración de Audience Analytics.

>[!NOTE]
>
>No aparecerán datos en otras soluciones de Experience Cloud, como [Audience Manager](https://experienceleague.adobe.com/docs/audience-manager/user-guide/aam-home.html?lang=es) o [Audiencias](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=es), hasta que haya completado los 3 pasos. Una vez que termine, la configuración tardará varias horas en tener efecto.
