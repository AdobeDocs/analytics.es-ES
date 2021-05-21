---
title: Limitar un VRS a determinadas fechas
description: Obtenga información sobre cómo limitar un intervalo de fechas de VRS para que se centre únicamente en datos vinculados.
exl-id: 421d101d-8c64-47f7-b5a2-da039889f663
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '256'
ht-degree: 100%

---

# Limitar un VRS a determinadas fechas

Cuando activamos la vinculación, la vinculación comienza en una fecha específica. Supongamos que la fecha es el 1 de junio. El VRS de CDA contendrá datos no enlazados antes del 1 de junio. Es posible que desee ocultar cualquier dato del VRS anterior al 1 de junio para que el análisis pueda centrarse en los intervalos de fechas después de iniciar la vinculación.

Puede limitar los datos del VRS a determinadas fechas haciendo lo siguiente:

## Paso 1: Crear VRS con un intervalo de fechas diario móvil

Cuando configure el VRS, en Componentes, añada un intervalo de fechas que tenga un inicio fijo, con un intervalo de fechas diario móvil. El inicio fijo debe ser el día en que comenzó la vinculación.

![](assets/rolling-daily.png)

## Paso 2: Crear un segmento de &quot;exclusión&quot;

A continuación, cree un segmento de visitas que coloque el intervalo de fechas en un contenedor de exclusión dentro de otro contenedor de exclusión. Es una &quot;exclusión&quot;.

El motivo de la exclusión es que los intervalos de fechas pretenden anular el intervalo de fechas del informe. Por lo tanto, si solo se incluye el 1 de junio en adelante, siempre se realizará el intervalo de fechas del informe a partir del 1 de junio. Esto dará lugar a resultados no deseados. Cuando excluye, anula este comportamiento y limita los datos que se pueden dibujar al intervalo de fechas adecuado.

![](assets/exclude-exclude.png)

## Paso 3: Aplicar este segmento a su VRS de CDA

![](assets/apply-segment.png)

## Paso 4: Ver los resultados en la creación de informes

Tenga en cuenta que ahora la creación de informes se inicia en la fecha deseada, el mismo día en que se implementó la vinculación por primera vez:

![](assets/report-limited-dates.png)
