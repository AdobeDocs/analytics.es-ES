---
description: Los ID de visitante se pueden importar seleccionando la categoría Genéricas (ID de transacción).
subtopic: Data sources
title: ID de visitante
topic-fix: Developer and implementation
uuid: 4e9ce675-72c2-42a4-8f2e-25140df19539
exl-id: 940af1ba-0d12-4552-a21e-0ceb06427ab2
source-git-commit: a7a116ddc9eddc500a52111e9c002bdbee3e4a56
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 81%

---

# VisitorID

Los ID de visitante se pueden integrar seleccionando la variable [!UICONTROL Datos del centro de llamadas] categoría.

Consulte [Integrar datos sin conexión](/help/import/c-data-sources/datasrc-integrating-offline-data.md).

## Dimension de VisitorID

| Nombre de columna | Descripción |
|--- |--- |
| [!UICONTROL VisitorID] | (Obligatorio) Valor único que representa a un cliente en ambos sistemas (conectado a Internet y sin conexión). |
| [!UICONTROL Fecha] | Utilice el siguiente formato de fecha: `MM/DD/YYYY/hh/mm/ss` (por ejemplo, 14/07/2017/06/00/00) |
| [!UICONTROL Código de seguimiento] | Nombre del código de seguimiento. |
| [!UICONTROL Categoría] | Nombre de la categoría. Si se indica una categoría, también se debe seleccionar un producto. |
| [!UICONTROL Canal] | Nombre del canal. |
| [!UICONTROL eVar ]*n* | Nombre de la eVar *n*. Los valores válidos para *n* son los números enteros entre 1 y 75. |
| [!UICONTROL Product] | Nombre del producto. |
| [!UICONTROL Estado] | Nombre del estado. |
| [!UICONTROL Zip] | Nombre del código postal. |

## Métricas de ID de visitante

| Nombre de columna | Descripción |
| --- | --- |
| [!UICONTROL Proporción de clics] | Número de vistas del código de seguimiento. |
| [!UICONTROL Adiciones al carro de compras] | Número de adiciones al carro de compras. |
| [!UICONTROL Aperturas del carro de compras] | Número de aperturas del carro de compras. |
| [!UICONTROL Eliminaciones del carro de compras] | Número de eliminaciones del carro de compras. |
| [!UICONTROL Vistas del carro de compras] | Número de vistas del carro de compras. |
| [!UICONTROL Cierres de compra] | Número de cierres de compra. |
| *Evento n* | Número de veces par *n* se ha producido. Los valores válidos para n son los números enteros entre 1 y 100.  Si especifica un [!UICONTROL Ver] , también debe especificar la dimensión de datos correspondiente (eVar). Por ejemplo, si se incluyen las vistas de eVar2, se deberá indicar la eVar2 con un valor. |
| [!UICONTROL Vistas de eVar ]*n* | Cantidad de veces que se vio la eVar *n*. Los valores válidos para *n* son los números enteros entre 1 y 75. |
| [!UICONTROL Precio] | Precio del producto. |
| [!UICONTROL Pedidos] | Número de pedidos asentados. |
| [!UICONTROL Vistas del producto] | Número de vistas del producto. |
| [!UICONTROL Cantidad] | Número de unidades vendidas. |
