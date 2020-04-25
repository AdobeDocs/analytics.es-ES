---
description: 'null'
keywords: Analytics Implementation
title: Resumen de las variables de comercialización
topic: Developer and implementation
uuid: 2ccf516a-a7ee-48ab-92aa-414228a4102f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Resumen de las variables de comercialización

Al medir el éxito de campañas o términos de búsqueda externos, normalmente se desea que un único valor reciba crédito por los eventos de éxito que se produzcan. Por ejemplo, si un cliente hace clic en un vínculo de una campaña de correo electrónico para visitar un sitio web, todas las compras que se realicen como resultado de ese clic deben abonarse a dicha campaña.

¿Pero qué ocurre con los eventos que se realizan mediante búsquedas internas o a través de la exploración de categorías, cuando un cliente busca varios artículos? Por ejemplo, un cliente busca &quot;gafas protectoras&quot; en un sitio y agrega un par al carro de compras:

![](assets/merch-example-goggles.png)

Antes de cerrar la compra, el cliente busca &quot;abrigo de invierno&quot; y agrega una chaqueta de plumón al carro de compras:

![](assets/merch-example-coat.png)

Cuando la compra se complete, si no se modifica la asignación de Más reciente, aparecerá una búsqueda interna de &quot;abrigo de invierno&quot; abonada con la compra de un par de gafas protectoras. Positivo para &quot;abrigo de invierno&quot;, pero negativo para las decisiones de marketing:

| Término de búsqueda interna | Ingresos |
|---|---|
| abrigo de invierno | 157 $ |

**Solución de este problema con las variables de comercialización**

Las variables de comercialización entre categorías o &quot;eVars de comercialización&quot; permiten asignar el valor actual de una eVar a un producto en el momento en que se produce un evento de éxito. Este valor se mantendrá enlazado con dicho producto, incluso en el caso de que posteriormente se establezcan uno o varios valores nuevos para la eVar específica.

Si se habilita la comercialización para la eVar del ejemplo anterior, el término de búsqueda &quot;gafas protectoras&quot; se enlazará con Gafas protectoras para la nieve Fernie, y el término de búsqueda &quot;abrigo de invierno&quot; se enlazará con Chaqueta de plumas El Gordo. Las variables de comercialización asignan los ingresos en el nivel de producto, por lo que cada término recibe crédito por la cantidad de ingresos del producto al que se encuentra asociado:

| Término de búsqueda interna | Ingresos |
|---|---|
| abrigo de invierno | 119 $ |
| gafas protectoras | 38 $ |

