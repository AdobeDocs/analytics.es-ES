---
product: analytics
audience: end-user
user-guide-title: Guía de exportación de Analytics
breadcrumb-title: Guía de exportación
user-guide-description: Utilice las fuentes de datos para recibir una exportación diaria o por hora de datos sin procesar. Utilice Data Warehouse para recuperar un extracto de datos en una hoja de cálculo. Aprenda a usar los protocolos FTP y SFTP para transferir archivos entre equipos y servidores.
source-git-commit: 70a1d61a6e9af27c449876ac4cf4d7504659be3a
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 100%

---


# Guía de exportación de Adobe Analytics {#export}

+ [Guía de exportación de Analytics](home.md)
+ [Notas de la versión de Analytics](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=es)
+ Fuente de datos de Analytics {#analytics-data-feed}
   + [Resumen de la fuente de datos](analytics-data-feed/data-feed-overview.md)
   + [Creación o edición de una fuente de datos](analytics-data-feed/create-feed.md)
   + [Administración de fuentes de datos](analytics-data-feed/df-manage-feeds.md)
   + [Administración de trabajos de fuentes de datos](analytics-data-feed/df-manage-jobs.md)
   + Contenido de la fuente de datos {#data-feed-contents}
      + [Resumen del contenido de la fuente de datos](analytics-data-feed/c-df-contents/datafeeds-contents.md)
      + [Calcular métricas](analytics-data-feed/c-df-contents/datafeeds-calculate.md)
      + [Referencia de columnas de datos](analytics-data-feed/c-df-contents/datafeeds-reference.md)
      + [Búsqueda de eventos de página](analytics-data-feed/c-df-contents/datafeeds-page-event.md)
      + [Búsqueda de atributos móviles](analytics-data-feed/c-df-contents/mobile-attributes-lookup.md)
      + [Búsqueda de eVars de comercialización](analytics-data-feed/c-df-contents/merchandising-evar-lookup.md)
      + [Caracteres especiales](analytics-data-feed/c-df-contents/datafeeds-spec-chars.md)
      + [Visitas que llegan tarde](analytics-data-feed/c-df-contents/late-arriving-hits.md)
   + [Preguntas frecuentes sobre fuentes de datos](analytics-data-feed/df-faq.md)
   + [Prácticas recomendadas de fuentes de datos](analytics-data-feed/data-feeds-best-practices.md)
   + [Solución de problemas de las fuentes de datos](analytics-data-feed/troubleshooting.md)
+ Data Warehouse {#data-warehouse}
   + [Resumen de Data Warehouse](data-warehouse/data-warehouse.md)
   + [Añadir un grupo de usuarios de Data Warehouse](data-warehouse/t-dw-group.md)
   + [Crear una solicitud de Data Warehouse](data-warehouse/t-dw-create-request.md)
   + [Hora del envío de la solicitud](data-warehouse/delivery-time.md)
   + [Archivo de datos Tableau](data-warehouse/t-tableau.md)
   + [Ordenar por métrica](data-warehouse/sorting-by-metric.md)
   + [Programar una solicitud recurrente](data-warehouse/dw-schedule-recurring.md)
   + [Administrar solicitudes de Data Warehouse](data-warehouse/data-warehouse-requests-manage.md)
   + [Componentes admitidos en Data Warehouse](data-warehouse/component-support.md)
   + [Preguntas frecuentes sobre Data Warehouse](data-warehouse/faq.md)
   + [Prácticas recomendadas de Data Warehouse](data-warehouse/data-warehouse-bp.md)
+ FTP y SFTP {#ftp-and-sftp}
   + [Utilizar FTP y SFTP con Adobe Experience Cloud](ftp-and-sftp/ftp-overview.md)
   + Configuración de cuentas FTP alojadas en Adobe {#set-up-ftp-accounts}
      + [Resumen de configuración de cuentas de FTP](ftp-and-sftp/c-set-up-ftp-accounts/ftp-accounts.md)
      + [Clasificaciones](ftp-and-sftp/c-set-up-ftp-accounts/ftp-saint.md)
      + [Fuentes de datos](ftp-and-sftp/c-set-up-ftp-accounts/ftp-datasources.md)
      + [Data Connectors](ftp-and-sftp/c-set-up-ftp-accounts/ftp-genesis.md)
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
   + Protocolo seguro de transferencia de archivos {#secure-file-transfer-protocol}
      + [Actualización de servicios SFTP: preguntas frecuentes](ftp-and-sftp/c-sftp/sftp-upgrade.md)
      + [Resumen del Protocolo seguro de transferencia de archivos (SFTP)](ftp-and-sftp/c-sftp/ftp-sftp.md)
      + [Conéctese a una cuenta de FTP de Adobe mediante un SFTP](ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
      + [Envío de datos de Adobe a una cuenta de FTP externa mediante un SFTP](ftp-and-sftp/c-sftp/ftp-sftp-transfer.md)
      + [Envío de solicitudes de Data Warehouse a los servidores SFTP](ftp-and-sftp/c-sftp/ftp-sftp-dw.md)
      + [Conectarse a Adobe a través de un SFTP sin contraseña](ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
+ [Descargas de Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=es)
+ [API de Adobe Analytics](https://www.adobe.io/apis/experiencecloud/analytics/docs.html)
+ [Report Builder](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/home.html?lang=es)
