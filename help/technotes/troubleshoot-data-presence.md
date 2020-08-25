---
title: Solución de problemas de presencia de datos
description: Conozca los pasos que puede seguir cuando no ve los datos en los informes.
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 4%

---


# Solución de problemas de presencia de datos

En Analysis Workspace, algunas configuraciones de proyecto devuelven cero filas. En Informes y análisis, ver ciertos informes devuelve el siguiente mensaje:

**&quot;No hay datos para los criterios seleccionados.&quot;**

Siga estos pasos para determinar por qué un informe no muestra datos.

## Los datos existen pero se filtran

El grupo de informes contiene datos, pero los componentes específicos utilizados en el informe filtros todos los datos.

* **Segmentos**: Los segmentos pueden evitar fácilmente que todos los datos aparezcan en un informe. Compruebe todas las definiciones de segmentos y elimine todos los segmentos para ver si un segmento está causando que los datos no aparezcan.
* **Métricas**: Compruebe que se utilizan las métricas correctas. Cambie la métrica a [Ocurrencias](/help/components/metrics/occurrences.md) para asegurarse de que la métrica no sea el colaborador de un informe sin datos.
* **Intervalos** de fechas: Los intervalos de fechas demasiado lejanos en el pasado o en cualquier momento del futuro no devuelven datos. La política [de retención de](data-retention.md) datos de su organización determina hasta dónde se guardan los datos anteriores.
* **Filtros**: Elimine todos los filtros de búsqueda del informe.

## Los datos no existen

Si no hay segmentos, la métrica es Ocurrencias, el intervalo de fechas es el mes actual y no hay filtros de búsqueda, compruebe lo siguiente:

* **Verifique el grupo** de informes: Asegúrese de que se encuentra en un grupo de informes que contiene datos. Muchas organizaciones tienen grupos de informes nuevos, de prueba o de desarrollo que generalmente no contienen muchos datos.
* **Latencia**: Si se ven datos recientes, es posible que los datos se retrasen. Consulte [Latencia](latency.md) para obtener más información.
* **Validar recopilación** de datos: Vaya a la propiedad web que debe rastrear el grupo de informes y abra el depurador [de](https://docs.adobe.com/content/help/es-ES/debugger/using/experience-cloud-debugger.html)Adobe. Asegúrese de que hay una solicitud de imagen de Analytics al cargar una página. Si ve una solicitud de imagen, asegúrese de que utiliza la ID del grupo de informes correcta, que incluye un [currencyCode](/help/implement/vars/config-vars/currencycode.md)válido y que la compatibilidad [con la](/help/implement/vars/page-vars/timestamp.md) marca de tiempo coincide con la solicitud de imagen y el grupo de informes.
