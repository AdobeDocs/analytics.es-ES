---
title: Eventos personalizados
description: El número de visitas en las que se produce un evento personalizado.
feature: Metrics
exl-id: 9ae3ff53-8634-466a-a9f6-786c1e62c2fa
TQID: https://experienceleague.adobe.com/1D8ONiUuG3T6DqM7HygbBbf0Y4ja5ej1Hfy8-hKo0yg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889beid: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 223
ht-degree: 91%

---

# Eventos personalizados

*Esta página de ayuda describe cómo funcionan los eventos personalizados como una métrica. Para obtener información sobre cómo funcionan los eventos personalizados como una variable de implementación, consulte [Información general sobre Eventos](/help/implement/vars/page-vars/events/events-overview.md) en la Guía del usuario de implementación.*

El evento personalizado [metrics](overview.md) muestra el número de visitas donde se configuró un evento personalizado determinado en una solicitud de imagen. Estas métricas son vitales para muchas implementaciones, ya que proporcionan una perspectiva de los eventos específicos de cada organización.

## Cálculo de esta métrica

Los eventos personalizados se calculan de forma diferente en función de su tipo. Puede comprobar el tipo de evento en [Eventos de éxito](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md) en la configuración del grupo de informes.

* **Eventos de contador**: La configuración de evento predeterminada. La mayoría de los eventos son eventos de contador. Cuenta el número de visitas en las que el evento personalizado coincidente `event1` - `event1000` existe en la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).
* **Eventos numéricos**: Suma el valor numérico asignado al evento en la variable `events`.
* **Eventos monetarios**: Aplica la conversión de moneda al tipo de cambio de ese día y, a continuación, suma el valor numérico asignado a cada visita individual en la variable `events`.

El número de eventos disponibles depende del contrato de Analytics de su organización. La mayoría de las organizaciones con contratos no incluidos tienen disponibles 1000 eventos personalizados. Contacte con el equipo de cuentas de Adobe si no está seguro de cuántos eventos personalizados tiene a su disposición.

Adobe recomienda que registre cómo utiliza cada evento en el [documento de diseño de soluciones](/help/implement/prepare/solution-design.md) de su organización.
