---
description: Obtenga información sobre las directrices y recomendaciones para el consentimiento de los usuarios para almacenar o leer cookies no esenciales en dispositivos o navegadores.
title: ¿Cuáles son las directrices de CNIL para el consentimiento y las cookies del usuario?
translation-type: tm+mt
source-git-commit: c5ebc92622e012699d64c27701b24a88429e9f4f
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 1%

---


# Exención de consentimiento de CNIL

El 1 de octubre de 2020, la Autoridad Francesa de Protección de Datos (la &quot;CNIL&quot;) publicó una versión revisada de sus directrices sobre cookies (las &quot;Directrices&quot;) y sus recomendaciones finales sobre la obtención del consentimiento de los usuarios para almacenar o leer cookies no esenciales y tecnologías similares en dispositivos o navegadores de los usuarios (el &quot;Recommendations&quot;).

Las Directrices establecen una exención limitada del requisito de consentimiento (&quot;Exención de consentimiento&quot;). La exención de consentimiento se aplica a las cookies de análisis cuyo propósito se limita a medir la audiencia del sitio o la aplicación únicamente en nombre del publicador web. Las Directrices establecen que, para que se aplique la exención por consentimiento, deben cumplirse las siguientes condiciones:

* Retención de datos máxima de 25 meses.  Puede revisar la configuración de retención de datos actual en Analytics > Administración > Administración de datos.  [Retención de datos](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html)
* Límite de cookies de 13 meses.  Puede anular la caducidad de la cookie de análisis mediante la variable `cookieLifetime`.  [cookieLifetime](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html)
* Ámbito limitado. El ámbito de la cookie debe limitarse a un solo sitio o aplicación. [Cookies del explorador](https://experienceleague.adobe.com/docs/analytics/technotes/cookies.html?lang=en&quot;\l&quot;third-party-cookie-implementaciones)
* Anónimización. Anonimizar el último octeto de la dirección IP. [Configuración general de la cuenta](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html)
* Ocultar ID de visitante de sistema de informes.  De forma predeterminada, los ID de visitante no están visibles en Adobe Workspace ni en Adobe Reports and Analytics.  Los ID de visitante están disponibles en Fuentes de datos y Data Warehouse.  El acceso a las fuentes de datos y la Data Warehouse se pueden limitar mediante [permisos de acceso en Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=en&quot;\l&quot;tarea_040673FE3E3E429B9531FBCB8B6A4391)
* Parámetros de geolocalización. La geolocalización no puede ser más precisa que el nivel de código postal. [Opciones ](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=en&quot;\l&quot;zip-in-adobe-experience-platform-launch) de código postal y configuración  [general de cuenta](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=en&quot;\l&quot;admin-tools)
* Configure las opciones de inclusión.  El servicio de inclusión le permite establecer protocolos de visitante para determinar si puede configurar una cookie en el dispositivo o explorador del usuario al visitar el sitio. [Servicio de inclusión](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html)
* Impedir el uso compartido de datos.  Para evitar el uso compartido de datos en Adobe Audience Manager, utilice la variable de contexto `opt.dmp` para [Sistema de informes de privacidad](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html?lang=en&quot;\l&quot;variables&quot;) a fin de evitar que las visitas se compartan.
* Capacidad de acceso y eliminación. Utilice el Privacy Service para acceder y eliminar solicitudes. [Analytics y Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html)

## Consideraciones adicionales para la recopilación de datos

Se aplican las siguientes consideraciones adicionales:

* No hay ninguna medición fuera del sitio o la aplicación sin el consentimiento previo, por ejemplo, ninguna campaña fuera del sitio, campañas por correo electrónico o iFrames.
* La recogida de información personal en variables no está permitida sin consentimiento.
* Los datos sólo se utilizan para producir estadísticas anónimas, sin combinarlos con otros datos.
* Los datos no se utilizan para las acciones de referencia cruzada.
* No se recopilan datos de geolocalización GPS.

Para obtener más información, consulte el sitio Web [CNIL Cookie Exemption](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications).
