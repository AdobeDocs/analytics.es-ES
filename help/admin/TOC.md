---
product: analytics
audience: admin
user-guide-title: Guía de administración de Analytics
breadcrumb-title: Guía de administración
user-guide-description: Obtenga información acerca de las tareas de administración de Analytics, como la gestión de usuarios y productos en Experience Cloud Admin Console, la configuración de grupos de informes y mucho más.
source-git-commit: 01aa0959a7ddd8d5a29c838bdbc771435784c9e6
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 94%

---


# Guía de administración de Adobe Analytics {#admin}

+ [Guía de administración de Analytics](home.md)
+ [Notas de la versión de Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
+ Consola de administración de Adobe {#admin-console}
   + [Información general](admin-console/home.md)
   + [Guía de administración inicial de Adobe Analytics](admin-console/first-admin-guide.md)
   + [Funciones de administrador en Adobe Analytics](admin-console/admin-roles-in-analytics.md)
   + Resumen de permisos de las herramientas de Analytics {#permissions}
      + [Permisos de Analytics en Admin Console](admin-console/permissions/summary-tables.md)
      + [Perfiles de producto para Adobe Analytics](admin-console/permissions/product-profile.md)
      + [Permisos de perfil de productos para las herramientas de grupo de informes](admin-console/permissions/report-suite-tools.md)
      + [Permisos de perfil de productos para las herramientas de Analytics](admin-console/permissions/analytics-tools.md)
+ Herramientas de administración de Analytics {#admin-tools}
   + [Información general sobre las herramientas de administración](admin/c-admin-tools.md)
   + [Facturación](admin/billing-admin.md)
   + [Administrador de códigos](admin/code-manager-admin.md)
   + [Fuentes de datos](admin/data-sources.md)
   + [Excluir por dirección IP](admin/exclude-ip.md)
   + [Registros](admin/logs.md)
   + [Administrador de actividades de creación de informes](admin/reporting-activity.md)
   + Administrador del grupo de informes {#manage-report-suites}
      + Editar la configuración de un grupo de informes {#edit-report-suite}
         + General {#report-suite-general}
            + [Configuración general de la cuenta](admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)
            + [Filtros URL internos](admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)
            + [Personalizar calendario](admin/c-manage-report-suites/c-edit-report-suites/general/custom-calendar.md)
            + Detección de búsqueda de pago {#paid-search-detection}
               + [Resumen de detección de búsqueda de pago](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md)
               + [Configurar la detección de búsqueda pagada](admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/t-paid-search-detection.md)
            + [Personalizar menús](admin/c-manage-report-suites/c-edit-report-suites/general/customize-menus.md)
            + Reglas de procesamiento {#c-processing-rules}
               + [Resumen de las reglas de procesamiento](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)
               + Reglas de procesamiento {#c-processing-rules-configuration}
                  + [Funcionamiento de las reglas de procesamiento](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/processing-rules-about.md)
                  + [Crear reglas de procesamiento](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)
                  + [Ver las reglas de procesamiento activas](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-view.md)
                  + [Ver el historial de reglas de procesamiento](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rule-view-history.md)
                  + [Restaurar reglas de procesamiento](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-restore.md)
                  + [Copiar reglas de procesamiento en otro grupo de informes](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md)
                  + [Dimensiones disponibles para las reglas de procesamiento](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rule-dimensions.md)
               + Ejemplos de reglas de procesamiento {#processing-rules-examples}
                  + [Ejemplos de reglas de procesamiento](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-examples.md)
                  + [Rellenar un ID de campaña desde un parámetro de cadena de consulta](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-populate-campaign-id.md)
                  + [Definir el evento de vistas de producto desde la página de información general del producto](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/setting-the-product-view-event.md)
                  + [Agregar una subcategoría concatenando la categoría y el nombre de página](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/subcategory-concatenating.md)
                  + [Determinar una ruta copiando un valor eVar en una propiedad](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-determining-path.md)
                  + [Limpiar los valores de un informe](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md)
                  + [Rellenar términos de búsqueda internos utilizando un parámetro de cadena de consulta](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-populating-internal-search.md)
                  + [Copiar una variable de datos de contexto en una eVar](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md)
                  + [Definir un evento con una variable de datos de contexto](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md)
                  + [Eliminar un evento de una visita](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-remove-event.md)
               + [Consejos y sugerencias de reglas de procesamiento](admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-tips.md)
            + Reglas de bots {#bot-removal}
               + [Eliminación de bots](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md)
               + [Resumen sobre reglas de Bot](admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md)
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
            + [Habilitar los informes de variables de tráfico](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/t-traffic-variable.md)
            + [Clasificaciones de tráfico](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-classifications.md)
            + [Descripciones personalizadas de informe](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/custom-desc-admin.md)
         + Conversión {#conversion-variables}
            + [Variables de conversión](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-var-admin.md)
            + [Métodos de búsqueda](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/finding-methods.md)
            + [Clasificaciones de conversión](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/conversion-classifications.md)
            + Variable única de visitante {#unique-visitor-variable}
               + [Especificar la variable única de visitante](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/t-unique-visitor-variable.md)
               + [Caso de uso: Extracción de ID de visitantes](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/unique-visitor-variable-admin/extract-visitorids-usecase.md)
            + Eventos de éxito {#success-events}
               + [Resumen de los eventos de éxito](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md)
               + [Configurar eventos de éxito](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/t-success-events.md)
               + [Información sobre el cambio de tipo de evento](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/event-type.md)
            + [Jerarquías de clasificación](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/classification-hierarchies.md)
            + [Variables de lista](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)
            + [eVars de comercialización](admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/merchandising-evars.md)
         + Canales de marketing {#marketing-channels}
            + [Administrador de canales de mercadotecnia](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md)
            + [Reglas de procesamiento de canal de marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)
            + [Clasificaciones de canal de marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/classifications-mchannel.md)
            + [Caducidad del canal de marketing](admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/visitor-engagement.md)
         + Administración del tráfico {#traffic-management}
            + [Información general](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/traffic-management.md)
            + [Programar picos](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md)
            + [Tráfico permanente](admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-permanent.md)
         + [Métricas predeterminadas](admin/c-manage-report-suites/c-edit-report-suites/default-metrics.md)
         + [Administración de aplicaciones](admin/c-manage-report-suites/c-edit-report-suites/mobile-management.md)
         + [Administración de medios](admin/c-manage-report-suites/c-edit-report-suites/media-management.md)
         + [Página de ](admin/c-manage-report-suites/c-edit-report-suites/activity-map.md)
         + [AEM](admin/c-manage-report-suites/c-edit-report-suites/adobe-experience-manager.md)
         + [Adobe Campaign](admin/c-manage-report-suites/c-edit-report-suites/adobe-campaign.md)
         + [Creación de informes de privacidad](admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md)
         + Administración de Document Cloud {#doc-cloud-mgt}
            + [Configuración de Document Cloud con Adobe Analytics](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-mgt.md)
            + [Configuración de informes de Document Cloud](admin/c-manage-report-suites/c-edit-report-suites/document-cloud-config.md)
         + [Configuración de Advertising Analytics](admin/c-manage-report-suites/c-edit-report-suites/advertising-analytics-config.md)
         + Tiempo real {#real-time-reports}
            + [Resumen de informes en tiempo real](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md)
            + [Configuración de informes en tiempo real](admin/c-manage-report-suites/c-edit-report-suites/realtime/t-realtime-admin.md)
            + [Métricas y dimensiones en tiempo real compatibles](admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md)
      + [Administrar grupos de informes](admin/c-manage-report-suites/report-suites-admin.md)
      + [Grupos de informes globales y de resumen](admin/c-manage-report-suites/rollup-report-suite.md)
      + [Guardar una búsqueda de grupos de informes](admin/c-manage-report-suites/t-report-suite-saved-search.md)
      + [Descargar la configuración de grupo de informes](admin/c-manage-report-suites/t-download-rs-settings.md)
      + Nuevo grupo de informes {#c-new-report-suite}
         + [Crear un grupo de informes](admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)
         + [Crear un grupo de informes resumidos](admin/c-manage-report-suites/c-new-report-suite/t-rollups.md)
         + [Crear un grupo de grupos de informes](admin/c-manage-report-suites/c-new-report-suite/t-create-rs-group.md)
         + [Descargar la configuración del grupo de informes](admin/c-manage-report-suites/c-new-report-suite/new-report-suite.md)
         + [Configuración que no se copia desde un grupo de informes de origen](admin/c-manage-report-suites/c-new-report-suite/settings-not-copied-from-rs.md)
      + Plantillas de grupos de informes {#report-suite-templates}
         + [Resumen de las plantillas de grupos de informes](admin/c-manage-report-suites/c-report-suite-templates/report-suite-templates.md)
         + [Portal de agregadores](admin/c-manage-report-suites/c-report-suite-templates/aggregator-portal.md)
         + [Comercio](admin/c-manage-report-suites/c-report-suite-templates/commerce-admin.md)
         + [Contenido y medios](admin/c-manage-report-suites/c-report-suite-templates/content-media.md)
         + [Plantilla predeterminada](admin/c-manage-report-suites/c-report-suite-templates/default-rs-template.md)
         + [Servicios financieros](admin/c-manage-report-suites/c-report-suite-templates/financial-services.md)
         + [Portal de trabajo](admin/c-manage-report-suites/c-report-suite-templates/job-portal.md)
         + [Generación de posibles clientes](admin/c-manage-report-suites/c-report-suite-templates/lead-generation.md)
         + [Medios de soporte técnico](admin/c-manage-report-suites/c-report-suite-templates/support-media.md)
   + Configuración de la empresa {#company-settings}
      + [Resumen de la configuración de la empresa](admin/company/c-company-settings.md)
      + [Administrador de seguridad](admin/company/security-manager.md)
      + [Servicios Web](admin/company/web-services-admin.md)
      + [Informes de Report Builder](admin/company/report-builder-reports-admin.md)
      + [Inicio de sesión único](admin/company/single-signon-admin.md)
      + [Promoción conjunta de marca](admin/company/co-branding-admin.md)
      + [Ocultar grupos de informes](admin/company/c-hide-report-suites.md)
      + [Administrador de preferencias](admin/company/preferences-manager.md)
      + [Acciones pendientes](admin/company/pending-actions-admin.md)
      + [Niveles de acceso de las funcionalidades](admin/company/feature-access-levels.md)
   + Uso de llamadas al servidor {#server-call-usage}
      + [Resumen del uso de llamadas al servidor](admin/c-server-call-usage/overage-overview.md)
      + [Ver uso de llamadas al servidor actual](admin/c-server-call-usage/server-call-usage-dashboard.md)
      + [Ver uso del grupo de informes](admin/c-server-call-usage/report-suite-usage.md)
      + [Alertas de uso de llamadas al servidor](admin/c-server-call-usage/scu-alerts.md)
      + [Preguntas frecuentes sobre uso de llamadas al servidor](admin/c-server-call-usage/overage-faq.md)
   + Administración de usuarios y productos (heredados) {#user-product-management}
      + [Administración de usuarios y productos  (Heredados)](admin/user-management2/user-management.md)
      + Migración de usuarios a Adobe Admin Console {#migrate-users}
         + [Migración de usuarios de Analytics a Admin Console](admin/user-management2/user-migration/c-migration-tool.md)
         + [Migración de cuentas de usuarios de Analytics para Adobe ID](admin/user-management2/user-migration/t-migrate-users.md)
         + [Migración de las cuentas de usuario de Analytics para Enterprise ID y Federated ID](admin/user-management2/user-migration/migrate-enterprise.md)
         + [Desactivación de inicios de sesión heredados](admin/user-management2/user-migration/t-disable-legacy-login.md)
         + [API afectadas por la migración](admin/user-management2/user-migration/developer.md)
+ [API de administración](c-admin-api/c-admin-api.md)

