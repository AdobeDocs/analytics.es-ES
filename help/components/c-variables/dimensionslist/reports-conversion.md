---
title: eVar
description: Dimensión personalizada que se puede utilizar en sistema de informes.
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# eVar

*Esta página de ayuda describe cómo funcionan las eVars como dimensiones. Para obtener información sobre cómo implementar eVars, consulte[eVars](/help/implement/vars/page-vars/evar.md)en la guía de implementación de usuario.*

Las eVars son variables personalizadas que se pueden utilizar como desee. Si tiene un documento [de diseño de](/help/implement/prepare/solution-design.md)solución, la mayoría de las dimensiones específicas de su organización terminan como eVars. De forma predeterminada, las eVars persisten más allá de la visita en la que están configuradas. Puede personalizar su caducidad y asignación en Variables [de](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversión en la configuración del grupo de informes.

## Cómo funcionan las eVars

Al enviar datos a Adobe Analytics, los servidores de recopilación de datos traducen la visita en una única fila de datos con cientos de columnas. Se dedican dos columnas a cada eVar; uno para la recopilación directa de datos y el otro para los valores persistentes.

* Una columna estándar contiene datos enviados a Adobe desde la solicitud de imagen.
* Una columna &quot;publicación&quot; contiene datos persistentes, que dependen de la caducidad y asignación de la eVar.

En casi todas las circunstancias, la columna `post_evar` se utiliza en los informes.

### Cómo se vinculan las eVars con las métricas

Los eventos de éxito y las eVars se definen con frecuencia en distintas solicitudes de imagen. La `post_evar` columna permite que los valores de eVar se vinculen a eventos, mostrando los datos en sistema de informes. Por ejemplo:

1. Un visitante llega a su sitio en la página de inicio.
2. Buscan &quot;gatos&quot; usando la búsqueda interna del sitio. La implementación configura eVar1 en búsqueda interna.
3. vista un producto y continúa el proceso de cierre de compra.

Una versión simplificada de los datos sin procesar tendría un aspecto similar al siguiente:

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* La `visitor_id` columna vincula las visitas al mismo visitante. En los datos sin procesar reales, los valores concatenados de `visid_high` y `visid_low` determinan el ID de visitante.
* La `pagename` columna rellena la dimensión Páginas.
* La `evar` columna determina las visitas cuando se configuró explícitamente eVar1.
* El `post_evar1` lleva el valor anterior, según la asignación y caducidad de la variable establecida en la configuración del grupo de informes.
* La `event_list` columna contiene todos los datos de la métrica. Para este ejemplo, `event1` es &#39;Búsquedas&#39; y los otros eventos son métricas estándar del carro de compras. En los datos sin procesar reales, `event_list` contiene un conjunto de números delimitados por comas con una tabla de búsqueda que vincula esos números a una métrica.

### Traducción de la recopilación de datos al sistema de informes

Las herramientas de Adobe Analytics, como el espacio de trabajo de Análisis, funcionan con estos datos recopilados. Por ejemplo: si extrajera un informe usando eVar1 como dimensión y Pedidos como métrica, vería un informe similar al siguiente:

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

Espacio de trabajo de Análisis extrae este informe con la siguiente lógica:

* Busque todos `event_list` los valores y elija todas las visitas con `purchase` ellos.
* De estas visitas, muestre el `post_evar1` valor.

### La importancia de la asignación y la caducidad

Dado que la asignación y la caducidad determinan qué valores persisten, son vitales para obtener el máximo valor de una implementación de Analytics. Adobe recomienda que explique en su organización cómo se administran los valores múltiples para cada eVar (asignación) y cuándo las eVars dejan de contener datos (caducidad).

* De forma predeterminada, una eVar utiliza la última asignación. Los valores nuevos sobrescriben los valores persistentes.
* De forma predeterminada, una eVar utiliza una caducidad de visita. Una vez que finaliza una visita, los valores dejan de copiarse de fila en fila en la `post_evar` columna.

Puede cambiar la asignación y caducidad de la eVar en Variables [de](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversión en la configuración del grupo de informes.
