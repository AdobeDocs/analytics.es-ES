---
title: Visitas que llegan tarde
description: Descubra cómo las fuentes de datos tratan las visitas que llegan tarde.
translation-type: tm+mt
source-git-commit: 7db88bce7b3d0f90fa5b50664d7c0c23904348c0

---


# Visitas que llegan tarde

Los datos históricos pueden llegar después de que un trabajo de fuente de datos termine de procesarse durante una hora o un día determinados, por ejemplo, mediante visitas con marca de hora o fuentes de datos. Las visitas que llegan tarde son una configuración de personalización del servidor proporcionada por Adobe para ayudar a incluir estos datos en las fuentes de datos.

## Cómo funcionan las visitas que llegan tarde

Cuando una fuente de datos procesa normalmente los datos, solo observa los datos dentro de su ventana de informes (generalmente la hora o el día más recientes). Si los datos llegan después de que una fuente termine de procesar esa ventana de informes, nunca se incluirán en ninguna fuente de datos.

Con las visitas que llegan tarde activadas, el método de procesamiento cambia para incluir estos datos. Cada vez que una fuente de datos procesa los datos, observa las visitas tardías que han llegado y las procesa en el siguiente archivo de fuente de datos enviado a su sitio FTP.

## Habilitación de las visitas que llegan tarde

Adobe puede habilitar manualmente las visitas que llegan tarde en las fuentes de datos individuales. Antes de hacerlo, considere lo siguiente:

* Los datos de diferentes días aparecen con frecuencia en las fuentes de datos cuando las visitas que llegan tarde están habilitadas. Asegúrese de que la plataforma que utiliza para la ingesta de fuentes de datos puede dar cabida a datos de diferentes días dentro del mismo archivo.
* Las visitas que llegan tarde aumentan el tiempo de procesamiento. Normalmente, este retraso es inferior a una hora, pero puede ser de varias horas o más si el grupo de informes recibe un gran número de visitas que llegan tarde. Adobe recomienda que no se active esta configuración si la llegada oportuna de fuentes de datos es imprescindible para el flujo de trabajo de su organización.
* Si se vuelve a procesar un archivo de fuente de datos, las visitas que llegan tarde y que se incluyeron en el archivo original no se incluirán en el archivo reprocesado.

Si desea habilitar las visitas que llegan tarde para una fuente de datos recurrente existente, un usuario de asistencia técnica debe ponerse en contacto con el Servicio de atención al cliente e incluir lo siguiente:

* Nota que le gustaría habilitar las visitas que llegan tarde para una fuente de datos específica
* ID del grupo de informes
* Nombre de la fuente de datos
