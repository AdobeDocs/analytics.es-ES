---
description: Los grupos de informes resumidos acumulan datos de varios grupos de informes secundarios y los muestran en un conjunto de datos resumido.
seo-description: Los grupos de informes resumidos acumulan datos de varios grupos de informes secundarios y los muestran en un conjunto de datos resumido.
seo-title: Grupos de informes globales y resumidos
solution: Analytics
title: Grupos de informes globales y resumidos
topic: Herramientas de administración
uuid: c 90 b 8 e 38-2 c 95-4318-8165-a 362106 b 6142
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Grupos de informes globales y resumidos

Los grupos de informes resumidos acumulan datos de varios grupos de informes secundarios y los muestran en un conjunto de datos resumido.

No deben confundirse con los grupos de informes globales. Los resúmenes ofrecen una ubicación conveniente para ver la suma de los totales de métricas como vistas de página, ingresos o tecnología. Los resúmenes se utilizan frecuentemente porque no requieren ninguna implementación adicional.

## Definiciones de los tipos de grupos de informes {#section_E51E03E3917040278600A7E9638A91C7}

**Grupo de informes globales**: la implementación se modifica para enviar solicitudes de imagen de varios dominios a un único grupo de informes globales, que se suma a los grupos de informes individuales.

**Grupo de informes resumidos**: se crea en las Herramientas de administración. Recibe la suma de cada métrica al final de cada día.

* Los resúmenes se pueden utilizar libremente y no incrementan las llamadas al servidor.
* Los resúmenes proporcionan datos totales, pero no registran valores individuales en los informes. Por ejemplo, los valores de eVar1 no están incluidos, pero sí puede estar incluido su total agregado.
* La duplicación de datos no se anula si se combinan datos de varios grupos de informes. Un usuario único puede influir en tres grupos e informes distintos en un solo día y aparecerá como tres visitantes únicos diarios en el resumen.
* La agregación de resúmenes se produce por la noche.
* Al agregar un grupo de informes a un resumen existente, los datos históricos no se incluyen en el resumen.
* Los grupos de informes resumidos tienen capacidades de creación de informes limitadas. Por ejemplo, los recuentos de visitantes únicos corresponden a todos los grupos de informes. Si la misma persona visita dos grupos de informes separados, el resumen contará a esa persona como dos visitantes, mientras que el grupo de informes global estándar mostrará a un solo visitante.
* Todos los grupos de informes secundarios deben contener datos para que el resumen funcione. Si se incluyen nuevos grupos de informes en un resumen, asegúrese de enviar al menos una vista de página a esos grupos de informes.
* Los grupos de informes resumidos están limitados a un máximo de 40 grupos de informes secundarios.
* Los grupos de informes resumidos están limitados a un máximo de 100 eventos.
* Los datos que contienen los grupos de informes resumidos no admiten subrelaciones, segmentos ni ninguna otra métrica introducida en los informes de marketing.
* El informe Páginas no está disponible en los grupos de informes de resumen. Se reemplaza por el informe Sitios más populares, que informa sobre las métricas en el nivel de grupo secundario.

## Grupos de informes globales y resumidos {#section_7B3703DC7ABF4B9EA9DF02A54592CAD0}

**Llamadas al servidor**: los grupos de informes globales aumentan las llamadas secundarias al servidor, mientras que los resumidos no realizan ninguna llamada al servidor.

**Cambios de implementación**: los grupos de informes resumidos no requieren cambios de implementación, mientras que los globales requieren que se incluya un ID del grupo de informes adicional en el archivo s_code.js.

**Duplicación**: a diferencia de los grupos de informes resumidos, los globales anulan la duplicación de visitantes únicos. Por ejemplo, si un usuario visita tres dominios de un mismo propietario el mismo día, los grupos de informes resumidos pueden contar tres visitantes únicos diarios. Los grupos de informes globales registrarían un único visitante.

**Lapso de tiempo**: los grupos de informes resumidos solo se procesan cada medianoche, mientras que los globales registran datos con latencia estándar.

**Espectro**: los grupos de informes globales pueden atribuir crédito a variables de conversión entre grupos de informes, y ofrecer las rutas entre los distintos grupos de informes. Los resumidos no permiten la comunicación entre grupos de informes.

**Datos históricos**: los grupos de informes resumidos pueden acumular datos históricos, mientras que los globales solo registran datos a partir del momento en que se implementan.

**Informes**: los grupos de informes globales ofrecen información adicional sobre TODOS los informes implementados, mientras que los resumidos ofrecen datos acumulados sobre los principales informes.

**Productos admitidos**: los grupos de informes resumidos no se admiten en el almacén de datos ni en los Ad Hoc Analysis. Los informes de marketing tienen un límite de 40 grupos de informes secundarios. Los grupos de informes globales pueden usarse en todos los productos y pueden disponer de un número ilimitado de grupos de informes secundarios.

## ¿Qué tipo de grupo de informes se debe implementar? {#section_868066B9604B49BABBF84074BA5E9C71}

A la hora de elegir entre grupos de informes globales y resumidos debe tenerse en cuenta lo siguiente:

* ¿Es relevante el número de llamadas al servidor para la organización? Si deben limitarse las llamadas al servidor, considere la posibilidad de utilizar grupos de informes resumidos. En los grupos globales prácticamente se realizan el doble de llamadas al servidor.
* ¿Quedan cubiertas las necesidades si se registra el tráfico total de todos los grupos? Si es necesario anular la duplicación de visitantes, considere la posibilidad de implementar un grupo de informes globales.
* ¿Son relevantes los eventos de éxito o conversión y las rutas de los distintos dominios? Si se utilizan con frecuencia campañas entre sitios, considere la posibilidad de implementar un grupo de informes globales.
* ¿Está sujeta a limitación temporal la visualización de los datos totales del sitio? Los grupos de informes individuales continúan registrando datos prácticamente en tiempo real. Si resulta aceptable ver los totales del grupo de informes al día siguiente, se recomiendan los grupos de informes resumidos.
* ¿Existen grandes volúmenes de datos históricos procesables? Los grupos de informes globales no registran datos de forma retroactiva. Si los datos históricos son relevantes, se recomiendan los grupos de informes resumidos.
* ¿El almacén de datos y los Ad Hoc Analysis son fundamentales para complementar a los informes? En caso afirmativo, se recomienda utilizar un grupo de informes globales.

Ninguna de estas opciones afecta a los grupos de informes individuales. Antes de determinar cuál es la solución más adecuada para una organización, deben sopesarse detenidamente los pros y los contras.
