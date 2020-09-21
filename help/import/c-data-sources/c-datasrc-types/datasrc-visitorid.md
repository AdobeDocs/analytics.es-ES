---
description: Los ID de visitante se pueden importar seleccionando la categoría Genéricas (ID de transacción).
subtopic: Data sources
title: ID de visitante
topic: Developer and implementation
uuid: 4e9ce675-72c2-42a4-8f2e-25140df19539
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: ht
source-wordcount: '230'
ht-degree: 100%

---


# ID de visitante

Los ID de visitante se pueden importar seleccionando la categoría Genéricas (ID de transacción).

Consulte [Integrar datos sin conexión](/help/import/c-data-sources/datasrc-integrating-offline-data.md).

<p class="head"> <b>Dimensiones de ID de visitante</b> </p>

| Nombre de columna | Descripción |
|--- |--- |
| ID de visitante | (Obligatorio) Valor no repetido que representa a un cliente en ambos sistemas (conectado a Internet y sin conexión). |
| Fecha | Utilice este formato de fecha: MM/DD/AAAA/hh/mm/ss (por ejemplo, 07/14/2017/06/00/00). |
| Código de seguimiento | Nombre del código de seguimiento. |
| Categoría | Nombre de la categoría.  Si se indica una categoría, también se debe seleccionar un producto. |
| Canal | Nombre del canal. |
| eVarn | Nombre de la eVarn. Los valores válidos para n son los números enteros entre 1 y 75. |
| Product | Nombre del producto. |
| Estado | Nombre del estado. |
| Zip | Nombre del código postal. |

**Métricas de ID de visitante**

| Nombre de columna | Descripción |
|--- |--- |
| Proporción de clics | Número de vistas del código de seguimiento. |
| Adiciones al carro de compras | Número de adiciones al carro de compras. |
| Aperturas del carro de compras | Número de aperturas del carro de compras. |
| Eliminaciones del carro de compras | Número de eliminaciones del carro de compras. |
| Vistas del carro de compras | Número de vistas del carro de compras. |
| Cierres de compra | Número de cierres de compra. |
| Evento n | Cantidad de veces que se produjo el evento n. Los valores válidos para n son los números enteros entre 1 y 100.  Cuando se indica un evento Vista, también hay que indicar la dimensión de datos (eVar) correspondiente. Por ejemplo, si se incluyen las vistas de eVar2, se deberá indicar la eVar2 con un valor. |
| Vistas de eVarn | Cantidad de veces que se vio la eVar n. Los valores válidos para n son los números enteros entre 1 y 75. |
| Precio | Precio del producto. |
| Pedidos | Número de pedidos asentados. |
| Vistas del producto | Número de vistas del producto. |
| Cantidad | Número de unidades vendidas. |
