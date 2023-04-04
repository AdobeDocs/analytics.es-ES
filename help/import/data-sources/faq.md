---
title: Preguntas frecuentes sobre fuentes de datos
description: Preguntas más frecuentes sobre las fuentes de datos.
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 5%

---

# Preguntas frecuentes sobre fuentes de datos

Preguntas más frecuentes sobre las fuentes de datos.

+++¿Cuál es el coste de utilizar fuentes de datos?
Las fuentes de datos no incurren en ningún cargo, ni cuentan para el uso de llamadas al servidor. [Fuentes de datos de procesamiento completo](full-processing-eol.md) se contabiliza en las llamadas al servidor antes de su jubilación.
+++

+++¿Cómo afectan las fuentes de datos a la atribución y a la caducidad de las eVars?
Si un transactionID coincide con un origen de datos y una visita en línea, los valores de eVar asociados asumen la misma atribución y caducidad que si se establecieran en la visita en línea.

El resto de los datos cargados a través de fuentes de datos no tienen ningún tipo de atribución o caducidad.
+++

+++¿Cómo afectan las fuentes de datos a las métricas predeterminadas, como las vistas de página, las visitas o los visitantes únicos?
Los datos cargados a través de fuentes de datos no afectan a [Vistas de página](/help/components/metrics/page-views.md), [Visitas](/help/components/metrics/visits.md)o [Visitantes únicos](/help/components/metrics/unique-visitors.md) de cualquier manera. La única métrica predeterminada a la que afectan incluye [Ocurrencias](/help/components/metrics/occurrences.md).
+++

+++¿Puedo eliminar datos importados mediante fuentes de datos?

**No.** Los datos cargados en informes mediante fuentes de datos son **permanente**. Una vez importada, no se puede eliminar, ni siquiera por Adobe. Adobe recomienda encarecidamente cargar las fuentes de datos en un grupo de informes de prueba antes de cargarlo en un grupo de informes de producción.
+++

+++¿Cuántos datos se pueden importar a la vez?

Si el tamaño de datos supera los 50 MB, el procesamiento se detendrá y no se reanudará hasta que el total sea menor que 50 MB. Asegúrese de que el tamaño total de todos los archivos del sitio FTP sea inferior a 50 MB.
+++

+++¿Qué sucede si se transmiten valores negativos a informes a través de fuentes de datos?

El valor disminuye según corresponda. Algunas organizaciones utilizan valores negativos de fuentes de datos para intentar corregir los datos. Los valores negativos de las fuentes de datos pueden afectar a los informes de formas potencialmente no deseadas o inesperadas. Adobe recomienda usar fuentes de datos negativas solo como último recurso.
+++

+++Las extensiones de archivo distinguen entre mayúsculas y minúsculas?
Sí. Archivos con extensión de `.TXT` o `.FIN` no se procesan. Asegúrese de que las extensiones de archivo estén todas en minúsculas.
+++

+++Cuántas columnas puedo agregar a un archivo de fuente de datos?
Puede incluir tantas columnas en un archivo de fuente de datos como desee, si todas son columnas válidas. Consulte [Formato del archivo](file-format.md) para obtener una lista de nombres de columnas o variables válidos.
+++

+++¿Puedo utilizar fuentes de datos sin utilizar la ubicación FTP proporcionada por el Adobe?
Puede usar la variable [API de fuentes de datos](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), que le permite enviar llamadas de API directamente a Adobe. Estas llamadas a API incluyen un `UploadData` , que le permite enviar datos mediante una carga útil de objeto JSON.
+++
