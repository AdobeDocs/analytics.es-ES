---
title: Preguntas más frecuentes sobre Attribution
description: Obtenga respuestas a preguntas más frecuentes sobre Attribution.
feature: Attribution
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '1030'
ht-degree: 99%

---


# Preguntas más frecuentes sobre Attribution

## ¿Cuál es el elemento de línea “Ninguno” al utilizar Attribution?

El elemento de línea “Ninguno” es un captador global que representa todas las conversiones que se produjeron sin ningún punto de contacto dentro de la ventana retrospectiva. Para reducir el número de conversiones atribuidas al elemento de línea “Ninguno”, intente utilizar una ventana retrospectiva personalizada con un periodo de retrospectividad más largo.

## ¿Por qué a veces veo fechas fuera de la ventana de informes al utilizar modelos de atribución?

Algunas métricas basadas en visitas, como [Entradas](/help/components/metrics/entries.md) o [Tasa de salida hacia otro sitio](/help/components/metrics/bounce-rate.md), pueden atribuir datos a un período antes del intervalo de fechas de inicio de la ventana de creación de informes. Esta situación se debe a que los modelos de atribución utilizan una ventana retrospectiva, que determina hasta qué punto la atribución retroactiva debería dar crédito por las métricas. El escenario más común es cuando las visitas se extienden más allá de la medianoche. Por ejemplo:

1. Un usuario visita su página principal a las 11:55 p.m. del 7 de septiembre.
1. Visitan varias páginas, la última de las cuales ocurrió a las 12:05 a.m. del 8 de septiembre.
1. Una semana después, se ejecuta un informe de tendencias diario con el intervalo de fechas del 8 de septiembre al 14 de septiembre.

Las métricas basadas en visitas, como [Vistas de página](/help/components/metrics/page-views.md), producirían el resultado esperado; los datos fueron tendencia todos los días del 8 de septiembre al 14 de septiembre. Sin embargo, las métricas basadas en visitas también mostrarían la visita anterior del 7 de septiembre. La entrada atribuida a la visita se produjo el 7 de septiembre y la ventana retroactiva predeterminada es del 1 de septiembre al 31 de septiembre.

La tasa de salida hacia otro sitio siempre muestra 0% el 7 de septiembre en este ejemplo. Esta métrica se define como `Bounces divided by Entries`, que es una métrica basada en visitas dividida por una métrica basada en visitas. Las salidas consisten en una sola solicitud de imagen, por lo que no pueden abarcar varios días. Cualquier salida producida el 7 de septiembre se produjo fuera de la ventana de creación de informes, lo que provoca la tasa de salida hacia otro sitio del 0% garantizada para ese día. Otras métricas basadas en visitas también mostrarían 0 para el 7 de septiembre en este informe, ya que esas visitas no se incluyen en la ventana de creación de informes.

Veamos otro ejemplo similar. La única diferencia entre el ejemplo siguiente y el ejemplo anterior son las fechas:

1. Un usuario visita su página principal a las 11:55 p.m. del 31 de agosto.
1. Visitan varias páginas, la última de las cuales ocurrió a las 12:05 a.m. del 1 de septiembre.
1. Una semana después, se ejecuta un informe de tendencias diario con el intervalo de fechas del 1 de septiembre al 7 de septiembre.

En este ejemplo, las entradas y la tasa de salida hacia otro sitio no mostraban datos del 31 de agosto. Tanto la ventana retroactiva como la ventana de creación de informes comienzan el 1 de septiembre, por lo que los datos no se pueden atribuir a partir del 31 de agosto.

## ¿Cuándo debo usar una retrospectiva de atribución de visita, de visitante o personalizada?

La elección de la retrospectiva de atribución depende de su caso de uso. Si las conversiones suelen tardar más de una sola visita, se recomienda una retrospectiva del visitante o personalizada. Para ciclos de conversión más largos, las ventanas de retrospectiva personalizadas son mejores ya que son el único tipo que puede extraer datos anteriores a los establecidos en la ventana para la creación de informes.

## ¿Cómo se comparan las props y las eVars al utilizar la atribución?

La atribución se vuelve a calcular durante el tiempo de ejecución del informe, por lo que no hay diferencia entre una prop o eVar (o cualquier otra dimensión) en cuanto al modelado de atribución. Las props pueden persistir con cualquier ventana retrospectiva o modelo de atribución y se omiten las opciones de asignación/caducidad de eVar.

## ¿Están disponibles los modelos de atribución en otras funciones de Analytics, como Fuentes de datos o Data Warehouse?

No. Los modelos de atribución utilizan el procesamiento del tiempo de los informes, que solo está disponible en Analysis Workspace. Consulte [Procesamiento de tiempo de informes](/help/components/vrs/vrs-report-time-processing.md) para obtener más información.

## ¿Los modelos de atribución solo están disponibles si utilizo un Grupo de informes virtuales con el procesamiento de tiempo de informes activado?

Los modelos de atribución están disponibles fuera de los grupos de informes virtuales. Aunque utilizan el procesamiento de tiempo de los informes en segundo plano, los modelos de atribución están disponibles tanto para los grupos de informes estándar como para los virtuales.

## ¿Qué dimensiones y métricas no son compatibles?

El panel de atribución admite todas las dimensiones. Las métricas no admitidas incluyen:

* Todas las métricas calculadas
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

## ¿Funciona la atribución con las clasificaciones?

Sí, las clasificaciones son compatibles.

## ¿La atribución funciona con fuentes de datos?

Sí, la mayoría de las fuentes de datos son compatibles. La atribución no es compatible con fuentes de datos de resumen porque no están vinculadas a un identificador de visitante de Analytics. Los orígenes de datos del ID de transacción también se admiten, excepto si se usan en un grupo de informes virtual con el procesamiento de tiempo de informe habilitado.

## ¿Se puede usar la atribución con la integración de Advertising Analytics?

Las dimensiones de metadatos, como el tipo de coincidencia y la palabra clave, se pueden usar con la atribución. Sin embargo, las métricas (como impresiones, coste, clics, posición promedio y puntuación de calidad promedio) utilizan fuentes de datos de resumen y, por lo tanto, son incompatibles.

## ¿Cómo funciona la atribución con los canales de marketing?

Cuando se introdujeron los canales de marketing por primera vez, solo incluyeron dimensiones de primer y último contacto. Ya no se necesitan dimensiones explícitas de primer/último contacto con la versión actual de atribución. Adobe proporciona dimensiones genéricas de “Canal de marketing” y “Detalle del canal de marketing” para que pueda utilizarlas con el modelo de atribución deseado. Estas dimensiones genéricas se comportan de forma idéntica a las dimensiones del canal de último contacto, pero tienen una etiqueta diferente para evitar confusiones al usar canales de marketing con un modelo de atribución diferente.

Dado que las dimensiones del canal de marketing dependen de una definición de visita tradicional (según lo definen sus reglas de procesamiento), su definición de visita no se puede cambiar mediante grupos de informes virtuales.

## ¿Cómo funciona la atribución con variables de varios valores, como las variables de lista?

Algunas dimensiones en Analytics pueden contener varios valores en una sola visita. Algunos ejemplos comunes son las variables de lista y la variable Products.

Cuando la atribución se aplica a visitas con varios valores, todos los valores de la misma visita obtienen el mismo crédito. Dado que muchos valores pueden recibir este crédito, el total del informe puede ser diferente a la suma de cada elemento de línea individual. El total del informe se deduplica, mientras que cada elemento de dimensión individual obtiene el crédito adecuado.

## ¿Cómo funciona la atribución con la segmentación?

La atribución siempre se ejecuta antes de la segmentación y esta se ejecuta antes de que se apliquen los filtros de informe. Este concepto también se aplica a los grupos de informes virtuales que utilizan segmentos.

Por ejemplo, si crea un VRS y le aplica un segmento “Display Hits”, puede ver otros canales en una tabla utilizando algunos modelos de atribución.

![Grupo de informes virtuales de solo visualización](assets/vrs-aiq-example.png)

>[!NOTE]
>
>Si un segmento suprime las visitas que contengan la métrica, esas instancias de métrica no se atribuirán a ninguna dimensión. Sin embargo, un filtro de informe similar simplemente ocultará algunos elementos de dimensión, sin ningún impacto en las métricas procesadas por el modelo de atribución. Como resultado, un segmento puede devolver valores más bajos que un filtro con una definición comparable.
