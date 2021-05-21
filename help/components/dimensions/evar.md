---
title: eVar
description: Dimensión personalizada que se puede utilizar en sistema de informes.
exl-id: ce7cc999-281d-4c52-b64d-d44cc320ab2d
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '788'
ht-degree: 100%

---

# eVar

*Esta página de ayuda describe cómo funcionan las eVars como dimensiones. Para obtener información sobre cómo implementar eVars, consulte [eVars](/help/implement/vars/page-vars/evar.md) en la guía de implementación de usuario.*

Las eVars son variables personalizadas que se pueden utilizar como desee. Si tiene un [documento de diseño de solución](/help/implement/prepare/solution-design.md), la mayoría de las dimensiones específicas de su organización terminan como eVars. De forma predeterminada, las eVars persisten más allá de la visita en la que están configuradas. Puede personalizar su caducidad y asignación en [Variables de conversión](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) en la configuración del grupo de informes.

El número de eVars disponibles depende del contrato con Adobe. Hay disponibles hasta 250 eVars si su contrato con Adobe lo permite.

Las eVars no hacen distinción entre mayúsculas y minúsculas. Si envía el mismo valor en casos diferentes (por ejemplo, `"DOG"` y `"Dog"`), Analysis Workspace los agrupa en el mismo elemento de dimensión. Se utiliza el caso del primer valor visto al comienzo del mes de creación de informes. Data Warehouse muestra el primer valor que se encuentra durante el período de solicitud.

## Propagar eVars con datos

Cada eVar recopila datos de la cadena de consulta [`v1` - `v250` ](/help/implement/validate/query-parameters.md) en solicitudes de imagen. Por ejemplo, el parámetro de cadena de consulta `v1` recopila datos para eVar1, mientras que el parámetro de cadena de consulta `v222` recopila datos para eVar222.

AppMeasurement, que compila variables JavaScript en una solicitud de imagen para la recopilación de datos, utiliza las variables `eVar1` - `eVar250`. Consulte [eVar](/help/implement/vars/page-vars/evar.md) en la Guía del usuario de implementación para ver las directrices de implementación.

## Elementos de dimensión

Dado que las eVars contienen cadenas personalizadas en la implementación, su organización determina cuáles son los elementos de dimensión para cada eVar. Asegúrese de registrar el propósito de cada eVar y los elementos de dimensión típicos en un [documento de diseño de solución](/help/implement/prepare/solution-design.md).

## Cómo funcionan las eVars

Al enviar datos a Adobe Analytics, los servidores de recopilación de datos traducen la visita en una única fila de datos con cientos de columnas. Se dedican dos columnas a cada eVar; una para la recopilación directa de datos y otra para los valores persistentes.

* Una columna estándar contiene datos enviados a Adobe desde la solicitud de imagen.
* Una columna &quot;publicación&quot; contiene datos persistentes, que dependen de la caducidad y asignación de la eVar.

En casi todas las circunstancias, la columna `post_evar` se utiliza en los informes.

### Cómo se vinculan las eVars con las métricas

Los eventos de éxito y las eVars se definen con frecuencia en distintas solicitudes de imagen. La columna `post_evar` permite que los valores de eVar se vinculen a eventos, mostrando los datos en sistema de informes. Examine la siguiente visita, por ejemplo:

1. Un visitante llega a su sitio en la página de inicio.
2. Buscan &quot;gatos&quot; usando la búsqueda interna del sitio. La implementación utiliza eVar1 para la búsqueda interna.
3. Ven un producto y continúan con el proceso de cierre de compra.

Una versión simplificada de los datos sin procesar tendría un aspecto similar al siguiente:

| `visitor_id` | `pagename` | `evar1` | `post_evar1` | `event_list` |
| --- | --- | --- | --- | --- |
| `examplevisitor_987` | `Home page` |  |  |  |
| `examplevisitor_987` | `Search results` | `cats` | `cats` | `event1` |
| `examplevisitor_987` | `Product page` |  | `cats` | `prodView` |
| `examplevisitor_987` | `Cart` |  | `cats` | `scAdd` |
| `examplevisitor_987` | `Checkout` |  | `cats` | `scCheckout` |
| `examplevisitor_987` | `Purchase confirmation` |  | `cats` | `purchase` |

* La columna `visitor_id` vincula las visitas al mismo visitante. En los datos sin procesar reales, los valores concatenados de `visid_high` y `visid_low` determinan el ID de visitante.
* La columna `pagename` rellena la dimensión Páginas.
* La columna `evar` determina las visitas cuando se configuró explícitamente eVar1.
* El `post_evar1` lleva el valor anterior, según la asignación y caducidad de la variable establecida en la configuración del grupo de informes.
* La columna `event_list` contiene todos los datos de la métrica. Para este ejemplo, `event1` es &#39;Búsquedas&#39; y los otros eventos son métricas estándar del carro de compras. En los datos sin procesar reales, `event_list` contiene un conjunto de números delimitados por comas con una tabla de búsqueda que vincula esos números a una métrica.

### Traducción de la recopilación de datos al sistema de informes

Las herramientas de Adobe Analytics, como Analysis Workspace, funcionan con estos datos recopilados. Por ejemplo: si extrajera un informe con eVar1 como dimensión y Pedidos como métrica, vería un informe similar al siguiente:

| `Internal search term (eVar1)` | `Orders` |
| --- | --- |
| `cats` | `1` |

Analysis Workspace extrae este informe con la siguiente lógica:

* Busque todos los valores de `event_list` y elija todas las visitas con `purchase` en ellos.
* De estas visitas, muestre el valor de `post_evar1`.

### La importancia de la asignación y la caducidad

Dado que la asignación y la caducidad determinan qué valores persisten, son vitales para obtener el máximo valor de una implementación de Analytics. Adobe recomienda explicar en su organización cómo se administran los valores múltiples para cada eVar (asignación) y cuándo las eVars dejan de contener datos (caducidad).

* De forma predeterminada, una eVar utiliza la última asignación. Los valores nuevos sobrescriben los valores persistentes.
* De forma predeterminada, una eVar utiliza una caducidad de visita. Una vez que finaliza una visita, los valores dejan de copiarse de fila en fila en la columna `post_evar`.

Puede cambiar la asignación y caducidad de la eVar en [Variables de conversión](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) en la configuración del grupo de informes.

## Valor de las eVars sobre las props

Adobe recomienda utilizar eVars en la mayoría de los casos, admitidas a través de lo siguiente:

* Las eVars tienen un límite de 255 bytes en los informes. Las props tienen un límite de 100 bytes.
* De forma predeterminada, las props no persisten más allá de la visita que están configuradas. Las eVars tienen una fecha de caducidad personalizada, lo que permite determinar cuándo una eVar deja de obtener crédito por un evento subsiguiente. Sin embargo, si utiliza el procesamiento [del tiempo de los informes](/help/components/vrs/vrs-report-time-processing.md), tanto las propiedades como las eVars pueden usar un modelo de atribución personalizado.
* Adobe admite hasta 250 eVars y solo 75 props.

Consulte [prop](prop.md) para obtener más comparaciones entre eVars y props.
