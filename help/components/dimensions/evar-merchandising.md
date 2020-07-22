---
title: eVar (comercialización)
description: Variables personalizadas que se relacionan con la dimensión products.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 25%

---


# eVar (comercialización)

*Esta página de ayuda describe cómo funcionan las eVars de comercialización como una dimensión. For information on how to implement merchandising eVars, see[eVars](/help/implement/vars/page-vars/evar.md)in the Implement user guide.*

Al medir el éxito de campañas o términos de búsqueda externos, normalmente se desea que un único valor reciba crédito por los eventos de éxito que se produzcan. Por ejemplo, si un cliente hace clic en un vínculo de una campaña de correo electrónico para visitar un sitio web, todas las compras que se realicen como resultado de ese clic deben abonarse a dicha campaña.

¿Qué sucede con los eventos que son impulsados por la búsqueda interna o por la exploración de categorías cuando un cliente busca varios elementos? For example, a customer searches your site for `"goggles"`, then adds a pair to their cart:

![Ejemplo de gafas](assets/merch-example-goggles.png)

Before checkout, the customer searches for `"winter coat"`, then adds a down jacket to the to their cart:

![Ejemplo de abrigo](assets/merch-example-coat.png)

Cuando el visitante complete esta compra, tendrá una búsqueda interna para `"winter coat"` acreditar la compra de un par de gafas (suponiendo que la eVar utilice la asignación predeterminada de &#39;Más reciente&#39;). Good for `"winter coat"`, but bad for marketing decisions:

| Término de búsqueda interna | Ingresos |
|---|---|
| abrigo de invierno | 157 $ |

## Solución de este problema con las variables de comercialización

Las eVars de comercialización permiten asignar el valor actual de una eVar a un producto en el momento en que se produce un evento de éxito. Este valor se mantendrá enlazado con dicho producto, incluso en el caso de que posteriormente se establezcan uno o varios valores nuevos para la eVar específica.

If merchandising is enabled for the eVar in the previous example, the search term `"goggles"` is tied to the snow goggles, and the search term `"winter coat"` is tied to the down jacket. Las eVars de comercialización asignan los ingresos a nivel de producto, de modo que cada término recibe el crédito por la cantidad de ingresos del producto al que se asoció el término:

| Término de búsqueda interna | Ingresos |
|---|---|
| abrigo de invierno | 119 $ |
| gafas protectoras | 38 $ |

Consulte [eVars](/help/implement/vars/page-vars/evar-merchandising.md) de comercialización para obtener instrucciones de implementación.

## Las instancias en las variables de comercialización

No se recomienda utilizar la métrica [Instancias](../metrics/instances.md) en variables de comercialización.

* Para las variables de comercialización que utilizan sintaxis de producto, las instancias no se incrementan en absoluto.
* Para las variables de comercialización que utilizan sintaxis de variable de conversión, las instancias se cuentan cada vez que se configura la eVar. Sin embargo, se atribuye al elemento de dimensión `"None"` , a menos que lo siguiente suceda en la misma visita:
   * La eVar de comercialización se establece con un valor.
   * La `products` variable se define con un valor.
   * Se establece un evento de enlace.

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

Dado que la mayoría de los casos de uso de la sintaxis de variables de conversión requieren la variable eVar y products en diferentes visitas, el uso de la métrica &#39;Instancias&#39; no es realista.
