---
description: Las ID de visitante se pueden importar seleccionando la categoría Fuente de datos genérica (ID de transacción).
seo-description: Las ID de visitante se pueden importar seleccionando la categoría Fuente de datos genérica (ID de transacción).
seo-title: ID del visitante
solution: Analytics
subtopic: Fuentes de datos
title: ID de visitante
topic: Desarrollador e implementación
uuid: 4 e 9 ce 675-72 c 2-42 a 4-8 f 2 e -25140 df 19539
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ID del visitante

Las ID de visitante se pueden importar seleccionando la categoría Fuente de datos genérica (ID de transacción).

See [Integrate Offline Data](../../../import/c-data-sources/datasrc-integrating-offline-data.md#concept_B5C576220F1548B5A3A57112AA3960C6).

<p class="head"> <b>Dimensiones de ID de visitante</b> </p>

| Nombre de columna | Descripción |
|--- |--- |
| ID del visitante | (Obligatorio) Valor no repetido que representa a un cliente en ambos sistemas (conectado a Internet y sin conexión). |
| Fecha | Utilice este formato de fecha: MM/DD/AAAA/hh/mm/ss (por ejemplo, 07/14/2017/06/00/00). |
| Código de seguimiento | Nombre del código de seguimiento. |
| Categoría | Nombre de la categoría.  Si se indica una categoría, también se debe seleccionar un producto. |
| Canal | Nombre del canal. |
| Evarn | Nombre de evarn. Los valores válidos para n son los números enteros entre 1 y 75. |
| Producto | Nombre del producto. |
| Estado | Nombre del estado. |
| Código postal | Nombre del código postal. |

**Métricas de ID de visitante**

| Nombre de columna | Descripción |
|--- |--- |
| Pulsaciones | Número de vistas del código de seguimiento. |
| Adiciones al carro de compras | Número de adiciones al carro de compras. |
| Aperturas del carro de compras | Número de aperturas del carro de compras. |
| Eliminaciones del carro de compras | Número de eliminaciones del carro de compras. |
| Vistas del carro de compras | Número de vistas del carro de compras. |
| Cierres de compra | Número de cierres de compra. |
| Evento n | Cantidad de veces que se produjo el evento n. Los valores válidos para n son los números enteros entre 1 y 100.  Cuando se indica un evento Vista, también hay que indicar la dimensión de datos (eVar) correspondiente. Por ejemplo, si se incluyen las vistas de eVar2, se deberá indicar la eVar2 con un valor. |
| Vistas de evarn | Cantidad de veces que se vio la eVar n. Los valores válidos para n son los números enteros entre 1 y 75. |
| Precio | Precio del producto. |
| Pedidos | Número de pedidos asentados. |
| Vistas del producto | Número de vistas del producto. |
| Cantidad | Número de unidades vendidas. |