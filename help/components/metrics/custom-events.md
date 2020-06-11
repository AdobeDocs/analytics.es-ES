---
title: Eventos personalizados
description: El número de visitas en las que existe un evento personalizado.
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 19%

---


# Eventos personalizados

*Esta página de ayuda describe cómo funcionan los eventos personalizados como una métrica. Para obtener información sobre cómo funcionan los eventos personalizados como una variable de implementación, consulte Información general sobre[Eventos](/help/implement/vars/page-vars/events/events-overview.md)en la Guía del usuario de implementación.*

Las métricas de evento personalizadas muestran el número de visitas en las que se configuró un evento personalizado determinado en una solicitud de imagen. Estas métricas son vitales para muchas implementaciones, ya que proporcionan una perspectiva de los eventos específicos de cada organización.

## Cómo se calcula esta métrica

Los eventos personalizados se calculan de forma diferente en función de su tipo. Puede comprobar el tipo de evento en eventos [de](../../admin/admin/c-success-events/success-event.md) éxito en la configuración del grupo de informes.

* **eventos** de contador: La configuración de evento predeterminada. La mayoría de los eventos son contreventos. Cuenta el número de visitas en las que el evento personalizado coincidente `event1` - `event1000` existe en la [`events`](/help/implement/vars/page-vars/events/events-overview.md) variable.
* **eventos** numéricos: Suma el valor numérico asignado al evento en la `events` variable.
* **eventos** monetarios: Aplica la conversión de moneda al tipo de cambio de ese día y, a continuación, suma el valor numérico asignado a cada visita individual en la `events` variable.

El número de eventos disponibles depende del contrato de Analytics de su organización. La mayoría de las organizaciones con contratos no incluidos tienen disponibles 1000 eventos personalizados. Contacte con el administrador de cuentas de su organización si no está seguro de cuántos eventos personalizados tiene a su disposición.

Adobe recomienda encarecidamente que registre cómo utiliza cada evento en el documento [de diseño de](/help/implement/prepare/solution-design.md)soluciones de su organización.
