---
description: Lista de eventos predefinidos.
keywords: Analytics Implementation;event
title: ¿Qué es un evento predefinido?
topic: Developer and implementation
uuid: 4d0799ba-0f97-42c3-a620-36c03f9995da
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# ¿Qué es un evento predefinido?

Lista de eventos predefinidos.

| prodView | El evento de éxito se produce cada vez que un visitante consulta un producto. |
|---|---|
| scView | El evento de éxito se produce cada vez que se ve un carro de compras. |
| scOpen | El evento de éxito se produce cada vez que un visitante abre un carro de compras por primera vez. |
| scAdd | El evento de éxito se produce cada vez que se agrega un producto a un carro de compras. |
| scRemove | El evento de éxito se produce cada vez que se elimina un artículo de un carro de compras. |
| scCheckout | El evento de éxito se produce en la primera página de un cierre de compra. |
| purchase | El evento de éxito se produce en la última página de un cierre de compra (incluye las métricas Ingresos, Pedidos y Unidades). |

Cuando se produce uno de los eventos predefinidos anteriores, se incrementa una instancia del evento. Puede ver las métricas relacionadas con el evento en diferentes informes. El siguiente es un ejemplo del código utilizado para configurar los eventos predefinidos.

```js
s.events="scAdd"
```

```js
s.events="scOpen,scAdd"
```

* En el primer ejemplo anterior, *`scAdd`* es el valor del evento. Cada vez que se agrega un artículo al carro de compras, se incrementa el evento.
* En el segundo ejemplo, se obtienen dos valores al mismo tiempo. Si se producen múltiples eventos en la misma página, cada evento se incrementa.

