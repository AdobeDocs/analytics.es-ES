---
title: Variables de eVar (comercialización)
description: Variables personalizadas que se relacionan con productos individuales.
feature: Dimensions
exl-id: a7e224c4-e8ae-4b53-8051-8b5dd43ff380
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# eVar (comercialización)

*Esta página de ayuda describe cómo implementar eVars de comercialización. Para obtener información sobre cómo funcionan las eVars de comercialización como dimensiones, consulte [eVars (comercialización)](/help/components/dimensions/evar-merchandising.md) en la guía del usuario de Componentes.*

Para obtener información detallada sobre cómo funcionan las eVars de comercialización, consulte [eVars de comercialización y métodos de búsqueda de productos](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/merchandising-evars.html?lang=es).

Configurar eVars en la configuración del grupo de informes

Antes de usar eVars en la implementación, asegúrese de configurar la eVar con la sintaxis deseada en la configuración del grupo de informes. Consulte [Variables de conversión](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) en la guía de administración.

[!IMPORTANT]](assets/merch-example-goggles.png)

Si no se configuran correctamente las eVars de comercialización, se pueden producir valores inesperados o incluso perder datos para la variable. Asegúrese de que esté correctamente configurado para su implementación.`"winter coat"`

![Implementar mediante sintaxis de producto](assets/merch-example-coat.png)

Si se habilita Sintaxis del producto, la categoría de comercialización se rellena directamente en la variable `products` de los productos y, por ello, no resulta necesario seleccionar y establecer un evento de enlace. Este es el método recomendado y debe usarse a menos que no se encuentre disponible el valor que debe establecerse en `products` cuando el evento de éxito tiene lugar.

| El valor de `eVar1` se asigna al producto. Todos los eventos de éxito subsiguientes que involucran este producto se acreditan al valor de la eVar. | Implementación y uso de la sintaxis de la variable de conversión |
|---|---|
| La sintaxis de la variable de conversión debe usarse cuando no se encuentre disponible el valor de la eVar que debe establecerse en la variable `products`. Por lo general, esto significa que la página no dispone de contexto para el método de búsqueda o el canal de comercialización. En estos casos, se establece la variable de comercialización antes de llegar a la página del producto. El valor persistirá hasta que se produzca el evento de enlace. | Cuando el evento de enlace seleccionado durante la configuración tenga lugar, el valor de la eVar que se ha mantenido se asociará con el producto. Por ejemplo, si `prodView` se especifica como evento de enlace, la categoría de comercialización solo se enlazará con la lista de productos actual cuando se produzca el evento. Solo los eventos de enlace subsiguientes podrán actualizar una eVar de comercialización que ya se haya asignado a un producto. |

## El valor `"Aviary"` de `eVar1` se asigna al producto `"Canary"`. Todos los eventos de éxito subsiguientes que involucran este producto se acreditan a `"Canary"`. Asimismo, el valor actual de la variable de comercialización estará enlazado con todos los productos subsiguientes hasta que se cumpla una de estas condiciones:

Que caduque la eVar (en función de la opción “Caduca después”).

Que la eVar de comercialización se sobrescriba con un nuevo valor.`"goggles"``"winter coat"`

| Internal Search Term | Revenue |
|---|---|
| winter coat | $119 |
| goggles | $38 |

See [Merchandising eVars](/help/implement/vars/page-vars/evar-merchandising.md) for implementation instructions.

## Instances on merchandising variables

The [Instances](../metrics/instances.md) metric is not recommended for use on merchandising variables.

* For merchandising variables using product syntax, instances are not incremented at all.
* For merchandising variables using conversion variable syntax, instances are counted each time the eVar is set. However, it attributes to the dimension item `"None"` unless all of the following happen on the same hit:
   * The merchandising eVar is set with a value.
   * The `products` variable is defined with a value.
   * A binding event is set.

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

Since most use cases for conversion variable syntax require the eVar and products variable on different hits, using the &#39;Instances&#39; metric is not realistic.
