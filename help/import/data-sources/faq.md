---
title: Preguntas frecuentes sobre fuentes de datos
description: Preguntas frecuentes sobre las fuentes de datos.
exl-id: a948dfe9-289f-43e2-a9e7-7990cf609f5c
feature: Data Sources
role: Admin
source-git-commit: 667870f9575bbc03a72738771f34bf1718725d6c
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 7%

---

# Preguntas frecuentes sobre fuentes de datos

Preguntas frecuentes sobre las fuentes de datos.

+++¿Cuál es el coste de utilizar fuentes de datos?
Las fuentes de datos no incurren en ningún cargo ni se contabilizan para el uso de llamadas al servidor. [Las fuentes de datos de procesamiento completo](full-processing-eol.md) se contaron en las llamadas al servidor antes de su retiro.
+++

+++¿Cómo afectan las fuentes de datos a la atribución y caducidad de las eVars?
Las fuentes de datos no tienen ningún tipo de atribución o caducidad.
+++

+++¿Cómo afectan las fuentes de datos a métricas como vistas de página, visitas o visitantes únicos?
Los datos cargados a través de fuentes de datos no afectan las [vistas de página](/help/components/metrics/page-views.md), las [visitas](/help/components/metrics/visits.md) ni los [visitantes únicos](/help/components/metrics/unique-visitors.md) de ninguna manera. La única métrica predeterminada a la que afectan incluye [Ocurrencias](/help/components/metrics/occurrences.md).
+++

+++¿Los datos cargados a través de fuentes de datos se procesan mediante reglas adicionales, como las reglas de procesamiento?
No. Datos cargados mediante fuentes de datos:

* No pasa por [Reglas de procesamiento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md)
* No pasa por [reglas de procesamiento de canal de marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md)
* No pasa por [reglas VISTA](/help/technotes/vista.md)
+++

+++¿Se pueden eliminar los datos importados mediante fuentes de datos?
Sí. Puede eliminar estos datos mediante la [API de reparación de datos](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/). Adobe recomienda encarecidamente cargar las fuentes de datos en un grupo de informes de prueba antes de cargarlos en un grupo de informes de producción para reducir la necesidad de eliminar datos.
+++

+++¿Cuántos datos se pueden importar a la vez?
Si el tamaño de datos supera los 50 MB, el procesamiento se detendrá y no se reanudará hasta que el total sea menor que 50 MB. Asegúrese de que el tamaño total de todos los archivos del sitio FTP sea inferior a 50 MB.
+++

+++¿Qué sucede si se transmiten valores negativos a informes a través de fuentes de datos?
El valor disminuye en consecuencia. Algunas organizaciones utilizan valores de fuentes de datos negativos para intentar corregir los datos. Los valores negativos de las fuentes de datos pueden afectar a los informes de formas potencialmente no deseadas o inesperadas. Adobe recomienda utilizar valores negativos en fuentes de datos solo como último recurso.
+++

+++¿Distinguen entre mayúsculas y minúsculas las extensiones de archivo?
Sí. No se procesarán los archivos con la extensión `.TXT` o `.FIN`. Asegúrese de que todas las extensiones de archivo estén en minúsculas.
+++

+++¿Cuántas columnas se pueden agregar a un archivo de fuente de datos?
Si todas las columnas son válidas, puede incluir tantas columnas en un archivo de fuente de datos como desee. Consulte [Formato de archivo](file-format.md) para obtener una lista de nombres válidos de variables/columnas.
+++

+++¿Puedo utilizar fuentes de datos sin utilizar la ubicación FTP proporcionada por Adobe?
Puede usar la [API de fuentes de datos](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), que le permite enviar llamadas de API directamente a Adobe. Estas llamadas a la API incluyen un método `UploadData`, que le permite enviar datos mediante una carga útil de objeto JSON.
+++
