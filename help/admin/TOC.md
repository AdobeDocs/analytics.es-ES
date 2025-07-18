---
product: analytics
audience: admin
user-guide-title: Guía de administración de Analytics
breadcrumb-title: Guía de administración
user-guide-description: Obtenga información acerca de las tareas de administración de Analytics, como la gestión de usuarios y productos en Experience Cloud Admin Console, la configuración de grupos de informes y mucho más.
source-git-commit: 0bed2622f54bf2f46aa57dbfad7bd55a61d6c7d0
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 98%

---


# Guía de administración de Adobe Analytics {#admin}

+ [Guía de administración de Analytics](home.md)
+ [Notas de la versión de Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
+ Adobe Admin Console {#admin-console}
   + [Información general](admin-console/home.md)
   + [Guía de administración inicial de Adobe Analytics](admin-console/first-admin-guide.md)
   + [Funciones de administrador en Adobe Analytics](admin-console/admin-roles-in-analytics.md)
   + Resumen de permisos de las herramientas de Analytics {#permissions}
      + [Perfiles de producto para Adobe Analytics](admin-console/permissions/product-profile.md)
      + [Permisos de perfil de productos para las herramientas de grupo de informes](admin-console/permissions/report-suite-tools.md)
      + [Permisos de perfil de productos para las herramientas de Analytics](admin-console/permissions/analytics-tools.md)
+ Herramientas de administración de Analytics {#admin-tools}
   + [Información general sobre las herramientas de administración](admin/c-admin-tools.md)
   + [Administrador de códigos](admin/code-manager-admin.md)
   + [Inventario de Analytics](admin/analytics-inventory.md)
   + [Fuentes de datos](admin/data-sources.md)
   + [Excluir por dirección IP](admin/exclude-ip.md)
   + [Registros](admin/logs.md)
   + Administrador de actividades de creación de informes {#reporting-activity-manager}
      + [Información general](admin/reporting-activity-manager/reporting-activity-overview.md)
      + [Visualización de la actividad de creación de informes](admin//reporting-activity-manager/reporting-activity.md)
      + [Cancelación de solicitudes de creación de informes](admin/reporting-activity-manager/reporting-activity-cancel-requests.md)
   + Migración de componentes {#component-migration}
      + [Preparación para la migración](admin/component-migration/prepare-component-migration.md)
      + [Flujo de trabajo de migración](admin/component-migration/component-migration.md)
   + Administrador del grupo de informes {#manage-report-suites}
      + Editar la configuración de un grupo de informes {#edit-report-suite}
         + General {#report-suite-general}
            + [Configuración general de la cuenta](admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
            + [Filtros URL internos](admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)
            + [Personalizar calendario](admin/c-manage-report-suites/c-edit-report-suites/general/custom-calendar.md)
            + Detección de búsqueda de pago {#paid-search-detection}
               + [Resumen de detección de búsqueda de pago](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md)
               + [Configurar la detección de búsqueda pagada](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/t-paid-search-detection.md)
            + Reglas de procesamiento {#processing-rules}
               + [Información general](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md)
               + [Interfaz](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-interface.md)
               + [Ver historial](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-view-history.md)
               + [Copiar reglas](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-copy.md)
               + [Dimensiones y métricas disponibles](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-variables.md)
               + [Casos de uso](admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-use-cases.md)
            + Reglas de bots {#bot-removal}
               + [Eliminación de bots](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md)
               + [Comprensión y configuración de reglas de bots](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)
               + [Firmas comunes de bots](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-signatures.md)
               + [Métodos de exclusión de bots](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-exclusion-methods.md)
            + [Configuración de privacidad](admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md)
            + [Configuración de marcas de hora](admin/c-manage-report-suites/c-edit-report-suites/general/timestamp-optional.md)
            + Reenvío del lado del servidor {#server-side-forwarding}
               + [Resumen del reenvío del lado del servidor](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)
               + [Cumplimiento de la privacidad en línea y del RGPD y reenvío del lado del servidor](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-gdpr.md)
               + [Requisitos para el reenvío del lado del servidor](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-requirements.md)
               + [Referencia de datos y código del reenvío del lado del servidor](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-reference.md)
               + [Comprobar la implementación del reenvío del lado del servidor](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-verify.md)
               + [Preguntas frecuentes acerca del reenvío del lado del servidor](admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-faq.md)
         + Tráfico {#traffic-variables}
            + [Variables de tráfico](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)
            + [Clasificaciones de tráfico](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-classifications.md)
            + [Descripciones personalizadas de informe](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/custom-desc-admin.md)
         + Conversión {#conversion-variables}
            + [Variables de conversión](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)
            + [Métodos de búsqueda](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/finding-methods.md)
            + [Clasificaciones de conversión](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-classifications.md)
            + Variable de visitante único {#unique-visitor-variable}
               + [Especificar la variable de visitante único](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [Caso de uso: Extracción de ID de visitantes](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + [Eventos de éxito](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)
            + [Jerarquías de clasificación](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/classification-hierarchies.md)
            + [Variables de lista](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)
            + [eVars de comercialización](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/merchandising-evars.md)
         + Canales de marketing {#marketing-channels}
            + [Administrador de canales de marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md)
            + [Reglas de procesamiento de canal de marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)
            + [Clasificaciones del canal de marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/classifications-mchannel.md)
            + [Caducidad del canal de marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/visitor-engagement.md)
         + Administración del tráfico {#traffic-management}
            + [Información general](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/traffic-management.md)
            + [Programar picos](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)
            + [Tráfico permanente](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-permanent.md)
         + [Métricas predeterminadas](admin/c-manage-report-suites/c-edit-report-suites/default-metrics.md)
         + Administración de aplicaciones {#app-management}
            + [Creación de informes de aplicaciones](admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md)
            + [Clasificaciones de aplicaciones](admin/c-manage-report-suites/c-edit-report-suites/app-classifications.md)
         + [Administración de medios](admin/c-manage-report-suites/c-edit-report-suites/media-management.md)
         + [Activity Map](admin/c-manage-report-suites/c-edit-report-suites/activity-map.md)
         + [AEM](admin/c-manage-report-suites/c-edit-report-suites/adobe-experience-manager.md)
         + [Adobe Campaign](admin/c-manage-report-suites/c-edit-report-suites/adobe-campaign.md)
         + [Creación de informes de privacidad](admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md)
         + Administración de Document Cloud {#doc-cloud-mgt}
            + [Configuración de Document Cloud con Adobe Analytics](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-mgt.md)
            + [Configuración de creación de informes de Document Cloud](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-config.md)
         + [Configuración de Advertising Analytics](admin/c-manage-report-suites/c-edit-report-suites/advertising-analytics-config.md)
         + Tiempo real {#real-time-reports}
            + [Resumen de informes en tiempo real](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)
            + [Configuración de informes en tiempo real](admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md)
            + [Métricas y dimensiones en tiempo real compatibles](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md)
      + [Administrar grupos de informes](admin/c-manage-report-suites/report-suites-admin.md)
      + [Grupos de informes globales](admin/c-manage-report-suites/rollup-report-suite.md)
      + [Guardar una búsqueda de grupos de informes](admin/c-manage-report-suites/t-report-suite-saved-search.md)
      + [Descargar la configuración del grupo de informes](admin/c-manage-report-suites/t-download-rs-settings.md)
      + Nuevo grupo de informes {#c-new-report-suite}
         + [Crear un grupo de informes](admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)
         + [Crear un grupo de grupos de informes](admin/c-manage-report-suites/c-new-report-suite/t-create-rs-group.md)
         + [Descargar la configuración del grupo de informes](admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)
         + [Configuración que no se copia desde un grupo de informes de origen](admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)
      + Plantillas del grupo de informes {#report-suite-templates}
         + [Resumen de las plantillas de grupos de informes](admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)
         + [Portal de agregadores](admin/c-manage-report-suites/c-report-suite-templates/aggregator-portal.md)
         + [Comercio](admin/c-manage-report-suites/c-report-suite-templates/commerce-admin.md)
         + [Contenido y medios](admin/c-manage-report-suites/c-report-suite-templates/content-media.md)
         + [Plantilla predeterminada](admin/c-manage-report-suites/c-report-suite-templates/default-rs-template.md)
         + [Servicios financieros](admin/c-manage-report-suites/c-report-suite-templates/financial-services.md)
         + [Portal de trabajo](admin/c-manage-report-suites/c-report-suite-templates/job-portal.md)
         + [Generación de posibles clientes](admin/c-manage-report-suites/c-report-suite-templates/lead-generation.md)
         + [Medios de soporte técnico](admin/c-manage-report-suites/c-report-suite-templates/support-media.md)
   + Configuración de la compañía {#company-settings}
      + [Información general de la configuración de la compañía](admin/company/c-company-settings.md)
      + [Administrador de seguridad](admin/company/security-manager.md)
      + [Servicios Web](admin/company/web-services-admin.md)
      + [Informes de Report Builder](admin/company/report-builder-reports-admin.md)
      + [Inicio de sesión único](admin/company/single-signon-admin.md)
      + [Ocultar grupos de informes](admin/company/c-hide-report-suites.md)
      + [Administrador de preferencias](admin/company/preferences-manager.md)
      + [Acciones pendientes](admin/company/pending-actions-admin.md)
      + [Niveles de acceso de las funcionalidades](admin/company/feature-access-levels.md)
   + Etiquetado de privacidad de gobernanza de datos {#data-governance}
      + [Flujo de trabajo de privacidad de datos de Adobe Analytics](admin/c-data-governance/an-gdpr-workflow.md)
      + [Preguntas frecuentes](admin/c-data-governance/gdpr-faq.md)
      + Etiquetado de datos {#data-labels}
         + [Etiquetas de privacidad de datos para componentes de Analytics](admin/c-data-governance/data-labeling/gdpr-labels.md)
         + [Etiquetado de datos de grupos de informes](admin/c-data-governance/data-labeling/gdpr-setup-reportsuite.md)
         + [Ver/administrar etiquetas de privacidad del grupo de informes](admin/c-data-governance/data-labeling/gdpr-view-settings.md)
         + [Prácticas recomendadas de etiquetado](admin/c-data-governance/data-labeling/gdpr-analytics-ids.md)
         + [Ejemplo de etiquetado](admin/c-data-governance/data-labeling/gdpr-labeling-example.md)
         + [Espacios de nombres](admin/c-data-governance/data-labeling/gdpr-namespaces.md)
      + [Exención de consentimiento de CNIL](admin/c-data-governance/cnil-consent-exemption.md)
   + Uso de llamada al servidor {#server-call-usage}
      + [Resumen del uso de llamadas al servidor](admin/c-server-call-usage/overage-overview.md)
      + [Ver uso de llamadas al servidor actual](admin/c-server-call-usage/server-call-usage-dashboard.md)
      + [Ver uso del grupo de informes](admin/c-server-call-usage/report-suite-usage.md)
      + [Alertas de uso de llamadas al servidor](admin/c-server-call-usage/scu-alerts.md)
      + [Preguntas frecuentes sobre uso de llamadas al servidor](admin/c-server-call-usage/overage-faq.md)
   + Administración de usuarios y productos (heredados) {#user-product-management}
      + [Administración de usuarios y productos (heredados)](admin/user-management2/user-management.md)
      + [Administración de cuentas de usuario, recursos y caducidades heredados](admin/user-management2/users-assets.md)
      + Migración de usuarios a Adobe Admin Console {#migrate-users}
         + [Migración de usuarios de Analytics a Admin Console](admin/user-management2/user-migration/c-migration-tool.md)
         + [Migración de cuentas de usuarios de Analytics para Adobe ID](admin/user-management2/user-migration/t-migrate-users.md)
         + [Migración de las cuentas de usuario de Analytics para Enterprise ID y Federated ID](admin/user-management2/user-migration/migrate-enterprise.md)
         + [Desactivación de inicios de sesión heredados](admin/user-management2/user-migration/t-disable-legacy-login.md)
         + [API afectadas por la migración](admin/user-management2/user-migration/developer.md)
+ [API de administración](c-admin-api/c-admin-api.md)
+ [Preguntas frecuentes sobre el final de la vida útil de la API de Adobe Analytics 1.4](c-admin-api/c-admin-14-api-eol.md)

