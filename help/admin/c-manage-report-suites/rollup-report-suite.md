---
description: Los grupos de informes resumidos acumulan datos de varios grupos de informes secundarios y los muestran en un conjunto de datos resumido.
title: Grupos de informes globales y resumidos
topic: Admin tools
uuid: c90b8e38-2c95-4318-8165-a362106b6142
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Grupos de informes globales y resumidos

Los grupos de informes resumidos acumulan datos de varios grupos de informes secundarios y los muestran en un conjunto de datos resumido. Proporcionan un lugar conveniente para ver los totales resumidos, como vistas de página, ingresos u otras dimensiones básicas. Los resúmenes se utilizan frecuentemente porque no requieren ninguna implementación adicional.

## Definiciones de los tipos de grupos de informes

**Grupo** de informes globales: La implementación se modifica para enviar solicitudes de imagen entre dominios a un único grupo de informes globales. Si las visitas también se envían a grupos de informes individuales, esta práctica se denomina etiquetado de grupos múltiples.

**Grupo de informes resumidos**: se crea en las Herramientas de administración. Recibe la suma de cada métrica al final de cada día.

* Los resúmenes son libres de usar y no aumentan el uso de llamadas al servidor.
* Los resúmenes proporcionan datos totales, pero no registran valores individuales en los informes. Por ejemplo, los valores de eVar1 no están incluidos, pero sí puede estar incluido su total agregado.
* La duplicación de datos no se anula si se combinan datos de varios grupos de informes.
* Los resúmenes se ejecutan todas las noches.
* Al agregar un grupo de informes a un resumen existente, los datos históricos no se incluyen en el resumen.
* Todos los grupos de informes secundarios deben contener datos para que el resumen funcione. Si se incluyen nuevos grupos de informes en un resumen, asegúrese de enviar al menos una vista de página a esos grupos de informes.
* Los grupos de informes resumidos están limitados a un máximo de 40 grupos de informes secundarios.
* Los grupos de informes resumidos están limitados a un máximo de 100 eventos.
* Los datos contenidos en los grupos de informes resumidos no admiten desgloses ni segmentos.
* El informe Páginas se reemplaza por el informe Sitios más populares, que informa sobre las métricas en el nivel de grupo secundario.

## Grupos de informes globales y resumidos

**Llamadas** al servidor secundario: Los resúmenes no realizan llamadas al servidor adicionales, más allá de lo que recopila un solo grupo de informes. Si su organización utiliza etiquetado de grupos múltiples, se realizan llamadas al servidor secundario para cada grupo de informes adicional incluido en una solicitud de imagen.

> [!TIP] Si solo utiliza un grupo de informes globales con grupos [de informes](../../components/vrs/vrs-considerations.md)virtuales, no se necesitan llamadas secundarias al servidor.

**Cambios** de implementación: Los resúmenes no requieren ningún cambio de implementación, mientras que los grupos de informes globales requieren que incluya la ID del grupo de informes global en la implementación.

**Duplicación**: a diferencia de los grupos de informes resumidos, los globales anulan la duplicación de visitantes únicos. Por ejemplo, si un usuario visita tres dominios de un mismo propietario el mismo día, los grupos de informes resumidos pueden contar tres visitantes únicos diarios. Los grupos de informes globales registrarían un único visitante.

**Lapso de tiempo**: los grupos de informes resumidos solo se procesan cada medianoche, mientras que los globales registran datos con latencia estándar.

**Ancho**: Los resúmenes no tienen forma de comunicarse entre grupos de informes. Los grupos de informes globales pueden atribuir crédito a variables de conversión entre grupos de informes, así como proporcionar rutas entre los grupos de informes.

**Datos históricos**: los grupos de informes resumidos pueden acumular datos históricos, mientras que los globales solo registran datos a partir del momento en que se implementan.

**Informes**: Los grupos de informes globales proporcionan datos sobre todas las dimensiones; los resúmenes solo proporcionan datos agregados en informes de alto nivel.

**Productos** admitidos: Los resúmenes solo se pueden usar en Informes y análisis. No son compatibles con Analysis Workspace, el almacén de datos o los análisis específicos. Los grupos de informes globales se pueden utilizar en todos los productos.

**Número de grupos** de informes agregados: Los resúmenes solo admiten un máximo de 40 grupos de informes secundarios. Los grupos de informes globales se pueden implementar en cualquier número de dominios o aplicaciones de su propiedad.
