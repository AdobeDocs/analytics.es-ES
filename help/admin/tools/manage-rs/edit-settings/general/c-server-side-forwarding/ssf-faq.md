---
description: Preguntas más frecuentes acerca de características, funcionalidades y problemas relativos al reenvío del lado del servidor.
title: Preguntas frecuentes acerca del reenvío del lado del servidor
feature: Report Suite Settings
exl-id: 63103d2b-e2e8-42da-bdbd-be90abe305f7
role: Admin
TQID: 'https://experienceleague.adobe.com/av541DJd5Ga5QaK2856YBHWW1M-JjkbzRs8JXxYma6c'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b8734a57-d5fb-44a8-8ee1-65225cecaeaeid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: c354699e-6555-4397-8706-1a9a89984069
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 707
ht-degree: 42%

---

# Preguntas frecuentes acerca del reenvío del lado del servidor

Preguntas más frecuentes acerca de características, funcionalidades y problemas relativos al reenvío del lado del servidor.

## Servidores de seguimiento {#section_28E5BECC2034484AB9726E513F2CCFB7}

| Pregunta | Respuesta |
|--- |--- |
| P: ¿Qué sucede si utilizo el antiguo reenvío de servidor basado en servidores de seguimiento? | El antiguo método de reenvío del lado del servidor basado en servidor de seguimiento seguirá reenviando datos de Analytics a Audience Manager. Sin embargo, si desea enviar segmentos de Audience Manager a Analytics, se requiere el nuevo reenvío del lado del servidor basado en grupos de informes. Además, no supone ningún daño habilitar un grupo de informes para el reenvío del lado del servidor además de la configuración del servidor de seguimiento: se utilizará la nueva configuración del reenvío del lado del servidor del grupo de informes siempre que haya un conflicto. |
| P: ¿Debo migrar mi antiguo reenvío de servidor basado en servidor de seguimiento al nuevo, basado en grupos de informes? | Seguiremos admitiendo el reenvío del lado del servidor basado en el servidor de seguimiento en el futuro próximo. Sin embargo, si desea aprovechar la integración de Audience Manager a Analytics (uso compartido de segmentos en Analytics), deberá habilitar el nuevo reenvío del lado del servidor basado en grupos de informes para todos los grupos de informes aplicables. Sin embargo, no hay ninguna razón urgente para deshabilitar el reenvío del lado del servidor basado en servidores de seguimiento heredados. |

## Etiquetado y realización de informes {#section_71391BA901AC47B9A2286281644FF281}

| Pregunta | Respuesta |
|--- |--- |
| P: ¿Qué pasa si en mi sitio tengo etiquetado multigrupo? ¿Duplicará el reenvío del lado del servidor las llamadas de servidor a Audience Manager? | No, las visitas se reenvían una única vez de Analytics a Audience Manager, con independencia del número de grupos de informes que haya en ellas. Si tiene en Audience Manager fuentes de datos correspondientes para cada grupo de informes de la visita, todas ellas se rellenarán apropiadamente a partir de esa única visita.  Tenga en cuenta, no obstante, que si utiliza la recopilación de datos de lado de clientes (DIL) y habilita el reenvío del lado del servidor sin instalar el módulo Gestión de público, estará duplicando las llamadas de servidor a Audience Manager, independientemente del número de grupos de informes que tenga en su visita de Analytics. |
| P: ¿Qué sucede si tengo grupos de informes etiquetados multigrupo asignados a distintas organizaciones empresariales de CX? | Nunca debe enviar datos de una sola visita de Analytics a dos grupos de informes que pertenezcan a organizaciones empresariales de CX independientes, pero, si esto ocurre, únicamente se reenviará la visita a la organización empresarial de CX que coincida con la configuración del servicio de ID en la página. |
| P: ¿Qué sucede si tengo etiquetado multigrupo y solo uno de mis grupos de informes está asignado a mi organización empresarial CX y el otro no? | La visita se reenviará al servidor de recopilación de datos correspondiente a la organización empresarial CX de su grupo de informes asignado. Sin embargo, como el grupo de informes no asignado no tendrá asociada una fuente de datos en Audience Manager, no se registrará ningún dato para el grupo de informes no asignado en Audience Manager. |
| P: ¿Qué sucede si tengo un grupo de informes asignado a varias organizaciones empresariales de CX? | Analytics considerará este grupo de informes como no asignado y no permitirá que se active el reenvío del lado del servidor para este grupo de informes. Póngase en contacto con el servicio de atención al cliente para resolver este problema de asignación. |
| P: ¿Será más lento el método de reenvío de servidor basado en grupos de informes que el basado en servidores de seguimiento? | No, el tiempo de respuesta es el mismo. |
| P: ¿Qué sucede si tenemos dos organizaciones empresariales CX (o instancias de Adobe Audience Manager) y queremos compartir datos entre ambas? ¿Puedo utilizar el reenvío de servidor para enviar una sola visita de Analytics a varias organizaciones empresariales de CX? | No. Si necesita compartir datos recopilados por una organización empresarial de CX con otra, le recomendamos que envíe las audiencias aplicables de una instancia de Audience Manager a otra mediante el mercado de audiencias. |
| P: ¿Resultará el reenvío del lado del servidor en alguna facturación adicional en Audience Manager o Analytics? | En Analytics no se producirá ninguna facturación adicional. En Audience Manager, las visitas reenviadas se tratan como cualquier otra visita y se facturan.  Por eso es tan importante no tener habilitados al mismo tiempo DIL y el reenvío del lado del servidor, lo que podría provocar dobles facturaciones, además de la duplicación de datos. |

>[!MORELIKETHIS]
>
>* [Reenvío del lado del servidor](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md)
