---
description: Respuestas a preguntas que podría tener al implementar Audience Analytics.
solution: Experience Cloud
title: Preguntas más frecuentes sobre Audience Analytics
feature: Audience Analytics
exl-id: 86e7967c-030c-44d6-8294-e7e6d41f6fc3
source-git-commit: e37b8f3e9508ebaf673c992c03064a43559fb9cf
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 29%

---

# Preguntas frecuentes

Respuestas a preguntas que podría tener al implementar Audience Analytics.

## Preguntas frecuentes del ámbito jurídico {#legal}

+++ ¿Cómo sé si tengo información de identificación personal (PII) en mis datos de Analytics? Y si es así, ¿qué puedo hacer al respecto?

Si tiene correos electrónicos, direcciones, etc. en una prop o eVar, considere crear valores hash de los datos durante la recopilación. Si su país considera que la dirección IP es PII, [active la confusión de IP](/help/admin/tools/exclude-ip.md). Hable con su administrador de Analytics para ver lo que está recopilando. Hable con su departamento legal para ver qué consideran PII.

+++

+++ ¿Cómo sé si mis grupos de informes realizan personalización en el sitio o direccionamiento fuera o dentro del sitio?

Esto no se aplica al envío de datos de Adobe Analytics a Adobe Audience Manager. Pregúntese a usted mismo:

* ¿Volverá a compartir un segmento compartido de Analytics con una dimensión MCA en Experience Cloud?

* ¿Va a realizar la exportación (por ejemplo, a través de fuentes de datos) a un sistema de inteligencia empresarial (BI) que se use para este propósito?

+++

## Preguntas más frecuentes acerca de Adobe Audience Manager {#aam-specific}

+++ ¿Cómo se crea un destino de Analytics en Audience Manager?

Consulte [Configurar un destino de Analytics en Adobe Audience Manager](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/experience-cloud-destinations/create-analytics-destination.html?lang=es)&quot;.

+++

+++ Después de crear y guardar un destino de Analytics, ¿cuánto tardan los datos en aparecer en mis grupos de informes seleccionados?

Los grupos de informes pueden tardar varias horas en rellenarse con datos nuevos.

+++

+++ He creado un nuevo destino de Analytics, pero no lo veo en la sección Asignaciones de destino de mis segmentos disponibles. ¿Dónde está el destino o cómo puedo encontrarlo?

Un destino de Analytics desaparece de la sección Asignaciones de destino de un segmento cuando selecciona la opción **[!UICONTROL Asignar automáticamente todos los segmentos actuales y futuros]** en **[!UICONTROL Asignaciones de segmentos]**. Para evitarlo, seleccione **[!UICONTROL Asignar segmentos manualmente]** en lugar de la opción automática.

+++ ¿Esto me proporcionará toda la información de Adobe Audience Manager en Analytics?

No, solo los datos relacionados con personas que vienen a su sitio durante o después de la activación de Audiencias de Audience Manager y durante o después de la calificación de segmentos.

+++

+++ ¿Esto me proporcionará una audiencia total a la que poder dirigirme por segmento?

No. Le indicará el número de visitantes de ese segmento que han llegado a su sitio durante o después de la calificación de segmentos.

+++

+++ ¿En qué se diferencia esto del destino heredado de las cookies en Analytics?

Los segmentos se califican y se devuelven en tiempo real, en la misma visita. Se muestran automáticamente los nombres descriptivos.

+++

+++ ¿Qué sucede si algunos de mis grupos de informes contienen datos personales y otros no?&lt;

Sugerencia: Cree dos destinos. Añada los grupos de informes con datos personales a uno y los grupos sin datos personales al otro.

+++

## Preguntas más frecuentes acerca de Analytics {#aa-specific}

+++ ¿Aparecerá esta integración como dimensión o como segmento en Analytics?

Como dimensiones: ID de audiencias y Nombre de audiencias.

+++

+++¿Dónde puedo utilizar estas dimensiones en Analytics?

En todas partes; se las trata como cualquier otra dimensión recopilada en Analytics.

+++

+++ ¿Por qué no veo los datos que pasan a través de Analytics?

Es probable que tenga en Adobe Audience Manager un conflicto de controles de privacidad entre la fuente de datos y el destino.

+++

+++ ¿Por qué faltan en Analytics algunos de mis segmentos, aunque elegí enviarlos todos?&lt;

* Puede haber conflictos entre los controles de exportación de datos de Adobe Audience Manager del destino y de las fuentes de datos del segmento que impidan el envío de determinados segmentos.

* Si utiliza características de datos de terceros en sus segmentos, estos no pueden compartirse con destinos (grupos de conjuntos de informes) que contengan datos personales.

+++

+++ ¿Por qué veo &quot;Se ha alcanzado el límite de audiencias&quot; en mi informe de Analytics? (Nota: Esto también se representará como ID de audiencia = -1 y `::max_audiences_exceeded::` en Data Warehouse)

De forma predeterminada, la integración de Audience Analytics para Adobe Audience Manager envía a Analytics, para cada visita, todos los segmentos a los que el visitante pertenece. Si un visitante pertenece a más de 150 segmentos de Adobe Audience Manager en una sola visita, se enviarán a Analytics los **150 segmentos para los que se ha obtenido cualificación más recientemente**, mientras que el resto se truncará. Se envía a Analytics un marcador adicional que indica que la lista de segmentos se ha truncado y se muestra “Alcanzado límite de públicos” en la dimensión Nombre de público y “-1” en la dimensión ID de público.

Aunque es poco probable que un visitante esté cualificado para pertenecer a más de 150 segmentos en una visita particular, puede suceder en un pequeño número de ocasiones. Si el mensaje “Alcanzado límite de públicos” aparece en su informe, tiene dos opciones:

* Opción 1: permita que la integración siga funcionando del modo predeterminado, con el envío de los 150 segmentos para los que un visitante particular ha obtenido cualificación más recientemente.

* Opción 2: en Adobe Audience Manager, elija para la integración los 150 segmentos más relevantes para su negocio. A continuación, Adobe Audience Manager comprobará la adecuación de los visitantes a estos 150 segmentos. La desventaja de este enfoque es que solo recibirá estos 150 segmentos para todos los visitantes. Por su parte, la opción 1 puede ofrecer segmentos ilimitados, ya que la integración se produce por visita.

+++

+++ ¿Se facturarán llamadas de servidor adicionales a Analytics por esta integración?

No. Las audiencias de Adobe Audience Manager se incorporan a las visitas de Analytics en el servidor. Esto no incurre en llamadas adicionales al servidor en Analytics (ni principales ni secundarias).

+++

## Preguntas más frecuentes acerca del reenvío de lado del servidor (SSF) {#SSF}

+++ Si tengo implementado el reenvío de servidor, ¿tengo que activar también el reenvío de servidor para los grupos de informes en Administración de Analytics?

Sí. En la configuración de destino de Adobe Audience Manager solo verá los grupos de informes que tengan activado el reenvío de servidor.

+++

+++ ¿Por qué no puedo activar el reenvío de servidor para determinados grupos de informes en Administración de Analytics?

Solo pueden habilitarse los grupos asignados a su organización de Experience Cloud.

Para saber más sobre este tema, consulte [Preguntas frecuentes sobre el reenvío de lado del servidor](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-faq.md).

+++

## Preguntas más frecuentes generales {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

+++ ¿Por qué el visitante del segmento tiene un recuento diferente en Audience Manager y Analytics?

Ver [Diferencias de recuento de visitantes](/help/integrate/c-audience-analytics/visitor-count-reconciliation.md).

+++

+++ ¿Cuál es la diferencia entre las &quot;audiencias&quot; de Adobe Audience Manager y los &quot;segmentos&quot; de Analytics?

Consulte [Explicación de los segmentos en Analytics y Audience Manager](/help/integrate/c-audience-analytics/aam-analytics-segments.md). Las audiencias de Adobe Audience Manager se envían y comparten como componentes de &quot;dimensión&quot; para su uso en Analytics. No aparecen como segmentos en el Generador de segmentos, por ejemplo, sino como dimensiones con las que se pueden crear segmentos.

+++

+++ ¿Cuál es la diferencia entre los atributos del cliente y los datos de clientes integrados desde Adobe Audience Manager?

Los atributos del cliente no dependen del tiempo: se aplican de forma retroactiva y en adelante. Los datos integrados de Adobe Audience Manager dependen del tiempo y solo se aplican en adelante. Además, los atributos del cliente son una tabla de búsqueda para los ID de visitante de Experience Cloud, mientras que la integración de Adobe Audience Manager consiste en datos vinculados a cada visita de un visitante.

+++

+++ ¿Qué sucede con los enfoques heredados para este problema, como los antiguos destinos de cookies beta o de complemento de consultoría?

Recomendamos implementar la nueva integración y eliminar los destinos antiguos.

+++
