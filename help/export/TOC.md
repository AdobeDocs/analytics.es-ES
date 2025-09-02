---
product: analytics
audience: end-user
user-guide-title: Guía de exportación de Analytics
breadcrumb-title: Guía de exportación
user-guide-description: Obtenga información sobre el uso de fuentes de datos y Data Warehouse para recuperar el resultado de los datos.
source-git-commit: 9131c9ffbcf409620a67b36637367af22733b909
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 95%

---


# Guía de exportación de Adobe Analytics {#export}

+ [Guía de exportación de Analytics](home.md)
+ [Notas de la versión de Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
+ Feed de datos de Analytics {#analytics-data-feed}
   + [Resumen del feed de datos](analytics-data-feed/data-feed-overview.md)
   + [Creación de una fuente de datos](analytics-data-feed/create-feed.md)
   + [Administración de fuentes de datos](analytics-data-feed/df-manage-feeds.md)
   + [Administración de trabajos de fuentes de datos](analytics-data-feed/df-manage-jobs.md)
   + Contenido de feed de datos {#data-feed-contents}
      + [Resumen del contenido de la fuente de datos](analytics-data-feed/c-df-contents/datafeeds-contents.md)
      + [Calcular métricas](analytics-data-feed/c-df-contents/datafeeds-calculate.md)
      + [Referencia de columnas de datos](analytics-data-feed/c-df-contents/datafeeds-reference.md)
      + [Búsqueda de eventos de página](analytics-data-feed/c-df-contents/datafeeds-page-event.md)
      + [Búsquedas dinámicas](analytics-data-feed/c-df-contents/dynamic-lookups.md)
      + [Búsqueda de eVars de comercialización](analytics-data-feed/c-df-contents/merchandising-evar-lookup.md)
      + [Caracteres especiales](analytics-data-feed/c-df-contents/datafeeds-spec-chars.md)
      + [Visitas que llegan tarde](analytics-data-feed/c-df-contents/late-arriving-hits.md)
   + [Preguntas frecuentes sobre fuentes de datos](analytics-data-feed/df-faq.md)
   + [Prácticas recomendadas de fuentes de datos](analytics-data-feed/data-feeds-best-practices.md)
   + [Solución de problemas de las fuentes de datos](analytics-data-feed/troubleshooting.md)
+ Data Warehouse {#data-warehouse}
   + [Resumen de Data Warehouse](data-warehouse/data-warehouse.md)
   + [Añadir un grupo de usuarios de Data Warehouse](data-warehouse/t-dw-group.md)
   + Crear una solicitud de Data Warehouse {#dw-create-request}
      + [Crear una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md)
      + [Configuración general](/help/export/data-warehouse/create-request/dw-general-settings.md)
      + [Elabore su informe](/help/export/data-warehouse/create-request/dw-request-build-report.md)
      + [Destino del informe](/help/export/data-warehouse/create-request/dw-request-report-destinations.md)
      + [Opciones del informe](/help/export/data-warehouse/create-request/dw-request-report-options.md)
      + [Opciones de programación](/help/export/data-warehouse/create-request/dw-request-scheduling.md)
      + [Correo electrónico de notificación](/help/export/data-warehouse/create-request/dw-request-email.md)
   + [Hora del envío de la solicitud](data-warehouse/delivery-time.md)
   + [Archivo de datos Tableau](data-warehouse/t-tableau.md)
   + [Ordenar por métrica](data-warehouse/sorting-by-metric.md)
   + [Administrar solicitudes de Data Warehouse](data-warehouse/data-warehouse-requests-manage.md)
   + [Componentes admitidos en Data Warehouse](data-warehouse/component-support.md)
   + [Prácticas recomendadas de Data Warehouse](data-warehouse/data-warehouse-bp.md)
+ FTP y SFTP {#ftp-and-sftp}
   + [Utilizar FTP y SFTP con Adobe Experience Cloud](ftp-and-sftp/ftp-overview.md)
   + Configurar cuentas FTP alojadas en Adobe {#set-up-ftp-accounts}
      + [Resumen de configuración de cuentas de FTP](ftp-and-sftp/c-set-up-ftp-accounts/ftp-accounts.md)
      + [Clasificaciones](ftp-and-sftp/c-set-up-ftp-accounts/ftp-saint.md)
      + [Fuentes de datos](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datasources.md)
      + [Fuentes de datos](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datafeeds.md)
      + [Informes entregados por Data Warehouse](ftp-and-sftp/c-set-up-ftp-accounts/ftp-dw-reports.md)
      + [Informes entregados por el Report Builder](ftp-and-sftp/c-set-up-ftp-accounts/ftp-arb-reports.md)
      + [Participación de los servicios de ingeniería en FTP](ftp-and-sftp/c-set-up-ftp-accounts/ftp-eng-services.md)
   + [Límites de FTP y retención de datos](ftp-and-sftp/ftp-limits.md)
   + [Eliminación de datos y cuentas de FTP](ftp-and-sftp/ftp-delete.md)
   + [Restauración de datos y cuentas de FTP eliminados](ftp-and-sftp/ftp-restore.md)
   + [Actualización de servidores FTP de Adobe](ftp-and-sftp/ftp-upgrade.md)
   + [Uso del modo FTP pasivo](ftp-and-sftp/ftp-passive.md)
   + [Tiempos de procesamiento de FTP](ftp-and-sftp/ftp-processing.md)
   + Protocolo seguro de transferencias de archivos {#secure-file-transfer-protocol}
      + [Actualización de servicios SFTP: preguntas frecuentes](ftp-and-sftp/c-sftp/sftp-upgrade.md)
      + [Resumen del Protocolo seguro de transferencia de archivos (SFTP)](ftp-and-sftp/c-sftp/ftp-sftp.md)
      + [Conéctese a una cuenta de FTP de Adobe mediante un SFTP](ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
      + [Envío de datos de Adobe a una cuenta de FTP externa mediante un SFTP](ftp-and-sftp/c-sftp/ftp-sftp-transfer.md)
      + [Envío de solicitudes de Data Warehouse a los servidores SFTP](ftp-and-sftp/c-sftp/ftp-sftp-dw.md)
      + [Conectarse a Adobe a través de un SFTP sin contraseña](ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
+ [Descargas de Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=es)
+ [API de Adobe Analytics](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)
+ [Report Builder](https://experienceleague.adobe.com/es/docs/analytics/analyze/report-builder/rb-overview)
