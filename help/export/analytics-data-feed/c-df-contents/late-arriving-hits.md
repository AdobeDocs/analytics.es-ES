---
title: Visitas que llegan tarde
description: Descubra cómo las fuentes de datos tratan las visitas que llegan tarde.
feature: Data Feeds
exl-id: c99a702b-2aaa-47a6-958a-1e5ab66961ba
source-git-commit: 81cbb115d50e1f55a67aac8b107749d0a5a5928b
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 85%

---

# Visitas que llegan tarde

Los datos históricos pueden llegar después de que un trabajo de fuente de datos termine de procesarse durante una hora o un día determinados, por ejemplo, mediante visitas con marca de tiempo u origen de datos. Las visitas que llegan tarde son una configuración de personalización backend proporcionada por Adobe para ayudar a incluir estos datos en las fuentes de datos.

## Funcionamiento de las visitas que llegan tarde

Cuando una fuente de datos procesa la información con normalidad, solo utiliza los datos dentro de su intervalo de informes (generalmente la hora o el día más recientes). Si los datos llegan después de que una fuente procese ese intervalo de informes, nunca se incluirán en ninguna fuente de datos.

Cuando las visitas que llegan tarde se encuentran habilitadas, el método de procesamiento cambia para incluir estos datos. Cada vez que una fuente de datos procesa la información, utiliza las visitas que llegan tarde y las procesa en el siguiente archivo de fuente de datos enviado a su sitio FTP.

## Habilitación de las visitas que llegan tarde

Adobe puede habilitar manualmente las visitas que llegan tarde en las fuentes de datos individuales. Antes de hacerlo, tenga en cuenta lo siguiente:

* Los datos de diferentes días aparecen con frecuencia en las fuentes de datos cuando las visitas que llegan tarde están habilitadas. Compruebe que la plataforma que utiliza para la ingesta de fuentes de datos puede admitir datos de diferentes días dentro del mismo archivo.
* Si se vuelve a procesar un archivo de fuente de datos, las visitas que llegan tarde y que se incluyeron en el archivo original se incluirán en el archivo reprocesado cuando el reprocesamiento se produzca en los primeros 5 días. Después de 5 días, las visitas que llegan tarde no se incluyen en el archivo reprocesado.

Si desea habilitar las visitas que llegan tarde para una fuente de datos recurrente que ya existe, intente que un usuario de asistencia técnica contacte con el Servicio de atención al cliente e incluya lo siguiente:

* Una nota en la que se indique que le gustaría habilitar las visitas que llegan tarde para una fuente de datos específica
* ID del grupo de informes
* Nombre de la fuente de datos
