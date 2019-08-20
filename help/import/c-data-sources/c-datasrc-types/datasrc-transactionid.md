---
description: Los ID de transacción se pueden integrar seleccionando la categoría Genéricas (ID de transacción).
seo-description: Los ID de transacción se pueden integrar seleccionando la categoría Genéricas (ID de transacción).
seo-title: ID de transacción
solution: Analytics
subtopic: Fuentes de datos
title: ID de transacción
topic: Desarrollador e implementación
uuid: f 3370 bb 7-3 f 28-460 b-a 20 d-c 9 e 58 d 7301 d 4
translation-type: tm+mt
source-git-commit: e9cb3575780db9eb5c9a766ef20d596e504a20d0

---


# ID de transacción

Los ID de transacción se pueden integrar seleccionando la categoría Genéricas (ID de transacción).

Consulte [Integración de datos sin conexión](../../../import/c-data-sources/datasrc-integrating-offline-data.md#concept_B5C576220F1548B5A3A57112AA3960C6).

Data uploaded with *`transactionID`* automatically associates with the same marketing channel that processed the original server call that contained the *`transactionID`*.

**Dimensiones de ID de transacción**

| Nombre de columna | Descripción |
|--- |--- |
| ID de transacción | (Obligatorio) Valor no repetido que representa una transacción en línea que dio lugar a una actividad sin conexión. |
| Fecha | Utilice este formato de fecha: MM/DD/AAAA/HH/mm/SS (por ejemplo, 01/01/2015/06/00/00) |
| Código de seguimiento | Nombre del código de seguimiento. |
| Categoría | Nombre de la categoría.  Si se indica una categoría, también se debe seleccionar un producto. |
| Canal | Nombre del canal. |
| eVarN | Nombre de evarn. Los valores válidos para N son números enteros entre 1 y 250. |
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
| Eventn | Número de veces que eventn ha tenido lugar. Los valores válidos para N son los números enteros entre 1 y 1000. Cuando se indica un evento Vista, también hay que indicar la dimensión de datos (eVar) correspondiente. Por ejemplo, si se incluyen las vistas de eVar2, se deberá indicar la eVar2 con un valor. |
| Vistas de evarn | Número de veces que se vio evarn. Los valores válidos para N son números enteros entre 1 y 250. |
| Precio | Precio del producto. |
| Pedidos | Número de pedidos asentados. |
| Vistas del producto | Número de vistas del producto. |
| Cantidad | Número de unidades vendidas. |
