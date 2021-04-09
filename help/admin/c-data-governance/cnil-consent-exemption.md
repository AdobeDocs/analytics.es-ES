---
description: Conozca las directrices y recomendaciones acerca del consentimiento de los usuarios para almacenar o leer cookies no esenciales en dispositivos o exploradores.
title: Directrices de CNIL sobre el consentimiento del usuario para almacenar cookies
exl-id: 04179e58-dbba-45e2-ba57-7fe5fdedc483
translation-type: tm+mt
source-git-commit: 0e09f6ee34560ca7f036e8f3fb743c822d5fcfc4
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 90%

---

# Exención de consentimiento de CNIL

El 1 de octubre de 2020, la Commission nationale de l&#39;informatique et des libertés (CNIL) publicó una versión revisada de sus directrices sobre cookies (las Directrices) y recomendaciones finales (las Recomendaciones) sobre la obtención del consentimiento de los usuarios para almacenar o leer cookies no esenciales y tecnologías similares en los dispositivos o exploradores de los usuarios.

Las Directrices establecen una exención limitada del requisito de consentimiento (la Exención de consentimiento). La Exención de consentimiento se aplica a las cookies de análisis cuyo propósito se limita a medir la audiencia del sitio o de la aplicación únicamente en nombre del publicador web. Las Directrices establecen que, para que se aplique la Exención de consentimiento, deben cumplirse las siguientes condiciones:

* Retención de datos máxima de 25 meses.  Puede revisar la configuración de retención de datos actual en Analytics > Administración > Gobernanza de datos.  [Retención de datos](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=es)
* Desactive las cookies de terceros en ECID. [disableThirdPartyCalls](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disablethirdpartycalls.html?lang=es#id-service-api), [disableThirdPartyCookies](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disable-cookies.html?lang=es#id-service-api) y [disableIdSyncs](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=es#id-service-api)
* Límite de cookies de 13 meses.  Puede anular la caducidad de la cookie de análisis mediante la variable `cookieLifetime`.  Las cookies del Experience Cloud, incluidas Analytics y ECID, amplían la fecha de caducidad de las cookies con cada visita.  Para establecer una caducidad de cookie estática no móvil, puede: (1) escribir código personalizado para establecer una fecha en la que eliminar la cookie, o (2) usar su CMP para controlar la fecha de restablecimiento de la cookie.   [](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/cookielifetime.html?lang=es) Cookies cookieLifetimeand  [Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html?lang=en#ec-cookies)
* Ámbito limitado. El ámbito de la cookie debe limitarse a un solo sitio o aplicación. [Cookies del explorador](https://experienceleague.adobe.com/docs/analytics/technotes/cookies.html?lang=es&quot;\l&quot;third-party-cookie-implementaciones)
* Anónimización. Anonimizar el último octeto de la dirección IP. [Configuración general de la cuenta](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=es)
* Ocultar el ID de visitante de la creación de informes.  De forma predeterminada, los ID de visitante no están visibles en Adobe Workspace ni en Adobe Reports and Analytics.  Los ID de visitante están disponibles en Data Feeds y Data Warehouse.  El acceso a las Data Feeds y a Data Warehouse puede limitarse mediante [permisos de acceso en Admin Console](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=es&quot;\l&quot;task_040673FE3E3E429B9531FBCB8B6A4391) y [Referencia de la columna de fuente de datos](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=es#columns%2C-descriptions%2C-and-data-types)
* Parámetros de geolocalización. El nivel de precisión de la geolocalización es equiparable al de los códigos postales. [Opción de código postal](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/zip.html?lang=es&quot;\l&quot;zip-in-adobe-experience-platform-launch) y [Configuración general de la cuenta](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/general-acct-settings-admin.html?lang=es&quot;\l&quot;admin-tools)
* Configuración de las opciones de inclusión.  Con el servicio de inclusión puede configurar protocolos para que los usuarios puedan decidir si permiten la instalación de cookies en sus dispositivos o exploradores cuando visitan su sitio web. [Servicio de inclusión](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=es)
* Impedir el uso compartido de datos.  Para impedir el uso compartido de datos en Adobe Audience Manager, utilice la variable de contexto `opt.dmp` para la [Creación de informes de privacidad](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/consent-variables.html?lang=es&quot;\l&quot;variables) a fin de impedir que se compartan datos sobre visitas.
* Capacidad de acceso y eliminación. Utilización de Privacy Service para acceder y eliminar solicitudes. [Analytics y Privacy Service](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=es)

## Consideraciones adicionales para la recopilación de datos

Se aplican las siguientes consideraciones adicionales:

* Considere la posibilidad de recopilar el estado de inclusión en una variable de Analytics para separar los datos de inclusión de los datos de exclusión para la segmentación, para los grupos de informes virtuales o para dirigirlos a puntos finales independientes.
* No se efectúa ninguna medición fuera del sitio o de la aplicación sin consentimiento previo, por ejemplo, campañas externas, campañas por correo electrónico o iFrames.
* La colección de información personal en variables no está permitida sin consentimiento. [Actividades de control de Experience Cloud basadas en el consentimiento del usuario](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html?lang=es&quot;\l&quot;implementation#implementation)
* Los datos solo se utilizan para producir estadísticas anónimas, sin combinarlas con otros datos.
* Los datos no se utilizan para acciones de referencias cruzadas.
* No se recopilan datos de geolocalización GPS.
* Cuando se da el consentimiento del usuario final, la configuración anterior se puede modificar y las restricciones se pueden mitigar.

Para obtener más información, consulte el sitio web de [Exención de cookies CNIL](https://www.cnil.fr/en/sheet-ndeg16-use-analytics-your-websites-and-applications).
