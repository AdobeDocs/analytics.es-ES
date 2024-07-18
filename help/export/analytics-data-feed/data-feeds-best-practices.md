---
description: A continuación se indican algunas de las prácticas recomendadas para el procesamiento y la entrega de una fuente de datos.
keywords: Fuente de datos;prácticas recomendadas;pico de tráfico;por hora;ftp
title: Prácticas recomendadas e información general
feature: Data Feeds
exl-id: 5f6fbc13-b176-4f69-8f2d-7accc6e6ac2d
source-git-commit: 6b42fc4a383b05a3630cbba7c5bce6b4561a9419
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 88%

---

# Prácticas recomendadas de fuentes de datos

A continuación se indican algunas de las prácticas recomendadas para el procesamiento y la entrega de una fuente de datos.

* Asegúrese de que comunica cualquier pico de tráfico anticipado con antelación. La latencia afecta directamente al tiempo de procesamiento de las fuentes de datos. Consulte [Programar un pico de tráfico](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md) en la guía del usuario de administración.

* Las fuentes de datos no contienen un acuerdo de nivel de servicio a menos que se indique explícitamente en el contrato con Adobe. Las fuentes generalmente se entregan dentro de las horas siguientes a la fecha en que pasa la ventana del informe, aunque ocasionalmente pueden tardar hasta 12 horas o más.

* Las fuentes por hora que utilizan la entrega de varios archivos realizan el proceso más rápido. Considere la posibilidad de utilizar fuentes de archivos múltiples por hora si una entrega a tiempo es de gran importancia para su organización.

* Si automatiza el proceso de introducción de fuentes, considere la posibilidad de que las visitas y los archivos se puedan transferir más de una vez. El proceso de ingesta de fuentes debe gestionar las visitas y los archivos duplicados sin tener que borrar o duplicar datos. Se recomienda utilizar la combinación de las columnas `hitid_high` y `hitid_low` para identificar una visita de forma exclusiva. 

  En casos excepcionales, puede ver valores `hitid_high` y `hitid_low` duplicados. Si esto sucede, confirme que el archivo no se ha enviado ni procesado anteriormente. Si solo algunas de las filas de un archivo están duplicadas, considere la posibilidad de añadir `visit_num` y `visit_page_num` para ayudar a determinar la exclusividad.

* Si utiliza un FTP (no recomendado), asegúrese de que dispone de suficiente espacio en su sitio FTP. Elimine los archivos del destino de forma regular para que no se quede sin espacio en disco.

* Si utiliza SFTP (no recomendado), no lea ni elimine archivos con un sufijo `.part`. El sufijo `.part` indica que el archivo se transfiere parcialmente. Una vez transferido el archivo, desaparece el sufijo `.part`.