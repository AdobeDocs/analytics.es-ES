---
description: El sistema de fuentes de datos admite las siguientes dimensiones y métricas para los tipos de datos que se procesan como conversiones.
subtopic: Data sources
title: Conversión
topic: Developer and implementation
uuid: 5e7907b1-6c9c-4073-876b-410f3a29767d
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Conversión

El sistema de fuentes de datos admite las siguientes dimensiones y métricas para los tipos de datos que se procesan como conversiones.

## Métricas y dimensiones de conversión {#section_FA1731B232B246DABEDF5A5D84159084}

Cuando se indica un evento Vista, también hay que indicar la dimensión de datos (eVar) correspondiente. Por ejemplo, si se incluyen las vistas de eVar2, se deberá indicar la eVar2 con un valor. La cantidad de eventos personalizados y vistas de eVar que admite un grupo de informes depende del contrato y varía según la empresa.

<p class="head"> <b>Dimensiones de conversión</b> </p>

| Nombre de columna | Descripción |
|--- |--- |
| Código de seguimiento | Nombre del código de seguimiento. |
| Fecha | Utilice este formato de fecha: MM/DD/AAAA/HH/mm/SS (por ejemplo, 01/01/2015/06/00/00) |
| Categoría | Nombre de la categoría.  Si se indica una categoría, también se debe seleccionar un producto. |
| Canal | Nombre del canal. |
| eVarn | Nombre de la eVarn. Los valores válidos para n son los números enteros entre 1 y 75. |
| Producto | Nombre del producto. |
| Estado | Nombre del estado. |
| Zip | Nombre del código postal. |

<p class="head"> <b>Métricas de conversión</b> </p>

| Nombre de columna | Descripción |
|--- |--- |
| Pulsaciones | Número de vistas del código de seguimiento. |
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
