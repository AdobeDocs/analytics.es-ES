---
title: Limitar un grupo de informes virtuales a determinadas fechas
description: Obtenga información sobre cómo limitar el intervalo de fechas de un grupo de informes virtuales para que se centre únicamente en los datos vinculados.
exl-id: 421d101d-8c64-47f7-b5a2-da039889f663
feature: CDA
role: Admin
TQID: https://experienceleague.adobe.com/x7zHG4xkSr1yDLZ2dfosn5PaK4JVxiMWC6xksSTLypE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 288
ht-degree: 41%

---

# Limitar un grupo de informes virtuales a determinadas fechas

{{available-existing-customers}}

Cuando activamos la vinculación, la vinculación comienza en una fecha específica. Supongamos que la fecha es el 1 de junio. El grupo de informes virtuales de CDA contendrá datos no enlazados antes del 1 de junio. Es posible que desee ocultar cualquier dato del grupo de informes virtuales anterior al 1 de junio para que el análisis pueda centrarse en los intervalos de fechas después de iniciar la vinculación.

Puede limitar los datos del grupo de informes virtuales a determinadas fechas haciendo lo siguiente:

## Paso 1: Crear un grupo de informes virtuales con un intervalo de fechas diario móvil

Cuando configure el grupo de informes virtuales, en Componentes, añada un intervalo de fechas que tenga un inicio fijo, con un intervalo de fechas diario móvil. El inicio fijo debe ser el día en que comenzó la vinculación.

![](assets/rolling-daily.png)

## Paso 2: Crear un segmento de &quot;exclusión&quot;

A continuación, cree un segmento de visitas que coloque el intervalo de fechas en un contenedor de exclusión dentro de otro contenedor de exclusión. Es una &quot;exclusión&quot;.

El motivo de la exclusión es que los intervalos de fechas pretenden anular el intervalo de fechas del informe. Por lo tanto, si solo se incluye el 1 de junio en adelante, siempre se realizará el intervalo de fechas del informe a partir del 1 de junio. Esto dará lugar a resultados no deseados. Cuando excluye, anula este comportamiento y limita los datos que puede dibujar al intervalo de fechas adecuado.

![](assets/exclude-exclude.png)

## Paso 3: Aplicar este segmento a su grupo de informes virtuales de análisis entre dispositivos

![](assets/apply-segment.png)

## Paso 4: Ver los resultados en la creación de informes

Tenga en cuenta que ahora la creación de informes se inicia en la fecha deseada, el mismo día en que se implementó la vinculación por primera vez:

![](assets/report-limited-dates.png)
