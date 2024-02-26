---
title: Preguntas frecuentes sobre fuentes de datos
description: Preguntas más frecuentes sobre las fuentes de datos.
exl-id: a948dfe9-289f-43e2-a9e7-7990cf609f5c
feature: Data Sources
role: Admin
source-git-commit: f7d07525c97f4aa145dc46198f883a37cde80158
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 5%

---

# Preguntas frecuentes sobre fuentes de datos

Preguntas más frecuentes sobre las fuentes de datos.

+++¿Cuál es el coste de utilizar fuentes de datos?
Las fuentes de datos no incurren en ningún cargo ni se contabilizan para el uso de llamadas al servidor. [Fuentes de datos de procesamiento completo](full-processing-eol.md) se contabilizan en las llamadas al servidor antes de su jubilación.
+++

+++¿Cómo afectan las fuentes de datos a la atribución y caducidad de las eVars?
Si transactionID coincide entre una fuente de datos y una visita en línea, los valores de eVar asociados asumen la misma atribución y caducidad que si se establecieran en la visita en línea.

El resto de los datos cargados a través de fuentes de datos no tienen ningún tipo de atribución o caducidad.
+++

+++¿Cómo afectan las fuentes de datos a las métricas predeterminadas, como las vistas de página, las visitas o los visitantes únicos?
Los datos cargados a través de fuentes de datos no afectan a [Page views](/help/components/metrics/page-views.md), [Visitas](/help/components/metrics/visits.md), o [Visitantes únicos](/help/components/metrics/unique-visitors.md) de cualquier manera. La única métrica predeterminada a la que afectan incluye [Ocurrencias](/help/components/metrics/occurrences.md).
+++

+++¿Se pueden eliminar los datos importados mediante fuentes de datos?

Sí. Puede eliminar estos datos mediante el [API de reparación de datos](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/). Además, el Adobe recomienda encarecidamente cargar las fuentes de datos en un grupo de informes de prueba antes de cargarlos en un grupo de informes de producción.
+++

+++¿Cuántos datos se pueden importar a la vez?

Si el tamaño de datos supera los 50 MB, el procesamiento se detendrá y no se reanudará hasta que el total sea menor que 50 MB. Asegúrese de que el tamaño total de todos los archivos del sitio FTP sea inferior a 50 MB.
+++

+++¿Qué sucede si se transmiten valores negativos a informes a través de fuentes de datos?

El valor disminuye en consecuencia. Algunas organizaciones utilizan valores de fuentes de datos negativos para intentar corregir los datos. Los valores negativos de las fuentes de datos pueden afectar a los informes de formas potencialmente no deseadas o inesperadas. El Adobe recomienda utilizar fuentes de datos negativas solo como último recurso.
+++

+++¿Distinguen entre mayúsculas y minúsculas las extensiones de archivo?
Sí. Archivos con la extensión `.TXT` o `.FIN` no se han procesado. Asegúrese de que todas las extensiones de archivo estén en minúsculas.
+++

+++¿Cuántas columnas se pueden agregar a un archivo de fuente de datos?
Si todas las columnas son válidas, puede incluir tantas columnas en un archivo de fuente de datos como desee. Consulte [Formato de archivo](file-format.md) para obtener una lista de nombres de variables/columnas válidos.
+++

+++¿Puedo utilizar fuentes de datos sin utilizar la ubicación FTP proporcionada por el Adobe?
Puede usar el complemento [API de fuentes de datos](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), que le permite enviar llamadas de API directamente al Adobe. Estas llamadas de API incluyen una `UploadData` , que le permite enviar datos mediante una carga útil de objeto JSON.
+++
