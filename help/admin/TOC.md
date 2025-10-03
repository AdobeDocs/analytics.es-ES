---
product: analytics
audience: admin
user-guide-title: Guía de administración de Analytics
breadcrumb-title: Guía de administración
user-guide-description: Obtenga información acerca de las tareas de administración de Analytics, como la gestión de usuarios y productos en Experience Cloud Admin Console, la configuración de grupos de informes y mucho más.
source-git-commit: 35675c2e65456a175d1516dd421b80d2af809286
workflow-type: ht
source-wordcount: '496'
ht-degree: 100%

---


# Guía de administración de Adobe Analytics {#admin}

+ [Guía de administración de Analytics](home.md)
+ [Notas de la versión de Analytics](https://experienceleague.adobe.com/es/docs/analytics/release-notes/latest)
+ Adobe Admin Console {#admin-console}
   + [Información general](admin-console/home.md)
   + [Guía de administración inicial de Adobe Analytics](admin-console/first-admin-guide.md)
   + [Funciones de administrador en Adobe Analytics](admin-console/admin-roles-in-analytics.md)
   + Resumen de permisos de las herramientas de Analytics {#permissions}
      + [Perfiles de producto para Adobe Analytics](admin-console/permissions/product-profile.md)
      + [Permisos de perfil de productos para las herramientas de grupo de informes](admin-console/permissions/report-suite-tools.md)
      + [Permisos de perfil de productos para las herramientas de Analytics](admin-console/permissions/analytics-tools.md)
+ Herramientas de administración de Analytics {#admin-tools}
   + [Información general sobre las herramientas de administración](tools/c-admin-tools.md)
   + [Administrador de códigos](tools/code-manager-admin.md)
   + [Inventario de Analytics](tools/analytics-inventory.md)
   + [Fuentes de datos](tools/data-sources.md)
   + [Excluir por dirección IP](tools/exclude-ip.md)
   + [Registros](tools/logs.md)
   + Administrador de actividades de creación de informes {#reporting-activity-manager}
      + [Información general](tools/reporting-activity-manager/reporting-activity-overview.md)
      + [Visualización de la actividad de creación de informes](tools//reporting-activity-manager/reporting-activity.md)
      + [Cancelación de solicitudes de creación de informes](tools/reporting-activity-manager/reporting-activity-cancel-requests.md)
   + Migración de componentes {#component-migration}
      + [Preparación para la migración](tools/component-migration/prepare-component-migration.md)
      + [Flujo de trabajo de migración](tools/component-migration/component-migration.md)
   + Administrador del grupo de informes {#manage-report-suites}
      + Editar la configuración de un grupo de informes {#edit-report-suite}
         + General {#report-suite-general}
            + [Configuración general de la cuenta](tools/manage-rs/edit-settings/general/general-acct-settings-admin.md)
            + [Filtros URL internos](tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)
            + [Personalizar calendario](tools/manage-rs/edit-settings/general/custom-calendar.md)
            + Detección de búsqueda de pago {#paid-search-detection}
               + [Resumen de detección de búsqueda de pago](tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md)
               + [Configurar la detección de búsqueda pagada](tools/manage-rs/edit-settings/general/paid-search-detection/t-paid-search-detection.md)
            + Reglas de procesamiento {#processing-rules}
               + [Información general](tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)
               + [Interfaz](tools/manage-rs/edit-settings/general/processing-rules/pr-interface.md)
               + [Ver historial](tools/manage-rs/edit-settings/general/processing-rules/pr-view-history.md)
               + [Copiar reglas](tools/manage-rs/edit-settings/general/processing-rules/pr-copy.md)
               + [Dimensiones y métricas disponibles](tools/manage-rs/edit-settings/general/processing-rules/pr-variables.md)
               + [Casos de uso](tools/manage-rs/edit-settings/general/processing-rules/pr-use-cases.md)
            + Reglas de bots {#bot-removal}
               + [Eliminación de bots](tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md)
               + [Comprensión y configuración de reglas de bots](tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)
               + [Firmas comunes de bots](tools/manage-rs/edit-settings/general/bot-removal/bot-signatures.md)
               + [Métodos de exclusión de bots](tools/manage-rs/edit-settings/general/bot-removal/bot-exclusion-methods.md)
            + [Configuración de privacidad](tools/manage-rs/edit-settings/general/privacy-settings.md)
            + [Configuración de marcas de hora](tools/manage-rs/edit-settings/general/timestamp-configuration.md)
            + Reenvío del lado del servidor {#server-side-forwarding}
               + [Resumen del reenvío del lado del servidor](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)
               + [Cumplimiento de la privacidad en línea y del RGPD y reenvío del lado del servidor](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-gdpr.md)
               + [Requisitos para el reenvío del lado del servidor](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-requirements.md)
               + [Referencia de datos y código del reenvío del lado del servidor](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-reference.md)
               + [Comprobar la implementación del reenvío del lado del servidor](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-verify.md)
               + [Preguntas frecuentes acerca del reenvío del lado del servidor](tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-faq.md)
         + Tráfico {#traffic-variables}
            + [Variables de tráfico](tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)
            + [Clasificaciones de tráfico](tools/manage-rs/edit-settings/c-traffic-variables/traffic-classifications.md)
            + [Descripciones personalizadas de informe](tools/manage-rs/edit-settings/c-traffic-variables/custom-desc-admin.md)
         + Conversión {#conversion-variables}
            + [Variables de conversión](tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md)
            + [Métodos de búsqueda](tools/manage-rs/edit-settings/conversion-var-admin/finding-methods.md)
            + [Clasificaciones de conversión](tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md)
            + Variable de visitante único {#unique-visitor-variable}
               + [Especificar la variable de visitante único](tools/manage-rs/edit-settings/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [Caso de uso: Extracción de ID de visitantes](tools/manage-rs/edit-settings/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + [Eventos de éxito](tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md)
            + [Jerarquías de clasificación](tools/manage-rs/edit-settings/conversion-var-admin/classification-hierarchies.md)
            + [Variables de lista](tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)
            + [eVars de comercialización](tools/manage-rs/edit-settings/conversion-var-admin/merchandising-evars.md)
         + Canales de marketing {#marketing-channels}
            + [Administrador de canales de marketing](tools/manage-rs/edit-settings/marketing-channels/c-channels.md)
            + [Reglas de procesamiento de canal de marketing](tools/manage-rs/edit-settings/marketing-channels/c-rules.md)
            + [Clasificaciones del canal de marketing](tools/manage-rs/edit-settings/marketing-channels/classifications-mchannel.md)
            + [Caducidad del canal de marketing](tools/manage-rs/edit-settings/marketing-channels/visitor-engagement.md)
         + Administración del tráfico {#traffic-management}
            + [Información general](tools/manage-rs/edit-settings/c-traffic-management/traffic-management.md)
            + [Programar picos](tools/manage-rs/edit-settings/c-traffic-management/t-traffic-schedule-spike.md)
            + [Tráfico permanente](tools/manage-rs/edit-settings/c-traffic-management/t-traffic-permanent.md)
         + [Métricas predeterminadas](tools/manage-rs/edit-settings/default-metrics.md)
         + Administración de aplicaciones {#app-management}
            + [Creación de informes de aplicaciones](tools/manage-rs/edit-settings/app-reporting.md)
            + [Clasificaciones de aplicaciones](tools/manage-rs/edit-settings/app-classifications.md)
         + [Administración de medios](tools/manage-rs/edit-settings/media-management.md)
         + [Activity Map](tools/manage-rs/edit-settings/activity-map.md)
         + [AEM](tools/manage-rs/edit-settings/adobe-experience-manager.md)
         + [Adobe Campaign](tools/manage-rs/edit-settings/adobe-campaign.md)
         + [Creación de informes de privacidad](tools/manage-rs/edit-settings/privacy-reporting.md)
         + Administración de Document Cloud {#doc-cloud-mgt}
            + [Configuración de Document Cloud con Adobe Analytics](tools/manage-rs/edit-settings/document-cloud-mgt.md)
            + [Configuración de creación de informes de Document Cloud](tools/manage-rs/edit-settings/document-cloud-config.md)
         + [Configuración de Advertising Analytics](tools/manage-rs/edit-settings/advertising-analytics-config.md)
         + Tiempo real {#real-time-reports}
            + [Resumen de informes en tiempo real](tools/manage-rs/edit-settings/realtime/realtime.md)
            + [Configuración de informes en tiempo real](tools/manage-rs/edit-settings/realtime/t-realtime-admin.md)
            + [Métricas y dimensiones en tiempo real compatibles](tools/manage-rs/edit-settings/realtime/realtime-metrics.md)
      + [Administrar grupos de informes](tools/manage-rs/report-suites-admin.md)
      + [Grupos de informes globales](tools/manage-rs/rollup-report-suite.md)
      + [Guardar una búsqueda de grupos de informes](tools/manage-rs/t-report-suite-saved-search.md)
      + [Descargar la configuración del grupo de informes](tools/manage-rs/t-download-rs-settings.md)
      + Nuevo grupo de informes {#c-new-report-suite}
         + [Crear un grupo de informes](tools/manage-rs/new-rs/t-create-a-report-suite.md)
         + [Crear un grupo de grupos de informes](tools/manage-rs/new-rs/t-create-rs-group.md)
         + [Descargar la configuración del grupo de informes](tools/manage-rs/new-rs/new-report-suite.md)
         + [Configuración que no se copia desde un grupo de informes de origen](tools/manage-rs/new-rs/settings-not-copied-from-rs.md)
      + Plantillas del grupo de informes {#report-suite-templates}
         + [Resumen de las plantillas de grupos de informes](tools/manage-rs/rs-templates/report-suite-templates.md)
         + [Portal de agregadores](tools/manage-rs/rs-templates/aggregator-portal.md)
         + [Comercio](tools/manage-rs/rs-templates/commerce-admin.md)
         + [Contenido y medios](tools/manage-rs/rs-templates/content-media.md)
         + [Plantilla predeterminada](tools/manage-rs/rs-templates/default-rs-template.md)
         + [Servicios financieros](tools/manage-rs/rs-templates/financial-services.md)
         + [Portal de trabajo](tools/manage-rs/rs-templates/job-portal.md)
         + [Generación de posibles clientes](tools/manage-rs/rs-templates/lead-generation.md)
         + [Medios de soporte técnico](tools/manage-rs/rs-templates/support-media.md)
   + Configuración de la compañía {#company-settings}
      + [Información general de la configuración de la compañía](tools/company/c-company-settings.md)
      + [Administrador de seguridad](tools/company/security-manager.md)
      + [Servicios Web](tools/company/web-services-admin.md)
      + [Informes de Report Builder](tools/company/report-builder-reports-admin.md)
      + [Inicio de sesión único](tools/company/single-signon-admin.md)
      + [Ocultar grupos de informes](tools/company/c-hide-report-suites.md)
      + [Administrador de preferencias](tools/company/preferences-manager.md)
      + [Acciones pendientes](tools/company/pending-actions-admin.md)
      + [Niveles de acceso de las funcionalidades](tools/company/feature-access-levels.md)
   + Etiquetado de privacidad {#privacy-labeling}
      + [Información general](tools/privacy-labeling/labeling-overview.md)
      + [Etiquetas de privacidad de datos para componentes de Analytics](tools/privacy-labeling/labels.md)
      + [Ver/administrar etiquetas de privacidad del grupo de informes](tools/privacy-labeling/view-settings.md)
      + [Prácticas recomendadas de etiquetado](tools/privacy-labeling/best-practices.md)
      + [Ejemplo de etiquetado](tools/privacy-labeling/examples.md)
      + [Espacios de nombres](tools/privacy-labeling/namespaces.md)
   + Uso de llamada al servidor {#server-call-usage}
      + [Resumen del uso de llamadas al servidor](tools/server-call-usage/overage-overview.md)
      + [Ver uso de llamadas al servidor actual](tools/server-call-usage/server-call-usage-dashboard.md)
      + [Ver uso del grupo de informes](tools/server-call-usage/report-suite-usage.md)
      + [Alertas de uso de llamadas al servidor](tools/server-call-usage/scu-alerts.md)
      + [Preguntas frecuentes sobre uso de llamadas al servidor](tools/server-call-usage/overage-faq.md)
   + Administración de usuarios y productos (heredados) {#user-product-management}
      + [Administración de usuarios y productos (heredados)](tools/user-management/user-management.md)
      + [Administración de cuentas de usuario, recursos y caducidades heredados](tools/user-management/users-assets.md)
      + Migración de usuarios a Adobe Admin Console {#migrate-users}
         + [Migración de usuarios de Analytics a Admin Console](tools/user-management/user-migration/c-migration-tool.md)
         + [Migración de cuentas de usuarios de Analytics para Adobe ID](tools/user-management/user-migration/t-migrate-users.md)
         + [Migración de las cuentas de usuario de Analytics para Enterprise ID y Federated ID](tools/user-management/user-migration/migrate-enterprise.md)
         + [Desactivación de inicios de sesión heredados](tools/user-management/user-migration/t-disable-legacy-login.md)
         + [API afectadas por la migración](tools/user-management/user-migration/developer.md)
+ [API de administración](c-admin-api/c-admin-api.md)
+ [Preguntas frecuentes sobre el final de la vida útil de la API de Adobe Analytics 1.4](c-admin-api/c-admin-14-api-eol.md)

