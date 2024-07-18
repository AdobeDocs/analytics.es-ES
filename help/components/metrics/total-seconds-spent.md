---
title: Segundos totales empleados
description: El número total agregado de segundos empleados en el elemento de la dimensión.
feature: Metrics
exl-id: 02302982-ce8c-44e9-9967-0a4f226f5e9e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 90%

---

# Segundos totales empleados

La [métrica](overview.md) &quot;Segundos totales empleados&quot; muestra la cantidad agregada de segundos que un visitante ha invertido en un elemento de dimensión determinado. Esta métrica es útil cuando desea la cantidad de tiempo sin procesar en un elemento de dimensión determinado y no los promedios como los que ofrecen otras métricas de tiempo empleado.

En Report Builder, esta métrica se denomina “Tiempo total empleado”.

## Cálculo de esta métrica

Esta métrica utiliza los siguientes pasos para medir el cálculo:

1. Para una visita determinada, observe la marca de tiempo.
2. Compare esta visita individual con la marca de tiempo de la siguiente en la visita general. Tanto las visitas individuales de seguimiento de vista de página como las de seguimiento de vínculos cuentan.
3. La cantidad de segundos que transcurrieron entre las dos visitas individuales contribuyen al elemento de dimensión.

Las variables persistentes, como las [eVars](../dimensions/evar.md), se contabilizan como segundos totales empleados. Las variables de tráfico, como las [props](../dimensions/prop.md), incluyen los segundos empleados en las llamadas de seguimiento de vínculos subsiguientes.

>[!TIP]
>
>El tiempo empleado no se mide durante la última visita individual de la visita general, ya que no hay ninguna solicitud de imagen posterior para medir el tiempo transcurrido. Este concepto también se aplica a las visitas que consisten en una sola visita (una devolución).

Consulte [Información general sobre el tiempo empleado](time-spent.md) para saber más detalles sobre el tiempo invertido.
