---
title: Eventos personalizados
description: El número de visitas en las que se produce un evento personalizado.
feature: Metrics
exl-id: 9ae3ff53-8634-466a-a9f6-786c1e62c2fa
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 83%

---

# Eventos personalizados

*Esta página de ayuda describe cómo funcionan los eventos personalizados como una métrica. Para obtener información sobre cómo funcionan los eventos personalizados como una variable de implementación, consulte [Información general sobre Eventos](/help/implement/vars/page-vars/events/events-overview.md) en la Guía del usuario de implementación.*

El evento personalizado [metrics](overview.md) muestra el número de visitas donde se configuró un evento personalizado determinado en una solicitud de imagen. Estas métricas son vitales para muchas implementaciones, ya que proporcionan una perspectiva de los eventos específicos de cada organización.

## Cálculo de esta métrica

Los eventos personalizados se calculan de forma diferente en función de su tipo. Puede comprobar el tipo de evento en [Eventos de éxito](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md) en la configuración del grupo de informes.

* **Eventos de contador**: La configuración de evento predeterminada. La mayoría de los eventos son eventos de contador. Cuenta el número de visitas en las que el evento personalizado coincidente `event1` - `event1000` existe en la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).
* **Eventos numéricos**: Suma el valor numérico asignado al evento en la variable `events`.
* **Eventos monetarios**: Aplica la conversión de moneda al tipo de cambio de ese día y, a continuación, suma el valor numérico asignado a cada visita individual en la variable `events`.

El número de eventos disponibles depende del contrato de Analytics de su organización. La mayoría de las organizaciones con contratos no incluidos tienen disponibles 1000 eventos personalizados. Póngase en contacto con el equipo de su cuenta de Adobe si no está seguro de cuántos eventos personalizados tiene a su disposición.

Adobe recomienda que registre cómo utiliza cada evento en el [documento de diseño de soluciones](/help/implement/prepare/solution-design.md) de su organización.
