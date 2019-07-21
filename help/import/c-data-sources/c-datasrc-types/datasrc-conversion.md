---
description: El sistema de fuentes de datos admite las siguientes dimensiones y métricas para los tipos de datos que se procesan como conversiones.
seo-description: El sistema de fuentes de datos admite las siguientes dimensiones y métricas para los tipos de datos que se procesan como conversiones.
seo-title: Conversión
solution: Analytics
subtopic: Fuentes de datos
title: Conversión
topic: Desarrollador e implementación
uuid: 5 e 7907 b 1-6 c 9 c -4073-876 b -410 f 3 a 29767 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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
| Evarn | Nombre de evarn. Los valores válidos para n son los números enteros entre 1 y 75. |
| Producto | Nombre del producto. |
| Estado | Nombre del estado. |
| Código postal | Nombre del código postal. |

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
| Vistas de evarn | Cantidad de veces que se vio la eVar n. Los valores válidos para n son los números enteros entre 1 y 75. |
| Precio | Precio del producto. |
| Pedidos | Número de pedidos asentados. |
| Vistas del producto | Número de vistas del producto. |
| Cantidad | Número de unidades vendidas. |