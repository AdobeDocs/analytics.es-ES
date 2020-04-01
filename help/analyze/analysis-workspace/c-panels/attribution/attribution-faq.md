---
title: Preguntas más frecuentes sobre Attribution
description: Obtenga respuestas a preguntas más frecuentes sobre Attribution.
translation-type: tm+mt
source-git-commit: f4fbe120e15d28da21b51849ff374ca4e2136ec7

---


# Preguntas más frecuentes sobre Attribution

**¿Cuál es el elemento de línea “Ninguno” al utilizar Attribution?**

El elemento de línea &#39;Ninguno&#39; es un elemento de captación global que representa todas las conversiones que se produjeron sin ningún punto de contacto dentro de la ventana retroactiva. Intente incluir un intervalo de tiempo más largo en la ventana de informes.

**¿Por qué a veces veo fechas fuera de la ventana de informes al utilizar modelos de atribución?**

Estas fechas adicionales se deben a la ventana retrospectiva de informes de visitantes. Consulte [Datos que aparecen fuera de la ventana de informes](https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html) en la BC de Analytics para obtener más información. Adobe filtrará estas filas extra en una próxima versión.

**¿Puedo utilizar una ventana retrospectiva personalizada con mis modelos de atribución?**

Actualmente, los modelos de atribución dependen de una ventana retrospectiva de visitante o visita. Cualquiera de estas ventanas retrospectivas se puede ajustar cambiando el intervalo de fechas de los informes (para retrospectiva de visitantes) o utilizando una definición de visita personalizada como parte de los grupos de informes virtuales. Consulte [Procesamiento de tiempo de informes](../../../../components/vrs/vrs-report-time-processing.md) para obtener más información.

**¿Cuándo debo usar una retrospectiva de atribución de visita o de visitante?**

La elección de la retrospectiva de atribución depende de su caso de uso. Si las conversiones suelen tardar más de una sola visita, se recomienda una retrospectiva del visitante. La creación de un grupo de informes virtuales con una definición de visita más larga también es una posible solución.

**¿Cómo se comparan las props y las eVars al utilizar la atribución?**

La atribución se vuelve a calcular durante el tiempo de ejecución del informe, por lo que no hay diferencia entre una prop o eVar (o cualquier otra dimensión) en cuanto al modelado de atribución. Las props pueden persistir con cualquier ventana retrospectiva o modelo de atribución y se omiten las opciones de asignación/caducidad de eVar.

**¿Están disponibles los modelos de atribución en otras funciones de Analytics, como Fuentes de datos o Data Warehouse?**

No. Los modelos de atribución utilizan el procesamiento del tiempo de los informes, que solo está disponible en Analysis Workspace. Consulte [Procesamiento de tiempo de informes](../../../../components/vrs/vrs-report-time-processing.md) para obtener más información.

**¿Los modelos de atribución solo están disponibles si utilizo un Grupo de informes virtuales con el procesamiento de tiempo de informes activado?**

Los modelos de atribución están disponibles fuera de los grupos de informes virtuales. Aunque utilizan el procesamiento de tiempo de los informes en segundo plano, los modelos de atribución están disponibles tanto para los grupos de informes estándar como para los virtuales.

**¿Qué dimensiones y métricas no son compatibles?**

El panel de atribución admite todas las dimensiones. Las métricas no admitidas incluyen:

* Visitantes únicos
* Visitas
* Ocurrencias
* Vistas de páginas
* Métricas de A4T
* Métricas de tiempo empleado
* Devoluciones
* Tasa de devoluciones
* Entradas
* Salidas
* Páginas no encontradas
* Búsquedas
* Visitas a una sola página
* Acceso único

**¿Puedo utilizar una ventana retrospectiva personalizada con mis modelos de atribución?**

Sí, con la opción de ventana retrospectiva personalizada, las ventanas retrospectivas se pueden configurar en cualquier intervalo de fechas de hasta 90 días antes de la ventana de sistema de informes. Consulte [Procesamiento de tiempo de informes](https://docs.adobe.com/content/help/en/analytics/components/virtual-report-suites/vrs-report-time-processing.html) para obtener más información.

**¿Funciona la atribución con las clasificaciones?**

Sí, las clasificaciones son compatibles.

**¿La atribución funciona con fuentes de datos?**

Sí, la mayoría de las fuentes de datos son compatibles. La atribución no es compatible con fuentes de datos de resumen porque no están vinculadas a un identificador de visitante de Analytics. Los orígenes de datos del ID de transacción también se admiten, excepto si se usan en un grupo de informes virtual con el procesamiento de tiempo de informe habilitado.

**¿Se puede usar la atribución con la integración de Advertising Analytics?**

Las dimensiones de metadatos, como el tipo de coincidencia y la palabra clave, se pueden usar con la atribución. Sin embargo, las métricas (como impresiones, coste, clics, posición promedio y puntuación de calidad promedio) utilizan fuentes de datos de resumen y, por lo tanto, son incompatibles.
