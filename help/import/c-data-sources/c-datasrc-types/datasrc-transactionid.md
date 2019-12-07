---
description: Los ID de transacción se pueden integrar seleccionando la categoría Genéricas (ID de transacción).
subtopic: Data sources
title: ID de transacción
topic: Developer and implementation
uuid: f3370bb7-3f28-460b-a20d-c9e58d7301d4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# ID de transacción

Los ID de transacción se pueden integrar seleccionando la categoría Genéricas (ID de transacción).

See [Integrating Offline Data](/help/import/c-data-sources/datasrc-integrating-offline-data.md).

Data uploaded with *`transactionID`* automatically associates with the same marketing channel that processed the original server call that contained the *`transactionID`*.

**Dimensiones de ID de transacción**

| Nombre de columna | Descripción |
|--- |--- |
| ID de transacción | (Obligatorio) Valor no repetido que representa una transacción en línea que dio lugar a una actividad sin conexión. |
| Fecha | Utilice este formato de fecha: MM/DD/AAAA/HH/mm/SS (por ejemplo, 01/01/2015/06/00/00) |
| Código de seguimiento | Nombre del código de seguimiento. |
| Categoría | Nombre de la categoría.  Si se indica una categoría, también se debe seleccionar un producto. |
| Canal | Nombre del canal. |
| eVarN | Nombre de eVarN. Los valores válidos para N son números enteros 1 - 250. |
| Producto | Nombre del producto. |
| Estado | Nombre del estado. |
| Zip | Nombre del código postal. |

<p class="head"> <b>Métricas de ID de transacción</b> </p>



| Nombre de columna | Descripción |
|--- |--- |
| Pulsaciones | Número de vistas del código de seguimiento. |
| Adiciones al carro de compras | Número de adiciones al carro de compras. |
| Aperturas del carro de compras | Número de aperturas del carro de compras. |
| Eliminaciones del carro de compras | Número de eliminaciones del carro de compras. |
| Vistas del carro de compras | Número de vistas del carro de compras. |
| Cierres de compra | Número de cierres de compra. |
| EventN | Número de veces que se produjo eventN. Los valores válidos para N son los números enteros 1 - 1000.  Cuando se indica un evento Vista, también hay que indicar la dimensión de datos (eVar) correspondiente. Por ejemplo, si se incluyen las vistas de eVar2, se deberá indicar la eVar2 con un valor. |
| Vistas de eVarN | Número de veces que se visualizó eVarN. Los valores válidos para N son números enteros 1 - 250. |
| Precio | Precio del producto. |
| Pedidos | Número de pedidos asentados. |
| Vistas del producto | Número de vistas del producto. |
| Cantidad | Número de unidades vendidas. |
