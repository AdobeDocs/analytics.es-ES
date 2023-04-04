---
title: Formato del archivo de origen de datos
description: Genere correctamente un archivo para utilizarlo en fuentes de datos.
source-git-commit: bb3036380eeec9b7a868f60a4c9076f2b772532b
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 7%

---

# Formato del archivo de origen de datos

Los archivos de fuente de datos tienen las siguientes propiedades:

* El archivo se encuentra en `.txt` formato.
* Las líneas comentadas empiezan por &#39;`#`y son opcionales.
* La primera línea no comentada contiene los encabezados del archivo.
* El primer valor de cada fila es la fecha, que utiliza el formato `MM/DD/YYYY` o `MM/DD/YYYY/HH/mm/SS`.
* Los valores de cada fila, incluidos los encabezados, están delimitados por tabuladores.
* Cada fila debe tener al menos una dimensión y una métrica.

## Comentarios

Cualquier fila que comience por &#39;`#`&#39; es un comentario. Al descargar un archivo de plantilla de fuente de datos, las dos primeras líneas son comentarios.

* El primer comentario indica el tipo de plantilla que configuró para la fuente de datos, el ID de usuario del servidor que creó la fuente de datos y el ID de la fuente de datos.
* El segundo comentario proporciona nombres descriptivos para cada uno de los encabezados incluidos en el archivo de plantilla.

Adobe ignora todas las filas de comentarios cuando se procesa el archivo, por lo que puede eliminar los comentarios de la plantilla o agregarlos a los suyos en todo el archivo. Solo se pueden comentar filas completas; no se pueden comentar campos individuales o filas parciales.

## Encabezados

Cuando se cargan archivos de fuente de datos, es necesario incluir encabezados de columna. Estos encabezados de columna no distinguen entre mayúsculas y minúsculas, pero se necesitan espacios obligatorios (por ejemplo, `eVar1` es un encabezado no válido, mientras que `EVAR 1` es válido). Los encabezados de columna se aplican a todos los grupos de informes. Utilice las tablas siguientes para asegurarse de que cada encabezado del archivo de origen de datos está configurado correctamente.

>[!TIP]
>
>Puede crear un archivo de fuente de datos desde cero si incluye los encabezados correctos en el archivo de fuente de datos. No hay límite en el número de encabezados que puede incluir en un solo archivo; sin embargo, cada fila solo puede tener un máximo de 4096 bytes.

| Dimensión | Encabezado de fuente de datos |
| --- | --- |
| [Categoría](/help/components/dimensions/category.md) | `Category` |
| [eVar1 - eVar250](/help/components/dimensions/evar.md) | `Evar 1` - `Evar 250` |
| [Canal de marketing](/help/components/dimensions/marketing-channel.md) | `Marketing Channel` |
| [Detalles del canal de marketing](/help/components/dimensions/marketing-detail.md) | `Marketing Channel Detail` |
| [Producto](/help/components/dimensions/product.md) | `Product` |
| [Código de seguimiento](/help/components/dimensions/tracking-code.md) | `Tracking Code` |
| [ID de transacción](/help/implement/vars/page-vars/transactionid.md) | `transactionID` |
| [Código postal](/help/components/dimensions/zip-code.md) | `Zip` |

{style="table-layout:auto"}

Los Dimension y las métricas van a la misma fila de encabezado.

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

Adobe no admite fuentes de datos para ninguna otra dimensión o métrica. Si se requieren variables que superen lo que se indica en las tablas anteriores, considere la posibilidad de usar la variable [API de inserción de datos en lote](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/) en su lugar.

## Fecha

El primer valor de cada fila **must** sea la fecha. El formato de fecha debe tener uno de los siguientes formatos:

* **`MM/DD/YY/HH/mm/SS`**
* **`MM/DD/YY`**

Si se omite la hora/minutos/segundos, automáticamente se establece la marca de tiempo en 12 PM para ese día.

Un solo archivo de fuente de datos admite hasta 90 días únicos. Si desea incluir más de 90 días únicos en una carga, divida los datos en varios archivos.

## datos de Dimension y métrica

Los valores posteriores después de la fecha de cada fila contienen los datos que desea cargar. Cada fila corresponde a la marca de tiempo correspondiente. Asegúrese de que exista el mismo número de pestañas en cada fila. Las columnas pueden estar en cualquier orden; asegúrese de que los datos de cada fila coinciden con los encabezados de la parte superior. La cantidad máxima de datos que puede tener una sola fila es de 4096 bytes.

Los datos del Dimension no pueden contener punto y coma (`;`). Las filas que contienen punto y coma se omiten.

## Pasos siguientes

[Carga de archivos](file-upload.md): Conozca el proceso para cargar un archivo de fuente de datos para su ingesta por Adobe.
