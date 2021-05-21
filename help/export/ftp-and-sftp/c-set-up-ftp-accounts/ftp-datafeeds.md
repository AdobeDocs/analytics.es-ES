---
description: Las fuentes de datos son una exportación de los datos sobre el flujo de navegación que Adobe recibe. Existen las fuentes de datos estándar y las personalizadas.
keywords: ftp;sftp
title: Archivo de fuentes de datos
uuid: 3c70eea3-ca59-4aa5-9b11-64e1bb677bfa
exl-id: 286050fa-e197-4b70-b167-da6921615c1b
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '280'
ht-degree: 100%

---

# Archivo de fuentes de datos

Las fuentes de datos son una exportación de los datos sobre el flujo de navegación que Adobe recibe. Existen las [fuentes de datos](/help/export/analytics-data-feed/data-feed-overview.md) estándar y las personalizadas.

Si ha comprado Adobe Data Warehouse, con [!UICONTROL fuentes de datos estándar] puede configurar sus propias fuentes de datos de Analytics. Se pueden enviar a cualquier cuenta de FTP (una que haya configurado Adobe o una de un FTP externo). Los servicios de ingeniería de Adobe ofrecen [!UICONTROL fuentes de datos] personalizadas que se pueden enviar prácticamente por cualquier medio.

Las cuentas de FTP de [!UICONTROL fuentes de datos ]permiten, de forma predeterminada, el uso de 10 GB. Las demás cuentas de FTP estándar tienen una capacidad predeterminada de 50 MB. En casos en que un cliente use la cuenta de FTP para los fines adecuados, algunos usuarios con grandes cantidades de tráfico pueden llenar rápidamente estas cuentas. Cuando una cuenta de FTP está llena, ya no puede recibir más archivos. Por lo tanto, los archivos que se envíen a esa cuenta de FTP ([!UICONTROL fuentes de datos], solicitudes de Data Warehouse, etc.) no se entregarán. Esto explica la importancia de eliminar de la cuenta de FTP de Adobe los archivos que se han recibido y descargado.

Cuando una cuenta de FTP está llena, hay que descargar y eliminar los archivos que contenga e informar a Adobe de que se ha liberado espacio. De este modo, Adobe puede volver a enviar los archivos que no se han entregado. Algunas herramientas, como el almacén de datos, permiten a los usuarios volver a enviar estos archivos. Es decir, para volver a enviar algo no es estrictamente necesaria la participación de Adobe. Si la cuenta de FTP parece llenarse con frecuencia, póngase en contacto con el servicio de atención al cliente de Adobe, que podrá sugerir alternativas de entrega, como incrementar el espacio del FTP y la cuota del número de archivos de la cuenta.
