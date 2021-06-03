---
title: Resolución de problemas de la presencia de datos
description: Conozca qué pasos puede seguir cuando no vea los datos en los informes.
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 4%

---


# Resolución de problemas de la presencia de datos

En Analysis Workspace, algunas configuraciones de proyecto devuelven cero filas. En Reports &amp; Analytics, ver ciertos informes devuelve el siguiente mensaje:

**&quot;No hay datos para los criterios seleccionados.&quot;**

Siga estos pasos para determinar por qué un informe no muestra datos.

## Los datos existen pero no se filtran

El grupo de informes contiene datos, pero los componentes específicos utilizados en el informe filtran todos los datos.

* **Segmentos**: Los segmentos pueden evitar fácilmente que todos los datos aparezcan en un informe. Compruebe todas las definiciones de segmentos y elimine todos los segmentos para ver si un segmento está causando que sus datos no aparezcan.
* **Métricas**: Compruebe que se utilizan las métricas correctas. Cambie la métrica a [Ocurrencias](/help/components/metrics/occurrences.md) para asegurarse de que la métrica no contribuya a un informe sin datos.
* **Intervalos** de fechas: Los intervalos de fechas demasiado lejanos en el pasado o en cualquier momento futuro no devuelven datos. La [política de retención de datos](data-retention.md) de su organización determina hasta dónde se conservan los datos.
* **Filtros**: Elimine todos los filtros de búsqueda del informe.

## Los datos no existen

Si no hay segmentos, la métrica es Ocurrencias, el intervalo de fechas es el mes actual y no hay filtros de búsqueda, compruebe lo siguiente:

* **Compruebe el grupo de informes**: Asegúrese de que está en un grupo de informes que contiene datos. Muchas organizaciones tienen grupos de informes nuevos, de prueba o de desarrollo que generalmente no contienen muchos datos.
* **Latencia**: Si se ven datos recientes, es posible que los datos se retrasen. Consulte [Latencia](latency.md) para obtener más información.
* **Validar la recopilación** de datos: Vaya a la propiedad web que debe rastrear el grupo de informes y abra el depurador de  [Adobes](https://docs.adobe.com/content/help/es-ES/experience-cloud/user-guides/home.translate.html). Asegúrese de que haya una solicitud de imagen de Analytics presente al cargar una página. Si ve una solicitud de imagen, asegúrese de que utiliza la ID de grupo de informes correcta, que incluye un [currencyCode](/help/implement/vars/config-vars/currencycode.md) válido y que [la compatibilidad con la marca de tiempo](/help/implement/vars/page-vars/timestamp.md) coincide entre la solicitud de imagen y el grupo de informes.
