---
description: Las fuentes de datos son una exportación de los datos sobre el flujo de navegación que Adobe recibe. Existen las fuentes de datos estándar y las personalizadas.
keywords: ftp;sftp
title: Fuentes de datos
feature: FTP Export
exl-id: 286050fa-e197-4b70-b167-da6921615c1b
TQID: 'https://experienceleague.adobe.com/JYiAXR-SbFNV3xQQ5Y1Qv10kVWpFJRWmuOvERcQ-zP4'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 331
ht-degree: 27%

---

# Fuentes de datos

>[!NOTE]
>
>La siguiente información está relacionada con los tipos de destino FTP y SFTP. FTP y SFTP son tipos de destino heredados. Al configurar una fuente de datos, debe utilizar un tipo de destino de nube, que es más seguro. Para obtener más información sobre la configuración de tipos de destinos de nube para una fuente de datos, consulte [Crear una fuente de datos](/help/export/analytics-data-feed/create-feed.md).

Las fuentes de datos son una exportación de los datos sobre el flujo de navegación que Adobe recibe. Existen las [fuentes de datos](/help/export/analytics-data-feed/data-feed-overview.md) estándar y las personalizadas.

Si ha comprado Adobe Data Warehouse, con [!UICONTROL fuentes de datos estándar] puede configurar sus propias fuentes de datos de Analytics. Se pueden enviar a cualquier cuenta de FTP (configurada por Adobe o un FTP externo). Los Servicios de ingeniería de Adobe ofrecen [!UICONTROL Fuentes de datos] personalizadas que se pueden enviar prácticamente por cualquier medio.

[!UICONTROL Fuente de datos] Las cuentas de FTP permiten 10 GB (de forma predeterminada). Todas las demás cuentas de FTP estándar tienen 50 MB de forma predeterminada. En los casos en los que los clientes utilizan la cuenta FTP para el uso previsto, algunos usuarios con grandes cantidades de tráfico pueden rellenar rápidamente estas cuentas. Cuando una cuenta de FTP está llena, no se les pueden insertar archivos adicionales. Por lo tanto, los archivos que se envíen a esa cuenta de FTP ([!UICONTROL fuentes de datos], solicitudes de Data Warehouse, etc.) no se entregarán. Este es un motivo por el que es importante administrar la cuenta de FTP de Adobe eliminando los archivos que se han recibido y descargado.

Cuando una cuenta de FTP está llena, debe descargar y quitar los archivos actuales e informar a Adobe de que se ha borrado el espacio. A continuación, Adobe puede reenviar los archivos que no se hayan entregado. Algunas herramientas, como Data Warehouse, permiten a los usuarios reenviar estos archivos. Es posible que la reentrega no requiera la participación de Adobe. Si su cuenta de FTP parece estar llenándose a menudo, póngase en contacto con el Servicio de atención al cliente de Adobe, que puede sugerirle alternativas de entrega que pueden incluir el aumento del espacio de FTP y la cuota de número de archivo en la cuenta.
