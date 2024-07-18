---
description: Aprenda a implementar el etiquetado de grupos múltiples para enviar solicitudes de imagen a varios grupos de informes.
title: Implementación del etiquetado de grupos múltiples
feature: Implementation Basics
exl-id: c7fb0478-97e1-4367-8742-e7539f6f82e7
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 93%

---

# Implementación del etiquetado de grupos múltiples

[El etiquetado de grupos múltiples](/help/admin/admin/c-manage-report-suites/rollup-report-suite.md) le permite enviar solicitudes de imagen no solo a un grupo de informes globales, sino también a grupos de informes secundarios individuales, de modo que pueda proporcionar subconjuntos de los datos del grupo de informes globales de su empresa a distintos usuarios finales.

Para implementar el etiquetado de grupos múltiples, debe incluir el ID del grupo de informes (RSID) para el grupo de informes globales y también los RSID para los grupos de informes secundarios aplicables en el código de seguimiento de sus páginas web y aplicaciones.

* En el caso de implementaciones de etiquetas de Adobe Experience Platform, especifique cada uno de los grupos de informes para la [[!DNL Analytics] extensión](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=es).

* En implementaciones heredadas de JavaScript y SDK móvil, separe los RSID con comas sin espacios (`rsid1,rsid2,rsid3`, etc.).

* Para otros tipos de implementación, utilice la sintaxis necesaria para enumerar varios RSID.

>[!TIP]
>
> La práctica recomendada es enumerar primero el grupo de informes global o el ID del grupo de informes.

El etiquetado de grupos múltiples implica varias llamadas al servidor para cada solicitud de imagen: una llamada primaria al grupo de informes globales y una llamada secundaria a cada grupo de informes secundarios.

>[!NOTE]
>
> [Los grupos de informes virtuales](/help/components/vrs/vrs-about.md), que también le permiten proporcionar subconjuntos de datos de grupos de informes globales de su empresa a distintos usuarios finales, no incurren en llamadas secundarias al servidor.

## ¿Debería implementar el etiquetado de grupos múltiples o los grupos de informes virtuales?

El uso de grupos de informes virtuales en lugar del etiquetado de grupos múltiples suele ser una práctica recomendada, pero las necesidades de su empresa determinan la mejor opción de los grupos de informes para su organización.

Para saber si los grupos de informes virtuales son su mejor opción, consulte &quot;[Grupos de informes virtuales y consideraciones sobre el etiquetado de grupos múltiples](/help/components/vrs/vrs-considerations.md)&quot;. Consulte también &quot;[Grupos de informes virtuales frente a ,etiquetado de grupos múltiples](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)&quot; para ver una comparación del etiquetado de grupos múltiples y la funcionalidad del grupo de informes virtuales.
