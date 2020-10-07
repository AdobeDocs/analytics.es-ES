---
title: Limitar un VRS a determinadas fechas
description: Comprender cómo limitar un intervalo de fechas de VRS para centrarse únicamente en los datos enlazados.
translation-type: tm+mt
source-git-commit: 954927359420cfdb3d0e908758fc36464e15fee5
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 0%

---


# Limitar un VRS a determinadas fechas

Cuando activamos la costura, los inicios de costura en una fecha específica. Supongamos que la fecha es el 1 de junio. El VRS de CDA contendrá datos no enlazados antes del 1 de junio. Es posible que desee ocultar cualquier dato en el VRS antes del 1 de junio para que su análisis pueda centrarse en los intervalos de fechas después de haber iniciado la vinculación.

Puede limitar los datos del VRS a determinadas fechas haciendo lo siguiente:

## Paso 1: Crear un VRS con un intervalo de fechas diario móvil

Al configurar el VRS, en Componentes, agregue un intervalo de fechas con un inicio fijo, con un intervalo de fechas diario móvil. El inicio fijo debería ser el día en que comenzó la cosificación.

![](assets/rolling-daily.png)

## Paso 2: Creación de un segmento de &quot;exclusión&quot;

A continuación, cree un segmento de visita que coloque el intervalo de fechas en un contenedor de exclusión dentro de otro contenedor de exclusión. Es una &quot;exclusión de exclusión&quot;.

El motivo de la &quot;exclusión&quot; es que los intervalos de fechas pretenden anular el intervalo de fechas del informe. Por lo tanto, si sólo incluye el 1 de junio en adelante, siempre hará que el intervalo de fechas del informe sea el 1 de junio en adelante. Esto dará lugar a resultados indeseables. Cuando &quot;excluye&quot;, anula este comportamiento y limita los datos que puede extraer al intervalo de fechas adecuado.

![](assets/exclude-exclude.png)

## Paso 3: Aplicar este segmento a su VRS de CDA

![](assets/apply-segment.png)

## Paso 4: Ver los resultados en sistema de informes

Observe que sistema de informes ahora inicio en la fecha deseada, el mismo día en que se implementó por primera vez la costura:

![](assets/report-limited-dates.png)