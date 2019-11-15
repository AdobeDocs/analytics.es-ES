---
title: Preguntas más frecuentes sobre atribución
description: Obtenga respuestas a las preguntas más frecuentes sobre atribución.
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Preguntas más frecuentes sobre atribución

**¿Cuál es el elemento de línea "Ninguno" al utilizar la atribución?**

El elemento de línea 'Ninguno' es un captador global que representa todas las conversiones que se produjeron sin ningún punto de contacto dentro de la ventana retroactiva. Intente incluir un intervalo de tiempo más largo en la ventana de informes.

**¿Por qué a veces veo fechas fuera de la ventana de informes al utilizar modelos de atribución?**

Estas fechas adicionales se deben a la ventana retrospectiva de informes de visitantes. Consulte [Datos que aparecen fuera de la ventana](https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html) de informes en la BC de Analytics para obtener más información. Adobe planea filtrar estas filas adicionales en una próxima versión.

**¿Puedo usar una ventana retrospectiva personalizada con mis modelos de atribución?**

Actualmente, los modelos de atribución dependen de una ventana retrospectiva de visitante o visita. Cualquiera de estas ventanas retroactivas se puede ajustar cambiando el intervalo de fechas de los informes (para retrospectiva de visitantes) o utilizando una definición de visita personalizada como parte de los grupos de informes virtuales. Consulte Procesamiento [de tiempo de](../../../../components/vrs/vrs-report-time-processing.md) informes para obtener más información.

**¿Cuándo debo usar un retrospectivo de atribución de visita vs. visitante?**

La elección del retroceso de atribución depende del caso de uso. Si las conversiones suelen tardar más de una sola visita, se recomienda una retrospectiva del visitante. La creación de un grupo de informes virtuales con una definición de visita más larga también es una solución potencial.

**¿Cómo se comparan las props y las eVars al utilizar la atribución?**

La atribución se vuelve a calcular durante el tiempo de ejecución del informe, por lo que no hay diferencia entre una prop o eVar (o cualquier otra dimensión) en aras del modelado de atribución. Las props pueden persistir con cualquier ventana retroactiva o modelo de atribución, y se omiten las opciones de asignación/caducidad de eVar.

**¿Están disponibles los modelos de atribución en otras funciones de Analytics, como Fuentes de datos o Almacén de datos?**

No. Los modelos de atribución utilizan el procesamiento del tiempo de los informes, que solo está disponible en Analysis Workspace. Consulte Procesamiento [de tiempo de](../../../../components/vrs/vrs-report-time-processing.md) informes para obtener más información.

**¿Los modelos de atribución solo están disponibles si estoy utilizando un grupo de informes virtuales con el procesamiento de tiempo de los informes habilitado?**

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
* Porcentaje de rebote
* Entradas
* Salidas
* Páginas no encontradas
* Búsquedas
* Visitas a una sola página
* Acceso único

**¿En qué se diferencia la atribución en Analysis Workspace de la atribución en el área de trabajo de datos?**

El Área de trabajo de datos ofrece en forma incremental:

* La capacidad de atribuir a través de más fuentes de datos de nivel de visitante, como impresiones de anuncios y punto de venta.
* Modelado algorítmico. La atribución en Analysis Workspace incluye solo modelos basados en reglas. Consulte [Mejor modelado](https://marketing.adobe.com/resources/help/en_US/insight/client/c_attrib_algorithmic.html) de ajuste en la guía del usuario de Área de trabajo de datos.
* Visualizaciones adicionales, como tablas de latencia. Consulte las tablas [de](https://marketing.adobe.com/resources/help/en_US/insight/client/c_lat_tbls.html) latencia en la guía del usuario de Área de trabajo de datos.

**¿Funciona la atribución con las clasificaciones?**

Sí, las clasificaciones son totalmente compatibles.

**¿Funciona la atribución con las fuentes de datos?**

Sí, la mayoría de las fuentes de datos son compatibles. La atribución no es posible con fuentes de datos de nivel de resumen porque no están vinculadas a un identificador de visitante de Analytics. También se admiten las fuentes de datos de ID de transacción, a menos que se utilicen en un grupo de informes virtuales con el procesamiento de tiempo del informe habilitado.

**¿Funciona la atribución con la integración de Análisis de publicidad?**

Las dimensiones de metadatos, como el tipo de coincidencia y la palabra clave, funcionan con la atribución. Sin embargo, las métricas (incluyendo impresiones, costo, clics, posición promedio y puntuación de calidad promedio) utilizan fuentes de datos de nivel de resumen y, por lo tanto, son incompatibles.
