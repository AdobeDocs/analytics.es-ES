---
description: Los ID de visitante se pueden importar seleccionando la categoría Genéricas (ID de transacción).
subtopic: Data sources
title: ID de visitante
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 940af1ba-0d12-4552-a21e-0ceb06427ab2
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# VisitorID

Los ID de visitante se pueden integrar seleccionando la categoría [!UICONTROL Datos del centro de llamadas].

Consulte [Integrar datos sin conexión](/help/import/c-data-sources/datasrc-integrating-offline-data.md).

## Dimensión de VisitorID

| Nombre de columna | Descripción |
|--- |--- |
| [!UICONTROL VisitorID] | (Obligatorio) Valor único que representa a un cliente en ambos sistemas (en línea y sin conexión). |
| [!UICONTROL Fecha] | Utilice el siguiente formato de fecha: `MM/DD/YYYY/hh/mm/ss` (por ejemplo, 14/07/2017/06/00/00) |
| [!UICONTROL Código de seguimiento] | Nombre del código de seguimiento. |
| [!UICONTROL Categoría] | Nombre de la categoría. Si se indica una categoría, también se debe seleccionar un producto. |
| [!UICONTROL Canal] | Nombre del canal. |
| [!UICONTROL eVar ]*n* | Nombre de la eVar *n*. Los valores válidos para *n* son los números enteros entre 1 y 75. |
| [!UICONTROL Producto] | Nombre del producto. |
| [!UICONTROL Estado] | Nombre del estado. |
| [!UICONTROL Código postal] | Nombre del código postal. |

## Métricas de ID de visitante

| Nombre de columna | Descripción |
| --- | --- |
| [!UICONTROL Proporción de clics] | Número de vistas del código de seguimiento. |
| [!UICONTROL Adiciones al carro de compras] | Número de adiciones al carro de compras. |
| [!UICONTROL Aperturas del carro de compras] | Número de aperturas del carro de compras. |
| [!UICONTROL Eliminaciones del carro de compras] | Número de eliminaciones del carro de compras. |
| [!UICONTROL Vistas del carro de compras] | Número de vistas del carro de compras. |
| [!UICONTROL Cierres de compra] | Número de cierres de compra. |
| [!UICONTROL Evento ]*n* | Cantidad de veces que se produjo el evento *n*. Los valores válidos para n son los números enteros entre 1 y 100.  Cuando se indica un evento [!UICONTROL Vista], también hay que indicar la dimensión de datos (eVar) correspondiente. Por ejemplo, si se incluyen las vistas de eVar2, se deberá indicar la eVar2 con un valor. |
| [!UICONTROL eVar ]*n* Vistas | Cantidad de veces que se vio la eVar *n*. Los valores válidos para *n* son los números enteros entre 1 y 75. |
| [!UICONTROL Precio] | Precio del producto. |
| [!UICONTROL Pedidos] | Número de pedidos asentados. |
| [!UICONTROL Vistas del producto] | Número de vistas del producto. |
| [!UICONTROL Cantidad] | Número de unidades vendidas. |
