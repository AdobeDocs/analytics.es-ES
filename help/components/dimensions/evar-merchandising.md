---
title: eVar (dimensión de comercialización)
description: Variables personalizadas que se relacionan con la dimensión Productos.
feature: Dimensions
exl-id: a7e224c4-e8ae-4b53-8051-8b5dd43ff380
TQID: https://experienceleague.adobe.com/No-Va3JzN6Qz9hBu73A5ZzKudEB1Tqa4sNPKVKAASGI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 437
ht-degree: 79%

---

# eVar (comercialización)

*Esta página de ayuda describe cómo funcionan las eVars de comercialización como una [dimensión](overview.md). Para obtener información sobre cómo implementar eVars de comercialización, consulte [eVar (variable de comercialización)](/help/implement/vars/page-vars/evar-merchandising.md) en la Guía del usuario de implementación.*

Para obtener información detallada sobre cómo funcionan las eVars de comercialización, consulte [eVars de comercialización y métodos de búsqueda de productos](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/merchandising-evars.md).

Al medir el éxito de campañas externas o términos de búsqueda externos, normalmente desea que un solo valor reciba crédito por cualquier evento de éxito que se produzca. Por ejemplo, si un cliente hace clic en un vínculo de una campaña de correo electrónico para visitar su sitio web, todas las compras realizadas como resultado deben acreditarse a esa campaña.

¿Qué ocurre con los eventos que se realizan mediante búsquedas internas o a través de la exploración de categorías, cuando un cliente busca varios artículos? Por ejemplo, un cliente busca `"goggles"` en un sitio y agrega un par al carro de compras:

![Ejemplo de gafas](assets/merch-example-goggles.png)

Antes de cerrar la compra, el cliente busca `"winter coat"` y agrega una chaqueta de plumón al carro de compras:

![Ejemplo de abrigo](assets/merch-example-coat.png)

Cuando el visitante complete esta compra, tendrá una búsqueda interna de `"winter coat"` declarada con la compra de un par de gafas (suponiendo que la eVar utilice la asignación predeterminada de “Más reciente”). Positivo para `"winter coat"`, pero negativo para las decisiones de marketing:

| Término de búsqueda interna | Ingresos |
|---|---|
| abrigo de invierno | $157 |

## Solución de este problema con las variables de comercialización

Las eVar de comercialización entre categorías permiten asignar el valor actual de una eVar a un producto en el momento en que se produce un evento de éxito. Este valor se mantendrá enlazado con dicho producto, incluso en el caso de que posteriormente se establezcan uno o varios valores nuevos para la eVar específica.

Si se habilita la comercialización para la eVar del ejemplo anterior, el término de búsqueda `"goggles"` se enlazará con gafas protectoras para la nieve, y el término de búsqueda `"winter coat"` se enlazará con la chaqueta de plumón. Las eVars de comercialización asignan los ingresos en el nivel de producto, por lo que cada término recibe crédito por la cantidad de ingresos del producto al que se encuentra asociado:

| Término de búsqueda interna | Ingresos |
|---|---|
| abrigo de invierno | $119 |
| gafas | $38 |

Consulte [eVars de comercialización](/help/implement/vars/page-vars/evar-merchandising.md) para ver las instrucciones de implementación.

## Las instancias en las variables de comercialización

No se recomienda utilizar la métrica [Instancias](../metrics/instances.md) en variables de comercialización.

* Para las variables de comercialización que utilizan sintaxis de producto, las instancias no se incrementan en absoluto.
* Para las variables de comercialización que utilizan sintaxis de variable de conversión, las instancias se cuentan cada vez que se configura la eVar. Sin embargo, se atribuye al elemento de la dimensión `"None"` a menos que suceda lo siguiente en la misma visita:
   * Que la eVar de comercialización se sobrescriba con un valor.
   * La variable `products` se define con un valor.
   * Se establece un evento de enlace.

```js
// This merchandising eVar uses conversion variable syntax, and counts an instance.
// However, if the binding event and products variable are not both set, the instance attributes to "None".
s.eVar1 = "Tower defense";

// This merchandising eVar uses product syntax, and does not count an instance.
s.products = "Games;Wizard tower;;;;eVar2=Tower defense";
```

Dado que la mayoría de los casos de uso de la sintaxis de variables de conversión requieren la variable eVar y Productos en diferentes visitas, el uso de la métrica “Instancias” no es realista.
