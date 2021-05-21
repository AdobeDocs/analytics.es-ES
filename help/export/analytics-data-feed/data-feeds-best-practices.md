---
description: 'A continuación se indican algunas de las prácticas recomendadas para el procesamiento y la entrega de una fuente de datos. Recomendaciones '
keywords: Fuente de datos;prácticas recomendadas;pico de tráfico;por hora;ftp
title: Prácticas recomendadas e información general
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
exl-id: 5f6fbc13-b176-4f69-8f2d-7accc6e6ac2d
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '219'
ht-degree: 100%

---

# Prácticas recomendadas

A continuación se indican algunas de las prácticas recomendadas para el procesamiento y la entrega de una fuente de datos.

* Asegúrese de que comunica cualquier pico de tráfico anticipado con antelación. La latencia afecta directamente al tiempo de procesamiento de las fuentes de datos. Consulte [Programar un pico de tráfico](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) en la guía del usuario de administración.
* Las fuentes de datos no contienen un acuerdo de nivel de servicio a menos que se indique explícitamente en el contrato con Adobe. Las fuentes generalmente se entregan dentro de las horas siguientes a la fecha en que pasa la ventana del informe, aunque ocasionalmente pueden tardar hasta 12 horas o más.
* Asegúrese de que tiene suficiente espacio en su sitio de FTP. Elimine los archivos del destino de forma regular para que no se quede sin espacio en disco.
* Las fuentes por hora que utilizan la entrega de varios archivos realizan el proceso más rápido. Considere la posibilidad de utilizar fuentes de archivos múltiples por hora si una entrega a tiempo es de gran importancia para su organización.
* Si utiliza SFTP, no lea ni elimine archivos con un sufijo `.part`. El sufijo `.part` indica que el archivo se transfiere parcialmente. Una vez transferido el archivo, desaparece el sufijo `.part`.
* Si automatiza el proceso de introducción de fuentes, considere la posibilidad de que un archivo se pueda transferir más de una vez. Los usuarios o, en algunos casos, Adobe, pueden enviar los archivos duplicados.
