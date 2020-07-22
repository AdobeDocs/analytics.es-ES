---
title: Segundos totales empleados
description: El número total agregado de segundos empleados en el elemento de dimensión.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 9%

---


# Segundos totales empleados

La métrica &#39;Segundos totales empleados&#39; muestra la cantidad agregada de segundos que un visitante ha invertido en un elemento de dimensión determinado. Esta métrica es útil cuando desea la cantidad de tiempo sin procesar en un elemento de dimensión determinado y no los promedios como la oferta de otras métricas de tiempo empleado.

En el Creador de informes, esta métrica se denomina &#39;Tiempo total empleado&#39;.

## Cómo se calcula esta métrica

Esta métrica utiliza los siguientes pasos para medir el cálculo:

1. Para una visita determinada, observe la marca de tiempo.
2. Compare esta visita individual con la marca de tiempo de la siguiente en la visita general. Tanto las visitas individuales de seguimiento de vista de página como las de seguimiento de vínculos cuentan.
3. La cantidad de segundos que transcurrieron entre las dos visitas individuales contribuyen al elemento de dimensión.

Las variables persistentes, como [las eVars](../dimensions/evar.md), se contabilizan como segundos totales empleados. Las variables de tráfico, como [props](../dimensions/prop.md), incluyen los segundos empleados en las llamadas de seguimiento de vínculos subsiguientes.

>[!TIP]
>
>El tiempo empleado no se mide para la última visita individual de la visita, ya que no hay solicitudes de imagen subsiguientes para medir el tiempo transcurrido. Este concepto también se aplica a las visitas que consisten en una sola visita (una devolución).

Consulte [Información general](time-spent.md) sobre el tiempo empleado para obtener información más general sobre el tiempo empleado.
