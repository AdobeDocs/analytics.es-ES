---
title: Formato del archivo de fuente de datos
description: Generar correctamente un archivo para utilizarlo en fuentes de datos.
exl-id: 6632b970-e931-4272-a69b-c1130ad6475f
feature: Data Sources
role: Admin
TQID: https://experienceleague.adobe.com/aOyIlKV8OwvmigJ7RFcNQsrsBiHbrC0a-IPN4xR0OZc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 546
ht-degree: 7%

---

# Formato del archivo de fuente de datos

Los archivos de fuente de datos tienen las siguientes propiedades:

* El archivo tiene el formato `.txt`.
* Las líneas comentadas comienzan con &#39;`#`&#39; y son opcionales.
* La primera línea sin comentarios contiene los encabezados del archivo.
* El primer valor de cada fila es la fecha, que usa el formato `MM/DD/YYYY` o `MM/DD/YYYY/HH/mm/SS`.
* Los valores de cada fila, incluidos los encabezados, están delimitados por tabuladores.
* Cada fila debe tener al menos una dimensión y una métrica.

## Comentarios

Cualquier fila que comience por &#39;`#`&#39; es un comentario. Al descargar un archivo de plantilla de fuente de datos, las dos primeras líneas son comentarios.

* El primer comentario indica el tipo de plantilla que configuró para la fuente de datos, el ID de usuario back-end que creó la fuente de datos y el ID de la fuente de datos.
* El segundo comentario proporciona nombres descriptivos para cada uno de los encabezados incluidos en el archivo de plantilla.

Adobe ignora todas las filas de comentarios cuando se procesa el archivo, por lo que puede quitar los comentarios de la plantilla o agregar los suyos propios a todo el archivo. Solo se pueden comentar las filas completas; no se pueden comentar campos individuales o filas parciales.

## Encabezados

Al cargar archivos de fuente de datos, se requieren encabezados de columna. Estos encabezados de columna no distinguen entre mayúsculas y minúsculas, pero se necesitan espacios obligatorios (por ejemplo, `eVar1` es un encabezado no válido, mientras que `EVAR 1` es válido). Los encabezados de columna se aplican a todos los grupos de informes. Utilice las siguientes tablas para asegurarse de que cada encabezado del archivo de fuente de datos está configurado correctamente.

>[!TIP]
>
>Puede crear un archivo de fuente de datos desde cero si incluye los encabezados correctos en el archivo de fuente de datos. No hay límite en el número de encabezados que se pueden incluir en un solo archivo; sin embargo, cada fila solo puede tener un máximo de 4096 bytes.

| Dimensión | Encabezado de fuente de datos |
| --- | --- |
| [Categoría](/help/components/dimensions/category.md) | `Category` |
| [eVar1 - eVar250](/help/components/dimensions/evar.md) | `Evar 1` - `Evar 250` |
| [Canal de mercadotecnia](/help/components/dimensions/marketing-channel.md) | `Marketing Channel` |
| [Detalles de canal de mercadotecnia](/help/components/dimensions/marketing-detail.md) | `Marketing Channel Detail` |
| [Producto](/help/components/dimensions/product.md) | `Product` |
| [Código de seguimiento](/help/components/dimensions/tracking-code.md) | `Tracking Code` |
| [ID de transacción](/help/implement/vars/page-vars/transactionid.md) | `transactionID` |
| [Código postal](/help/components/dimensions/zip-code.md) | `Zip` |

{style="table-layout:auto"}

Las dimensiones y las métricas van a la misma fila de encabezado.

| Métrica | Encabezado de fuente de datos |
| --- | --- |
| [Adiciones al carro de compras](/help/components/metrics/cart-additions.md) | `Cart Adds` |
| [Eliminaciones del carro de compras](/help/components/metrics/cart-removals.md) | `Cart Removes` |
| [Vistas del carro de compras](/help/components/metrics/cart-views.md) | `Cart Views` |
| [Carros de compras](/help/components/metrics/carts.md) | `Cart Opens` |
| [Cierres de compra](/help/components/metrics/checkouts.md) | `Checkouts` |
| [Eventos personalizados](/help/components/metrics/custom-events.md) | `Event 1` - `Event 1000` |
| [Pedidos](/help/components/metrics/orders.md) | `Orders` |
| [Ingresos](/help/components/metrics/revenue.md) | `Price` |
| [Unidades](/help/components/metrics/units.md) | `Quantity` |

{style="table-layout:auto"}

Adobe no admite fuentes de datos para ninguna otra dimensión o métrica. Si se requieren variables que vayan más allá de las enumeradas en las tablas anteriores, considere la posibilidad de usar la [API de inserción de datos en lotes](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) en su lugar.

## Fecha

El primer valor de cada fila **debe** ser la fecha. El formato de fecha debe tener uno de los siguientes formatos:

* **`MM/DD/YYYY/HH/mm/SS`**
* **`MM/DD/YYYY`**

Si se omiten las horas, minutos o segundos, la marca de tiempo se establece automáticamente en 12 p. m. para ese día.

Un solo archivo de fuente de datos admite hasta 90 días únicos. Si desea incluir más de 90 días únicos en una carga, divida los datos en varios archivos.

## Datos de métricas y Dimension

Los valores posteriores a la fecha en cada fila contienen los datos que desea cargar. Cada fila corresponde a la marca de tiempo correspondiente. Asegúrese de que existe el mismo número de pestañas en cada fila. Las columnas pueden estar en cualquier orden; asegúrese de que los datos de cada fila se alinean con los encabezados de la parte superior. La cantidad máxima de datos que puede tener una sola fila es de 4096 bytes.

Los datos de Dimension no pueden contener punto y coma (`;`). Las filas que contienen punto y coma se omiten.

## Pasos siguientes

[Carga de archivo](file-upload.md): Conozca el proceso para cargar un archivo de fuentes de datos para que lo incorpore Adobe.
