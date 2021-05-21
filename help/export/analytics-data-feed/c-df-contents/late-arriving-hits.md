---
title: Visitas que llegan tarde
description: Descubra cómo las fuentes de datos tratan las visitas que llegan tarde.
exl-id: c99a702b-2aaa-47a6-958a-1e5ab66961ba
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '331'
ht-degree: 100%

---

# Visitas que llegan tarde

Los datos históricos pueden llegar después de que un trabajo de fuente de datos termine de procesarse durante una hora o un día determinados, por ejemplo, mediante visitas con marca de tiempo u origen de datos. Las visitas que llegan tarde son una configuración de personalización backend proporcionada por Adobe para ayudar a incluir estos datos en las fuentes de datos.

## Funcionamiento de las visitas que llegan tarde

Cuando una fuente de datos procesa la información con normalidad, solo utiliza los datos dentro de su intervalo de informes (generalmente la hora o el día más recientes). Si los datos llegan después de que una fuente procese ese intervalo de informes, nunca se incluirán en ninguna fuente de datos.

Cuando las visitas que llegan tarde se encuentran habilitadas, el método de procesamiento cambia para incluir estos datos. Cada vez que una fuente de datos procesa la información, utiliza las visitas que llegan tarde y las procesa en el siguiente archivo de fuente de datos enviado a su sitio FTP.

## Habilitación de las visitas que llegan tarde

Adobe puede habilitar manualmente las visitas que llegan tarde en las fuentes de datos individuales. Antes de hacerlo, tenga en cuenta lo siguiente:

* Los datos de diferentes días aparecen con frecuencia en las fuentes de datos cuando las visitas que llegan tarde están habilitadas. Compruebe que la plataforma que utiliza para la ingesta de fuentes de datos puede admitir datos de diferentes días dentro del mismo archivo.
* Las visitas que llegan tarde aumentan el tiempo de procesamiento. Normalmente, este retraso es inferior a una hora, pero puede ser de varias horas o más si el grupo de informes recibe un gran número de visitas que llegan tarde. Adobe recomienda que no se active esta configuración si la llegada oportuna de fuentes de datos es imprescindible para el flujo de trabajo de su organización.
* Si se vuelve a procesar un archivo de fuente de datos, las visitas que llegan tarde y que se incluyeron en el archivo original no se incluirán en el archivo reprocesado.

Si desea habilitar las visitas que llegan tarde para una fuente de datos recurrente que ya existe, intente que un usuario de asistencia técnica contacte con el Servicio de atención al cliente e incluya lo siguiente:

* Una nota en la que se indique que le gustaría habilitar las visitas que llegan tarde para una fuente de datos específica
* ID del grupo de informes
* Nombre de la fuente de datos
