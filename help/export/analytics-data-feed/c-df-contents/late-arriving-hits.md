---
source-git-commit: 71899840dd5b401c6892b6ad5088d4a32fd07042
translation-type: tm+mt

---
# Visitas que llegan tarde

Los datos históricos pueden llegar después de que un trabajo de fuente de datos termine de procesarse durante una hora o un día determinados, como por ejemplo las visitas con marca de hora o las fuentes de datos. Las visitas que llegan tarde son una personalización de servidor que Adobe proporciona para incluir estos datos en fuentes de datos.

## Cómo funcionan las visitas que llegan tarde

Cuando una fuente de datos procesa datos normalmente, sólo examina los datos dentro de su ventana de informes (generalmente la hora o el día más recientes). Si los datos llegan después de que una fuente termine de procesar esa ventana de informe, esos datos nunca se incluyen en ninguna fuente de datos.

Con las visitas que llegan tarde activadas, el método de procesamiento cambia para incluir estos datos. Cada vez que un archivo de fuente de datos procesa datos, examina las visitas que llegan tarde y las lotes en el siguiente archivo de fuente de datos enviado al sitio FTP.

## Habilitar visitas que llegan tarde

Adobe puede habilitar las visitas entrantes finales de forma manual en fuentes de datos individuales. Antes de hacerlo, considere lo siguiente:

* Los datos de los distintos días aparecen frecuentemente en fuentes de datos cuando las visitas que llegan tarde están activadas. Asegúrese de que la plataforma que utiliza para ingestar fuentes de datos puede incluir datos de distintos días dentro del mismo archivo.
* Las visitas que llegan tarde aumentan el tiempo de procesamiento. Generalmente, este retraso es menor que hora, pero puede ser varias horas o más si el grupo de informes recibe un gran número de visitas que llegan tarde. Adobe recomienda no habilitar esta configuración si el flujo de trabajo de la organización requiere una llegada oportuna para las fuentes de datos.
* Si se vuelve a procesar un archivo de fuente de datos, las visitas que llegan tarde que se incluyeron en el archivo original no se incluirán en el archivo reprocesado.

Si desea habilitar las visitas que llegan tarde para una fuente de datos recurrente existente, póngase en contacto con el Servicio de atención al cliente e incluya lo siguiente:

* Una nota que le gustaría habilitar las visitas que llegan tarde para una fuente de datos específica
* ID del grupo de informes
* Nombre de fuente de datos
