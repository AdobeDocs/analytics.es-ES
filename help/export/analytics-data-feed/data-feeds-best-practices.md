---
description: 'A continuación se indican algunas de las prácticas recomendadas para el procesamiento y la entrega de una fuente de datos. Recomendaciones '
keywords: Data Feed;best practices;traffic spike;hourly;ftp
solution: Analytics
title: Prácticas recomendadas e información general
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
translation-type: tm+mt
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# Prácticas recomendadas

A continuación se indican algunas de las prácticas recomendadas para el procesamiento y la entrega de una fuente de datos.

* Asegúrese de que comunica cualquier pico de tráfico anticipado con antelación. La latencia afecta directamente al tiempo de procesamiento de las fuentes de datos. Consulte [Programar un pico](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) de tráfico en la guía del usuario de administración.
* Las fuentes de datos no contienen un acuerdo de nivel de servicio a menos que se indique explícitamente en el contrato con Adobe. Las fuentes generalmente se entregan dentro de las horas siguientes a la fecha en que pasa la ventana del informe, aunque ocasionalmente pueden tardar hasta 12 horas o más.
* Asegúrese de que tiene suficiente espacio en su sitio de FTP. Elimine los archivos del destino de forma regular para que no se quede sin espacio en disco de forma involuntaria.
* Las fuentes por hora que utilizan la entrega de varios archivos procesan el proceso más rápido. Considere la posibilidad de utilizar fuentes de archivos múltiples por hora si una entrega oportuna es una prioridad alta para su organización.
* Si utiliza SFTP, no lea ni elimine archivos con un `.part` sufijo. El `.part` sufijo indica que el archivo se transfiere parcialmente. Una vez transferido el archivo, desaparece el `.part` sufijo.
* Si automatiza el proceso de ingestión de fuentes, considere la posibilidad de que un archivo se pueda transferir más de una vez. Los archivos duplicados pueden ser enviados por el usuario o raramente por Adobe.
