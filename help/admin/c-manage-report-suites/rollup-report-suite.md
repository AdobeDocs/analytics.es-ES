---
description: Los grupos de informes resumidos acumulan datos de varios grupos de informes secundarios y los muestran en un conjunto de datos resumido.
title: Grupos de informes globales y resumidos
topic: Herramientas de administración
uuid: c90b8e38-2c95-4318-8165-a362106b6142
translation-type: tm+mt
source-git-commit: d0fe97b9368cbc4c9e79f9e56adf9786b58dce1a
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 98%

---


# Grupos de informes globales y resumidos

Los grupos de informes resumidos acumulan datos de varios grupos de informes secundarios y los muestran en un conjunto de datos resumido. Proporcionan un lugar conveniente para ver los totales resumidos, como vistas de página, ingresos u otras dimensiones básicas. Los resúmenes se utilizan frecuentemente porque no requieren ninguna implementación adicional.

## Definiciones de los tipos de grupos de informes

**Grupo de informes globales**: la implementación se modifica para enviar solicitudes de imagen de varios dominios a un único grupo de informes globales. Si las visitas también se envían a grupos de informes individuales, esta práctica se denomina etiquetado de grupos múltiples.

**Grupo de informes resumidos**: se crea en las Herramientas de administración. Recibe la suma de cada métrica al final de cada día.

* Los resúmenes se pueden usar sin cargo adicional y no suponen un aumento de llamadas al servidor.
* Los resúmenes proporcionan datos totales, pero no registran valores individuales en los informes. Por ejemplo, los valores de eVar1 no están incluidos, pero sí puede estar incluido su total agregado.
* La duplicación de datos no se anula si se combinan datos de varios grupos de informes.
* Los resúmenes se ejecutan todas las noches.
* Al agregar un grupo de informes a un resumen existente, los datos históricos no se incluyen en el resumen.
* Todos los grupos de informes secundarios deben contener datos para que el resumen funcione. Si se incluyen nuevos grupos de informes en un resumen, asegúrese de enviar al menos una vista de página a esos grupos de informes.
* Los grupos de informes resumidos están limitados a un máximo de 40 grupos de informes secundarios.
* Los grupos de informes resumidos están limitados a un máximo de 100 eventos.
* Los datos contenidos en los grupos de informes resumidos no admiten desgloses ni segmentos.
* El informe de páginas se reemplaza por el informe de sitios más populares, que trata sobre las métricas en el nivel de grupo secundario.

## Grupos de informes globales y resumidos

**Llamadas secundarias al servidor**: los resúmenes no realizan llamadas adicionales al servidor más allá de lo que recopila un solo grupo de informes. Si su organización utiliza el etiquetado de grupos múltiples, se realizan llamadas secundarias al servidor para cada grupo de informes adicional incluido en una solicitud de imagen.

>[!TIP]
>
>Si solo utiliza un grupo de informes globales con [grupos de informes virtuales](../../components/vrs/vrs-considerations.md), no se necesitan llamadas secundarias al servidor.

**Cambios de implementación**: los resúmenes no requieren ningún cambio de implementación, mientras que los grupos de informes globales requieren que incluya el ID del grupo de informes global en la implementación.

**Duplicación**: a diferencia de los grupos de informes resumidos, los globales anulan la duplicación de visitantes únicos. Por ejemplo, si un usuario visita tres dominios de un mismo propietario el mismo día, los grupos de informes resumidos contabilizarían tres visitantes únicos al día. Los grupos de informes globales registrarían un único visitante.

**Lapso de tiempo**: los grupos de informes resumidos solo se procesan cada medianoche, mientras que los globales registran datos con latencia estándar.

**Espectro**: los grupos de informes resumidos no permiten la comunicación entre grupos de informes. Los grupos de informes globales pueden atribuir crédito a variables de conversión entre grupos de informes y ofrecer rutas entre los distintos grupos de informes.

**Datos históricos**: los grupos de informes resumidos pueden acumular datos históricos, mientras que los globales solo registran datos a partir del momento en que se implementan.

**Informes**: los grupos de informes globales ofrecen datos de todas las dimensiones, mientras que los resumidos ofrecen datos acumulados sobre los informes principales.

**Productos compatibles**: los grupos de informes resumidos solo se pueden usar en Reports &amp; Analytics. No son compatibles con Analysis Workspace o Data Warehouse. Los grupos de informes globales se pueden utilizar en todos los productos.

**Número de grupos de informes agregados**: los grupos de informes resumidos solo admiten un máximo de 40 grupos de informes secundarios. Los grupos de informes globales se pueden implementar en cualquier dominio o aplicación de su propiedad.
