---
description: Configure y utilice cuentas de FTP alojadas en Adobe.
keywords: ftp;sftp
title: Resumen de configuración de cuentas de FTP
uuid: e5524619-248a-4aae-9f64-cd7d33f3c407
exl-id: 55f942fe-cb06-43e1-bd3c-57d6786278b7
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '290'
ht-degree: 100%

---

# Resumen de configuración de cuentas de FTP

Configure y utilice cuentas de FTP alojadas en Adobe.

Adobe mantiene clústeres de FTP con un alto nivel de disponibilidad y rendimiento que están especialmente diseñados para mejorar la fiabilidad de las transferencias de archivos sin dejar de ofrecer un rendimiento excelente.

Como los eventos de mantenimiento están programados, los clientes de Adobe reciben notificaciones de mantenimiento a través del proceso estándar. Para garantizar el correcto funcionamiento de los sistemas de FTP de Adobe y seguir ofreciendo seguridad, fiabilidad y un alto rendimiento en las transferencias de datos, Adobe exige el cumplimiento de las siguientes normas:

* La mayoría de las cuentas de FTP de Adobe (clasificaciones, fuentes de datos y otras) se habilitan automáticamente cuando se configura la característica en cuestión. En el caso de las cuentas de entrega de archivos generales y de fuentes de datos, el servicio de atención al cliente de Adobe puede configurarle una nueva cuenta de FTP. La finalidad de este proceso es garantizar la seguridad y la disponibilidad de espacio en la cuenta de FTP.
* Después de haberlos transferido correctamente a sus sistemas, los usuarios deben eliminar los datos que Adobe envió a la cuenta de FTP.
* Se debe informar a Adobe cuando las cuentas de FTP ya no se necesiten para proceder a su desactivación.

El nombre de host del de FTP de Adobe es [!DNL ftp.omniture.com] o [!DNL ftp2.omniture.com].

Esta información, junto con el nombre de usuario y la contraseña, se debe suministrar en [!UICONTROL Experience Cloud] (en el caso de las clasificaciones y fuentes de datos). También se puede delegar esta tarea en un representante de Adobe encargado de configurar la cuenta. Si no sabe qué dirección de FTP usar, póngase en contacto con el administrador de cuentas de Adobe, que le indicará la dirección correcta. Además, en el caso de las cuentas de clasificaciones y fuentes de datos, Adobe no procesa los archivos de FTP a ninguna hora determinada del día, sino que utiliza un script que sondea continuamente las cuentas de FTP en busca de nuevos procesos de archivo. Los archivos cargados en estas cuentas se procesan lo más rápido posible.
