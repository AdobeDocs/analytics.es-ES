---
title: Eventos personalizados
description: El número de visitas en las que se produce un evento personalizado.
translation-type: ht
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: ht
source-wordcount: '221'
ht-degree: 100%

---


# Eventos personalizados

*Esta página de ayuda describe cómo funcionan los eventos personalizados como una métrica. Para obtener información sobre cómo funcionan los eventos personalizados como una variable de implementación, consulte [Información general sobre Eventos](/help/implement/vars/page-vars/events/events-overview.md) en la Guía del usuario de implementación.*

Las métricas de evento personalizadas muestran el número de visitas en las que se configuró un evento personalizado determinado en una solicitud de imagen. Estas métricas son vitales para muchas implementaciones, ya que proporcionan una perspectiva de los eventos específicos de cada organización.

## Cálculo de esta métrica

Los eventos personalizados se calculan de forma diferente en función de su tipo. Puede comprobar el tipo de evento en [Eventos de éxito](../../admin/admin/c-success-events/success-event.md) en la configuración del grupo de informes.

* **Eventos de contador**: La configuración de evento predeterminada. La mayoría de los eventos son eventos de contador. Cuenta el número de visitas en las que el evento personalizado coincidente `event1` - `event1000` existe en la variable [`events`](/help/implement/vars/page-vars/events/events-overview.md).
* **Eventos numéricos**: Suma el valor numérico asignado al evento en la variable `events`.
* **Eventos monetarios**: Aplica la conversión de moneda al tipo de cambio de ese día y, a continuación, suma el valor numérico asignado a cada visita individual en la variable `events`.

El número de eventos disponibles depende del contrato de Analytics de su organización. La mayoría de las organizaciones con contratos no incluidos tienen disponibles 1000 eventos personalizados. Contacte con el administrador de cuentas de su organización si no está seguro de cuántos eventos personalizados tiene a su disposición.

Adobe recomienda que registre cómo utiliza cada evento en el [documento de diseño de soluciones](/help/implement/prepare/solution-design.md) de su organización.
